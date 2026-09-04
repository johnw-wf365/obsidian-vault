# WorkForce365.ai — Business Plan

**Status:** Approved (rev 3, 2026-09-04)
**Author:** [[Ava]] (Business Strategist)
**Source:** [WOR-3](Paperclip issue) — full plan document on issue

---

## Executive Summary

WorkForce365.ai is building **OnboardAI** — a deployable AI agent that automates new-hire employee onboarding.

**Why now:** Agentic AI in HCM market growing from $2.47B (2025) → $4.56B (2026), on track to $13.48B by 2031 (Mordor Intelligence, 2026).

**Year 1 headline:**
- **$360K ARR** target (M12)
- **55%** gross margin
- **< 6 months** CAC payback
- **Break-even: M8**

---

## Financial Snapshot

| Metric | Value |
|--------|-------|
| Year 1 ARR target | $360K |
| Year 1 cumulative revenue | ~$150,700 |
| Year 1 total burn | ~$28,500 |
| Gross margin | 55% |
| M12 MRR | $30,000 |
| M12 monthly burn | $4,000 |
| LTV:CAC | 5.7:1 |
| CAC payback | 4 months |

**Pricing (hybrid base + usage):**

| Tier | Monthly Base | Included Hires | Overage |
|------|-------------|----------------|---------|
| Starter | $49/mo | 10 hires/mo | $5/hire |
| Growth | $199/mo | 50 hires/mo | $4/hire |
| Scale | $499/mo | 200 hires/mo | $3/hire |
| Enterprise | Custom | Custom | Custom |

---

## Market Sizing

**Bottom-Up Analysis (Ira, 2026-09-03):**

| Layer | Calculation | Result |
|-------|-------------|--------|
| **TAM** | 120,000 mid-market companies × $7,500 avg annual spend | **$900M** |
| **SAM** | TAM × 50% (active buying intent) | **$450M** |
| **SOM Year 1** | 300 paying customers × $100/mo × 12 months | **$360K** |
| **SOM Year 3** | 1,500 customers × $150/mo × 12 months | **$2.7M** |

**Top-Down Validation:**

| Source | Market | Size (2026) | Implied Mid-Market US |
|--------|--------|-------------|----------------------|
| Mordor Intelligence — Digital Onboarding | Global $7.59B | US ~40% = $3.04B, mid-market ~30% = **$912M** |
| Research and Markets — Employee Onboarding | Global $2.53B | US ~45% = $1.14B, mid-market ~40% = **$456M** |
| Mordor Intelligence — Preboarding/Onboarding | Global $4.81B | US ~40% = $1.92B, mid-market ~25% = **$481M** |
| Mordor Intelligence — Agentic AI in HCM | Global $4.56B | Onboarding ~25% = $1.14B, US ~40% = **$456M** |

**TAM reconciliation:** Bottom-up = $900M. Top-down range = $456M-$912M. Adopted: **$900M**.

**SOM Sensitivity:**

| Scenario | Customers (Yr 1) | ARPU/Mo | Year 1 ARR | SAM Share |
|----------|------------------|---------|------------|-----------|
| Conservative | 200 | $100 | $240K | 0.053% |
| **Base case** | **300** | **$100** | **$360K** | **0.080%** |
| Optimistic | 400 | $110 | $528K | 0.117% |

**Verdict:** Base case ($360K ARR) requires just 0.08% of SAM — highly achievable.

**Data foundation:**
- US companies with 100-2,000 employees: ~120,000 (US Census Bureau, County Business Patterns 2023)
- Average fully-loaded onboarding cost per hire: $3,000-$4,500 (SHRM 2024)
- HR time spent on admin: 57% (Deloitte Human Capital Trends 2025)
- Current AI onboarding adoption in mid-market: 34% (SHRM Talent Trends 2025)

---

## Competitive Landscape

**Competitor Matrix:**

| | Workday | BambooHR | Rippling | Leena AI | Paradox (Olivia) |
|---|---|---|---|---|---|
| **Category** | Full HCM suite | HRIS for SMB/mid-market | Workforce platform (HR+IT+Finance) | AI employee experience | Conversational recruiting AI |
| **Pricing** | Per-employee, multi-year; $4-$11/seat/mo + $4K annual min | $10-$25 PEPM | $8 PEPM base + $35-40/mo flat | $150/emp/yr (1,000 seat min) | ~$1,000/mo starting; enterprise $25K-$150K+/yr |
| **Deployment** | 4-6 months | 2-4 weeks | 2-4 weeks; $1,500-$20,000 impl. fee | 45-90 days | Enterprise sales cycle, $15K-$35K setup |
| **Target** | Enterprise (5,000+) | SMB (25-500) | SMB/mid-market (50-5,000) | Enterprise (1,000+) | Enterprise/franchise |
| **AI Capability** | Illuminate agents (6 agents rolling out 2026) | Rule-based + basic AI assistant | Workflow Studio (no-code, rule-based) | Agentic AI, 70%+ ticket resolution | Conversational AI (recruiting-focused) |
| **Key Weakness** | Overkill for mid-market; slow; expensive | Not agent-native; limited automation depth | Broad but shallow; AI bolted on | Too expensive for mid-market | Narrow to recruiting; enterprise pricing |

**OnboardAI occupies the white space: agent-native + mid-market price.**

**Competitive Gaps (OnboardAI's Openings):**
1. No agent-native onboarding tool for mid-market
2. No competitor offers inference-aware/hybrid pricing
3. No competitor deploys in an afternoon
4. Mid-market (500-2,000 employees) is overlooked
5. HR team time recovery is the wedge, not chat

**Top Risks:**

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| Workday/Leena AI drop price for mid-market | Low (12-24 mo) | High | Build workflow depth + HRIS integration moat |
| BambooHR/Rippling add agentic AI | Medium (12-18 mo) | Medium | First-mover advantage; they need architectural change |
| Buyers prefer bundled HRIS + onboarding | Medium | Medium | Position as complement, not replacement |
| AI onboarding commoditized by OpenAI/Anthropic | Low (12-24 mo) | High | Moat = workflow depth + vertical distribution |

---

## 7-Day Roll-Out

- **Day 1** — Plan approved, kickoff
- **Day 2** — PRD, research, tech stack ready
- **Day 3** — Core build sprint
- **Day 4** — Integration & workflows
- **Day 5** — Manager flows & exception handling
- **Day 6** — QA, polish, demo prep
- **Day 7** — Launch 🚀

---

## Key Assumptions

1. Ira's research confirms onboarding as top-3 HR pain point ✓ (validated)
2. Founder's network yields 5+ pilot introductions
3. Zoe delivers core MVP in 5 build days
4. Inference costs stay at ~$0.002/1K tokens
5. No regulatory blocker for AI onboarding (US-first)

---

## Related

- [[Ava]] — Business Strategist
- [[Ira]] — Market Research (research inputs received 2026-09-04)
- [[Leo]] — Product Manager
- [[OnboardAI]] — Beachhead product
- [[Projects/Paperclip]] — Product context
- [[Research/Market-Analysis]] — Market sizing analysis
- [[Research/Competitor-Research]] — Competitor deep-dive
