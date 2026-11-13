# Formplus: company research

Raw research, not conclusions. All sources checked 2026-11-13 unless stated. Anything not stated by a source is marked INFERRED. Quotes are verbatim; where a fetch tool could only return a paraphrase, it says "paraphrase".

## What they sell

- Online and offline form builder. Homepage hero: "Let forms do the work" / "Switch to a paperless office with functional online and offline (beta) forms". Source: https://www.formpl.us (checked 2026-11-13)
- Homepage product cards: "Online Survey maker", "Create Online Forms" (applications, payments, registration), "PDF Builder" (legal contracts, quizzes, questionnaires). Source: https://www.formpl.us
- New product: Form2Doc. Banner: "Form2Doc is here: generate polished, branded documents from every form submission, automatically." Source: https://www.formpl.us. The feature page https://www.formpl.us/e/features/document-merge renders only with JavaScript and returned no content.
- Solution pages (all loaded 2026-11-13): survey forms, data collection, registration, application, payment, booking, order, offline forms, plus e-signature (https://www.formpl.us/e-signature-forms) and quiz maker (https://www.formpl.us/quiz-maker). Details in [voice.md](voice.md).
- Note: offline forms are labelled "(beta)" on the homepage hero but are presented as a full feature on https://www.formpl.us/offline-forms.

### Feature claims (from pages that loaded)

- "20+ field types and hundreds of form templates". Source: https://www.formpl.us
- Template counts differ by page: "100+" (https://www.formpl.us/application-forms), "200+" (https://www.formpl.us/order-forms), "over 1000 templates" (pricing FAQ, https://www.formpl.us/pricing).
- Payments: PayPal, Stripe, Flutterwave, Paystack, Stripe Subscriptions. Source: https://www.formpl.us/compare-plans. Payment forms page claims "over 105 currencies" (paraphrase) and "We do not charge a fee to integrate a form with any of our payment partners." Source: https://www.formpl.us/payment-forms
- Cloud storage: Google Drive, OneDrive, Dropbox, Formplus storage, Google Sheets. Source: https://www.formpl.us/compare-plans. Note: the pricing FAQ names only "Google Drive, Google Sheets and Dropbox", so pages disagree on OneDrive.
- Homepage integration grid (32 names): Google Drive, Google Sheets, Dropbox, Trello, Slack, Salesforce, Airtable, Mailchimp, Discord, Asana, FreshDesk, Wordpress, Basecamp, SMS by Zapier, Google Contacts, Breezy HR, Stripe, MySQL, Flutterwave, Paystack, Paypal, Active Campaign, Google Calendar, Gmail, Twilio, Twitter, Acuity Scheduling, Zendesk, Webhooks, Keap, Podio, Google Docs. Source: https://www.formpl.us. Many of these are likely via Zapier (INFERRED from "SMS by Zapier" and the Zapier help article in nav).
- Pricing page says all plans get "3000+ integrations". Source: https://www.formpl.us/pricing. INFERRED: this counts Zapier-connected apps.
- Security and compliance: pricing FAQ says 256-bit SSL on all forms, data "encrypted at rest using AES-256", "Formplus is also GDPR Compliant", "Our payment processors are PCI compliant". Source: https://www.formpl.us/pricing. Nav lists "GDPR Compliant" and "PCI Complaint" (typo on site). Source: https://www.formpl.us
- Privacy policy: "We use encryption techniques to protect the transmission of data between your device and our servers." (section 7(a)); "This Privacy Notice outlines how we collect, use, and protect your personal data in accordance with the General Data Protection Regulation (“GDPR”)..."; "We may transfer your personal data to organizations in other countries" (section 9). Uses Microsoft Clarity and Microsoft Advertising (section 2(e)). Source: https://www.formpl.us/terms-and-privacy (checked 2026-11-13). No DPA, sub-processor list or NDPA mention found.
- Offline in the EULA (section 12.1): "Formplus forms are intended to work seamlessly offline and online. Once the User comes online, the offline responses are synced with the online response." Source: https://www.formpl.us/terms-and-privacy. Whether offline uses an app or the browser: Not found.
- Payments: "they integrate with the largest online payment processors in the industry (PayPal, Stripe, Flutterwave and Paystack)." and "Formplus does not have extra charges for third-party integrations like Google Drive, Dropbox, Stripe, PayPal, Flutterwave and Paystack." Source: https://www.formpl.us/payments. Terms 6.1: "the money received goes directly to the Form Owner or User, and not FormPlus." Source: https://www.formpl.us/terms-and-privacy
- Paystack page: "perfect for Africans who want to receive payments from anyone, anywhere in the world"; requires "upgrading to a paid plan". Source: https://www.formpl.us/payments/paystack. Flutterwave page title: "Accept Online Payments anywhere in the World, including Africa." Source: https://www.formpl.us/payments/flutterwave (both checked 2026-11-13).
- Cancellation: Terms 16.2(i) "Revoking access to the Formplus application by cancelling a subscription from the user Account." Refund policy: Not found (only "without refund" for prohibited use, 7.2).
- Help centre https://help.formpl.us renders only with JavaScript (checked 2026-11-13); its articles could not be read.
- SOC 2, HIPAA, ISO 27001: Not found on any page that loaded.
- Data hosting location: Not found on formpl.us. A third-party comparison lists Formplus data residency as US: https://www.spotsaas.com/compare/formplus-vs-typeform (unverified).
- Feature hub https://www.formpl.us/e/features and every /e/features/* page tried (gdpr-compliance, document-merge) render only via JavaScript and returned only a cookie banner. Content of the Security, Teams, Analytics and other feature subpages: Not found.

## Pricing model

Freemium SaaS, per-account subscription (not per seat), USD. Sources: https://www.formpl.us/pricing and https://www.formpl.us/compare-plans (checked 2026-11-13).

Pricing headline: "Superb data collection for small and large teams". Header: "Start for free", "No credit card required", "Save 20% on all yearly plans."

| Plan | Tagline | Monthly | Yearly (per month) | Submissions/mo | Storage | Members | Teams | Forms | Audit trail |
|---|---|---|---|---|---|---|---|---|---|
| Free | "Simple forms for basic needs" | $0 | $0 | 50 | 100MB | 4 | 1 | 3 | none |
| Starter ("Most popular") | "Functional Forms for Businesses" | $25 | $20 | 1,000 | 20GB | 10 | 3 | Unlimited | none |
| Professional | "Powerful Forms for Brands" | $45 | $36 | 15,000 | 50GB | 15 | 5 | Unlimited | 1 month |
| Platinum | "Advanced Forms for Enterprises" | $85 | $68 | 50,000 | 100GB | 20 | 7 | Unlimited | 2 months |
| Enterprise | n/a | "Contact Us" | "Contact Us" | 100,000 | 200GB | 20+ | unlimited | Unlimited | 6 months |

- Monthly vs yearly mapping is INFERRED from the 20% arithmetic (25 to 20, 45 to 36, 85 to 68); the page text does not label the numbers.
- Form views: Starter 20,000/month; Professional and above unlimited. Free plan is listed as both "1000" and "50 Views/month" on different pages; unclear.
- Inventory products: 2 / 10 / 50 / 200 / 500. Address autocomplete searches/month: 10 / 200 / 500 / 1,000 / 2,000. Source: https://www.formpl.us/compare-plans
- Locked on Free (padlock icons): form lookup, analytics and reports, collect payments, Stripe subscriptions, white-label, sub-domain and custom links, quiz timer. Locked on Starter: Stripe subscriptions, white-label, sub-domain, quiz timer. Source: https://www.formpl.us/pricing. Note the FAQ says "Yes! After you sign up, you have access to all features on the free plan", which conflicts with the padlocks.
- Discounts: 20% for yearly billing. "Nonprofits and educational institutions" get 10% off any plan via support@formpl.us. Source: https://www.formpl.us/pricing. The registration page says 10% plus an extra 20% on annual. Source: https://www.formpl.us/registration-forms
- Enterprise: "Want to collect more responses or implement custom-built features on your account?" with a contact form https://www.formpl.us/form/31606002. Source: https://www.formpl.us/pricing
- Free trial of paid plans: Not found as a stated policy. The compare-plans "Start For Free" button links to /subscribe/platinum_subscription?trial=platinum_subscription, which suggests a Platinum trial on sign-up (INFERRED).
- File upload size limit: Not found.
- Non-USD or local (Naira) pricing: Not found.

## Scale claims (company-stated)

- Homepage counters: "1429+" Trusted users, "13913430+" Received responses, "124397+" Forms created. Source: https://www.formpl.us (checked 2026-11-13). Note: "1429+ trusted users" is far below older third-party claims; it may count paying accounts only (INFERRED, unverified).
- "Thousands of organizations trust Formplus to manage their data collection." Source: https://www.formpl.us/convince-your-team
- 2018 metrics (third-party article, as of 2018, not current): "70K+ users," "14 million forms filled and counting," "~900 paying users," "89% user retention," "12 months – average user lifetime," "Largest market by revenue (60%) is the US," forms used "in 70 countries worldwide." Source: https://9jagistland.blogspot.com/2018/11/the-formplus-story-from-cchub-to.html (fetched 2026-11-13). Note: the 2026 homepage shows "13913430+" responses, below the 2018 "14 million forms filled", so the counters may measure different things or be stale (INFERRED).
- 2019 secondary-source claim that the forms "power data collection in 70 countries worldwide–including two of the biggest ride-hailing companies in the world." Source: search snippet via https://innovation-village.com/straight-out-of-nigeria-how-formplus-is-helping-global-companies-collect-and-manage-data-with-digital-forms (article dated 2019-01-15; full text not fetched). INFERRED: the ride-hailing companies are Careem and GO-JEK/Grab, whose logos appear on formpl.us.

## Markets

- Customer case studies are mostly US, plus UK, Finland, India, Nigeria, Kenya and Latin America. See [customers.md](customers.md).
- Local African payment gateways (Flutterwave, Paystack) sit next to Stripe and PayPal. Source: https://www.formpl.us/compare-plans. INFERRED: built with African buyers in mind while selling globally.
- Official market split by country or revenue: Not found.

## Origin and leadership

- Origin: Lagos, Nigeria. Started at CcHub in Yaba, Lagos. Sources: https://9jagistland.blogspot.com/2018/11/the-formplus-story-from-cchub-to.html (2018 blog, not fetched in full; via search snippet) and https://businessday.ng/?p=304477 (via search snippet: "founded by Busayo Longe and launched in 2014 at the Co-Creation Centre (CcHUB)").
- Origin story per the 2018 article, fetched in full 2026-11-13 (https://9jagistland.blogspot.com/2018/11/the-formplus-story-from-cchub-to.html; it says it reposts a TechCabal piece dated 2018-11-23, original not fetched):
  - "It all began in 2012 when five UNILAG undergraduates participated in the Google Apps Developer Challenge." They "won the first place prize of $20K."
  - In 2013 three co-founders "decided to take their share of the Google prize money and walk."
  - CEO Busayo Longe ran operations, accounting, marketing and sales; Bolu Ogunsola was responsible for "everything software". Ogunsola moved to Poland for Codility and "decided to remain in Europe and left the business to Longe."
  - "Eventually, Longe moved back to Nigeria in mid-2017."
  - "2017 launched offline forms in beta", demoed at TechCrunch Battlefield 2017.
  - The "$5 Billion Dollar Company" in the headline is not named in the body. The body names Go-Jek, Careem and Grab Taxi as customers.
- Founding year: conflicting. 2012 (competition entry) vs 2014 (BusinessDay launch). Exact incorporation date: Not found.
- CEO: Busayo (Olubusayo) Longe per 2018 profile and several data aggregators (e.g. https://pitchbook.com/profiles/company/279391-78, https://getlatka.com/companies/formplus via search snippets). Current confirmation from Formplus itself: Not found. No About or Team page on formpl.us.
- CB Insights lists "Michael Adeyeri" as founder (https://www.cbinsights.com/company/formplus via search snippet). No corroboration found; likely a data error (INFERRED).
- Other leadership, current CTO, board: Not found.
- Named staff in 2019: Jadesola Odujole, Communications Team Lead. Source: Innovation Village 2019 article (search snippet).

## HQ and entities

- Legal entity (company's own terms, effective 4 March 2024): "Formplus Inc is incorporated in the United States at 251 Little Falls Drive, Wilmington, New Castle County, Delaware 19808-1674." Source: https://www.formpl.us/terms-and-privacy (checked 2026-11-13). The same EULA (section 15.1) also refers to "Formplus Limited", which conflicts.
- Privacy policy contact: "Address: 2138 South Indiana Avenue, Chicago. 60616 U.S" / "Phone Number: +1 865 264 0403" / "E-mail: privacy@formpl.us". Source: https://www.formpl.us/terms-and-privacy (checked 2026-11-13). INFERRED: the Delaware address is a registered-agent address and Chicago is a mailing address.
- Governing law: US (Delaware), EULA section 18.1. Source: https://www.formpl.us/terms-and-privacy
- Lagos, NG per https://www.startuplist.africa/startups/formplus (search snippet). 2018 article: started at CcHub, Yaba, then "to iDEA Hub briefly, from CcHub," then "moved to Surulere." Source: https://9jagistland.blogspot.com/2018/11/the-formplus-story-from-cchub-to.html (fetched 2026-11-13).
- Leeds, UK: the 2018 article says Longe ran the company from the UK, where the University of Leeds helped set up an office through its Spark Accelerator. Source: same 2018 article. A profile lists "Form+ Inc." at a Clarendon Road address in Leeds with website formpl.us (https://cuspera.com/products/formplus-x-7722, search snippet). Crunchbase also lists Leeds (https://www.crunchbase.com/organization/form-f840). Trustpilot has a "Form+" profile at a Leeds address with 0 reviews (https://www.trustpilot.com/review/formpl.us, fetched 2026-11-13).
- Earlier name: "Form+". A 2017 press release is titled "Google Apps Developer Challenge Winner, Form+, Provides Unique Survey and Questionnaire Functionalities" (https://www.prnewswire.co.uk/news-releases/google-apps-developer-challenge-winner-form-provides-unique-survey-and-questionnaire-functionalities-633610153.html, search snippet). INFERRED: Form+ and Formplus are the same product; the Capterra, GetApp and Software Advice "Form+" listings are probably Formplus.
- Current operating HQ: Not found. No address in the formpl.us footer.

## Funding

- Total raised about $100K over 3 rounds per CB Insights and PitchBook (search snippets: https://www.cbinsights.com/company/formplus/financials, https://pitchbook.com/profiles/company/279391-78).
- Kepple Africa Ventures in a Seed VC round dated 2020-12-17 per CB Insights (search snippet). Amount: Not found. No press release found.
- Google for Startups listed as a funder on Crunchbase, probably non-equity support (search snippet).
- Google Apps Developer Challenge prize of $20K (2018 blog, unverified).
- No evidence of a priced Series A or later round. Not found.

## Team size and revenue (third-party estimates only)

- About 15 employees and "$1.4M revenue" per Latka title (https://getlatka.com/companies/formplus, search snippet; Latka figures are often self-reported or estimated, unverified).
- 10 employees per PitchBook and Tracxn (search snippets).
- ZoomInfo entries range from under 25 to 11-50 (search snippet, https://www.zoominfo.com/c/formplus/466541391).
- 2018: "The team has grown to 13 members." Source: https://9jagistland.blogspot.com/2018/11/the-formplus-story-from-cchub-to.html (fetched 2026-11-13).
- Company-confirmed current headcount or revenue: Not found.
- No 2025 or 2026 interview with, or LinkedIn post by, Busayo Longe found in search (checked 2026-11-13).

## Reviews (G2 and others)

- G2 product, Jotform comparison and Typeform comparison pages all returned HTTP 403 to fetch. Capterra also 403. Direct data: Not found.
- Via search snippets only: G2 shows about 12 to 13 reviews, average about 4.3/5 (https://www.g2.com/products/formplus/reviews). Capterra "Form+" listing 4.5/5 from 38 ratings (https://www.capterra.com/p/162563/Form/reviews/). SpotSaaS 4.5 from 46 ratings (https://www.spotsaas.com/product/formplus/reviews). Unverified.
- Pros in snippets: ease of use ("Creating forms is now easy"), helpful chat support, templates, sharing options. Cons: limited design options, "Commercial policy, subscription terms", limited functionality (2017 review).
- SpotSaaS, fetched directly 2026-11-13 (https://www.spotsaas.com/product/formplus/reviews): 4.4 "Very Good", "Based on 10 ratings & 20 reviews" (meta description says "46 reviews, rated 4.5/5"; conflicting). Reviews shown are dated 03/19/22 to 12/19/23. No sub-ratings or company sizes. Verbatim quotes:
  - Pro, Rie T (2.5/5, 12/19/23): "Form creation is very easy and can be handled even by beginners."
  - Pro, Laura C (5/5, 09/06/23): "The customer service is great even though it is through a chat."
  - Con, Rie T: "I felt that the free features are limited and the paid features are a bit expensive."
  - Con, Enrique L (3/5, 12/19/23): "Design and personalization are not good enought." (sic)
  - Con, Laura C: "I really struggled with using the calculations, but the support I received completely compensated for that."
- Trustpilot (https://www.trustpilot.com/review/formpl.us, fetched 2026-11-13): "Form+" profile, 0 reviews.
- GetApp, Software Advice, TrustRadius, Product Hunt: HTTP 403 on 2026-11-13. SaaSworthy reviews URL 404. Not found.
- A SaaSworthy listing says Formplus does not provide an API (https://www.saasworthy.com/product/formplus, search snippet; unverified). Homepage lists "Webhooks" as an integration.
- G2 summary snippet: users "feel more confident in the reliability and performance of Formstack compared to Formplus" because Formstack has more reviews (https://www.g2.com/compare/formplus-vs-formstack-forms).
- Award badge image names on pricing page: saasworthy_2021, ss_bv_fall_2020, premium_usability_2019, risingstar_2019, ss_bv_2021, ss_bv_winter_2022 (FinancesOnline-style badges, INFERRED). Most recent: 2022.

## Site observations

- Broken link on https://www.formpl.us/convince-your-team: "Repeatable Sections" card points to "https://www.formpl.u/e/features/multiple-users" (malformed host).
- Pricing FAQ says free plan has all features, while the grid padlocks several.
- Case-study and user-story pages show month and day but no year.
