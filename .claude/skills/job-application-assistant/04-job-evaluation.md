# Job Evaluation Framework — Bhushan Murari

*Used by Claude during /apply to score a job posting before proceeding to CV drafting.
Always evaluate fit before generating any documents. Present the scored assessment to
the user and ask for confirmation if fit is below 70.*

---

## Scoring Method

Score each dimension below. Sum the weighted scores for a total out of 100.
Present results as a scorecard, then give a **Recommend / Proceed with caveats /
Pass** verdict with a one-paragraph rationale.

| Dimension | Weight | Max points |
|-----------|--------|------------|
| Domain match | 30% | 30 |
| Skills match | 25% | 25 |
| Seniority & scope | 20% | 20 |
| Location fit | 15% | 15 |
| Company / sector fit | 10% | 10 |
| **Total** | | **100** |

---

## Dimension 1 — Domain Match (30 pts)

*Does the role's core domain overlap with Bhushan's primary expertise?*

| Match level | Points |
|-------------|--------|
| Primary domain: Wallet / Payments Platform / Ledger / Financial Infrastructure | 28–30 |
| Primary domain: Fraud, Risk, AML, or Chargeback Management | 25–28 |
| Primary domain: iGaming / Social Gaming Monetisation / Bonus Platform | 22–26 |
| Primary domain: Digital Banking / FinTech with strong payments component | 20–24 |
| Adjacent domain: eCommerce payments, subscription billing, marketplace payments | 15–20 |
| Weak overlap: Generic platform PM, no financial/payments angle | 5–12 |
| No overlap: Pure B2C consumer product with no payments/monetisation/fintech | 0–5 |

**Auto-flag if:** Role is described as "Growth PM", "Consumer PM", or "Social Media PM"
with no financial infrastructure component — score this dimension ≤ 5 and note the gap
explicitly.

---

## Dimension 2 — Skills Match (25 pts)

*Tally how many of the role's required skills appear in Bhushan's profile.*

### Must-have skills (from Bhushan's core stack):

**Wallet & Platform:**
Ring-fenced balance design · Wallet state machine / ledger architecture ·
WaaS / API contract ownership · PSP integration · Smart routing logic ·
Balance reconciliation · Platform configurability · Event-driven systems

**Regulatory & Compliance:**
AML / KYC workflow design · 3DS / SCA · Multi-jurisdiction regulatory translation ·
UKGC / MGA / RBI / Spain SAFE compliance · Responsible gambling tooling

**Payments:**
PSP onboarding · APM integration · Deposit & withdrawal flows ·
Decline-reason analytics · Purchase recovery · Chargeback management ·
Settlement & reconciliation · Fraud detection / transaction monitoring

**Product Delivery:**
PRD / user story writing · Agile / Scrum · Backlog management ·
Cross-functional squad leadership · Roadmap prioritisation · API product management ·
A/B testing (Optimizely) · UAT / production sign-offs

**Analytics:**
SQL · Looker · Funnel & cohort analysis · Revenue modelling · Metric definition

**AI / Tooling:**
Claude API · Claude Code · GitHub · Supabase · Vercel · Cloudflare · Figma

### Scoring:

| Coverage | Points |
|----------|--------|
| 80–100% of JD required skills covered | 22–25 |
| 60–79% covered | 16–21 |
| 40–59% covered, strong adjacent skills | 10–15 |
| Below 40% covered | 0–9 |

**Note any hard gaps** — skills the JD treats as essential that Bhushan does not have.
Flag these explicitly so they can be addressed in the cover letter or interview prep.

---

## Dimension 3 — Seniority & Scope (20 pts)

*Is the level and scope a genuine match?*

| Scenario | Points |
|----------|--------|
| Senior PM title, clear cross-functional scope, owns a product area end-to-end | 18–20 |
| Senior PM title but narrow scope (single feature, single market) | 13–17 |
| Lead PM / Principal PM — step-up opportunity with justified scope | 16–20 |
| Staff PM / Group PM — requires managing other PMs (assess carefully) | 12–16 |
| PM (not Senior) — lower level, flag to user | 5–10 |
| Head of Product / Director — assess if scope is realistic step-up | 10–16 |
| IC contributor with no PM responsibilities | 0–5 |

**Auto-flag if:** Title is "Associate PM", "Junior PM", or equivalent — score ≤ 8 and
note deal-breaker risk.

---

## Dimension 4 — Location Fit (15 pts)

*Does the role's location match Bhushan's stated preferences?*

| Location scenario | Points |
|-------------------|--------|
| Fully remote (India timezone acceptable) | 15 |
| Hybrid — Bengaluru | 13–15 |
| Hybrid — Hyderabad or Pune | 12–14 |
| Hybrid — Mumbai or Delhi | 8–11 |
| Onsite — Bengaluru, Hyderabad, or Pune | 11–13 |
| Onsite — Mumbai or Delhi | 7–10 |
| Fully remote but timezone mismatch (e.g. US EST only) | 8–12 |
| Onsite — Australia, UK, EU, UAE, Singapore, Malaysia (relocation required) | 8–12 |
| Onsite — North America | 2–5 |
| Location not stated | Score 10 and flag as unknown; recommend clarifying before applying |

---

## Dimension 5 — Company / Sector Fit (10 pts)

*Does the company's stage, sector, and culture suit Bhushan's profile and preferences?*

| Scenario | Points |
|----------|--------|
| Regulated iGaming operator (Entain, Flutter, Bet365, DraftKings, Aristocrat etc.) | 9–10 |
| Payments infrastructure (Stripe, Adyen, Razorpay, Cashfree, Airwallex, Nuvei etc.) | 9–10 |
| Neo-bank / digital banking (Revolut, Wise, Jupiter, Fi, Slice, Niyo, Zeta etc.) | 8–10 |
| FinTech with strong payments/wallet/lending component (CRED, PhonePe, Paytm, BharatPe) | 8–10 |
| eCommerce / marketplace with payments infrastructure team | 6–8 |
| Series B+ startup, clear PMF, funded, payments/fintech adjacent | 6–8 |
| Enterprise SaaS with financial module (e.g. billing, invoicing, treasury) | 5–7 |
| Pre-seed / seed startup without PMF — risky fit | 2–4 |
| Consumer product, no financial/payments component — deal-breaker territory | 0–3 |

---

## Verdict Thresholds

| Total score | Verdict | Action |
|-------------|---------|--------|
| 85–100 | ✅ **Strong fit — Recommend** | Proceed to CV tailoring immediately |
| 70–84 | ⚡ **Good fit — Proceed** | Proceed; note gaps in cover letter |
| 55–69 | ⚠️ **Partial fit — Proceed with caveats** | Flag gaps clearly; ask user to confirm before generating docs |
| 40–54 | 🔶 **Weak fit — Caution** | Present gaps; only proceed if user explicitly confirms |
| Below 40 | ❌ **Poor fit — Pass** | Recommend skipping; explain why |

---

## Fit Assessment Output Format

When presenting the assessment to the user, use this format:

```
## Fit Assessment — [Company] | [Role Title]

| Dimension | Score | Max | Notes |
|-----------|-------|-----|-------|
| Domain match | X | 30 | [1-line rationale] |
| Skills match | X | 25 | [1-line rationale] |
| Seniority & scope | X | 20 | [1-line rationale] |
| Location fit | X | 15 | [1-line rationale] |
| Company / sector | X | 10 | [1-line rationale] |
| **Total** | **X** | **100** | |

**Verdict:** [✅ / ⚡ / ⚠️ / 🔶 / ❌] [Recommend / Good fit / Proceed with caveats / Caution / Pass]

**Why this role fits:**
[2–3 sentences on the strongest alignment points]

**Gaps to address:**
[Bullet list of any missing skills, level mismatch, location issues, or domain gaps —
be specific. These become the focus of cover letter framing.]

**Recommended bullet stack-ranking for this role:**
[List the top 5–6 bullets from 01-candidate-profile.md that are most relevant to this
specific JD, in order of priority]
```

---

## JD Parsing Guide

When reading a job description, extract these fields before scoring:

- **Role title** — exact title as listed
- **Seniority signals** — years of experience required, team size, reporting line
- **Domain** — what the product/platform actually is (wallet, payments, fraud, gaming etc.)
- **Must-have skills** — skills listed as "required" or "essential"
- **Nice-to-have skills** — skills listed as "preferred" or "bonus"
- **Location & work mode** — remote / hybrid / onsite + city/country
- **Company type** — startup / scale-up / enterprise / regulated operator
- **Key JD phrases** — exact language to mirror in the CV and cover letter (e.g. "ring-fenced balances", "payment routing", "wallet ledger", "regulatory compliance")

**Mirror the JD's language** in the tailored CV — if the JD says "payment orchestration",
use that phrase rather than "smart routing"; if it says "financial controls", use that
rather than "balance reconciliation". Same concepts, JD-native vocabulary.
