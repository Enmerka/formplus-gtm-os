# CLAUDE.md

## Company

Formplus (https://www.formpl.us): self-serve online and offline (beta) form builder for surveys, registrations, applications, payments and orders. Its pitch: "Let forms do the work" (https://www.formpl.us, accessed 2026-11-13). Freemium, $0 to $85 a month plus Enterprise (https://www.formpl.us/pricing, accessed 2026-11-13). Started in Lagos, Nigeria, at CcHub (https://9jagistland.blogspot.com/2018/11/the-formplus-story-from-cchub-to.html, accessed 2026-11-13). Legal entity Formplus Inc, Delaware (https://www.formpl.us/terms-and-privacy, accessed 2026-11-13). Main buyers in its case studies: schools, nonprofits, small service businesses and field reporting teams (https://www.formpl.us/case-studies, accessed 2026-11-13).

Key files (everything written for Formplus so far; starter-kit files are covered by the folder guide below):

- `context/docs/research/company.md`: products, pricing, entity, origin, funding, team, reviews.
- `context/docs/research/customers.md`: named customers, case studies, testimonials with quotes.
- `context/docs/research/competitors.md`: competitor positioning and pricing.
- `context/docs/research/market.md`: regulation (NDPA, GDPR), admissions cycles, donor reporting, paper forms.
- `context/docs/research/signals.md`: public evidence of buying triggers.
- `context/docs/research/voice.md`: how Formplus describes itself, verbatim.
- `context/icp/icp.md`: ICP in five layers, six segments, NGO test cell, not-a-fit list.
- `context/icp/personas.md`: champion, economic buyer and influencer personas.
- `context/icp/signal-matrix.md`: segment x persona angles, scored buying signals, build order and workflow tracker (v1, work in progress).
- `context/docs/gtm-system.md`: outbound GTM system design, step by step with decisions (v1, not built).
- `context/docs/case-studies.md`: every customer story: size, industry, problem, result, quote, source.
- `context/positioning/value-proposition.md`: job, pain, gain and proof per persona.
- `context/positioning/positioning.md`: category, target, alternatives, unique value, positioning statement.
- `context/positioning/competitors.md`: competitor table, where Formplus wins and loses, how to respond.
- `context/messaging/messaging.md`: core message, four pillars with proof, persona angles, words to use and avoid.
- `context/brand-kit/brand.md`: tone of voice and key phrases from Formplus's own copy.
- `output/campaigns/workflow-candidates.md`: three candidate workflows; W1 recommended.
- `output/campaigns/google-forms-documents-payments/workflow-spec.md`: W1 spec, STRUCTURE-APPROVED 2026-11-13, copy pending.
- `weekly-priorities/2026-W46.md`, `work-log/2026-W46.md`: this week's priorities and change log.

Not created yet: `context/messaging/facts.md` (needed by `/campaign-copy`), brand visuals (logo, colours, fonts), anything in `knowledge-base/learnings/` and `meetings/`.

## How this folder works

- `.claude/skills/`: reusable Claude skills for this repo. Read when a task matches a skill.
- `context/icp/`: ideal customer profiles and personas. Read before any targeting, list building or copy.
- `context/positioning/`: positioning, category and competitor notes. Read before writing messaging or comparisons.
- `context/messaging/`: approved value props, proof points and message house. Read before writing any copy.
- `context/brand-kit/`: voice, tone, visual and naming rules. Read before producing anything customer-facing.
- `context/docs/research/`: raw public-source research with links. Read when you need a fact and its source.
- `knowledge-base/playbooks/`: repeatable GTM processes. Read before running a workflow.
- `knowledge-base/learnings/`: what worked, what failed, and why. Read before planning a new campaign.
- `meetings/`: meeting notes, one file per meeting. Read for decisions and open actions.
- `output/campaigns/`: finished campaign assets and drafts. Read to reuse or update past work.
- `tools/`: scripts and tool configs. Read before calling or building a tool.
- `weekly-priorities/`: one file per ISO week (YYYY-Www.md). Read at the start of every session.
- `work-log/`: one file per ISO week, timestamped entries. Read for recent changes; write after every change.

## Rules

- Cite a public source (URL and access date) for every company fact.
- Never invent numbers. If a figure is unknown, write "unknown" and flag it.
- No em dashes in any copy.
- Ask before sending or publishing anything.
- Log every change in this week's work log (`work-log/YYYY-Www.md`).

## Skills

From the GTM starter kit (`.claude/skills/`). Method docs they read are in `knowledge-base/playbooks/`.

- Research to copy, in order: `campaign-strategy`, `signal-matrix`, `build-workflow-spec`, `campaign-copy`. Visual map: `miro-gtm-flowchart`.
- Clay builds: `build-clay`, `prompt-builder`, `campaign-contract`, `design-clay-table-json`, `import-clay-table`, `save-clay-schema`.
- Clay costs and data: `calculate-costs`, `workspace-cost-audit`, `export-tables`. Pre-launch checks: `campaign-qa`.
- Research and deliverability: `crawl4ai`, `agent-browser`, `inbox-placement-test`.

## Tools

GTM stack:

- Clay: account and contact enrichment, signal tables, AI research columns.
- Apollo: prospect and contact data, list building.
- n8n: workflow automation that connects the stack.
- HubSpot: CRM, the system of record for contacts, companies and deals.
- Instantly: cold email sending and sequencing.

In this repo (`tools/`):

- `rex/`: unofficial Python SDK for Clay, driven by your browser session. Start with `tools/rex/GETTING_STARTED.md`.
- `crawl4ai/`, `agent-browser/`: install guides for site crawling and browser automation.
