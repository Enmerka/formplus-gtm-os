# Formplus signal matrix

**Status: work in progress, v1 (2026-11-13).** Hypotheses to validate with Formplus sales and leadership, not a final plan. Method: `knowledge-base/playbooks/signal-matrix-framework.md` and `workflow-anatomy.md`.

Inputs: [icp.md](icp.md), [personas.md](personas.md), `context/docs/research/`. Source key: [CO](../docs/research/company.md), [CU](../docs/research/customers.md), [CP](../docs/research/competitors.md), [MK](../docs/research/market.md), [SG](../docs/research/signals.md), [VO](../docs/research/voice.md). Data-source checks done for this file are cited inline with URL and date. INFERRED = our judgement, not in the research.

Formplus is single-product, so there are no product columns. The angle changes per cell; the product does not.

---

## Matrix 1: Segments x personas

### 1a. Angle per cell

Angles describe the buyer's situation, in their words where we have them. Each cites the proof behind it.

| Segment | Champion (ops or program owner) | Economic buyer (founder, director, COO) | Influencer (IT, data, finance, users) |
|---|---|---|---|
| **A. Schools and education programs** | Applications arrive on paper and get typed into a spreadsheet. Polk State: "We were manually entering students into a spreadsheet once they completed a paper application." Now "100% faster to obtain enrollment applications" [CU] | Time and paper cost per admission cycle. Polk: "decreased our time and cost ten times over" [CU]. 10% education discount [CO]. Title of the school's approver: Not found (open question) | Applicant files and IDs collected safely: 256-bit SSL, AES-256 at rest, GDPR statement [CO]. Do not claim NDPA compliance: Not found [CO] |
| **B. Nonprofits and membership bodies** | Registration, fee, agreement and certificate in one flow. AASHE: "We used to create certificates manually" [CU] | Paid registrations without add-ons breaking. Ruby's Place COO: "It was the easiest to use, it provided what we needed and actually simplified the process for us" [CU]. 10% nonprofit discount; no Formplus fee on payments [CO] | Finance: "the money received goes directly to the Form Owner or User, and not FormPlus" [CO]. YMCA uses Formplus for accounting forms [CU] |
| **C. Commercial mobile reporting teams** | Reports from many people in many places. Noah Kriska: "a program that could record information from multiple people from anywhere" [CU] | Keeping records current. Brooke Ziegler: "keeping up with our database of reporting, brand ambassadors" [CU] | IT checks mobile use and multi-user access [CU]. Do not lead with offline: neither C story mentions it [CU] |
| **D. Service SMBs (bookings, orders, payments)** | Same person as the economic buyer [personas.md] | Take details and payment in one step. Motive: "We needed somewhere to collect all the athlete information and take payment together"; Watamu: "about 80% of what we need, at a fraction of the cost of a custom system" [CU] | Respondents and outside partners can use it with no sign-in. We Insure: "globally accessible" [CU]; Google Forms uploads need a Google sign-in [CP] |
| **E. African SMEs on Paystack or Flutterwave** | Same person as the economic buyer [personas.md] | Orders out of DMs and phone calls into one form that takes payment. Beauty Bar "cut the steps involved in their sales funnel by 60%" [CU]. Paystack integration "perfect for Africans who want to receive payments from anyone, anywhere in the world" [VO] | Staff handling refunds and customer service (Beauty Bar runs refund forms) [CU]. Expect the USD-price objection; Naira pricing Not found [CO] |
| **F. HR and admin in mid-size companies** | Documents and claims without email threads. Kellton: email "led to long email threads; which led to missed deadlines" (case-study narrative) [CU] | Approver not named in research (open question). INFERRED angle: fewer missed deadlines and less chasing | Sensitive files. Total Sec: "things that you can't send with unsecure email" [CU]. Risk: no SOC 2 or ISO claim [CO] |
| *NGO M&E test cell (not a target)* | M&E officer. INFERRED angle: offline submissions that "sync when you're back online" [VO] | Program director. Budgets shrinking: 84% of IFES respondents lost funding in 2025 [MK] | Data quality lead. Already on KoboToolbox or ODK [SG] |

### 1b. Target definition, examples, priority

Headcount and industry filters are INFERRED starting points for Clay. The research gives customer sizes, not segment ranges.

| Segment | Target definition (filterable) | Real examples (from research) | Signal density | PMF | Penetrability | Priority |
|---|---|---|---|---|---|---|
| **A-US. US schools and programs** | US charter and private K-12 schools, arts schools, student associations, training consortia. Industry: Primary/Secondary Education, Education Management. INFERRED: 10 to 500 staff | Customers as lookalike seeds: Polk State College Charter Schools (FL), COTSA (CO), Pennsylvania Academy of Ballet (PA), NPTC [CU]. New prospects: requires Clay research (industry + US + Google Forms or PDF forms on site) | Med | High (3 education stories with numbers) | High (US data) | **High** |
| **A-NG. Nigerian schools** | Nigerian tertiary institutions and Lagos private secondary schools that sell admission forms each session | Selling 2026/2027 forms: LASU International School, LASU Staff School, UNILAG School of Foundation Studies, Chrisland Schools [MK]. 649 tertiary institutions on the NDPC notice [MK] | High (form-sale news, JAMB calendar) | Med (no Nigerian school customer story [CU]) | Med | **High** (test) |
| **B. Nonprofits and membership bodies** | Associations and nonprofits running paid registrations, calls for proposals or trainings. Industry: Non-profit, Civic & Social Organisation | Seeds: AASHE, Ruby's Place, YMCA (LAC), MMPA Task Force, PactWorld [CU]. New prospects: requires Clay research | Med | High | High (US) | **High** |
| **C. Commercial mobile reporting** | Field service, equipment, demo-staffing and agency firms whose staff file reports from phones | Seeds: Performance Equipment (CO), B.E Naturale (MN) [CU] | Low | Med (2 stories) | High | Low |
| **D. Service SMBs** | Gyms, studios, hotels and retreats, markets, small professional services taking bookings or orders online | Seeds: Motive School of Movement, Watamu Treehouse, I Made It! Market, We Insure Group, Yellow Dandelion, Career Consultant, Perpetual CPA, Inspirock [CU] | Med | High (8 stories) | Med (INFERRED: small firms thin in Apollo) | **Medium** |
| **E. African SMEs** | Nigerian and Kenyan online sellers and service firms with Paystack or Flutterwave on their site | Seeds: Beauty Bar Group (NG), Watamu Treehouse (KE) [CU]. New prospects: BuiltWith Paystack or Flutterwave list | Med | Med (2 stories; USD pricing) | Med | **Medium** |
| **F. Mid-size HR and admin** | Companies with 300 to 5,000 staff collecting employee documents or claims | Seeds: Kellton Tech (IN), Total Sec Oy (FI), MCAM NorthWest [CU] | Med | Med (member caps, no SOC 2 [CO]) | High | Low |
| *NGO M&E test cell* | Nigerian NGOs hiring M&E officers or data collectors | Hiring in 2026: OHRI, Notify Health, Management Sciences for Health, RECEF, One Acre Fund Nigeria [SG] | Med | Low (no offline proof) | Med | Test only |

---

## Matrix 2: Signals

### Scoring

Four tests from the Mother Intent rules in `workflow-anatomy.md`, each scored 1 to 5. All scores are INFERRED judgement.

- **Reason**: clear buying reason now (timing)
- **Volume**: enough companies to sustain a workflow
- **Data**: data we can get programmatically
- **Story**: natural narrative backed by a Formplus proof point

Status uses the framework's labels: VERIFIED, VERIFIED (COMPOUND), VERIFIED (PARTIAL), KILLED.

### 2a. Signal table

| # | Type | Signal | Mother intent | Data source | Tool / Clay action | Segments | Reason | Volume | Data | Story | Total /20 | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| S1 | Niche | School announces admission or entrance form sales for the new session | Niche-specific play (calendar) | School sites and Nigerian education news, e.g. https://myschoolgist.com, https://myschoolnews.ng, https://unilag.edu.ng; JAMB bulletins https://jamb.gov.ng [MK] | crawl4ai or Clay HTTP on news pages weekly, then Claygent to extract school, fee, payment method, deadline | A-NG | 5 | 3 | 4 | 4 | **16** | VERIFIED (sources exist [MK]; volume per season unknown) |
| S2 | Universal | Google Forms on the site where documents or payments are requested | Companies using specific software | BuiltWith Google Forms: 54,491 live sites, 28,913 in the US (https://trends.builtwith.com/widgets/Google-Forms, checked 2026-11-13). Page-level check with crawl4ai for `docs.google.com/forms` or `forms.gle` links | BuiltWith via Clay "Find Technology Stack", then Clay HTTP or crawl4ai on admissions, registration and vendor pages | A-US, A-NG, B, D | 3 | 5 | 4 | 5 | **17** | VERIFIED (COMPOUND): pair with S4, S5 or a segment filter |
| S3 | Universal | Paper process on the site: downloadable PDF or Word forms, "print and submit", "email your documents to", "send proof of payment" | Website content mentions | The organisation's own site | crawl4ai or Claygent keyword scan on a Clay list of segment domains (ICP-first list) | A-US, A-NG, B, C, D, E | 3 | 4 | 3 | 5 | **15** | VERIFIED (PARTIAL): needs a domain list first. Signal itself INFERRED [SG] |
| S4 | Universal | Organisation runs a recurring event, conference, competition or paid training | Companies hosting an event (adapted from "attending an event") | Eventbrite via Apify actors, e.g. https://apify.com/scrapesage/eventbrite-scraper (checked 2026-11-13; no organiser emails returned); the org's own events page | Apify via Clay HTTP; match organiser site to domain; filter for events registered via Google Forms or bank transfer, not Eventbrite checkout | B, D, A-US | 4 | 4 | 4 | 4 | **16** | VERIFIED. Proof: We Insure Kickoff, COTSA, Motive, AASHE [CU] |
| S5 | Universal | Hiring admissions, registrar, admin, operations or event coordinator roles | Hiring specific roles | Clay "Find Jobs at Company" (LinkedIn); Indeed via Apify; Nigeria: https://www.myjobmag.com [SG] | Clay Find Jobs with title keywords per segment; MyJobMag scrape for Nigeria | A-US, A-NG, B, D, F | 3 | 5 | 4 | 3 | **15** | VERIFIED. The link from hire to buying is INFERRED |
| S6 | Niche | Paystack or Flutterwave on site, with orders taken via WhatsApp, Instagram or bank transfer | Companies using specific software | BuiltWith Flutterwave list (1,172 live sites, https://builtwith.com/websitelist/Flutterwave/CANZUK, checked 2026-11-13); Paystack detected on BuiltWith site pages | BuiltWith via Clay, then crawl4ai for `wa.me` links or "send proof of payment" | E | 3 | 2 | 4 | 4 | **13** | VERIFIED (COMPOUND). Paystack list size: Not found |
| S7 | Universal | New leader in an operations, admissions or program role in the last 90 days | New leadership | Clay "Find People" (title + start date) | Clay Find People | A-US, B, F | 3 | 4 | 4 | 2 | **13** | VERIFIED. No research shows a new leader triggering a Formplus purchase (INFERRED) |
| S8 | Universal | Headcount growth over 25% in 6 months | Companies in hypergrowth | Clay "Company Headcount" / Apollo | Clay Enrich Company, monthly delta | D, F | 3 | 3 | 3 | 3 | **12** | VERIFIED. Proof: Watamu "grown from just 3 employees to 45" [CU] |
| S9 | Universal | Lookalikes of named Formplus customers | Lookalike of customers | Seed list from [CU] (21 named customers) | Clay lookalike / Find Companies | All | 1 | 5 | 5 | 4 | **15** | VERIFIED as an **ICP list base, not a mother intent**: no timing |
| S10 | Niche | NGO hiring M&E officers or data collectors, ad names KoboToolbox or ODK | Hiring specific roles + competitor customers | https://www.myjobmag.com, https://www.hotnigerianjobs.com, https://www.jobzilla.ng [SG] | Scrape via Apify or Clay HTTP; keyword "KoboToolbox", "ODK" | NGO test cell | 2 | 3 | 4 | 2 | **11** | VERIFIED, test only (they already have a tool [SG]) |
| S11 | Niche | Named in the NDPC compliance notice to 649 tertiary institutions (19 Feb 2026) | Regulatory changes | Newspaper notice of 19 Feb 2026 (https://www.itedgenews.africa/ndpc-issues-compliance-notices-to-649-nigerian-tertiary-institutions-urges-stronger-privacy-protection/, checked 2026-11-13). The list itself was not found online | One-time list build, then Clay enrichment | A-NG | 4 | 2 | 1 | 2 | **9** | KILLED as a workflow: one-time list, not accessible online, and Formplus has no NDPA claim to back the story [CO] |
| S12 | Niche | NGO wins a new grant or program (FCDO, Global Fund) | Niche-specific play | FCDO IATI activity files, published "at least quarterly" [MK]. Programmatic access route: Not verified | Not defined | B, NGO test cell | 3 | 3 | 2 | 2 | **10** | KILLED for now: fails the Iron Law (no exact endpoint verified) |
| S13 | Universal | Recently funded (Crunchbase) | Companies fundraising | Crunchbase | Clay Find Organization | n/a | n/a | n/a | n/a | n/a | n/a | KILLED: customers are schools, nonprofits and SMBs, not VC-backed [CU] |
| S14 | Niche | Google Forms payment add-on discontinued, or other tool breakage | Niche-specific play | None programmatic (Ruby's Place story only [CU]) | n/a | B, D | 5 | 1 | 1 | 5 | **12** | KILLED: no data source. Keep as a copy angle |
| S15 | Niche | Listed on the NDPC register of DCPMIs | Regulatory changes | Said to be published yearly (secondary source [MK]); not located | n/a | A-NG, F | 3 | 3 | 1 | 2 | **9** | KILLED until the register is found online |

### 2b. Universal vs niche-specific

- **Universal, build once, swap keywords:** S2, S3, S4, S5, S7, S8, S9. That's 7 of 10 live signals.
- **Niche-specific, separate build:** S1 (Nigerian school calendar), S6 (African payment stack), S10 (NGO jobs).
- What changes per segment: job-title keywords (S5), page types scanned (S2, S3: admissions vs registration vs vendor pages), the proof story (Polk for schools, AASHE for nonprofits, Motive or Watamu for SMBs, Beauty Bar for African SMEs).

### 2c. Play per priority segment

| Signal | A-US schools | A-NG schools | B nonprofits | D service SMBs |
|---|---|---|---|---|
| S1 Form-sale announcement | n/a | **Primary.** School opens form sales, fee paid by bank transfer. Proof: Polk State | n/a | n/a |
| S2 Google Forms on site | Admissions page uses Google Forms with uploads. Proof: Polk tried Google Forms; COTSA called it "clunky" | Same, on admissions or screening pages | Registration or proposals via Google Forms. Proof: Ruby's Place, AASHE | Booking or order form on Google Forms. Proof: Career Consultant, Total Sec |
| S3 Paper process | "Download the application form" PDFs. Proof: Polk | Same | Paper or emailed registrations. Proof: AASHE "scattered spreadsheets" | Orders by phone or DM. Proof: Beauty Bar, Yellow Dandelion |
| S4 Recurring event | Student competitions, camps. Proof: COTSA | n/a | Conferences, trainings. Proof: AASHE, Ruby's Place | Competitions, kickoffs, markets. Proof: Motive, We Insure, I Made It! |
| S5 Hiring | Admissions officer, registrar | Admissions officer, registrar (MyJobMag) | Program, membership or events coordinator | Operations or front-desk manager |

---

## Top signals to build first

| Rank | Signal | Why first |
|---|---|---|
| 1 | **S2 Google Forms on site + S3 paper process** (one compound build) | Biggest volume (54,491 live Google Forms sites, 28,913 US) and the strongest proof: Google Forms was the "before" tool in 5 of 21 stories, and paper in 5 [CU] [CP]. The sign-in-for-uploads problem is concrete and checkable [CP]. Works across A, B and D with keyword swaps |
| 2 | **S4 Recurring event registration** | A dated reason to act (next event), four proof stories (We Insure, COTSA, Motive, AASHE) [CU], and Eventbrite data is scrapable. Filter to events not already on a checkout tool |
| 3 | **S1 Nigerian school form-sale announcements** | Strongest timing of any signal: a fixed admission season [MK], with fees often paid by bank transfer. Built as a test, because there is no Nigerian school customer story yet [CU] and Naira pricing is unknown [CO] |
| 4 | **S5 Hiring admissions, admin or event roles** | Highest-volume universal build and reusable for every segment. Weaker story, so use it as a secondary enrichment on S2 or S4 before running it alone |

Not first: S6 (small list, USD-price objection), S7 and S8 (no Formplus proof of the trigger), S10 (competitor-locked and in the test cell).

---

## Matrix 3: Workflow tracker

| W # | Status | Workflow name | Mother intent | Segments | Campaigns | Launch date | Channel | Clay URL | Total leads |
|---|---|---|---|---|---|---|---|---|---|
| W1 | Planned | Google Forms or paper forms on site | Companies using specific software + website content | A-US, A-NG, B, D | | | | | |
| W2 | Planned | Recurring event registration | Companies hosting an event | B, D, A-US | | | | | |
| W3 | Planned | Nigerian school form sales | Niche-specific play | A-NG | | | | | |
| W4 | Planned | Hiring admissions, admin, ops roles | Hiring specific roles | A, B, D, F | | | | | |
| W5 | Planned | Paystack or Flutterwave SMEs taking DM orders | Companies using specific software | E | | | | | |
| W6 | Planned | New ops or program leader | New leadership | A-US, B, F | | | | | |
| W7 | Planned | Headcount growth | Hypergrowth | D, F | | | | | |
| W8 | Planned (test) | NGO M&E hiring with KoboToolbox or ODK | Hiring + competitor customers | NGO test cell | | | | | |

S9 (lookalikes) is the list base for W1 to W4, not its own workflow. S11 to S15 are killed (reasons in 2a).

## Open questions

- Does Formplus sales agree with the priority order? It assumes US data and Nigerian timing both matter.
- How many Nigerian schools announce form sales per season? Measure S1 over one cycle.
- Is the NDPC list of 649 institutions available as a file? It would revive S11 as a one-time list.
- Who approves spend in schools (A) and mid-size firms (F)? Not in research.
- Is there Naira pricing for A-NG and E? Not found [CO].
