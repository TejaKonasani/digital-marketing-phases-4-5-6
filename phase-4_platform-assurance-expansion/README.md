# Stage 2 — Phase 4: Platform Resilience & Assurance Expansion (13 agents)

> **Build order:** Built AFTER Phase 3 is complete. These agents extend Sutra's (Technology) and Satya's (Assurance) platform capabilities.
>
> **Status:** Each agent has a full production-grade specification document (matching the Stage 1 Arjun SAM-AG-001 template — 18 sections: identity card, authority matrix enforced in code, workflows, tools, system prompt, pass+deliberate-fail test scenarios, DB schema, pytest scaffolding, build checklist).

## Overview

Phase 4 adds operational resilience to the Technology department (Sutra) and expands the independent Assurance office (Satya). All 13 agents are **P1 priority** — built after the P0 foundation is stable.

**Reports to:**
- TEC P1 agents → Sutra (SAM-AG-007, AI CTO)
- GOV P1 agents → Satya (SAM-AG-010, Chief Assurance Agent)

---

## TEC P1 RESILIENCE AGENTS (7)

| # | Agent | Canonical ID | Position | Spec |
|---|-------|-------------|----------|------|
| 1 | Smritikosh | SAM-AG-164 | TEC-013 | [Knowledge Base & Memory Management](SAM-AG-164_Smritikosh_Knowledge-Memory.md) |
| 2 | Margdarshak | SAM-AG-165 | TEC-014 | [Model Routing & Inference Optimisation](SAM-AG-165_Margdarshak_Model-Routing.md) |
| 3 | Punarsthapana | SAM-AG-169 | TEC-018 | [Rollback & Recovery Coordination](SAM-AG-169_Punarsthapana_Rollback-Recovery.md) |
| 4 | Upalabdh | SAM-AG-171 | TEC-020 | [Infrastructure Reliability & Availability](SAM-AG-171_Upalabdh_Infrastructure-Reliability.md) |
| 5 | Sanchay | SAM-AG-172 | TEC-021 | [Data Storage & Retention Management](SAM-AG-172_Sanchay_Data-Storage-Retention.md) |
| 6 | Kshamatra | SAM-AG-173 | TEC-022 | [Digital Workforce Capacity Infrastructure](SAM-AG-173_Kshamatra_Capacity-Infrastructure.md) |
| 7 | Pratikriya | SAM-AG-174 | TEC-023 | [Technology Incident & Problem Management](SAM-AG-174_Pratikriya_Incident-Problem-Management.md) |

**Responsibilities:** Knowledge lifecycle, model routing, recovery/rollback, availability monitoring, data archival, load/capacity modelling, incident response.

---

## GOV P1 ASSURANCE EXPANSION AGENTS (6)

| # | Agent | Canonical ID | Position | Spec |
|---|-------|-------------|----------|------|
| 8 | Vivek | SAM-AG-179 | GOV-005 | [Internal Audit Lead](SAM-AG-179_Vivek_Internal-Audit.md) |
| 9 | Samyak | SAM-AG-180 | GOV-006 | [Incident & CAPA Assurance Lead](SAM-AG-180_Samyak_Incident-CAPA-Assurance.md) |
| 10 | Lekhapari | SAM-AG-188 | GOV-014 | [Financial & Operational Audit](SAM-AG-188_Lekhapari_Financial-Operational-Audit.md) |
| 11 | Vicharana | SAM-AG-190 | GOV-016 | [Incident Investigation](SAM-AG-190_Vicharana_Incident-Investigation.md) |
| 12 | Nivaran | SAM-AG-191 | GOV-017 | [CAPA Verification](SAM-AG-191_Nivaran_CAPA-Verification.md) |
| 13 | Suchita | SAM-AG-194 | GOV-020 | [Governance Reporting](SAM-AG-194_Suchita_Governance-Reporting.md) |

**Responsibilities:** Internal audit, incident/CAPA assurance, financial & operational audit, incident investigation, CAPA verification, governance reporting. Independent of operational departments; findings immutable to audited agents.

---

## Authority Principles

- **Rule 05** — Tool and data access enforced by the platform, not prompts.
- **Rule 06** — Production work must produce sufficient evidence for independent evaluation.
- **Rule 09** — Material agent changes require versioning, testing and approval.
- **Rule 10** — Critical failures trigger containment, escalation and independent verification.
- **Financial control** — Agents cannot independently authorise or execute financial transfers.
- **Client isolation** — Tenant isolation mandatory; no cross-client data access.

## Build Note

> "The P0 capabilities must exist, but they do not require sixteen independent autonomous agents. A small engineering team can initially implement them using existing infrastructure, deterministic services and a limited number of AI assistants." — Blueprint PDF p.473. Apply the same principle here — logical positions, not necessarily separate model instances.
