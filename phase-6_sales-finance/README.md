# Stage 2 — Phase 6: Sales & Finance (22 agents)

> **Build order:** Built AFTER Phase 5 is complete. These agents cover sales and finance functions under Vikram (AI CGO) and Niti (AI CFO).
>
> **Status:** Each agent has a full production-grade specification document (matching the Stage 1 Arjun SAM-AG-001 template — 18 sections: identity card, authority matrix enforced in code, workflows, tools, system prompt, pass+deliberate-fail test scenarios, DB schema, pytest scaffolding, build checklist).

## Overview

Phase 6 builds the revenue and financial backbone: **SAL** (Sales & Business Development) owns the entire sales funnel from market identification to signed agreements; **FIN** (Finance & Administration) handles invoicing, collections, financial analysis, and reporting.

**Reports to:**
- SAL agents → Vikram (SAM-AG-005, AI CGO) → Arjun (SAM-AG-001)
- FIN agents → Niti (SAM-AG-006, AI CFO) → Arjun (SAM-AG-001)

---

## SAL DEPARTMENT — Sales & Business Development (9 agents)

| # | Agent | Canonical ID | Position | Spec |
|---|-------|-------------|----------|------|
| 1 | Vikram | SAM-AG-005 | CGO-001 | [AI CGO (Chief Growth Officer)](SAM-AG-005_Vikram_AI-CGO.md) |
| 2 | Aarav | SAM-AG-016 | SAL-001 | [Sales Operations & Pipeline Lead](SAM-AG-016_Aarav_Sales-Operations-Pipeline.md) |
| 3 | Khoj | SAM-AG-018 | SAL-002 | [Prospect Research & Market Intelligence](SAM-AG-018_Khoj_Prospect-Research.md) |
| 4 | Lakshit | SAM-AG-019 | SAL-003 | [Lead Qualification & Scoring](SAM-AG-019_Lakshit_Lead-Qualification.md) |
| 5 | Sampark | SAM-AG-020 | SAL-004 | [Outbound Prospecting & Outreach](SAM-AG-020_Sampark_Outbound-Outreach.md) |
| 6 | Amantran | SAM-AG-021 | SAL-005 | [Meeting & Appointment Coordination](SAM-AG-021_Amantran_Meeting-Scheduling.md) |
| 7 | Prastav | SAM-AG-023 | SAL-006 | [Solution Design & Proposal](SAM-AG-023_Prastav_Solution-Design-Proposal.md) |
| 8 | Anugrah | SAM-AG-025 | SAL-007 | [Sales Follow-up & Nurturing](SAM-AG-025_Anugrah_Sales-Followup.md) |
| 9 | Setu | SAM-AG-027 | SAL-008 | [Sales-to-Delivery Handover](SAM-AG-027_Setu_Sales-to-Delivery-Handover.md) |

**Mandate:** Build a predominantly AI-operated revenue acquisition engine that identifies healthcare businesses, creates qualified opportunities, manages outreach/follow-ups, supports consultations/proposals, and converts opportunities into profitable long-term clients. Owns the funnel from market identification to signed agreements → handover to Client Experience.

**Key distinction from Marketing:** Marketing generates demand; Sales qualifies, reaches out, meets, proposes, negotiates, converts.

**Sales workflow:** ICP development → Market segmentation → Target account ID → Prospect research → Lead enrichment/scoring → Outbound prep → Outreach → Inbound qualification → Appointment booking → Discovery → Solution design → Proposal → Follow-up/nurturing → Conversion → Client handover → Account expansion.

---

## FIN DEPARTMENT — Finance & Administration (13 agents)

| # | Agent | Canonical ID | Position | Spec |
|---|-------|-------------|----------|------|
| 10 | Niti | SAM-AG-006 | CFO-001 | [AI CFO (Chief Financial Officer)](SAM-AG-006_Niti_AI-CFO.md) |
| 11 | Lekhan | SAM-AG-134 | FIN-001 | [Invoicing](SAM-AG-134_Lekhan_Invoicing.md) |
| 12 | Dhanika | SAM-AG-135 | FIN-002 | [Collections](SAM-AG-135_Dhanika_Collections.md) |
| 13 | Arth | SAM-AG-136 | FIN-003 | [Financial Analysis](SAM-AG-136_Arth_Financial-Analysis.md) |
| 14 | Vidhi | SAM-AG-138 | FIN-004 | [Expense Management](SAM-AG-138_Vidhi_Expense-Management.md) |
| 15 | Beejak | SAM-AG-139 | FIN-005 | [Budgeting](SAM-AG-139_Beejak_Budgeting.md) |
| 16 | Vasooli | SAM-AG-140 | FIN-006 | [Payment Processing](SAM-AG-140_Vasooli_Payment-Processing.md) |
| 17 | Milaan | SAM-AG-141 | FIN-007 | [Reconciliation](SAM-AG-141_Milaan_Reconciliation.md) |
| 18 | Bhugtan | SAM-AG-142 | FIN-008 | [Vendor Payments](SAM-AG-142_Bhugtan_Vendor-Payments.md) |
| 19 | Kosh | SAM-AG-143 | FIN-009 | [Treasury](SAM-AG-143_Kosh_Treasury.md) |
| 20 | Labh | SAM-AG-145 | FIN-010 | [Profit Optimization](SAM-AG-145_Labh_Profit-Optimization.md) |
| 21 | LekhaPatra | SAM-AG-149 | FIN-011 | [Accounting Records](SAM-AG-149_LekhaPatra_Accounting-Records.md) |
| 22 | Vittadarshi | SAM-AG-152 | FIN-012 | [Financial Reporting](SAM-AG-152_Vittadarshi_Financial-Reporting.md) |

**Mandate:** Financial intelligence, invoicing, profitability, collections, expenses, vendor coordination. Under Niti (AI CFO).

---

## Authority Principles

- **Rule 07 — Financial control (CRITICAL):** Agents cannot independently authorise or execute financial transfers. All payments, invoicing approvals, and financial commitments require human authority. Lekhan prepares invoices but cannot dispatch without approval; Vasooli/Bhugtan coordinate payment processing but human approves actual money movement.
- **Rule 08 — Client protection:** Client data must remain isolated according to approved permissions (tenant isolation mandatory).
- External prospect communications, pricing commitments and contract decisions require defined human authority.
- No delivery agent should independently promise additional scope, altered timelines, discounts or performance guarantees to clients.
- Niti (CFO) coordinates financial intelligence but cannot independently approve capital allocation or sign financial commitments.
- Independent Assurance (Satya) audits financial controls; Lekhapari (GOV-014) performs financial & operational audit independently.

## Cross-Department Interfaces

- SAL ↔ MKT: Lead handoff — Marketing generates inbound, Sales qualifies. Lead enters sales pipeline only after meeting agreed qualification criteria.
- SAL ↔ CEX: Handover after deal closure (Setu).
- SAL ↔ DAT: Revenue intelligence, forecasting data.
- FIN ↔ OPS: Delivery cost data, resource costing.
- FIN ↔ GOV: Financial audit, compliance.
