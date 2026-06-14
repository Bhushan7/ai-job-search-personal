# Interview Preparation — Bhushan Murari

*Pre-loaded STAR stories, behavioural question banks, and framework for generating
role-specific interview prep after each /apply run. Stories are grounded in canonical
metrics — never embellish or alter figures.*

---

## How to Use This File

After /apply generates a CV and cover letter, run interview prep by:
1. Identifying the role's 3–4 core competency themes from the JD
2. Selecting the most relevant STAR stories below (tagged by theme)
3. Generating 5 tailored talking points and 3 strong questions to ask the interviewer

---

## STAR Story Library

Each story follows: **Situation → Task → Action → Result**
Tags indicate which JD themes each story addresses.

---

### Story 1 — Bonus Balance Separation (Wallet Architecture)

**Tags:** `wallet-architecture` `ledger-design` `fraud-prevention` `platform-thinking`
`cross-functional` `technical-depth`

**Situation:**
At Patrianna, bonus credits and real-money balances were stored in a single wallet
balance field. This caused two problems: players couldn't distinguish what they could
withdraw vs what was bonus-locked, and internally we had no reliable way to enforce
play-through requirements (PTRs) or detect bonus abuse at the transaction level.

**Task:**
Design a wallet architecture change that separated bonus funds from real-money funds at
the ledger level — without breaking existing payment flows or requiring a full platform
rewrite.

**Action:**
I mapped the current wallet state machine and identified where balance mutations happened
across deposit, bonus credit, wager, withdrawal, and expiry events. I defined a new
dedicated bonus balance bucket as a separate ledger field, wrote the product spec covering
every state transition (pending → active → expired/forfeited), defined the PTR
configuration schema (configurable per brand and bonus type), and worked with engineering
to design a migration path for existing live balances. I also defined the player-facing
UX — a split balance display showing "Bonus" vs "Withdrawable" so players always knew
their state.

**Result:**
The architecture enabled ring-fenced accounting, per-wallet-type PTR configs, and future
bonus forfeiture logic. It directly enabled the bonus abuse detection system that
eliminated ~**$150K/month** in abuse. It also became the foundation for the Automated
Chargeback Collection initiative, since we could now audit exactly which balance state a
transaction was drawn from.

---

### Story 2 — Purchase Recovery ($22K/week)

**Tags:** `conversion-optimisation` `payments` `player-experience` `A/B-testing`
`revenue-impact` `decline-reason-analytics`

**Situation:**
A significant portion of payment attempts on Patrianna's brands were failing silently —
players would hit a decline and either abandon or contact CS. We had no structured recovery
flow: no retry logic, no player-facing messaging that matched the actual failure reason,
and no data on which decline types were recoverable.

**Task:**
Design and ship purchase recovery flows that turned failed payment states into actionable
player experiences — recovering revenue that was otherwise permanently lost.

**Action:**
I pulled decline-reason data from our PSP feeds and segmented failures into recoverable
categories: soft declines eligible for retry, insufficient funds cases where a nudge to a
lower denomination or alternative method might convert, and hard declines where no
recovery was possible. For each category I defined a distinct UX flow — smart retry with
updated messaging for soft declines, denomination nudge + alternative payment prompt for
NSF cases, and a clean fallback for hard declines. I wrote the specs, defined the A/B
test structure in Optimizely, and worked with engineering to abstract the underlying PSP
error codes into player-readable states.

**Result:**
Smart retry flow recovered **$22K/week**. The insufficient funds nudge flow recovered an
additional **$6K/week**. The abstraction layer also reduced CS tickets related to "why
did my payment fail" — players now received a meaningful explanation and a clear next step
rather than a generic error.

---

### Story 3 — $8.3M Revenue Uplift (Monetisation & Checkout Optimisation)

**Tags:** `monetisation` `conversion-optimisation` `A/B-testing` `squad-leadership`
`revenue-impact` `data-driven`

**Situation:**
Patrianna's US social gaming brands had a functioning checkout but no structured
optimisation programme. Conversion rates and AOV varied widely across brands with no
clear understanding of why — pricing, UX, offer mechanics, and payment method mix had
never been systematically tested.

**Task:**
Lead the monetisation strategy rebuild for the US brands — running cross-functional squads
to improve checkout conversion, AOV, and monthly revenue per user through structured
experimentation.

**Action:**
I led two 6-member cross-functional squads (product, engineering, design) running parallel
experiment tracks. I defined the metric hierarchy — RPU as the north star, with AOV and
conversion rate as the primary input metrics. I built the experiment roadmap in three
phases: (1) personalised pricing and offer mechanics by player segment, (2) checkout flow
UX optimisation, and (3) deposit limit and denomination structure tests. Each experiment
was structured with a hypothesis, a minimum detectable effect threshold, and a clear
ship/kill/iterate criteria. I used Optimizely for A/B testing and Looker for cohort
analysis on post-experiment retention.

**Result:**
Delivered **19.9% revenue uplift**, **+$8.3M incremental monthly revenue**, **30% AOV
lift**, and **+6.5% monthly RPU** across the brand portfolio.

---

### Story 4 — Smart Payment Routing Engine (Entain)

**Tags:** `payments` `API-design` `platform-thinking` `PSP-integration` `technical-depth`
`multi-market`

**Situation:**
At Entain, payment success rates varied significantly across markets because all
transactions were routed through a fixed PSP preference list with no real-time
intelligence. When a PSP had degraded performance, transactions still routed to it,
causing avoidable declines.

**Task:**
Design and own the Smart Payment Routing Engine — a rules-based routing layer that could
ingest real-time PSP signals and route transactions dynamically to maximise success rates.

**Action:**
I defined the API contract for the routing engine: the input schema (transaction metadata,
player segment, market, method type), the signal ingestion interface (real-time PSP error
rate feeds, latency metrics), and the routing rule configuration schema (allow operators
to define custom routing logic per market without engineering involvement). I worked with
engineering on the architecture — event-driven, with a configuration layer that compliance
and commercial teams could adjust. I also defined the monitoring dashboard so the ops team
could see routing decisions and override in real-time.

**Result:**
Improved payment success rates across UK, Spain, US, and Canada markets. The
configurability of the rule layer meant new markets could be onboarded without custom
engineering work for routing — it became a reusable platform component.

---

### Story 5 — Multi-Jurisdiction Regulatory Translation (Entain)

**Tags:** `regulatory-compliance` `multi-market` `AML-KYC` `platform-thinking`
`stakeholder-management` `market-launch`

**Situation:**
Entain operated across 6+ regulated markets, each with distinct regulatory requirements
(UKGC, Spain SAFE/Decree 2.0, KGC, US State bodies, Canadian provincial rules). The
existing approach was to build market-specific features as one-off solutions — creating
a fragmented codebase and compliance risk when regulations changed.

**Task:**
Translate multi-jurisdiction regulatory requirements into configurable platform features —
so the same underlying wallet and payment platform could operate compliantly across all
markets without forked codebases.

**Action:**
I built a regulatory requirements matrix — mapping each jurisdiction's AML thresholds,
KYC verification tiers, SCA requirements, and responsible gambling rules against our
existing platform capabilities. I identified which requirements were truly market-specific
(needing separate config) vs which were variations of the same underlying capability
(needing a configurable field). I wrote product specs that expressed regulatory rules as
configuration rather than hard-coded logic — for example, AML threshold amounts as
operator-configurable fields rather than fixed values. I coordinated review across
compliance, legal, and engineering across 3 squads.

**Result:**
The same wallet and payment platform operated compliantly across UK, Spain, US, Canada,
Brazil, and Greece. Delivered 2 regulated market launches (Sports Interaction Canada;
Unikrn Canada + Brazil) with **zero compliance incidents**. The configurable approach
also reduced time-to-comply when regulations changed — a rule update was a config change,
not a sprint.

---

### Story 6 — Bill Payment UX Redesign, ICICI Pockets / BBPS (400% / 300% Growth)

**Tags:** `user-research` `UX-simplification` `friction-removal` `conversion-optimisation`
`discovery` `digital-banking` `data-driven` `revenue-impact`

**Situation:**
ICICI Bank's Pockets digital wallet and BBPS (Bharat Bill Payment System) platform
supported bill payments across dozens of biller categories — electricity, broadband,
DTH, water, mobile postpaid — but adoption was low and drop-off in the bill payment
flow was high. The flows existed across 3 mobile apps and 2 websites, all with
inconsistent UX and unnecessary friction at the point of payment.

**Task:**
Understand why users were abandoning the bill payment flow and redesign the experience
across all 5 surfaces to drive meaningful growth in registrations and transaction volume.

**Action:**
I started with deep discovery — mapping the full bill payment user journey end-to-end
for each biller category. I looked at how billing companies generated and sent bills to
customers, and specifically what information was available to the customer at the moment
they needed to pay. The key insight: billers were requiring customers to enter a 17-character
account ID as the primary identifier, but customers almost never had that to hand — they
only knew their registered mobile number. For most billers, the mobile number was a
perfectly valid lookup key, just not being used. I extended this analysis across every
field in the payment form: for each field I asked — does the customer know this without
looking it up? Is it on the bill they're holding? Can we pre-fill or auto-detect it?
I then prioritised the fields to retain on the UI (those genuinely required to complete
the transaction) and removed the ones creating friction without adding value. The redesign
also surfaced account details automatically once a known identifier (mobile number, email)
was entered — reducing manual entry significantly. On top of this, I added an auto-pay
feature: customers could connect a preferred credit/debit card or bank account and
schedule automatic payments 2 days before the bill-due date per biller category —
removing the need to return to the app for recurring bills entirely.

**Result:**
The redesigned experience across 3 mobile apps and 2 websites drove **400% new user
registration growth** and **300% transaction volume growth** for Pockets and BBPS.
The auto-pay feature drove recurring engagement — once set up, users returned through
automated transactions rather than requiring active re-acquisition.

---

### Story 7 — WaaS API for ICICI Bank (B2B Distribution Channel)

**Tags:** `API-design` `developer-experience` `platform-thinking` `wallet`
`B2B-product` `new-channel`

**Situation:**
ICICI Bank's Pockets digital wallet had strong consumer traction but no B2B distribution
channel. Neobanks and fintech startups wanted to embed wallet and payment functionality
but had no standardised API to integrate with — each integration was bespoke and
expensive for both sides.

**Task:**
Define the Wallet-as-a-Service (WaaS) API contract and integration specifications to
unlock a new distribution channel — treating external engineering teams as the primary
customer.

**Action:**
I defined the API contract: endpoints, request/response schemas, error code taxonomy,
rate-limit policy, and sandbox environment, and wrote the developer documentation. I
worked with engineering on the authentication model and webhook design for async events
(balance updates, transaction confirmations). I designed the integration onboarding flow
— a self-serve sandbox, a testing checklist, and a go-live certification process — so
partners could onboard without hand-holding from our engineering team.

**Result:**
Unlocked a new B2B distribution channel with zero incremental CAC. The WaaS API gave
neobank and startup partners a standardised, well-documented integration path — removing
the barrier that had previously made each partnership a one-off engineering project.

---

### Story 8 — Kellton Tech New Business (FinTech MVPs)

**Tags:** `discovery` `PRD-writing` `stakeholder-management` `fintech` `B2B`

**Situation:**
At Kellton Tech, I was working with B2C FinTech and eCommerce clients who had product
ideas but no structured discovery or requirements process — resulting in vague briefs
handed to engineering that produced the wrong product.

**Task:**
Run product discovery and translate complex financial product requirements into PRDs and
phased delivery plans that engineering could execute against.

**Action:**
I ran structured discovery workshops with business stakeholders — mapping current flows,
identifying the core problem to solve, and defining success metrics before writing a
single requirement. I built PRDs with phased scope (MVP vs Phase 2) and ran review
sessions with both the client and the engineering team to resolve ambiguities before
sprint planning.

**Result:**
Contributed to **INR 50M+** in new business by giving clients confidence that their
product was well-defined and deliverable. Several clients extended engagements based on
the quality of the PRD process.

---

## Behavioural Question Bank

### "Tell me about a time you dealt with a complex technical problem as a PM"
→ Use Story 1 (Bonus Balance Separation) or Story 4 (Routing Engine)
→ Emphasise: mapped the state machine before writing a spec; worked at the API contract
level; understood the migration risk and designed for it

### "Tell me about a time you drove significant revenue impact"
→ Use Story 3 ($8.3M uplift) — lead with the number, then walk through the experiment
structure and what made the approach rigorous
→ Alternate: Story 2 (Purchase Recovery) if payments context is more relevant to the JD

### "Tell me about a time you navigated a complex regulatory environment"
→ Use Story 5 (Multi-jurisdiction regulatory translation)
→ Emphasise: regulatory matrix as a discovery tool; configuration vs hard-coding as a
strategic product decision; compliance coordination across 3 squads

### "Tell me about a time you launched a product in a new market"
→ Use Story 5 (Entain market launches) — Sports Interaction Canada and Unikrn Canada+Brazil
→ Emphasise: zero compliance incidents, SCA exemption design, KYC flow per jurisdiction

### "Tell me about a time you designed an API product or worked closely with engineering"
→ Use Story 7 (WaaS at ICICI) or Story 4 (Routing Engine at Entain)
→ Emphasise: treated external engineers as the primary customer; defined error taxonomy,
rate limits, sandbox, and go-live certification — not just endpoints

### "Tell me about a time you used data to make a product decision"
→ Use Story 2 (Purchase Recovery) — segment decline-reason data before designing flows
→ Or Story 3 (Monetisation) — metric hierarchy, MDE thresholds, post-experiment cohort
analysis

### "Tell me about a time you improved the user experience and drove measurable growth"
→ Use Story 6 (BBPS bill payment redesign at ICICI)
→ Emphasise: started with discovery — mapped how billers send information to customers
and what the customer actually has to hand at the point of payment; removed fields that
created friction without adding value; the 17-character account ID vs mobile number
insight is the crux — shows PM instinct to question the default and design around
the user's real context

### "Tell me about a time you influenced without authority"
→ Use Story 5 (Regulatory translation across 3 squads at Entain) or Story 1 (Bonus
Balance Separation — aligning engineering on a platform architecture change)

### "Tell me about a failure or something you'd do differently"
→ Be specific: at Entain, initial APM integrations underestimated reconciliation
complexity — settlement format mismatches caused 2-week delays post-launch; learned to
define reconciliation requirements as part of the API contract spec, not as an
afterthought
→ Or: first Purchase Recovery A/B test at Patrianna had a sampling error (two segments
with very different base conversion rates in the same test) — caught it in week 1, reset
the test; now always define segment eligibility criteria before configuring the experiment

---

## Questions to Ask the Interviewer

### About the role:
- "What does the payments / wallet platform look like today — what's the current
  architecture, and where are the biggest reliability or scalability pain points?"
- "What does the regulatory footprint look like across markets, and how does the team
  currently manage compliance requirements across jurisdictions?"
- "What does a successful first 6 months look like for this role?"

### About the team:
- "How does the PM team currently work with engineering — are squads organised by domain
  or by platform layer?"
- "What's the biggest cross-functional challenge the team is working through right now?"

### About the company:
- "Where is the payments/wallet platform in its maturity curve — are you primarily
  building new capabilities, or optimising and scaling what exists?"
- "How does the company think about build vs buy for payments infrastructure?"

---

## Role-Specific Interview Prep Template

*After each /apply run, generate a tailored prep block using this format:*

```
## Interview Prep — [Company] | [Role Title]

**The 3 things they will probe hardest:**
1. [Theme 1 from JD] → use Story [X]
2. [Theme 2 from JD] → use Story [X]
3. [Theme 3 from JD] → use Story [X]

**Tailored talking points:**
1. [Specific angle on Bhushan's experience most relevant to this role]
2. [Second angle]
3. [Third angle]
4. [Fourth angle]
5. [Fifth angle]

**Questions to ask:**
1. [Specific question based on what this company/role is doing]
2. [Second question]
3. [Third question]

**Potential gaps to prepare for:**
- [Any skill or experience gap flagged in the fit assessment — how to frame it honestly]
```
