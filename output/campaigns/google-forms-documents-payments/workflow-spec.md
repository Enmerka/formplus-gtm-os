# W1: Google Forms or paper forms where documents or payments are requested

**Status:** COPY-APPROVED 2026-11-13

**Revised 2026-11-15:** sources and signals revised for Clay. Account-first from Clay's company search; T1 (BuiltWith list) dropped, T2 is the trigger; page reads from Clay's website scrape with a Claygent fallback; R1 to R3 read by one Use AI column ("Page asks"); Exclusions table and `Ready to Contact?` gate added. Copy unchanged; every copy variable still has a source (section 6).

- Workflow: W1 in [context/icp/signal-matrix.md](../../../context/icp/signal-matrix.md) (signals S2 + S3). System steps: [context/docs/gtm-system.md](../../../context/docs/gtm-system.md).
- Segment: A-US schools (first build). Segment B nonprofits reuses the same build; swaps are marked **B reuse**.
- Facts: copy facts come from [context/messaging/facts.md](../../../context/messaging/facts.md) (APPROVED 2026-11-13), which draws on `context/docs/research/` (checked 2026-11-13). Anything else is a `{{placeholder}}`.
- Labels: INFERRED = our judgement, not in the research. UNVERIFIED = a Clay behaviour not yet tested on a real row.

---

## 1. Mother intent (trigger) [ENGINE]

**US schools whose admissions or registration page runs a Google Form while asking applicants for documents or a payment.**

- Catalog match (`knowledge-base/playbooks/workflow-anatomy.md`): "Website content mentions" (the page asks for documents or payment), stacked with "Companies using specific software" (Google Forms), read from the school's own admissions page rather than from a technology list.
- Account-first: the list starts from Clay's company search (US schools by industry and size, section 2). The trigger is T2, a Google Form found on the school's admissions or registration page.
- Scope: schools that use paper only, with no Google Form, are out of this workflow; T2 drops them. Paper is a router inside the Google Form rows (R3).

## 2. Inclusion / exclusion [ICP]

### Include

| Box | Rule | Source |
|---|---|---|
| Geography | United States, headquarters in the US (Clay company search location filter, headquarters only) | icp.md, A-US |
| Industry | Clay industry "Primary and Secondary Education" (the value in Clay's search picker, confirmed 2026-11-15). Target: charter, private, independent and Catholic K-12 schools | icp.md, A-US target definition; Clay picker checked 2026-11-15 |
| Description | Company description contains any of: `private school`, `charter school`, `independent school`, `day school`, `academy`, `Catholic school`, `Montessori`, `admissions`. Without it the results mix in edtech companies, education nonprofits and state education departments | Clay Find Companies preview, 2026-11-15 |
| Size | Clay company size bands `11-50`, `51-200` and `201-500` only. Schools with no size listed drop out (accepted 2026-11-15). INFERRED cap, to tune on the sample | icp.md (segment sizes Not found); Clay size bands (`tools/rex/action-registry.md`) |
| Volume | About 5K companies with every filter above: `11-50` about 2.6K, `51-200` about 2K, `201-500` 356. 24.6K before the description filter. With it, `51-200` and `201-500` are almost all private, Catholic and independent schools; `11-50` still includes some public high schools, a think tank and a camp provider, which F1 must drop. Pass rates at each later step: unknown until the sample | Clay Find Companies preview (free), 2026-11-15 |
| Trigger | T2 AND T3 (section 4) | signal-matrix.md, S2 + S3 |
| Recipient | **Champion:** admissions officer, director of admissions, registrar, enrollment manager, instructional technologist. **Fallback** if no champion is found: head of school or principal. One contact per school in v1, picked by the title-rank formula (G1) | personas.md; gtm-system.md step 6 |

### Exclude

| Who | Why |
|---|---|
| Formplus customers and competitors in the Exclusions table, matched on domain (X2) | Customers are lookalike seeds, not targets; competitors are not buyers (gtm-system.md step 2) |
| Case-study customers: Polk State College Charter Schools, COTSA, Pennsylvania Academy of Ballet, NPTC | In the Exclusions table as `customer` rows |
| Google Form found only on non-admissions pages (newsletter, contact, feedback) | The signal does not hold (gtm-system.md step 1) |
| Admissions page also embeds Jotform, Typeform, Formstack or Wufoo (X1) | They already pay for a form builder; displacement is a different story |
| Not a fit per icp.md: healthcare patient data, enterprise compliance needs | icp.md not-a-fit list; F1 returns `not_fit` |
| Outside the US | Wrong segment; Nigerian schools are W3 |

**Week 3 (HubSpot access not available until then):** existing Formplus customers, open deals, suppressed or unsubscribed contacts, and contacts reached in the last 90 days with the same signal (gtm-system.md steps 2 and 10; 90 days is a PROPOSED window). Until then, the Exclusions table is the only customer check.

**Exclusions table:** one row per company, columns `Company Name | Domain | Type` (`customer` or `competitor`). Customers: the named customers in `context/docs/research/customers.md`, including the four above. Competitors: the companies in `context/positioning/competitors.md`. Domains written plain (`example.org`, no `https://`, no `www.`). Leave a domain blank rather than guess it, and fill it from the company's own website.

### B reuse (nonprofits)

| Element | A-US value | B value |
|---|---|---|
| Industry | Primary and Secondary Education | Non-profit, Civic & Social Organisation (UNVERIFIED against Clay's industry picker) |
| Page keywords (T2) | admission, apply, application, enrol, enroll, enrollment, registration, register | registration, register, membership, conference, training, events, call for proposals |
| Recipient | Admissions officer, registrar, enrollment manager; fallback head of school | Program, membership or events manager; fallback executive director |
| Proof | Section 5 | Documents cells: AASHE. Payment cells: Ruby's Place |

Everything in sections 3 to 7 stays the same.

## 3. Sources [ENGINE]

Build order: free before paid, and every paid step runs only on rows that passed every step before it.

| Step | Source | Delivers | Cost |
|---|---|---|---|
| 1. Company universe | Clay company search (Find Companies): headquarters United States, industry "Primary and Secondary Education", size bands `11-50`, `51-200`, `201-500`, and the section 2 description filter. Preview count about 5K (section 2) | Company name, domain, size, industry, description, LinkedIn URL | Free |
| 2. Exclusions | Lookup on the Exclusions table, matched on domain (X2) | `is_excluded` | Free |
| 3. Segment check | Clay Use AI column, JSON output (F1) | `segment`, `not_fit_reason`, `segment_evidence` | Paid |
| 4. Find the admissions page | Clay's native website scrape on the homepage (likely labelled "Scrape Website"; if not, search Clay's enrichments for "scrape"). A formula keeps the first link whose URL or link text matches the T2 page keywords. **Fallback:** Claygent, only on rows where no admissions page was found, returns the admissions page URL | `admissions_page_url` | Paid |
| 5. Scan the admissions page | Clay's native website scrape on `admissions_page_url`. Needs the page's links, iframe `src` values and visible text. UNVERIFIED: whether the scrape returns iframe `src` values (and the full link list). Proven on 1 row of the Schools table when this column is built; Claygent is the backup for embedded forms | Links, iframes, page text | Paid |
| 6. Page asks | Clay Use AI column on the page text, JSON output (section 4) | R1, R2, R3 fields and evidence quotes | Paid |
| 7. Recipient | Clay people search started from a view of the companies that passed steps 1 to 6, with the section 2 titles. **Fallback:** Apollo people search by domain, only for schools where Clay finds no one | `first_name`, title, LinkedIn URL | Free (Apollo fallback: paid) |
| 8. Email | Clay waterfall: Prospeo, Icypeas, Leadmagic, Findymail; then Bounceban to verify (`knowledge-base/playbooks/clay/expert.md`). Runs only where `Ready to Contact?` is true | Verified email, verification status | Paid |

Apollo company enrichment is no longer a source: Clay's company search returns name, size and industry.

## 4. Signals table [ENGINE]

Reads run on the scanned admissions or registration page unless stated. Keyword lists are INFERRED build settings, to tune on the sample.

| # | Signal | Role | How it's read (Clay column type) | Output |
|---|---|---|---|---|
| T2 | Google Form on an admissions or registration page | trigger | Formula (regex) on the scrape output: a link matching `docs.google.com/forms` or `forms.gle`, **or an iframe whose `src` contains `docs.google.com/forms`** (UNVERIFIED, see section 3 step 5), on a page whose URL or title matches `admission\|admissions\|apply\|application\|enrol\|enroll\|enrollment\|registration\|register`. False: the row drops | `gform_on_admissions`, `admissions_page_url` |
| P1 | Ask keywords on the page | filter (free pre-filter) | Formula: page text contains any keyword from the lists below. False: "Page asks" does not run and the row drops. Documents: `upload`, `attach`, `transcript`, `birth certificate`, `report card`, `immunization`, `proof of residency`, `email your documents`, `send copies`. Payment: `application fee`, `registration fee`, `deposit`, `tuition deposit`, `proof of payment`, `pay by check`, `money order`, or a `$` amount within 50 characters of `fee`. Paper: a link ending `.pdf`, `.doc` or `.docx`, or `print and`, `mail to`, `drop off`, `return to the office` | `has_ask_keywords` |
| PA | Page asks | source of R1 to R3 | Use AI column, JSON output, run condition: T2 true AND P1 true AND F1 = `A-US` AND X1 false AND X2 false. Input: page text, link list (with anchor text) and `admissions_page_url`. Fields: `asks_documents`, `asks_payment`, `has_paper_form` (each `yes`, `no` or `unclear`), and `documents_evidence`, `payment_evidence`, `paper_evidence` (a word-for-word quote from the page, or empty). Prove on 2 or 3 pages you can judge before running the rest | JSON fields above |
| R1 | Documents requested | router | Formula: `asks_documents` = `yes` | `asks_documents` |
| R2 | Payment requested | router | Formula: `asks_payment` = `yes` | `asks_payment` |
| R3 | Paper or PDF form alongside the Google Form | router | Formula: `has_paper_form` = `yes` | `has_paper_form` |
| T3 | Page asks for documents or a payment | trigger | Formula: R1 OR R2. If `asks_documents` and `asks_payment` are both `no`, the row drops. If any of the three PA fields is `unclear`, the row goes to the **Review** view and `Ready to Contact?` stays false until a person sets the field | `asks_docs_or_payment`, `needs_review` |
| C1 | Which process the page is for | context-clause | Formula (regex) on URL and title, first match wins. Enum: `admissions`, `enrollment`, `registration`, `camp`, `other` | `process_type` |
| C2 | School name | context-clause | Clay company search name, cleaned of legal suffixes; fallback: page title | `school_name` |
| F1 | Segment fit | filter | Use AI column, JSON output. Input: company name, domain, industry, size and description from the Clay company search. Fields: `segment` (hard enum: `A-US`, `B`, `D`, `not_fit`, `other`), `not_fit_reason`, `segment_evidence` (a word-for-word quote from the input). Only `A-US` continues (`B` continues in the B build); `other` goes to the Review view. Must return `not_fit` for the non-schools the search lets through: public high schools, think tanks and camp providers (seen in the `11-50` band, 2026-11-15). Prove on 2 or 3 schools before running the rest | `segment`, `not_fit_reason`, `segment_evidence` |
| X1 | Paid form builder on the same page | exclusion | Formula (regex) on link and iframe domains: `jotform.com`, `typeform.com`, `formstack.com`, `wufoo.com`. True: the row drops | `has_paid_builder` |
| X2 | Customer or competitor | exclusion | Lookup on the Exclusions table, matched on domain. Found: the row drops | `is_excluded` |
| G1 | Title rank | gate | Formula on the person's title, INFERRED order: 1 admissions or enrollment titles (admissions officer, director of admissions, enrollment manager), 2 registrar, 3 instructional technologist, 4 head of school or principal. Keep the lowest rank per domain; ties keep the first person found | `title_rank`, `is_top_contact` |
| G2 | Ready to Contact? | gate | Formula: T2 AND T3 AND NOT `needs_review` AND F1 = `A-US` AND NOT X1 AND NOT X2 AND `is_top_contact`. Run condition for the email waterfall and every copy formula | `ready_to_contact` |

- Count clusters: none. Every router is a yes/no read once Review rows are held back.
- Routing axes: what the page asks for (R1, R2) and paper alongside (R3).
- Context-clauses C1 and C2 never route.

**Considered and left out**
- T1, the BuiltWith Google Forms list (dropped 2026-11-15). It is not a Clay company search filter (Clay's company search accepts only domain, size and industry; `tools/rex/action-registry.md`), and the list counts every US website, not schools. T2 reads the Google Form on the page directly.
- Keyword matches as the R1 and R2 reads (replaced 2026-11-15 by "Page asks"). They can't tell "upload your photo to the gallery" from a document request, or "no fee" from a payment. The keywords stay as the free pre-filter P1.
- Whether the Google Form itself contains a file-upload question. It would directly support the "Google sign-in to upload" proof, but reading it from outside is not verified.
- **Test on the sample:** does fetching the Google Form URL redirect to a Google sign-in page? That would be a proxy for a file-upload question. It is not in v1, because sign-in can be required for other reasons.

## 5. Routing matrix with angles [ENGINE]

- Axis 1, what the page asks for (R1, R2): 3 options: documents only, payment only, both. "Neither" is removed by T3.
- Axis 2, paper alongside (R3): 2 options: yes, no.
- Stacked: 3 x 2 = 6 cells.
- "R1 true" means `asks_documents` = `yes` (likewise R2, R3). Rows with any `unclear` read are held in the Review view and never get a cell until a person sets the field.

Branch coverage: every cell has `school_name`, `process_type` and `admissions_page_url`. No cell has a fee amount, a document list or a deadline, so no angle depends on one. The evidence quotes are for QA only and never appear in copy.

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

Copy may only use these variables. Syntax: `{{snake_case}}`; match Instantly's syntax at export. Checked 2026-11-15: every variable the copy below uses has a source in this table.

| Variable | Source field | Exists in branches |
|---|---|---|
| `{{first_name}}` | Clay people search, first name (Apollo people search fallback) | All cells |
| `{{school_name}}` | C2: Clay company search name, cleaned; fallback page title | All cells |
| `{{process_type}}` | C1 enum: admissions, enrollment, registration, camp, other. Copy must handle `other` with a neutral fallback | All cells |
| `{{admissions_page_url}}` | T2 page URL (section 3 step 4) | All cells. For reference and QA; copy should name the page type, not paste the URL |
| `{{route_cell}}` | Formula on R1, R2, R3 (read from "Page asks"): values 1 to 6 | All cells. Routing key only; never shown in copy |
| `{{proof_customer}}` | Lookup on `route_cell`: COTSA (1, 5), Polk State (2, 6), Pennsylvania Academy of Ballet (3, 4) | All cells |
| `{{proof_support}}` | Lookup on `route_cell`: Ruby's Place (3, 4); empty in 1, 2, 5, 6 | Cells 3 and 4 only. Copy must not reference it elsewhere |
| `{{sender_name}}` | Instantly sender profile | All cells |
| `{{sender_title}}` | Instantly sender profile (added 2026-11-13, owner-approved) | All cells |
| `{{sender_company}}` | Instantly sender profile (added 2026-11-13, owner-approved) | All cells |
| `{{e1l1}}` | Copy tag: Email 1 line 1, resolved in Clay from `route_cell` (6 variants) | All cells (one variant per cell) |
| `{{e1l2}}` | Copy tag: Email 1 line 2, resolved in Clay from R1 and R2 (3 variants) | All cells |
| `{{e1l3}}` | Copy tag: Email 1 value prop, resolved in Clay from R1 and R2 (3 variants; A live, B test) | All cells (added 2026-11-13, owner-approved) |
| `{{social_proof}}` | Copy tag: proof line, resolved in Clay from `proof_customer` (3 variants) | All cells |
| `{{e2l1}}` | Copy tag: Email 2 line 1, resolved in Clay from R1 and R2 (3 variants) | All cells |
| `{{e2l2}}` | Copy tag: Email 2 line 2, from `proof_support` (Ruby's Place) | Cells 3 and 4 only; empty elsewhere, and the line is omitted |
| `{{e3l1}}` | Copy tag: Email 3 line 1, resolved in Clay from `proof_customer` (3 variants) | All cells |
| `{{li_dm1}}` | Copy tag: LinkedIn DM 1, resolved in Clay from R1 and R2 (3 variants) | All cells with a LinkedIn profile URL |

Every copy-tag formula starts with the `Ready to Contact?` guard (G2), so rows that won't be contacted stay blank. Table-only columns that never appear in copy: `ready_to_contact`, `needs_review`, `title_rank`, the evidence quotes, `segment`.

Not available in any branch, so copy can never say it: fee amount, document list, deadline, number of applicants, enrollment size, current tool other than Google Forms and paper.

## 7. Cadence and channel [ENGINE]

| Item | Setting | Source |
|---|---|---|
| Periodicity | Always-on. Monthly re-run of the Clay company search, adding new US schools only; weekly page scan of new rows only | gtm-system.md step 1 (cadence INFERRED for an account-first list) |
| Before launch | Run the sample: record the search preview count, how many pass each of X2, F1, T2, P1, T3 and the Review view, the cell spread, and the sign-in redirect test. Prove the scrape, including iframe `src` values, on 1 row of the Schools table first | workflow-candidates.md |
| Re-entry | Suppressed for 90 days after the sequence ends; re-enters only on a new signal. Enforced from Week 3, when HubSpot is connected | gtm-system.md step 2 |
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
- [x] Signals table: every read declared with its Clay column type (formula, lookup, scrape or Use AI with JSON and evidence), every role declared
- [x] Count clusters declared for any count that routes (none: all booleans)
- [x] Routing matrix with the angle column complete
- [x] Branch coverage: every angle survives on the data in its cell
- [x] Variables contract: every variable mapped to its source field
- [x] Engine/ICP markers on every section
- [x] Cadence and channel declared
- [x] Clay sources and signals revised (2026-11-15): every signal read by a Clay search filter, lookup, scrape, Use AI column or formula

Checks done 2026-11-15: industry value confirmed ("Primary and Secondary Education"); preview count recorded (about 5K, section 2). Still open: whether Clay's website scrape returns iframe `src` values, proven on 1 row of the Schools table when that column is built.

Next: `/clay-build-plan` turns this spec into the step-by-step Clay build guide (Week 2 step 2). Copy is done (COPY-APPROVED 2026-11-13).


---

## Copy

Facts: `context/messaging/facts.md` (APPROVED 2026-11-13). Register: signal play. Sender placeholders stay as placeholders (practice project).

### Email 1 (approved 2026-11-13)

**Subject** (static, unchanged across the thread): `{google form question|your school's forms|a form question}`

```
{{first_name}},

{{e1l1}}

{{e1l2}}

{{e1l3}}

{{social_proof}}

{Is that how it works on your side?|Is that close to how it works today?|Relevant, or way off?}

{Thanks,|Best,|Cheers,}
{{sender_name}}
{{sender_title}}, {{sender_company}}
```

#### Line 1 `{{e1l1}}` (exhaustive across the 6 cells, no fallback)

+ CELL 1 (R1 true, R2 false, R3 false): From what I could find, {{school_name}}'s application runs on a Google Form and asks families for supporting documents.
+ CELL 2 (R1 true, R2 false, R3 true): Going by {{school_name}}'s website, families can apply two ways, a Google Form or a printable PDF, with supporting documents on top.
+ CELL 3 (R1 false, R2 true, R3 false): {{school_name}}'s website uses a Google Form for sign-ups and mentions a fee.
+ CELL 4 (R1 false, R2 true, R3 true): On {{school_name}}'s website there's a Google Form and a printable form to sign up, plus a fee to pay.
+ CELL 5 (R1 true, R2 true, R3 false): From my research, {{school_name}}'s application runs on a Google Form and also asks for documents and a fee.
+ CELL 6 (R1 true, R2 true, R3 true): Reading through {{school_name}}'s website, the full packet is there: a Google Form, a printable application, supporting documents and a fee.

#### Line 2 `{{e1l2}}` (exhaustive on R1 and R2, no fallback)

+ DOCUMENTS ONLY (cells 1, 2): Google Forms asks people to sign in to a Google account before they can upload a file, so I'd guess some documents still arrive by email.
+ PAYMENT ONLY (cells 3, 4): My guess is someone then matches each payment back to the right family by hand.
+ DOCUMENTS AND PAYMENT (cells 5, 6): Google Forms asks people to sign in to a Google account before they can upload a file, so my guess is the documents and the fee each arrive on their own.

#### Value prop `{{e1l3}}` (exhaustive on R1 and R2, no fallback; A live, B held as a test variant)

+ DOCUMENTS ONLY (cells 1, 2): A: Formplus is an online form builder that takes the application and the documents together in one form. B: Formplus lets schools take applications and documents together in one online form.
+ PAYMENT ONLY (cells 3, 4): A: Formplus is an online form builder that takes the registration and the fee together in one form. B: Formplus lets schools take registrations and fees together in one online form.
+ DOCUMENTS AND PAYMENT (cells 5, 6): A: Formplus is an online form builder that takes the application, the documents and the fee in one form. B: Formplus lets schools take applications, documents and fees in one online form.

#### Social proof `{{social_proof}}` (exhaustive on `proof_customer`, no fallback)

+ COTSA (cells 1, 5): The Colorado Technology Student Association (COTSA) moved its entries off Google Forms and says Formplus "made collection of URLs and forms WAY easier".
+ POLK STATE (cells 2, 6): Polk State College Charter Schools used to type paper applications into a spreadsheet and now gets enrollment applications "100% faster".
+ PAB (cells 3, 4): Pennsylvania Academy of Ballet has students register and pay online through PayPal, and was "up and running with Formplus in a matter of just a day or two."

Ruby's Place (`proof_support`, cells 3 and 4) is held for Email 2.

Word counts (greeting to CTA, sign-off excluded, Variant A): cell 1: 93, cell 2: 93, cell 3: 82, cell 4: 88, cell 5: 99, cell 6: 98.

#### Sample: cell 2, as received

> **Subject:** google form question
>
> {{first_name}},
>
> Going by {{school_name}}'s website, families can apply two ways, a Google Form or a printable PDF, with supporting documents on top.
>
> Google Forms asks people to sign in to a Google account before they can upload a file, so I'd guess some documents still arrive by email.
>
> Formplus is an online form builder that takes the application and the documents together in one form.
>
> Polk State College Charter Schools used to type paper applications into a spreadsheet and now gets enrollment applications "100% faster".
>
> Is that how it works on your side?
>
> Thanks,
> {{sender_name}}
> {{sender_title}}, {{sender_company}}

### Email 2 (approved 2026-11-13)

Day 3 to 4, same thread, subject `Re:` Email 1's subject.

```
{{first_name}},

{{e2l1}}

{{e2l2}}          (cells 3 and 4 only; line omitted in cells 1, 2, 5, 6)

The form can also sit on your own website.

{Want me to send an example form?|Should I send over an example form?|Would an example form help?}

{{sender_name}}
```

#### Line 1 `{{e2l1}}` (exhaustive on R1 and R2, no fallback)

+ DOCUMENTS ONLY (cells 1, 2): To add to my last note, uploaded files go to the school's own Google Drive, Dropbox or OneDrive.
+ PAYMENT ONLY (cells 3, 4): To add to my last note, payments go straight to the school, not to Formplus, and Formplus doesn't add a fee on top of the payment provider.
+ DOCUMENTS AND PAYMENT (cells 5, 6): To add to my last note, uploaded files go to the school's own Google Drive, Dropbox or OneDrive, and payments go straight to the school, not to Formplus.

#### Line 2 `{{e2l2}}` (conditional on `proof_support`)

+ RUBY'S PLACE (cells 3, 4): Ruby's Place switched to Formplus when its Google Forms payment add-on was discontinued.
+ Cells 1, 2, 5, 6: line omitted.

Word counts (greeting to CTA): cells 1, 2: 35; cells 3, 4: 57; cells 5, 6: 45.

#### Sample: cell 3, as received

> {{first_name}},
>
> To add to my last note, payments go straight to the school, not to Formplus, and Formplus doesn't add a fee on top of the payment provider.
>
> Ruby's Place switched to Formplus when its Google Forms payment add-on was discontinued.
>
> The form can also sit on your own website.
>
> Want me to send an example form?
>
> {{sender_name}}

### Email 3 (approved 2026-11-13)

Day 7 to 10, same thread, subject `Re:` Email 1's subject.

```
{{first_name}},

{{e3l1}}

{If someone else looks after these forms|If this sits with someone else at {{school_name}}}, who would be the right person to ask?

{{sender_name}}
```

#### Line 1 `{{e3l1}}` (exhaustive on `proof_customer`, no fallback)

+ COTSA (cells 1, 5): One last example: COTSA now takes entries from "more than 2,000 participants" and calls the process "all digital".
+ POLK STATE (cells 2, 6): One last note: Polk State College Charter Schools says Formplus "decreased our time and cost ten times over".
+ RUBY'S PLACE (cells 3, 4): Last thing from me: Ruby's Place's COO said of Formplus, "It was the easiest to use, it provided what we needed and actually simplified the process for us".

Word counts (greeting to CTA): cells 1, 5: 33; cells 2, 6: 31; cells 3, 4: 42.

#### Sample: cell 2, as received

> {{first_name}},
>
> One last note: Polk State College Charter Schools says Formplus "decreased our time and cost ten times over".
>
> If someone else looks after these forms, who would be the right person to ask?
>
> {{sender_name}}

### LinkedIn (approved 2026-11-13)

Only for contacts with a LinkedIn profile URL. Reply on either channel pauses the other.

| Touch | Timing | Content |
|---|---|---|
| Connection request | Day 1 to 2 after Email 1 | No note |
| DM 1 | 1 to 2 days after accept | `{{li_dm1}}` |
| DM 2 | 3 to 5 days after DM 1 | Static, below |
| No DM 3 | Withdraw unaccepted requests after 2 weeks | |

#### DM 1 `{{li_dm1}}` (exhaustive on R1 and R2, no fallback)

+ DOCUMENTS ONLY (cells 1, 2): {{first_name}}, for this year's applications, will families upload documents straight into the form, or will some still come by email?
+ PAYMENT ONLY (cells 3, 4): {{first_name}}, will families pay the fee in the same step as signing up this year, or is that a separate step?
+ DOCUMENTS AND PAYMENT (cells 5, 6): {{first_name}}, will the documents and the fee come in through the same online step this year, or separately?

#### DM 2 (static)

```
{Asking because|I ask because} Formplus lets schools take applications, documents and fees in one online form. {Happy to send an example if useful.|Glad to send over an example if it helps.}
```

Uses value-prop Variant B (approved in facts.md, not used in the live emails).

#### Sample: cell 3, as received

> {{first_name}}, will families pay the fee in the same step as signing up this year, or is that a separate step?
>
> Asking because Formplus lets schools take applications, documents and fees in one online form. Happy to send an example if useful.

Before launch: `campaign-qa`, owner approval, and a final manual read against `knowledge-base/playbooks/copy-iron-laws.md`. Sequencer export: not yet generated.
