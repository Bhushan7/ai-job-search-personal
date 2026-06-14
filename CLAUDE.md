# Job Application Assistant for Bhushan Murari

## Role

This repo is a job application workspace. Claude acts as a career advisor and application
assistant for Bhushan Murari, helping with:

1. **Job fit evaluation** — Assess job postings against the profile (skills, experience,
   domain expertise, behavioral traits, location constraints)
2. **CV tailoring** — Adapt the master CV to target specific roles; all output is DOCX.
   Use the docx skill for all document generation.
3. **Cover letter writing** — Draft targeted, narrative-driven cover letters (DOCX)
4. **Interview preparation** — Prepare STAR answers, talking points, and questions to ask
5. **Career strategy** — Advise on positioning, targeting, and personal branding

> **Output format:** This workspace uses DOCX output (not LaTeX/PDF). When the /apply
> command drafts a CV or cover letter, generate a Word-compatible .docx file using the
> docx skill. The LaTeX compilation workflow in the default framework does not apply here.

---

## Candidate Profile

### Identity

- **Name:** Bhushan Murari
- **Location:** Bengaluru, India
- **Phone:** +91 80977 92083
- **Email:** bhushan1993.m@gmail.com
- **LinkedIn:** linkedin.com/in/bhushan-murari
- **Portfolio:** bhushan-murari-portfolio.vercel.app
- **GitHub:** github.com/Bhushan7
- **LinkedIn headline:** Senior Product Manager · Wallet & Payments Platform · iGaming · FinTech
- **Status:** Actively job searching

### Target Locations (priority order)

1. **Remote** (India-based) — highest preference
2. **Hybrid** — Bengaluru, Hyderabad, or Pune
3. **Onsite** — Bengaluru, Hyderabad, or Pune
4. **Onsite / Relocation** — Australia, UK, EU, UAE, Singapore, Malaysia (open to relocate)

### Languages

English (fluent), Hindi (native)

---

### Education

- **MBA — Marketing, Operations, Strategy & Analytics** (Jun 2017 – Mar 2019) — IIM Kashipur
- **BE — Electronics & Telecommunication Engineering** (Jul 2011 – Jun 2015) — University of Mumbai

---

### Professional Experience

**Senior Product Manager — Payments, Fraud and Wallet Platform**
**Patrianna** | Remote | Social Gaming (US) | B2Spin, YSI, CardCrush, Jokio
**Jul 2024 – Present**

- Rebuilt checkout and monetisation strategy for US social gaming brands (B2Spin, YSI,
  etc.), leading two 6-member cross-functional squads (product, engineering, design);
  delivered **19.9% uplift** with **+$8.3M incremental monthly revenue growth**, **+6.5%
  lift in monthly RPU**, and **30% AOV lift** through personalised flows, pricing
  experiments, and iterative A/B testing (Optimizely)
- Designed Bonus Balance Separation at the wallet architecture level — splitting bonus
  credits into a dedicated balance bucket, decoupled from real-money balances; enabled
  ring-fenced accounting, separate Play-Through Requirement (PTR) configurations per
  wallet type, and future bonus forfeiture logic, making complex wallet states transparent
  and manageable for players (part of Automated Chargeback Collection initiative)
- Identified bonus-abuse costing ~**$150K/month**; defined transaction monitoring rules
  and real-time detection logic in collaboration with engineering — eliminating 95% of
  abuse; designed the system to be configurable
- Redesigned payout automation workflows with rules-based processing logic — reducing
  processing time from 72 hours to ~8 hours and cutting reconciliation-related CS tickets
  by **42%**; ensured balance state transitions were auditable end-to-end
- Shipped Purchase Recovery flows translating failed payment states into clear, actionable
  player experiences — recovering **$22K/week** via smart retry flows and **$6K/week**
  via insufficient funds nudges; abstracted underlying payment failure complexity into a
  seamless player UX
- Launched 3 US gaming brands (Ace, CardCrush, Jokio) on a shared wallet and payments
  platform — designed the underlying product to be brand-configurable rather than forked
  per launch; coordinated across product, engineering, legal, compliance, and marketing
- Defined and tracked wallet and payment platform KPIs — including transaction success
  rates, payout SLA, and fraud signal accuracy — using Looker and SQL; drove iterative
  platform improvements from data insights

**Product Manager — Payments Platform & Regulatory Compliance**
**Entain** | Remote | iGaming / Sports Betting | Bwin, Ladbrokes, Coral, Sportingbet
**Jan 2022 – Jun 2024**

- Translated multi-jurisdiction regulatory requirements (AML, KYC, 3DS/SCA, UKGC,
  Spain SAFE/Decree 2.0, KGC, US State Regulatory bodies) into configurable platform
  features across regulated markets — defining product specs that enabled the same
  underlying wallet and payment platform to operate compliantly across UK, Spain, US,
  Canada, Brazil, Greece
- Designed and owned the Smart Payment Routing Engine — defined the API contract and
  routing logic (real-time PSP error signals, custom logic) in collaboration with
  engineering; improving payment success rates
- Owned end-to-end integration of APMs, crypto, and bank transfer methods (Aircash,
  DIAS, BVNK) across global markets; scaled new methods to ~**10% of total transaction
  volume** in 6 months per integration — each required defining the API contract,
  reconciliation requirements, and settlement reporting specs with external providers
- Delivered 2 regulated market launches — Sports Interaction (Canada) and Unikrn
  (Canada + Brazil) — designing KYC/AML-compliant wallet and payment flows for each
  jurisdiction; implemented SCA exemptions for low-risk transactions to preserve
  conversion while meeting regulatory obligations; **zero compliance incidents**
- Produced structured platform post-mortems on payment and wallet failures — covering
  PSP downtime impact on balance states, decline rate spikes, and reconciliation
  discrepancies; analysis directly shaped platform reliability roadmap priorities

**Product Manager — Digital Wallet Platform & Payments Infrastructure**
**ICICI Bank** | Mumbai, India | Digital Banking | Pockets Wallet | BBPS
**Jan 2021 – Dec 2021**

- Defined the Wallet-as-a-Service (WaaS) API contract and integration specifications for
  neobank and startup partners — owned the developer experience end-to-end, treating
  external engineering teams as the primary customer; unlocked a new distribution channel
  with zero incremental CAC
- Drove **400% new user registration growth** and **300% transaction volume growth** for
  the Pockets digital wallet and BBPS — through UX redesigns that abstracted complex
  multi-biller, multi-category payment states into a seamless player experience, grounded
  in cohort analysis
- Managed 100+ operational wallet and payment incidents end-to-end — including balance
  discrepancy investigations, failed reconciliation events, and settlement delays; **zero
  major SLA breaches**; outcomes fed directly into platform reliability improvements

**Business Analyst — Digital Transformation**
**Kellton Tech** | Gurugram, India | FinTech & eCommerce
**Apr 2019 – Dec 2020**

- Contributed **INR 50M+** in new business by designing FinTech and eCommerce MVPs for
  B2C clients; translated complex financial product requirements into PRDs and phased
  delivery plans, bridging business stakeholders and engineering teams

**Software Engineer — Banking & Payment Systems**
**Infosys** | Pune, India | Enterprise Banking
**Sep 2015 – May 2017**

- Built and maintained enterprise banking and payment systems for a global client —
  transaction processing logic and automated workflow design; reduced manual processing
  effort by **80%** for a document processing workflow

---

### Skills

**Wallet & Platform Product:** Ring-Fenced Balance Design · API Contract Ownership ·
Wallet-as-a-Service (WaaS) · Developer Experience · Platform Configurability ·
Balance Reconciliation · Event-Driven Systems

**Regulatory & Compliance:** Multi-Jurisdiction Regulatory Translation · AML · KYC ·
3DS/SCA · SCA Exemptions · Segregated Account Compliance · UKGC · Responsible Gambling ·
Spain SAFE/Decree 2.0 · Financial Audit

**Payments & FinTech:** PSP Onboarding · Smart Routing Engine · APMs / Crypto /
Bank Transfers · Deposits & Withdrawals · Fraud Detection · Transaction Monitoring ·
Chargeback Management · Settlement & Reconciliation

**Product Delivery:** Agile/Scrum · Backlog Management · PRD & User Story Writing · UAT ·
Cross-functional Squad Leadership · Roadmap Prioritisation · Stakeholder Management ·
Production Sign-offs

**Analytics & Technical:** SQL · Looker · Tableau · A/B Testing (Optimizely) · Funnel &
Cohort Analysis · Success Metric Definition · Distributed Systems · API Design ·
Data-Driven Iteration

**AI & Tooling:** Claude AI · Claude Code · JIRA · Confluence · Figma · Vercel ·
Supabase · GitHub · Cloudflare

---

### Side Projects (always include in applications)

**GLP-1 Companion** [Early Stage]
- Full-stack health SaaS (Next.js, Supabase, Claude API)
- Demonstrates platform product ownership: API design, data model, and user-facing
  experience built and shipped independently

**AI Pulse Newsletter for PMs** [Early Stage]
- AI-driven newsletter built with Claude API & Supabase
- Demonstrates use of AI tooling to accelerate product workflow and reduce manual effort

---

### Behavioral Profile

- **Systems thinker** — comfortable with wallet state machines, ledger design, event-driven
  patterns, and API architecture trade-offs
- **Technically fluent** — works directly with engineering on distributed systems and API
  design; can read code, review contracts, participate in architecture reviews
- **Data-first** — every decision tied to a metric; SQL, Looker, Amplitude, cohort analysis
- **Regulatory translator** — experienced turning complex multi-jurisdiction compliance
  requirements into configurable platform features (UKGC, AML, KYC, 3DS/SCA, RBI)
- **Outcome-oriented** — measures success in revenue recovered, failure rate reduced, and
  conversion lifted — not features shipped
- **AI-native operator** — uses Claude and Claude Code as genuine workflow accelerators
  for PRD drafting, data analysis, and discovery
- **Strengths:** Payment infrastructure depth, regulatory translation, fraud strategy,
  multi-market launch execution
- **Growth areas:** Scaling team leadership above 10; enterprise B2B sales cycle exposure
- **Thrives in:** Remote-first, fast-paced, regulated environments with clear metrics and
  cross-border scope

### What Excites Bhushan

- Wallet and payment infrastructure problems — routing, retry logic, balance state machines
- Fraud prevention at the intersection of ML and product
- Launching products in new regulated markets (iGaming, fintech, digital banking)
- Building AI-native tools and workflows as genuine productivity multipliers
- Environments where monetisation complexity is high and platform decisions matter

### Target Roles

- Senior Product Manager — Wallet / Payments Platform
- Senior Product Manager — Fraud & Risk
- Senior Product Manager — Financial Infrastructure / Ledger
- Senior Product Manager — iGaming / Monetisation
- Lead / Principal PM (step-up roles where scope clearly justifies it)

### Target Companies (types)

- Regulated iGaming operators (Entain, Flutter, Bet365, DraftKings, Aristocrat, IGT,
  Light & Wonder, Rush Street)
- Payments infrastructure (Stripe, Adyen, Checkout.com, Razorpay, Cashfree, Nuvei,
  Paysafe, Airwallex, Monoova)
- Neo-banks and digital banking platforms (Revolut, Wise, Jupiter, Fi, Slice, Niyo,
  Open, Zeta)
- FinTech with payments / wallet / lending component (CRED, BharatPe, PhonePe,
  Paytm, Groww)

### Deal-Breakers

- Pure B2C consumer product with no payments, monetisation, or fintech component
- Roles below Senior PM level (unless exceptional scope/step-up opportunity)
- Companies in early pre-seed stage without product-market fit

---

## Source of Truth Documents

When files are available in `documents/`:

| File | Purpose |
|------|---------|
| `Bhushan_Murari_SeniorPM_Resume.pdf` | Master CV — base for all tailored CVs |
| `Bhushan_Murari_BulletVault.docx` | Tagged bullet library — pull from here, never invent |
| `CV_guidance.md` | Full rules, formatting standards, and metrics table |

**Bullet Vault usage:** When tailoring a CV, identify the closest analogue bullet from
the Vault first (match by domain and skill), then reframe surrounding bullets to match
the JD's language. ⭐ bullets are the strongest and should appear on every CV unless
directly irrelevant. Never fabricate achievements.

---

## Repo Structure

- `cv/` — DOCX CV variants (name: `Bhushan_Murari_CV_<Company>_<Role>.docx`)
- `cover_letters/` — DOCX cover letters (name: `Bhushan_Murari_CL_<Company>_<Role>.docx`)
- `.claude/skills/` — AI skill definitions for the application workflow
- `documents/` — Source materials (master CV, bullet vault, guidance)
- `job_search_tracker.csv` — Application log (update after every /apply run)

---

## Workflow for New Job Applications

1. User provides a job posting (URL or pasted text)
2. **Always evaluate fit first** — skills match, experience match, location fit, level,
   domain alignment. Score out of 100 and present the assessment before proceeding.
3. If good fit (≥ 70): tailor CV from master, using Bullet Vault for bullet selection.
   Generate DOCX to `cv/`.
4. Draft a targeted cover letter. Generate DOCX to `cover_letters/`.
5. **Verify both documents** (see Verification Checklist below)
6. Prepare 5 interview talking points and 3 questions to ask the interviewer
7. Update `job_search_tracker.csv`: company, role, date applied, fit score, status

**When mentioning AI tooling:** Reference specific tools by name (Claude API, Claude Code,
Cloudflare Workers, Supabase, Vercel) and cite the AI Pulse Newsletter and GLP-1
Companion as concrete proof points.

---

## Verification Checklist

After generating a CV or cover letter, verify **all** of the following. Report as pass/fail.

### Factual accuracy
- [ ] All claims match the profile above — no fabricated skills, experience, or metrics
- [ ] Metrics match the canonical figures table (see below) exactly
- [ ] Dates are correct: Patrianna Jul 2024–Present · Entain Jan 2022–Jun 2024 ·
      ICICI Jan 2021–Dec 2021 · Kellton Apr 2019–Dec 2020 · Infosys Sep 2015–May 2017
- [ ] Education correct: MBA IIM Kashipur (Jun 2017–Mar 2019) ·
      BE University of Mumbai (Jul 2011–Jun 2015)
- [ ] Entain brands: Bwin, Ladbrokes, Coral, Sportingbet
- [ ] Entain markets: UK, Spain, US, Canada, Brazil, Greece (not Germany or Australia)
- [ ] Infosys always included (Sep 2015 – May 2017, Pune)
- [ ] Both side projects always in the Projects section

### Targeting
- [ ] CV summary/opener is tailored to the specific role (not generic)
- [ ] Bullet stack-ranking reflects the JD's priorities (closest analogue bullets first)
- [ ] Key JD requirements are addressed; gaps acknowledged where relevant
- [ ] Skills section reordered so JD-relevant skills appear first

### Formatting
- [ ] All percentage figures are **bold** in the DOCX output
- [ ] All currency figures (USD, INR) are **bold** in the DOCX output
- [ ] CV is maximum 2 pages
- [ ] Date format consistent throughout: `Jul 2024 – Present` / `Jan 2022 – Jun 2024`

### Consistency
- [ ] Brand order: Patrianna → Entain → ICICI Bank → Kellton Tech → Infosys
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter

### Quality
- [ ] No spelling or grammar errors
- [ ] Bullets follow outcome-first structure: problem → solution → outcome
- [ ] Cover letter addressed to the correct person/hiring manager (or "Dear Hiring Team")

---

## Canonical Metrics (never alter these figures)

| Metric | Exact figure | Role |
|--------|-------------|------|
| Incremental monthly revenue growth | **+$8.3M** | Patrianna |
| Revenue uplift % | **19.9%** | Patrianna |
| AOV lift | **30%** | Patrianna |
| Monthly RPU lift | **+6.5%** | Patrianna |
| Bonus abuse eliminated | **~$150K/month, 95% eliminated** | Patrianna |
| Payout processing time reduction | **72 hrs → ~8 hrs** | Patrianna |
| CS ticket reduction (reconciliation) | **42%** | Patrianna |
| Purchase recovery — retry flow | **$22K/week** | Patrianna |
| Purchase recovery — nudge flow | **$6K/week** | Patrianna |
| New payment method scale | **~10% of transaction volume in 6 months** | Entain |
| Market launches, zero compliance incidents | **2 (Sports Interaction CA; Unikrn CA+BR)** | Entain |
| Pockets wallet user growth | **400%** | ICICI Bank |
| Pockets transaction volume growth | **300%** | ICICI Bank |
| Wallet/payment incidents managed | **100+, zero major SLA breaches** | ICICI Bank |
| New business contributed | **INR 50M+** | Kellton Tech |
| Manual processing effort reduction | **80%** | Infosys |

---

## Cover Letter Principles

- Open with a specific hook tied to the company (a product decision, a regulatory
  challenge, a market they operate in) — never a generic "I am excited to apply"
- Second paragraph: what you bring that is directly relevant — 3 specific proof points,
  not a list of skills
- Third paragraph: one concrete story from the canonical bullets that mirrors the role's
  core challenge
- Close: clear ask, enthusiasm for the specific opportunity, and a forward-looking line
- Tone: confident, specific, senior — not sycophantic
- Length: 3–4 paragraphs, maximum 1 page
