# Campaign strategy: Formplus

**Status: v1, 2026-11-13.** 19 ideas. Inputs: `CLAUDE.md`, `context/` (ICP, personas, signal matrix, positioning, messaging, case studies, research) and `knowledge-base/playbooks/workflow-anatomy.md`. Next step for a chosen idea: `/build-workflow-spec`.

- **Target audience (given):** schools, nonprofits and membership bodies, service SMBs, African SMEs, mid-size HR teams; US first, then Nigeria and Kenya ([icp.md](../../context/icp/icp.md)).
- **Core value proposition:** one form takes the details, the documents and the payment ([messaging.md](../../context/messaging/messaging.md)).
- **Key differentiators:** file uploads without a Google sign-in; Stripe, PayPal, Paystack and Flutterwave with no Formplus fee; free to start ([positioning.md](../../context/positioning/positioning.md)).

**Rules for this file**
- Customer names are proof points from [case-studies.md](../../context/docs/case-studies.md). Before any name goes into copy, it must be authorised in `context/messaging/facts.md`, which doesn't exist yet.
- No monthly volume figure exists in the research. Known pool sizes are cited; everything else is an INFERRED band: **Low** under 100 a month, **Medium** 100 to 500, **High** over 500. Each band says how to measure it.
- Scores are INFERRED judgement, 1 to 5. **Signal** = how strongly the filter shows a need now. **Data** = how reliably the signal can be pulled without manual research.

---

## Customer discovery analysis

Full detail: [case-studies.md](../../context/docs/case-studies.md).

| Pattern | What the 21 stories show |
|---|---|
| Industries | Education (Polk State, COTSA, PAB, NPTC, AASHE), nonprofits (Ruby's Place, YMCA, MMPA), small e-commerce and services (Beauty Bar, Yellow Dandelion, Watamu, Motive, I Made It!, We Insure, Career Consultant, Perpetual CPA, Inspirock), HR and admin (Kellton, Total Sec) |
| Sizes | From an owner and two daughters (Yellow Dandelion) to 1001 to 5000 staff (Kellton). Most are small teams |
| Roles that bought | Instructional technologist, state advisor, operations coordinator, founder, CEO, director, COO, IT manager, marketing analyst |
| Problems solved | Paper re-entry, Google Forms upload sign-in, payments with registration, email threads, team access |
| Before tools | Paper (5), Google Forms (5), email (4), SurveyMonkey, Wufoo, Microsoft Forms ruled out |

**Targeting challenge:** the ICP leads with schools, but 9 of 21 stories are small e-commerce and service businesses that take bookings, orders or payments. Arts and activity studios (PAB, Motive) sit between "school" and "SMB" and are an untapped lookalike (ideas 5 and 8). Nigeria is thin: one Nigerian story (Beauty Bar Group).

**Best customers for lookalikes:** Polk State (charter school), COTSA (student association), Pennsylvania Academy of Ballet (studio), AASHE (membership association), Beauty Bar Group (Nigerian online seller).

---

## Ranked campaign ideas

Ranked by Signal + Data (out of 10). Ties are broken by Data, then volume.

| # | Campaign | Targeting | Mother intent | Segment and persona | Signal and data source | Angle | Volume per month | Difficulty | Signal | Data | Total | Tier |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Google Forms admissions (W1)** | Focused | Companies using specific software | A-US schools; admissions officer or registrar | Google Forms on an admissions page asking for documents or fees. BuiltWith via Clay + crawl4ai scan. Pool: 28,913 live US Google Forms sites (BuiltWith, checked 2026-11-13) | Documents and fees arrive with the application, no Google sign-in for families | Medium (INFERRED; measure with the 500-domain sample) | Medium | 4 | 4 | 8 | **Tier 1**: spec approved, largest verified pool |
| 2 | **Google Forms registrations, nonprofits (W1-B)** | Focused | Companies using specific software | B nonprofits and associations; program or membership manager | Same build, nonprofit page keywords (registration, membership, training) | Registration, fee and documents in one form | Medium (INFERRED; same sample) | Easy (reuses W1) | 4 | 4 | 8 | **Tier 1**: keyword swap on an approved build |
| 3 | **Creative Ideas: three forms for your site** | Broad | Niche-specific play | A-US and B base list; champion | Base list from Apollo (industry + US). Claygent reads the site's admissions, events and registration pages | Three specific forms they could run, each tied to a Formplus template (Camp Registration, Event Registration, Membership Registration, Vendor Registration) | High (INFERRED; any domain list works) | Easy | 2 | 5 | 7 | **Tier 1**: no signal needed, fast build |
| 4 | **Lookalike of best customers** | Broad | Lookalike of customers | A-US, B, D; champion or founder | Clay lookalike seeded with Polk State, COTSA, PAB, AASHE, Ruby's Place | "A school (or studio, or association) like yours moved off paper" | High (INFERRED) | Easy | 2 | 5 | 7 | **Tier 1**: proof-led, fast; no timing, so pair with a signal later |
| 5 | **Dance and arts studios taking registrations (PAB lookalike)** | Niche | Lookalike of customers + website content mentions | A-US and D studios; owner or studio director | Google Maps category (dance school, ballet, music, martial arts) via Clay; site scan for PDF registration forms, Google Forms or "pay at the front desk" | Students register and pay for classes online on a schedule, like PAB | Medium (INFERRED; Google Maps counts per metro) | Medium | 4 | 3 | 7 | **Tier 1**: golden ICP, same-segment proof, untouched audience |
| 6 | **New admissions or registrar lead (New Hire)** | Focused | New leadership (past 90/180 days) | A-US and B; new director of admissions, registrar, program manager | Clay "Find People", title + start date under 90 days | A new lead inherits the intake process; first admissions cycle without paper | Low to Medium (INFERRED; check Apollo start-date counts) | Easy | 3 | 4 | 7 | **Tier 2**: reliable data, weaker proof (no Formplus story starts with a new hire) |
| 7 | **Hiring admissions, events or admin coordinators** | Focused | Hiring specific roles | A-US, B, D; hiring manager or the champion | Clay "Find Jobs at Company"; Indeed via Apify. Titles: admissions coordinator, registrar, events coordinator, office administrator | More applications or events coming; take intake off the new hire's plate | Medium (INFERRED; job volume) | Easy | 3 | 4 | 7 | **Tier 2**: high volume, weaker story; best as a W1 enrichment |
| 8 | **Recurring events on Google Forms or bank transfer (W2)** | Focused | Companies attending an event (adapted: hosting) | B and D; events or program manager, founder | Events pages, Eventbrite via Apify to find recurring organisers; keep events registered by Google Form, email or bank transfer | Next year's registration with the fee taken in the form | Medium (INFERRED) | Hard | 4 | 3 | 7 | **Tier 2**: dated reason and four proof stories, slower build |
| 9 | **Craft markets and fairs with juried vendor applications** | Niche | Website content mentions | D market organisers; founder or vendor coordinator | Claygent search for "vendor application" pages of craft markets and makers fairs; scan for Google Forms or emailed images | Vendor applications with image uploads into Drive and Sheets, like I Made It! Market | Low (INFERRED) | Medium | 4 | 3 | 7 | **Tier 2**: exact proof match, small list |
| 10 | **Nigerian school form sales (W3)** | Niche | Niche-specific play | A-NG schools; admissions officer or registrar | Nigerian education news (myschoolgist, myschoolnews), school sites, JAMB bulletins; form fee paid by bank transfer | Sell and receive admission forms online, fee included (Paystack, Flutterwave) | Low to Medium in season, near zero outside (INFERRED; 649 tertiary institutions on the NDPC notice is a floor) | Hard | 5 | 2 | 7 | **Tier 2**: best timing; no Nigerian school proof, Naira pricing unknown |
| 11 | **NGO M&E hiring (test cell)** | Focused | Hiring specific roles + competitor customers | NGO test cell; M&E officer | MyJobMag, HotNigerianJobs, Jobzilla ads naming KoboToolbox or ODK | Registrations, trainings and payments alongside their field tool | Low (INFERRED) | Easy | 2 | 4 | 6 | **Tier 3**: competitor-locked; test only |
| 12 | **African sellers on Paystack or Flutterwave taking DM orders** | Niche | Companies using specific software | E; founder or CEO | BuiltWith Paystack or Flutterwave (Flutterwave: 1,172 live sites, checked 2026-11-13) + scan for WhatsApp order links or "send proof of payment" | Orders and payment in one form, out of the DMs, like Beauty Bar Group | Low (pool is small) | Medium | 3 | 3 | 6 | **Tier 2**: real proof, small pool, USD-price objection |
| 13 | **Paper booking and order forms at service SMBs** | Focused | Website content mentions | D; owner | ICP-first list from Apollo (studios, gyms, retreats, small services), then scan for PDF forms, "print and", "email to book" | Bookings and orders online with payment, no printing | Medium (INFERRED) | Medium | 3 | 3 | 6 | **Tier 2**: needs a list first |
| 14 | **Associations with calls for proposals (AASHE lookalike)** | Niche | Website content mentions | B associations; education or conference manager | Claygent search for "call for proposals" pages; scan for email submission or Google Forms | Proposals, fees, agreements and certificates in one flow | Low (INFERRED) | Hard | 4 | 2 | 6 | **Tier 2**: strong proof match, hard sourcing |
| 15 | **Web agencies that build school and nonprofit sites (Creative, non-ICP)** | Focused | Niche-specific play | Agencies serving A and B; agency founder | Apollo: web design agencies, keywords "schools", "nonprofits", "WordPress"; Claygent reads their portfolio for school or nonprofit clients | Give their clients online applications and payments that embed on the site (Formplus has a WordPress embed) | Low to Medium (INFERRED) | Medium | 2 | 3 | 5 | **Tier 2**: untouched audience; partner terms not in research |
| 16 | **Boutique hotels and retreats (Watamu lookalike)** | Niche | Lookalike of customers | D hospitality, Kenya and beyond; founder or manager | Google Maps (boutique hotel, retreat) + site scan for PDF indemnity or registration forms | Guest pre-arrival registration and indemnity with e-signature, no check-in queue | Low (INFERRED) | Medium | 2 | 3 | 5 | **Tier 3**: one proof story |
| 17 | **Mid-size HR teams collecting employee documents** | Focused | Hiring specific roles | F; HR or people operations | Clay Find Jobs: HR coordinator, onboarding specialist, at 300 to 5,000 staff | Employee documents and claims by secure form, not email (Kellton, Total Sec) | Low (INFERRED) | Easy | 2 | 3 | 5 | **Tier 3**: Low-priority segment, no SOC 2 |
| 18 | **Instagram-first sellers with "DM to order"** | Niche | Niche-specific play | E; founder | Instagram bios with "DM to order" or WhatsApp links (Apify Instagram scraper; access not verified) | An order form in the bio link that takes payment | Low (INFERRED) | Hard | 3 | 2 | 5 | **Tier 3**: data source unverified |
| 19 | **Nigerian data protection compliance firms (Creative, non-ICP)** | Niche | Niche-specific play | Licensed DPCOs filing audit returns for clients; founder | DPCO list from the NDPC (public list not verified) | Clients collecting personal data on paper or ad-hoc forms | Low (INFERRED) | Hard | 2 | 2 | 4 | **Tier 3**: Formplus has no NDPA claim; list not found |

**Considered and killed (signal-matrix.md):** NDPC 649-institution list (not online), grant awards via IATI (no verified route), fundraising (customers aren't VC-backed), Google Forms add-on breakage (not detectable).

---

## Campaign overviews (copywriter handoff)

1. **Google Forms admissions (W1).** Hook: the school's own admissions page, a Google Form plus documents or fees. Personalisation: `school_name`, `process_type`, the cell from the spec. Proof: COTSA, Polk State, PAB by cell. CTA: confirm their setup ("Are families uploading documents to that form?"). Spec: [workflow-spec.md](google-forms-documents-payments/workflow-spec.md). Different from idea 3: signal-led, not idea-led.
2. **W1-B nonprofits.** Same six cells. Proof: AASHE for the documents cells, Ruby's Place for payments. Recipient: program, membership or events manager.
3. **Creative Ideas.** Hook: "I had three form ideas for {{company_name}}". Claygent reads the site and picks three processes it can see (admissions, camp, events, volunteer sign-up), each mapped to a named Formplus template. CTA: "Would any of these be useful?" No proof needed in email 1; proof in email 2.
4. **Lookalike.** Hook: a similar organisation's result in one line (Polk State "100% faster", COTSA "all digital"). Personalisation: which seed they resemble. CTA: "Is your intake set up the same way?" Pair with idea 1's signal when possible.
5. **Dance and arts studios.** Hook: how the studio takes new-student registration today (PDF, Google Form, front desk). Proof: PAB, "up and running with Formplus in a matter of just a day or two". CTA: "Do students sign up for classes online yet?" Trial path likely: small owner-run teams.
6. **New Hire.** Hook: their new role and the coming intake cycle. Personalisation: start date, previous school. Don't guess problems, only their situation. CTA: "Are you reviewing how applications come in this year?"
7. **Hiring coordinators.** Hook: the open role. Personalisation: job title, post date. Best stacked onto idea 1 as line 2 rather than run alone.
8. **Recurring events (W2).** Hook: last year's event and how registration ran. Proof: We Insure, COTSA, Motive, AASHE. CTA tied to the next date.
9. **Craft markets.** Hook: their vendor application page. Proof: I Made It! Market, "significantly reduced the time and effort required to manage applications."
10. **Nigerian school form sales (W3).** Hook: the announced form sale and payment method. Proof is thin (US schools only); run as a test after Naira pricing is answered.
11. **NGO M&E (test).** Don't pitch offline against KoboToolbox. Angle on what Kobo isn't used for: paid trainings and registrations.
12. **Paystack and Flutterwave sellers.** Hook: the payment gateway already on their site plus DM ordering. Proof: Beauty Bar Group "cut the steps involved in their sales funnel by 60%".
13. **Paper booking forms.** Hook: the PDF or "email to book" line on their site. Proof: Yellow Dandelion, Watamu.
14. **Calls for proposals.** Hook: their open call. Proof: AASHE "We used to create certificates manually".
15. **Web agencies (non-ICP).** Hook: their school or nonprofit clients by name, from their portfolio. Offer: forms they can embed for clients. Partner or referral terms are OPEN; confirm with Formplus before launch.
16. **Boutique retreats.** Hook: their PDF indemnity or booking form. Proof: Watamu, "Formplus already covers about 80% of what we need".
17. **HR documents.** Hook: the HR role. Proof: Total Sec "things that you can't send with unsecure email". Expect security questions; route to a call.
18. **Instagram sellers.** Hook: their "DM to order" bio. Verify the Instagram data source before building.
19. **DPCOs (non-ICP).** Only if Formplus confirms an NDPA position. Without it, the story doesn't hold.

---

## No-AI campaigns

**Google Forms sign-in (static, on the W1 list)**
- Why it works without AI: the list itself is the personalisation. Every recipient runs a Google Form on an admissions page.
- Core message: one question about whether families must sign in to Google to upload documents, one line of proof (COTSA), and a "Relevant?" CTA.

**Studios: online registration (static, on idea 5's list)**
- Why it works: every studio on the list takes registrations offline or on PDF.
- Core message: "Students can register and pay for classes online" plus PAB's day-or-two setup line.

---

## Front-end offer suggestions

1. **Ready template matched to their process.** Send the Formplus template that fits what's on their site (Camp Registration, Event Registration, Membership Registration, Vendor Registration, or an order template). It works on the free plan: "Start for free", "No credit card required". Fits the trial path in gtm-system.md step 9.
2. **"Your form, rebuilt" (INFERRED offer; needs Formplus approval).** We rebuild one of their current Google Forms or PDFs in Formplus and send the link. They see their own process working before deciding.
3. **Paper-to-online check.** A short note listing the PDF and Google Forms found on their admissions or registration pages (from the W1 scan), with the fix for each. Uses data the workflow already collects.

---

## What to build next

1. Idea 1 is specced. Run `/campaign-copy` once `context/messaging/facts.md` exists.
2. Idea 2 reuses the same build: add it as a second campaign.
3. Spec next: idea 5 (studios). It's the strongest new Tier 1 and brings same-segment proof (PAB) with a trial-path audience.
