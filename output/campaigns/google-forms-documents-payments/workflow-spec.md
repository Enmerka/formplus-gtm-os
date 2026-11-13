# W1: Google Forms or paper forms where documents or payments are requested

**Status:** STRUCTURE-APPROVED 2026-11-13 · copy pending

- Workflow: W1 in [context/icp/signal-matrix.md](../../../context/icp/signal-matrix.md) (signals S2 + S3). System steps: [context/docs/gtm-system.md](../../../context/docs/gtm-system.md).
- Segment: A-US schools (first build). Segment B nonprofits reuses the same build; swaps are marked **B reuse**.
- Facts: there is no `context/messaging/facts.md` yet. Every fact here comes from `context/docs/research/` (checked 2026-11-13). Anything else is a `{{placeholder}}`.
- Labels: INFERRED = our judgement, not in the research.

---

## 1. Mother intent (trigger) [ENGINE]

**US schools whose admissions or registration page runs a Google Form while asking applicants for documents or a payment.**

- Catalog match (`knowledge-base/playbooks/workflow-anatomy.md`): "Companies using specific software" (Google Forms), stacked with "Website content mentions" (the page asks for documents or payment).
- Signal-led: the list starts from the BuiltWith Google Forms list, not from a list of schools.
- Scope: schools that use paper only, with no Google Form, are out of this workflow. They are not on the BuiltWith list. Paper is a router inside the Google Forms list (R3).

## 2. Inclusion / exclusion [ICP]

### Include

| Box | Rule | Source |
|---|---|---|
| Geography | United States | icp.md, A-US |
| Industry | Primary/Secondary Education, Education Management (charter and private K-12 schools, arts schools, student associations, training consortia) | icp.md, A-US target definition |
| Size | Drop only rows with a **known** Apollo headcount above 500. Rows with a blank headcount pass through to F1. Lower bound: none in v1 (INFERRED cap from icp.md, to tune) | icp.md |
| Trigger | T1 AND T2 AND T3 (section 4) | signal-matrix.md, S2 + S3 |
| Recipient | **Champion:** admissions officer, director of admissions, registrar, enrollment manager, instructional technologist. **Fallback** if no champion is found: head of school or principal. One contact per school in v1 | personas.md; gtm-system.md step 6 |

### Exclude

| Who | Why |
|---|---|
| Existing Formplus customers, open deals, suppressed or unsubscribed contacts in HubSpot | gtm-system.md steps 2 and 10 |
| Case-study customers: Polk State College Charter Schools, COTSA, Pennsylvania Academy of Ballet, NPTC | Lookalike seeds, not targets (gtm-system.md step 2) |
| Contacted in the last 90 days with the same signal | gtm-system.md step 2 (PROPOSED window) |
| Google Form found only on non-admissions pages (newsletter, contact, feedback) | The signal does not hold (gtm-system.md step 1) |
| Admissions page also embeds Jotform, Typeform, Formstack or Wufoo (X1) | They already pay for a form builder; displacement is a different story |
| Not a fit per icp.md: healthcare patient data, enterprise compliance needs | icp.md not-a-fit list |
| Outside the US | Wrong segment; Nigerian schools are W3 |

### B reuse (nonprofits)

| Element | A-US value | B value |
|---|---|---|
| Industry | Primary/Secondary Education, Education Management | Non-profit, Civic & Social Organisation |
| Page keywords (T2) | admission, apply, application, enrol, enroll, enrollment, registration, register | registration, register, membership, conference, training, events, call for proposals |
| Recipient | Admissions officer, registrar, enrollment manager; fallback head of school | Program, membership or events manager; fallback executive director |
| Proof | Section 5 | Documents cells: AASHE. Payment cells: Ruby's Place |

Everything in sections 3 to 7 stays the same.

## 3. Sources [ENGINE]

| Step | Source | Delivers |
|---|---|---|
| Trigger universe | BuiltWith Google Forms list via Clay "Find Technology Stack". 54,491 live sites, 28,913 in the US (https://trends.builtwith.com/widgets/Google-Forms, checked 2026-11-13) | Domain, `has_google_forms` |
| ICP box | Apollo company enrichment via Clay | Industry, headcount (may be blank), country, company name |
| Page discovery and scan | crawl4ai (`tools/crawl4ai/`), or Claygent in Clay. Crawl the homepage and navigation; keep pages whose URL or link text matches the page keywords; return each kept page's links, iframe `src` values and visible text | `admissions_page_url`, links, iframes, page text |
| Segment check | Clay AI fit-check column, enum output (gtm-system.md step 4) | `segment`, `not_fit_reason` |
| Exclusions | HubSpot companies, deals and suppression list | Customer, deal and suppression flags |
| Recipient | Apollo people search by domain + section 2 titles | `first_name`, title, LinkedIn URL |
| Email | Clay waterfall: Prospeo, Icypeas, Leadmagic, Findymail; then Bounceban to verify (`knowledge-base/playbooks/clay/expert.md`) | Verified email, verification status |

## 4. Signals table [ENGINE]

Reads run on the scanned admissions or registration pages unless stated. Keyword lists are INFERRED build settings, to tune on the 500-domain sample.

| # | Signal | Role | How it's read | Output |
|---|---|---|---|---|
| T1 | Google Forms on the site | trigger | Boolean: domain is on the BuiltWith Google Forms list | `has_google_forms` |
| T2 | Google Form on an admissions or registration page | trigger | Regex: a link matching `docs.google.com/forms` or `forms.gle`, **or an iframe whose `src` contains `docs.google.com/forms`**, on a page whose URL or title matches `admission\|admissions\|apply\|application\|enrol\|enroll\|enrollment\|registration\|register` | `gform_on_admissions`, `admissions_page_url` |
| T3 | Page asks for documents or a payment | trigger | Boolean: R1 OR R2. Both false: the row drops | `asks_docs_or_payment` |
| R1 | Documents requested | router | Keyword match on page text: `upload`, `attach`, `transcript`, `birth certificate`, `report card`, `immunization`, `proof of residency`, `email your documents`, `send copies` | `asks_documents` |
| R2 | Payment requested | router | Keyword match: `application fee`, `registration fee`, `deposit`, `tuition deposit`, `proof of payment`, `pay by check`, `money order`, or a `$` amount within 50 characters of `fee` | `asks_payment` |
| R3 | Paper or PDF form alongside the Google Form | router | Regex: a link ending `.pdf`, `.doc` or `.docx` whose anchor text or file name matches `application\|enrol\|enroll\|registration\|form`, OR page text matching `print and\|mail to\|drop off\|return to the office` | `has_paper_form` |
| C1 | Which process the page is for | context-clause | Regex on URL and title, first match wins. Enum: `admissions`, `enrollment`, `registration`, `camp`, `other` | `process_type` |
| C2 | School name | context-clause | Apollo company name; fallback: page title | `school_name` |
| F1 | Segment fit | filter | Clay AI column, hard enum: `A-US`, `B`, `D`, `not_fit`, `other`. Only `A-US` continues (`B` continues in the B build) | `segment`, `not_fit_reason` |
| X1 | Paid form builder on the same page | exclusion | Regex on embed domains: `jotform.com`, `typeform.com`, `formstack.com`, `wufoo.com`. True: the row drops | `has_paid_builder` |

- Count clusters: none. Every router is a boolean.
- Routing axes: what the page asks for (R1, R2) and paper alongside (R3).
- Context-clauses C1 and C2 never route.

**Considered and left out**
- Whether the Google Form itself contains a file-upload question. It would directly support the "Google sign-in to upload" proof, but reading it from outside is not verified.
- **Test on the 500-domain sample:** does fetching the Google Form URL redirect to a Google sign-in page? That would be a proxy for a file-upload question. It is not in v1, because sign-in can be required for other reasons.

## 5. Routing matrix with angles [ENGINE]

- Axis 1, what the page asks for (R1, R2): 3 options: documents only, payment only, both. "Neither" is removed by T3.
- Axis 2, paper alongside (R3): 2 options: yes, no.
- Stacked: 3 x 2 = 6 cells.

Branch coverage: every cell has `school_name`, `process_type` and `admissions_page_url`. No cell has a fee amount, a document list or a deadline, so no angle depends on one.

| Cell | Deterministic read | What it tells us (inferred situation) | The angle it earns |
|---|---|---|---|
| **1. Documents, no paper** | R1 true, R2 false, R3 false | The school takes applications on a Google Form and collects supporting documents through it or alongside it, for example by email. One online intake; the documents are the extra step | **Documents arrive with the application, with no Google sign-in for families.** Facts: Google Forms file uploads require a Google sign-in that can't be turned off (competitors.md); Formplus sends uploads to Google Drive, Dropbox or OneDrive (company.md). **Proof: COTSA**, which moved from Google Forms ("clunky") to collect documents for its early-submission events (customers.md) |
| **2. Documents + paper** | R1 true, R2 false, R3 true | The school runs two intakes at once: a Google Form and a printable PDF. Applications and documents arrive both ways, so the office probably enters paper applications into the same record the Google Form fills | **Replace both intakes with one online application that includes the uploads.** **Proof: Polk State**, which entered paper applications into a spreadsheet by hand and had tried Google Forms. Now "100% faster to obtain enrollment applications" and "decreased our time and cost ten times over" (customers.md) |
| **3. Payment, no paper** | R1 false, R2 true, R3 false | Registration happens on a Google Form; the fee is paid in a separate step (check, money order or proof of payment). Two steps that staff match afterwards | **Take the fee inside the registration form.** Facts: Stripe and PayPal integrations; "We do not charge a fee to integrate a form with any of our payment partners." (company.md, voice.md). **Proof: Pennsylvania Academy of Ballet**: students register and pay through a PayPal integration: "Formplus empowered our students to register themselves for our online classes and pay for them on an enrollment schedule..." (customers.md). **Supporting line: Ruby's Place**, whose Google Forms payment add-on was discontinued (customers.md) |
| **4. Payment + paper** | R1 false, R2 true, R3 true | Some families register on the Google Form and some on a printed form, and the fee arrives separately, likely by mail or in person. Registration and payment come in through several channels | **One online form for registration and fee, replacing print-and-mail.** **Proof: Pennsylvania Academy of Ballet**, which moved registration and payment from in person or phone to an online form with PayPal (customers.md). **Supporting line: Ruby's Place**, as in cell 3 |
| **5. Documents + payment, no paper** | R1 true, R2 true, R3 false | The Google Form takes the application, but documents and the fee are separate steps. One application, three moving parts | **Application, documents and fee in one submission.** Facts: file uploads plus Stripe or PayPal in the same form (company.md). **Proof: COTSA**: "The Formplus tool has made collection of URLs and forms WAY easier! And it allows us to be all digital." (customers.md) |
| **6. Documents + payment + paper** | R1 true, R2 true, R3 true | The full paper packet still exists: print the form, attach copies, enclose the fee. The Google Form is a partial online route beside it | **Retire the paper packet: one online application with uploads and fee.** **Proof: Polk State** (paper to online, "decreased our time and cost ten times over"). Secondary proof if needed: COTSA used to "collect thousands of pieces of paper for each conference" (customers.md) |

**Plan fit (cells 3 to 6):** payments are locked on the Free plan, so these cells need Starter or above (company.md). This affects the trial-or-call step, not routing. Most A-US positive replies go to a call (gtm-system.md step 5).

**Niche-native test:** each angle comes from what this school's own page shows (a Google Form next to a PDF, a fee by check). A different page gives a different cell.

**B reuse:** the same 6 cells and reads. Proof swaps only: AASHE for the documents cells (calls for proposals with file uploads), Ruby's Place as the main payment proof for cells 3 and 4.

## 6. Variables contract [ENGINE]

Copy may only use these variables. Syntax: `{{snake_case}}`; match Instantly's syntax at export.

| Variable | Source field | Exists in branches |
|---|---|---|
| `{{first_name}}` | Apollo people search, first name | All cells |
| `{{school_name}}` | C2: Apollo company name, fallback page title | All cells |
| `{{process_type}}` | C1 enum: admissions, enrollment, registration, camp, other. Copy must handle `other` with a neutral fallback | All cells |
| `{{admissions_page_url}}` | T2 page URL | All cells. For reference and QA; copy should name the page type, not paste the URL |
| `{{route_cell}}` | Formula on R1, R2, R3: values 1 to 6 | All cells. Routing key only; never shown in copy |
| `{{proof_customer}}` | Lookup on `route_cell`: COTSA (1, 5), Polk State (2, 6), Pennsylvania Academy of Ballet (3, 4) | All cells |
| `{{proof_support}}` | Lookup on `route_cell`: Ruby's Place (3, 4); empty in 1, 2, 5, 6 | Cells 3 and 4 only. Copy must not reference it elsewhere |
| `{{sender_name}}` | Instantly sender profile | All cells |

Not available in any branch, so copy can never say it: fee amount, document list, deadline, number of applicants, enrollment size, current tool other than Google Forms and paper.

## 7. Cadence and channel [ENGINE]

| Item | Setting | Source |
|---|---|---|
| Periodicity | Always-on. Monthly BuiltWith pull for new US sites; weekly page scan of new rows only | gtm-system.md step 1 (PLAYBOOK: tech adoption monthly) |
| Before launch | Run the 500-domain sample: measure how many pass T1 to T3 and F1, the cell spread, and the sign-in redirect test | workflow-candidates.md |
| Re-entry | Suppressed for 90 days after the sequence ends; re-enters only on a new signal | gtm-system.md step 2 |
| Channel | Both. Email in Instantly for every verified contact. LinkedIn if a profile URL exists | gtm-system.md steps 7 and 8 |
| Email | Day 0, Day 3 to 4, Day 7 to 10, optional Day 14+ | knowledge-base/playbooks/copy-frameworks.md |
| LinkedIn | Connection request Day 1 to 2 with no note; DM 1 one to two days after accept; DM 2 three to five days later; no DM 3; max 20 to 30 requests per account per day | knowledge-base/playbooks/linkedin-dm-frameworks.md |
| Catch-all or no email | LinkedIn only if a profile exists; otherwise drop | gtm-system.md step 7 |
| Positive reply | Default path: call (A-US). Trial link only if the reply asks for it | gtm-system.md step 9 |
| Launch gate | `campaign-qa` passed and owner approval before any send | CLAUDE.md rule; gtm-system.md step 8 |
| Timing | US admissions calendar: Not found in research. No seasonal timing in v1 | market.md |

---

## Definition of done

- [x] Mother intent: one sentence, signal-led, matched to the catalog
- [x] Inclusion: ICP box + trigger definition + recipient, tagged [ICP]
- [x] Exclusion: who's out and why
- [x] Sources: trigger + every enrichment
- [x] Signals table: every read deterministic, every role declared
- [x] Count clusters declared for any count that routes (none: all booleans)
- [x] Routing matrix with the angle column complete
- [x] Branch coverage: every angle survives on the data in its cell
- [x] Variables contract: every variable mapped to its source field
- [x] Engine/ICP markers on every section
- [x] Cadence and channel declared

Next: `/campaign-copy` reads this file (GATE 1) and turns the six approved angles into copy.
