# Formplus ICP

Built only from `context/docs/research/` (checked 2026-11-13). Every row cites its source file. INFERRED = our reading of the research, not a stated fact. Gaps are listed as open questions.

Source key: [CO](../docs/research/company.md) company, [CU](../docs/research/customers.md) customers, [CP](../docs/research/competitors.md) competitors, [MK](../docs/research/market.md) market, [SG](../docs/research/signals.md) signals, [VO](../docs/research/voice.md) voice.

## Plan reference [CO: Pricing model]

| Plan | $/mo (yearly) | Submissions/mo | Members | Teams | Unlocks that matter for fit |
|---|---|---|---|---|---|
| Free | 0 | 50 | 4 | 1 | 3 forms; payments, analytics, form lookup locked |
| Starter | 25 (20) | 1,000 | 10 | 3 | Payments, analytics, form lookup, Form2Doc |
| Professional | 45 (36) | 15,000 | 15 | 5 | Stripe subscriptions, white-label, sub-domain, quiz timer, 1-month audit trail |
| Platinum | 85 (68) | 50,000 | 20 | 7 | 2-month audit trail |
| Enterprise | Contact | 100,000 | 20+ | unlimited | 6-month audit trail, custom features |

Schools and nonprofits get 10% off [CO: Pricing model]. All "Likely plan" calls below are INFERRED from these limits.

## Layer 1: Firmographic, by segment

| Segment | Evidence (named customers) | Stated sizes | Regions seen | Likely plan |
|---|---|---|---|---|
| **A. Schools and education programs** | Polk State College Charter Schools, COTSA, Pennsylvania Academy of Ballet, NPTC, University of Notre Dame (logo) [CU] | Polk: "over 550 students enrolling"; COTSA: "nearly 3,000 members in more than 75 chapters", "more than 2,000 participants"; NPTC: team of 4 [CU] | US (FL, CO, PA). Nigeria: 649 tertiary institutions got an NDPC compliance notice on 19 Feb 2026 [MK] | Starter (550 applications fit 1,000/mo). Professional if a peak month passes 1,000 (COTSA-size) |
| **B. Nonprofits and membership bodies** | AASHE, YMCA (Latin America and Caribbean), Ruby's Place, MMPA Task Force, PactWorld (testimonial), Adra (logo) [CU] | AASHE: "over 900 colleges and universities that are members"; YMCA: "over 700,000 volunteers and 96,000 professionals" (global body, not the buying unit) [CU] | US, Latin America and Caribbean, global [CU] | Starter for paid registrations. Professional if recurring dues need Stripe subscriptions |
| **C. Commercial mobile reporting teams** (businesses whose staff file reports from phones in the field, online) | Performance Equipment: mechanics' job reports, sales and rental staff logging calls on mobile. B.E Naturale: brand ambassadors filing post-event reports with photos and e-signatures [CU] | Performance Equipment: "nearly 10,000 entries via forms", "dozens of forms"; B.E Naturale: "at least a hundred ambassadors" a month, "25,000+ in-store demo events" [CU] | US (Erie, CO; MN) [CU] | Starter to Professional, by monthly volume (10,000 entries over several years fits Starter; INFERRED, period not stated) |
| **D. Service SMBs taking bookings, orders and payments** | Motive School of Movement, Watamu Treehouse, I Made It! Market, We Insure Group, Yellow Dandelion, Career Consultant, Perpetual CPA, Inspirock [CU] | Watamu: "grown from just 3 employees to 45", "about 30 active forms"; Yellow Dandelion: owner and two daughters, "an average of 100 orders in a week"; Motive: "hundreds of competitors" [CU] | US, UK, Kenya [CU] | Starter (payments unlocked). Professional for white-label or a custom sub-domain |
| **E. African SMEs needing Paystack or Flutterwave** | Beauty Bar Group (Nigeria), Watamu Treehouse (Kenya) [CU] | Beauty Bar: "thousands of responses" in under 3 months [CU]. Other sizes: Not found | Nigeria, Kenya [CU]. Paystack page: "perfect for Africans who want to receive payments from anyone, anywhere in the world" [VO] | Starter minimum: the Paystack integration requires "upgrading to a paid plan" [CO] |
| **F. HR and admin teams in mid-size companies** | Kellton Tech (reimbursements), Total Sec Oy (employee documents), MCAM NorthWest (appraisals, testimonial) [CU] | Kellton: "between 1001–5000 people"; Total Sec: "network of ~ 300 employees" [CU] | India, Finland; MCAM region Not stated [CU] | Starter to Professional. Member caps (10 to 15) may limit this segment |

Segment sizes (how many organisations exist per segment and region): Not found in research. Open question.

What segment C buys (evidence): staff collecting reports "from multiple people from anywhere" (Noah Kriska, IT Manager), photo uploads, e-signatures, mobile entry. Neither story mentions offline collection [CU]. The trigger was paper that "could get lost, crumpled, or get stained with oil, grease and dirt" [CU]. Do not pitch these teams on offline.

### Test cell, not a target: NGO M&E field data teams

Not a segment until a test proves it. The evidence is split:

| For | Against |
|---|---|
| Formplus has offline forms; even Jotform says Formplus suits "teams that need offline access" [CP] | Offline is labelled "(beta)" on the homepage; it launched "in beta" in 2017 [CO] |
| PactWorld (international NGO) gives a homepage testimonial; AASHE's homepage testimonial is about offline field teams [CU] | AASHE's own story never mentions offline, and its name and title don't match the testimonial. No story shows offline field collection [CU] |
| Nigerian NGOs are hiring M&E officers and data collectors in 2026 [SG] | Those ads ask for KoboToolbox or ODK by name [SG]. KoboToolbox is free "for over 95% of our users" [CP] |
| Aid cuts may push NGOs to cheaper tools (INFERRED) [MK] | The same cuts shrink NGO budgets: 84% of IFES respondents lost funding in 2025 [MK] |

To prove it before scaling: one NGO running offline collection on Formplus, with a named result.

## Layer 2: Technographic

| What they use now | Evidence | Segments |
|---|---|---|
| Paper forms and manual spreadsheet entry | Polk, Beauty Bar, Performance Equipment, COTSA, Watamu [CU] | A, C, D, E |
| Google Forms (named "before" tool in 5 of 21 stories) | Career Consultant, Total Sec, Polk, COTSA, Ruby's Place [CU] [CP] | A, B, D, F |
| Email back-and-forth | Kellton, Inspirock, MMPA, AASHE [CU] | B, D, F |
| SurveyMonkey, Wufoo | NPTC, COTSA [CU] | A |
| Microsoft Forms (ruled out for external partners) | We Insure [CU] | D |
| WhatsApp, Instagram, phone orders | Watamu, Beauty Bar [CU] | D, E |
| KoboToolbox, ODK, SurveyCTO, CommCare | Nigerian NGO M&E job ads [SG] | NGO test cell |
| Stack they connect to | Google Drive, Sheets, Dropbox, OneDrive, WordPress, Zapier, Trello; PayPal, Stripe, Paystack, Flutterwave [CO] [CU] | All |

## Layer 3: Intent signals [SG]

| Signal | Why it matters (customer evidence) | Segments |
|---|---|---|
| Paper or downloadable PDF forms on the website (INFERRED signal) | Polk: "We were manually entering students into a spreadsheet once they completed a paper application." [CU] | A, C, D |
| Google Forms embedded where uploads or payments are needed | File uploads need a Google sign-in that cannot be turned off [CP]; Total Sec and Ruby's Place switched for this [CU] | A, B, D, F |
| Admission or form-sale window opening | Nigerian post-UTME forms about July to August; Lagos secondary form sales, often paid by bank transfer [MK] | A |
| Named in an NDPC notice (649 tertiary institutions, Feb 2026; 1,300+ organisations, Aug 2025) | Regulator deadlines of 21 days [MK] | A, B |
| Annual event, conference or competition coming up | We Insure Kickoff, COTSA conference, Motive competitions [CU] | A, B, D |
| Hiring M&E, data collector, admin or operations roles | 2026 Nigerian NGO ads naming KoboToolbox or ODK [SG] | NGO test cell (current tool is named, so expect a competitive switch) |
| Orders taken by DM or bank transfer with "send proof of payment" (INFERRED signal) | Beauty Bar moved from phone and paper [CU] | E |
| Fast growth or new locations | Watamu 3 to 45 staff; We Insure "expanded its footprint across multiple states" [CU] | D |
| Grant reporting cycle (Global Fund PU/DR, FCDO quarterly IATI) | Sub-recipients send program data up on a fixed cycle [MK] | B, NGO test cell |

## Layer 4: Persona (detail in [personas.md](personas.md))

| Role | Typical titles in research | Segment pattern |
|---|---|---|
| Champion | Instructional Technologist, Operations Coordinator, Senior Education Manager, Marketing Analyst, IT Manager, Data & Program Support [CU] | A, B, F, and larger D |
| Economic buyer | Founder, CEO, Director, COO, Managing Director, State Advisor [CU] | Same person as the champion in small D and E teams |
| Influencer | IT Manager, M&E officer, finance or accounting staff, team members who approve applications [CU] [SG] | A, B, C, F |

## Layer 5: Engagement readiness

| Stage | Evidence that they are ready | Source |
|---|---|---|
| Hot | A dated trigger is live: admission window, event registration, NDPC notice, or a tool that just broke (Ruby's Place's payment add-on was discontinued) | [MK] [CU] |
| Warm | Paper, email or Google Forms process visible, with no dated trigger | [CU] [SG] |
| Cold | Already on Microsoft 365 or KoboToolbox with no complaint | [CP] |

Readiness facts:
- Self-serve, free to start, "No credit card required" [CO].
- Fast to start: PAB was "up and running with Formplus in a matter of just a day or two"; Career Consultant wanted to "receive CVs the same day which we were able to do" [CU].
- Formplus publishes a "Convince your team (and Boss)" page, so some buyers need sign-off [VO].

## Not a fit

| Who | Why (research) |
|---|---|
| Consumers and one-off personal users | Free plan is "Simple forms for basic needs" with 3 forms and 50 submissions [CO]. Tally offers unlimited free forms and submissions [CP]. Not one customer story is a personal user [CU] |
| Healthcare teams handling patient data | HIPAA: "Not found on any page that loaded" [CO]. No healthcare patient-data story. A dental logo (Commonwealth Endodontics) and NPTC (psychology training, not patient records) exist, but without a HIPAA claim [CU] |
| Enterprises needing SOC 2, ISO 27001, a DPA, a sub-processor list or a set data-hosting region | All Not found [CO]. Typeform lists SOC 2 [CP] |
| Enterprises needing more than 20 members, long audit logs or an API | Platinum caps at 20 members; the longest audit trail is 6 months on Enterprise; one listing says "does not provide an API" (unverified) [CO] |
| Teams needing proven offline collection at large scale | Homepage labels offline "(beta)"; it launched "in beta" in 2017; no customer story shows offline field collection [CO] [CU]. KoboToolbox is free "for over 95% of our users" and widely required in Nigerian NGO jobs [CP] [SG] |
| Microsoft 365 organisations running internal-only surveys | Forms is included in Microsoft 365 business plans, up to 50,000 responses per form [CP] |
| Buyers who mainly want design-led marketing forms | Reviewers say "Design and personalization are not good enought" [CO]. Typeform leads on design and AI automation [CP] |

## Open questions

- How many organisations are in each segment and region? Not in research.
- Is there Naira pricing or local billing for segment E? Not found [CO].
- Does Formplus comply with Nigeria's data protection law (NDPA)? Its privacy policy covers GDPR only [CO]. This matters for segment A in Nigeria.
- Is SSO available? Not researched.
- How does offline actually work (app or browser), and is it still beta? [CO]
- Which plans do current customers actually pay for? Not in research.
- Is there any NGO customer using offline forms at scale? None found in research. This decides the NGO test cell.
- Are there more segment C customers than the two US stories? Not in research.
