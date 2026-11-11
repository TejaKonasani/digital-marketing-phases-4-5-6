# Stage 2 — Phase 5: Growth — Paid Media, SEO & Samrudhi Marketing (23 agents)

> **Build order:** Built AFTER Phase 4 is complete. These agents cover paid media, SEO, and Samrudhi's own marketing under Tejas (AI Head of Performance & Growth Marketing).
>
> **Status:** Each agent has a full production-grade specification document (matching the Stage 1 Arjun SAM-AG-001 template — 18 sections: identity card, authority matrix enforced in code, workflows, tools, system prompt, pass+deliberate-fail test scenarios, DB schema, pytest scaffolding, build checklist).

## Overview

Phase 5 builds the growth engine: **PMG** (Paid Media, SEO & Growth Marketing) delivers paid media/SEO services for Samrudhi's clients; **MKT** (Samrudhi Brand & Marketing) generates demand for Samrudhi itself.

**Reports to:**
- PMG agents → Tejas (SAM-AG-008) → Daksh (SAM-AG-002, AI COO) → Arjun (SAM-AG-001)
- MKT agents → Vikram (SAM-AG-005, AI CGO) → Arjun (SAM-AG-001)

---

## PMG DEPARTMENT — Paid Media, SEO & Growth Marketing (14 agents)

| # | Agent | Canonical ID | Position | Spec |
|---|-------|-------------|----------|------|
| 1 | Tejas | SAM-AG-008 | PMG-001 | [AI Head of Performance & Growth Marketing](SAM-AG-008_Tejas_Head-Performance-Growth-Marketing.md) |
| 2 | Lakshman | SAM-AG-097 | PMG-002 | [Paid Media Strategy & Campaign Lead](SAM-AG-097_Lakshman_Paid-Media-Strategy.md) |
| 3 | Arohan | SAM-AG-098 | PMG-003 | [SEO & Organic Growth Lead](SAM-AG-098_Arohan_SEO-Organic-Growth.md) |
| 4 | Metrika | SAM-AG-100 | PMG-005 | [Marketing Measurement & Attribution Lead](SAM-AG-100_Metrika_Marketing-Measurement.md) |
| 5 | Raksha | SAM-AG-101 | PMG-006 | [Campaign Quality & Compliance Lead](SAM-AG-101_Raksha_Campaign-Quality-Compliance.md) |
| 6 | Khojika | SAM-AG-102 | PMG-007 | [Keyword & Audience Research](SAM-AG-102_Khojika_Keyword-Audience-Research.md) |
| 7 | Abhikalp | SAM-AG-103 | PMG-008 | [Campaign Architecture & Setup](SAM-AG-103_Abhikalp_Campaign-Architecture.md) |
| 8 | Boli | SAM-AG-104 | PMG-009 | [Bidding & Budget Pacing](SAM-AG-104_Boli_Bidding-Budget-Pacing.md) |
| 9 | Lakshyaved | SAM-AG-105 | PMG-010 | [Campaign Optimisation](SAM-AG-105_Lakshyaved_Campaign-Optimisation.md) |
| 10 | Sandarbh | SAM-AG-106 | PMG-011 | [Ad Copy & Creative Brief](SAM-AG-106_Sandarbh_Ad-Copy-Creative-Brief.md) |
| 11 | Anveshana | SAM-AG-108 | PMG-013 | [SEO Keyword & Search Intent](SAM-AG-108_Anveshana_SEO-Keyword-Search-Intent.md) |
| 12 | Maapan | SAM-AG-112 | PMG-017 | [Conversion Tracking & Tagging](SAM-AG-112_Maapan_Conversion-Tracking-Tagging.md) |
| 13 | Vishleshan | SAM-AG-113 | PMG-018 | [Campaign Analytics & Insight](SAM-AG-113_Vishleshan_Campaign-Analytics-Insight.md) |
| 14 | Prahari | SAM-AG-115 | PMG-020 | [Budget Anomaly & Policy Risk Monitoring](SAM-AG-115_Prahari_Budget-Anomaly-Policy-Risk.md) |

**Functional groups:** Performance & Growth Leadership (Tejas); Paid Media Strategy & Execution (Lakshman + Khojika, Abhikalp, Boli, Lakshyaved, Sandarbh); SEO & Organic Growth (Arohan + Anveshana); Marketing Measurement & Attribution (Metrika + Maapan, Vishleshan); Campaign Quality & Compliance (Raksha + Prahari).

**Workflow:** Client Goals → Market Intelligence → Channel Strategy → Creative/Funnel → Tracking/Quality Gates → Controlled Launch → Monitoring/Optimisation → Reporting/Learning.

---

## MKT DEPARTMENT — Samrudhi Brand & Marketing (9 agents)

| # | Agent | Canonical ID | Position | Spec |
|---|-------|-------------|----------|------|
| 15 | Prerna | SAM-AG-028 | MKT-001 | [Brand Inspiration](SAM-AG-028_Prerna_Brand-Inspiration.md) |
| 16 | Aditi | SAM-AG-029 | MKT-002 | [Brand Identity](SAM-AG-029_Aditi_Brand-Identity.md) |
| 17 | Uday | SAM-AG-030 | MKT-003 | [Brand Growth](SAM-AG-030_Uday_Brand-Growth.md) |
| 18 | Vaani | SAM-AG-031 | MKT-004 | [Brand Voice](SAM-AG-031_Vaani_Brand-Voice.md) |
| 19 | Spandan | SAM-AG-033 | MKT-005 | [Brand Engagement](SAM-AG-033_Spandan_Brand-Engagement.md) |
| 20 | Katha | SAM-AG-035 | MKT-006 | [Brand Storytelling](SAM-AG-035_Katha_Brand-Storytelling.md) |
| 21 | Tarang | SAM-AG-036 | MKT-007 | [Brand Reach](SAM-AG-036_Tarang_Brand-Reach.md) |
| 22 | Pravah | SAM-AG-041 | MKT-008 | [Brand Flow](SAM-AG-041_Pravah_Brand-Flow.md) |
| 23 | Maanak | SAM-AG-042 | MKT-009 | [Brand Standards](SAM-AG-042_Maanak_Brand-Standards-Enforcement.md) |

**Note:** MKT generates demand for Samrudhi itself (unlike PMG which serves clients). Coordinates with PMG (campaign assets), CRT (Creative production), and SAL (lead handoff). Lead enters sales pipeline only after meeting agreed qualification criteria.

---

## Authority Principles

- No delivery agent should independently promise additional scope, altered timelines, discounts or performance guarantees to clients.
- Tejas cannot independently approve advertising expenditure beyond delegated human-approved limits.
- Raksha coordinates compliance; Independent Assurance (Satya) retains audit authority.
- **Financial control** — Agents cannot independently authorise or execute financial transfers.
- **Client isolation** — PMG agents must not access one client's data for another (tenant isolation).
- Pricing commitments and contract decisions require defined human authority.
