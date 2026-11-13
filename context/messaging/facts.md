# Formplus: authorized copy facts

> The ONLY source of names, numbers and claims for prospect-facing copy (`/campaign-copy` FACTS GATE). Anything not listed here renders as `{{placeholder}}`. Built from `context/docs/research/` (checked 2026-11-13) on the owner's instruction. Practice project: the sender does not work for Formplus.

**Last updated:** 2026-11-13 by Emmy (owner), drafted by Claude. **Status: DRAFT, pending owner approval.**

---

## Sender identity

| Field | Value |
|---|---|
| Sender name | `{{sender_name}}` |
| Title | `{{sender_title}}` |
| Company | `{{sender_company}}` |
| Signature format | `{{sender_name}}` / `{{sender_title}}`, `{{sender_company}}` |
| Sender persona notes | First person singular. Practice project: placeholders stay as placeholders; never fill in a real Formplus employee |

## What we do (locked value prop)

Lead-in verbatim; the tail may adapt per route.

- **Variant A:** "Formplus is an online form builder that takes the application, the documents and the fee in one form."
- **Variant B:** "Formplus lets schools take applications, documents and fees in one online form."

Product one-liner (context, not copy): self-serve online form builder for applications, registrations, payments and orders (company.md).

## Approved claims (use these exact phrasings)

| Claim | Approved phrasing | Source | Approved by / date |
|---|---|---|---|
| Google Forms upload sign-in | "Google Forms asks people to sign in to a Google account before they can upload a file." | competitors.md (https://formswrite.com/blog/why-can-t-i-upload-a-file-to-google-forms, https://contentsnare.com/google-forms-file-uploads/) | Pending |
| Where files go | "Uploaded files go to the school's own Google Drive, Dropbox or OneDrive." | company.md (https://www.formpl.us/compare-plans) | Pending |
| Payment providers | "Fees are paid in the form through Stripe or PayPal." | company.md (https://www.formpl.us/payments) | Pending |
| No Formplus payment fee | "Formplus doesn't add a fee on top of the payment provider." Source wording: "We do not charge a fee to integrate a form with any of our payment partners." | company.md, voice.md (https://www.formpl.us/payment-forms) | Pending |
| Money goes to the school | "Payments go straight to the school, not to Formplus." Source wording: "the money received goes directly to the Form Owner or User, and not FormPlus." | company.md (https://www.formpl.us/terms-and-privacy) | Pending |
| Embed on the website | "The form can sit on the school's own website." Source wording: "Create booking forms with payments to embed in your website pages." | voice.md (https://www.formpl.us/booking-forms) | Pending |
| Security (replies only, not cold copy) | "256-bit SSL on every form; data encrypted at rest with AES-256; GDPR compliant." | company.md (https://www.formpl.us/pricing) | Pending |

**Formatting rules for proof**
- Write customer names exactly as in the table below. No domains.
- Quote customers only with the exact words listed. No truncated quotes in copy.
- US spelling for A-US campaigns ("enrollment").

## Authorized social-proof names

Only these five may appear in prospect-facing copy.

| Name (write exactly) | What it proves | Approved quote or result (exact) | Matches | Caveat |
|---|---|---|---|---|
| Polk State College Charter Schools | Paper applications moved online | "We were manually entering students into a spreadsheet once they completed a paper application." (Virginia Richard, Instructional Technologist). Result: "It is also 100% faster to obtain enrollment applications." Fragment: "decreased our time and cost ten times over" | US charter schools; documents + paper cells | Also tried Google Forms before Formplus. The full time-and-cost quote is truncated in research: use the fragment only |
| Colorado Technology Student Association (COTSA) | Documents and entries collected online, off paper | Fragment: "made collection of URLs and forms WAY easier". Results: "all digital"; entries from "more than 2,000 participants" | US student association; documents cells | A student association, not a school. The full quote ends in "!", banned in copy: use the fragment only. Before: Google Forms ("clunky") |
| Pennsylvania Academy of Ballet | Students register and pay online | "We were able to get up and running with Formplus in a matter of just a day or two." (Elizabeth). Payments via PayPal | US arts school; payment cells | Name only, no surname or title. Don't use the "empowered" quote (banned word family) |
| Ruby's Place | Left Google Forms when its payment add-on was discontinued | "It was the easiest to use, it provided what we needed and actually simplified the process for us" (Debi Himovitz, COO) | Nonprofit; payment support line (A-US), main payment proof (B) | Not a school: supporting line only in A-US copy |
| AASHE | Program submissions and certificates online | "Formplus gives us structure without limiting flexibility" (Daita Serghi, PhD, Senior Education Manager); "We used to create certificates manually" | Higher-ed membership nonprofit; segment B documents cells | Segment B only. Never use the homepage testimonial version (name and title don't match the story) |

Everyone else (Beauty Bar Group, Watamu Treehouse, homepage logos such as Notre Dame, Red Bull, Grab) stays out of copy until added here.

## Numbers to keep fuzzy (never quote)

- Formplus user, form or response counts ("1429+", "thousands", "70K+": they conflict).
- Template counts ("100+", "200+", "1000+": they conflict).
- Prices and discounts in cold copy.
- Polk State's student count, COTSA's member count.

## Proof caveats

- Polk State proves paper-to-online for applications with uploads. It doesn't prove payments; don't use it for payment-only cells.
- COTSA proves documents and entries. It doesn't prove payments.
- PAB proves registration and payment. It doesn't prove document collection.
- Ruby's Place proves leaving Google Forms over payments. It's not a school.
- No customer proves offline collection.

## Banned

### Banned angles
- Price, discount or plan framing in cold copy.
- Offline forms (labelled "(beta)", no customer proof).
- Compliance claims beyond the security line above: no SOC 2, HIPAA, ISO, NDPA.
- AI features.
- Claiming the prospect's Google Form has a file-upload question (not detected).
- Anything that implies the school's staff are slow, behind or failing (insult test).
- Competitor prices or user counts.

### Banned words and phrasing (company-specific)
Global list: `knowledge-base/playbooks/copy-bans.yaml`. Also:
- No em dashes (CLAUDE.md).
- "powerful", "superb", "paperless office" (Formplus site language; prefer the customer's result).
- "seamless" is already banned globally.

### Never in copy, under any circumstance
- Segment codes (A-US, B), cell numbers, signal names (T1, R1), `admissions_page_url` pasted as a link.

## Voice notes

- Register: plain, helpful, peer to an admissions or registrar lead.
- Hedges about the prospect: "my guess is", "could be off", "not sure if".
- Subjects: lowercase, 3 to 5 words, no variables, same subject across the thread.

## CTA ladder

- **Primary (E1):** a question that confirms their setup, e.g. "Is that how it works on your side?" or "Relevant?"
- **Secondary (E2):** offer to send an example, e.g. "Want me to send an example?"
- **Final (E3):** right-person check.
- Never: "book a call", calendar links, "free".

## Internal only (never in prospect copy)

- Pricing, plan fit, discounts, review counts, competitor weaknesses, the trial-or-call rule, segment and cell logic, all research marked INFERRED.
