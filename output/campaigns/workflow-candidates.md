# Formplus outbound workflow candidates

**Status: proposal, 2026-11-13.** Three candidates, one per priority signal in [context/icp/signal-matrix.md](../../context/icp/signal-matrix.md). Next step for the chosen one: `/build-workflow-spec`.

The research has no monthly volume figures. The only verified pool is BuiltWith's Google Forms list. Volume estimates are INFERRED, each with a way to measure it.

| | **W1: Google Forms or paper forms where documents or payments are requested** | **W2: Recurring event registration** | **W3: Nigerian school form sales** |
|---|---|---|---|
| Mother intent | Companies using specific software (Google Forms), stacked with a website-content signal (PDF forms, "email your documents", "send proof of payment") | Companies running an event (adapted from "attending an event") | Niche-specific play: admissions calendar |
| Segment | A-US schools and B nonprofits | B nonprofits and D service SMBs | A-NG: Nigerian tertiary and Lagos private secondary schools |
| Persona | Champion: admissions officer, registrar, program or membership manager | B: program or events manager. D: founder or owner (also the buyer) | Champion: admissions officer or registrar. Then principal or bursar (approver title unknown) |
| Proof story | Polk State and COTSA moved from Google Forms or paper; Ruby's Place left Google Forms when its payment add-on stopped | We Insure Kickoff, COTSA conference, Motive competitions, AASHE programs | Polk State (US). No Nigerian school customer yet |
| Data source | BuiltWith Google Forms list via Clay, then crawl4ai or Claygent scan of admissions and registration pages | Org events pages; Eventbrite via Apify only to find recurring organisers | Nigerian education news (myschoolgist, myschoolnews), school sites, JAMB bulletins |
| Volume | Pool: 28,913 live US sites use Google Forms (https://trends.builtwith.com/widgets/Google-Forms, checked 2026-11-13). Share that are schools or nonprofits asking for documents or payments: unknown. INFERRED: a few hundred qualified a month from the backlog, then a smaller monthly trickle | Unknown. INFERRED: lower than W1 after dropping events already on a ticketing checkout | Unknown and seasonal. 649 tertiary institutions got the NDPC notice (a floor). INFERRED: tens to low hundreds of announcements a month in season (about March to September), near zero outside it |
| Difficulty | Medium. BuiltWith is a standard Clay action; the page scan is the only custom step. US contact data is strong | High. Finding events not on a checkout means crawling many org sites; event dates add timing logic | High. Custom scraper plus AI extraction of school, fee and deadline. Nigerian contact data likely thin in Apollo (INFERRED). Naira pricing unknown; routes to calls |
| Reply path | Mostly call (schools), some trial (small nonprofits) | Mostly trial | Call |

## Recommendation: W1

- Only candidate with a verified pool.
- Strongest proof: Google Forms and paper were each the "before" tool in 5 of 21 customer stories ([customers.md](../../context/docs/research/customers.md)). The Google Forms sign-in-to-upload problem is checkable on the page.
- Lowest build risk. Reusable for B and D with keyword swaps; its page scan is the base for W2.
- Rich US data for enrichment and email finding.

Start on A-US schools (Polk State, COTSA proof). Replies there mostly go to a call, so feedback is slower. Running B nonprofits from the same build as a second campaign gives faster answers through the trial path.

**Measure before committing:** pull 500 domains from the BuiltWith US list, run the page scan, and count schools or nonprofits asking for documents or payments.

**Next test: W3.** It has the best timing, but needs a Nigerian proof point and an answer on Naira pricing first.
