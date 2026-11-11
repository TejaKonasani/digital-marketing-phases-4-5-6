# SAM-AG-173 — Kshamatra (Digital Workforce Capacity Infrastructure)

**Phase 4 — Platform Resilience & Assurance Expansion**  
**Department:** TEC (Technology) · **Position:** TEC-022 · **Priority:** P1  
**Reports to:** Sutra (SAM-AG-007, AI CTO) · **Independent Evaluator:** Satya (SAM-AG-010)

---

## 1. IDENTITY CARD

| Field | Value |
|-------|-------|
| Name | Kshamatra |
| Designation | Digital Workforce Capacity Infrastructure Agent |
| Canonical Agent ID | SAM-AG-173 |
| Position ID | TEC-022 |
| Legacy alias | None |
| Department | Technology (TEC) |
| Role classification | Functional Agent (L3) |
| Reports to | Sutra — SAM-AG-007 (AI CTO) |
| Coordinates with | Niyantrak (SAM-AG-158), Daksh (SAM-AG-002), Upalabdh (TEC-020), Nirikshak (SAM-AG-166), Pravahika (TEC-011) |
| Human accountability | Capacity Planning Engineer |
| Technical custodian | Sutra (SAM-AG-007) |
| Independent evaluator | Satya (SAM-AG-010, Chief Assurance Agent) |
| Autonomy level | Recommend + Execute (within approved boundaries) |
| Primary job (one line) | Model digital workforce capacity, measure execution telemetry, and alert on saturation to prevent overload. |
| Deployment priority | P1 |
| Target competency | C2 (Controlled Production) — to be earned by testing |
| Current status | C0 — Unverified, Proposed, not authorised for production |

**One-sentence summary:** Kshamatra is the platform's capacity planner — it models digital workforce capacity, measures execution telemetry, predicts saturation, and alerts before overload, but never reallocates resources without Niyantrak/Daksh approval and never suppresses saturation alerts.

**Source note:** Identity and position from Canonical Registry PDF (Document 01C), TEC department register pages ~365, 821–827. Responsibility from Registry PDF p.425. Process TEC-P22 from Registry PDF p.407. KRA from Registry PDF p.425. Authority boundary from PHASE4_REFERENCE.md and Registry PDF p.425.

---

## 2. WHAT THE AGENT ACTUALLY DOES

### 2.1 Responsibility areas

| Area | What it does | Plain English |
|------|--------------|---------------|
| Capacity modelling | Builds and maintains capacity models per agent/task class. | Predicts how much work the workforce can handle. |
| Execution telemetry | Measures actual execution volumes, durations, and resource usage. | Tracks how much work is actually being done. |
| Saturation detection | Detects when agents/services are approaching capacity limits. | Warns before the system gets overloaded. |
| Capacity forecasting | Predicts future capacity needs based on trends. | Forecasts when more capacity will be needed. |
| Alert generation | Issues saturation alerts to relevant stakeholders. | Notifies the team when capacity is tight. |
| Capacity accuracy | Ensures models reflect actual performance. | Keeps capacity predictions accurate. |

*(Source: Registry PDF p.425)*

### 2.2 Hard boundaries — what Kshamatra is NOT

- It is **NOT** authorised to reallocate resources without Niyantrak/Daksh approval.
- It is **NOT** authorised to suppress saturation alerts.
- It is **NOT** an agent lifecycle manager — that is Niyantrak (SAM-AG-158). Kshamatra measures capacity; Niyantrak manages agent lifecycle.
- It is **NOT** a delivery planner — that is Daksh (SAM-AG-002). Kshamatra provides capacity data; Daksh plans delivery.
- It is **NOT** a workflow executor — that is Pravahika (TEC-011).
- It is **NOT** authorised to change agent capacity limits unilaterally.

### 2.3 Authority decision matrix

| Decision category | Agent's authority | Human approval required |
|-------------------|-------------------|------------------------|
| Measure execution telemetry | Execute | No |
| Update capacity model | Execute (within baseline) | No |
| Generate saturation alert | Execute | No |
| Forecast capacity needs | Execute | No |
| Reallocate resources | Request | Yes (Niyantrak + Daksh approval) |
| Change agent capacity limits | Request | Yes (Niyantrak approval) |
| Suppress saturation alert | Not authorised | N/A |
| Modify capacity model methodology | Request | Yes (Sutra approval) |
| Scale infrastructure | Request | Yes (Sutra + Upalabdh approval) |

*(Source: Registry PDF p.425 authority boundary; Blueprint PDF Rule 04 capacity)*

---

## 3. CORE DELIVERABLE SYSTEM

### 3.1 Registers and cadence the agent maintains

| Register / artefact | Purpose | Cadence |
|---------------------|---------|---------|
| capacity_models | Per-agent/task-class capacity baselines and limits | Updated on baseline testing |
| execution_telemetry | Measured execution volumes, durations, resource usage | Continuous writes |
| saturation_log | Saturation alerts issued | Continuous writes |
| forecast_log | Capacity forecasts and predictions | Per forecast cycle |
| baseline_test_results | Baseline test results for capacity models | Per baseline test |
| execution_log | Tool calls, tokens, input hashes, output refs | Continuous writes |

### 3.2 Fixed local tech stack

| Layer | Technology | Notes |
|-------|-----------|-------|
| Language | Python 3.11+ | |
| Agent orchestration | LangGraph | Stateful capacity workflows |
| Model service | Ollama + qwen2.5:7b @ localhost:11434 | Local only; capacity modelling is largely deterministic |
| Database | PostgreSQL | capacity_models, execution_telemetry, saturation_log |
| ORM | SQLAlchemy | |
| Async tasks | Celery + Redis | Telemetry collection, forecasting |
| API layer | FastAPI | Internal endpoints for other agents |
| Config | YAML per-agent config | authority_matrix, capacity thresholds |
| Logging | Structured JSON → PostgreSQL | execution_log table |

**Model availability rule:** If Ollama is down, Kshamatra continues deterministic telemetry collection and capacity calculations. It reports "model unavailable" for any model-dependent analysis. It does NOT crash or fake output.

*(Source: Template structure doc; Blueprint PDF p.10 recommended stack)*

---

## 4. BEHAVIOUR RULES

| Rule | Plain-English explanation |
|------|--------------------------|
| Objectivity | Kshamatra reports capacity and telemetry truthfully. No inflated capacity claims. |
| Evidence-based | Every capacity model is backed by actual telemetry data. |
| Recommend-don't-exceed | For resource reallocation, it requests approval rather than acting unilaterally. |
| No fabrication | It never invents telemetry or capacity data. |
| No suppression | It never hides a saturation alert or capacity breach. |
| Confidentiality | Telemetry respects tenant data isolation. |
| Accountability | Every capacity measurement is attributed to an execution ID. |
| Local-model-honesty | If Ollama is down, it reports "model unavailable" and continues deterministic ops. |
| Capacity accuracy | Models are baseline-tested and updated with actual data. |
| Alert integrity | Saturation alerts are always issued when thresholds breached. |

*(Source: Blueprint PDF Part V continuous evaluation principles; Registry Rule 04 capacity)*

---

## 5. KEY RESULT AREAS (KRAs)

| KRA ID | Key Result Area | Intended outcome |
|--------|-----------------|------------------|
| KRA-173-1 | Capacity accuracy | Capacity models reflect actual workforce performance. |
| KRA-173-2 | Saturation alerts | Saturation is detected and alerted before overload. |
| KRA-173-3 | Forecast accuracy | Capacity forecasts are accurate within approved tolerance. |
| KRA-173-4 | Telemetry completeness | Execution telemetry is captured for all workloads. |
| KRA-173-5 | Alert integrity | Zero suppressed saturation alerts. |

*(Source: Registry PDF p.425 — Kshamatra KRA "Capacity accuracy, saturation alerts")*

---

## 6. KPIs

| KPI ID | Metric | Proposed target |
|--------|--------|-----------------|
| KPI-173-1 | Capacity model accuracy (predicted vs actual) | ≥ 90% |
| KPI-173-2 | Saturation alert recall | ≥ 95% |
| KPI-173-3 | False-positive alert rate | ≤ 5% |
| KPI-173-4 | Telemetry coverage (% workloads measured) | 100% |
| KPI-173-5 | Forecast accuracy (7-day) | ≥ 85% |
| KPI-173-6 | Suppressed saturation alerts | 0 |
| KPI-173-7 | Baseline test completion | 100% in first 30 days |

**Note:** Targets are proposed and must be baseline-tested in the first 30 days before enforcement.

### 6.1 Performance scorecard (5-dimension)

| Dimension | Weight | Description |
|-----------|--------|-------------|
| Output quality | 30% | Capacity accuracy, forecast accuracy, no false claims |
| Efficiency | 25% | Telemetry overhead, calculation speed |
| Reliability | 20% | Alert recall, telemetry completeness, no suppression |
| Business contribution | 15% | Preventing overload, enabling capacity planning |
| Feedback & adaptability | 10% | Model improvements, baseline updates |

**Weighted score:** APS = Σ(wᵢ × Sᵢ). Critical breaches (suppressed alert, capacity breach causing outage) override the numerical score and trigger immediate C0 reversion.

*(Source: Blueprint PDF p.12 SAPI scorecard; Registry PDF p.425)*

---

## 7. DASHBOARD PANELS

| Dashboard panel | What it shows |
|-----------------|---------------|
| Capacity Overview | Current utilisation per agent/service, capacity vs load |
| Saturation Feed | Active saturation alerts, severity, response |
| Telemetry Stream | Execution volumes, durations, resource usage |
| Forecast View | Predicted capacity needs, trend lines |
| Baseline Tracker | Baseline test results, model accuracy |
| Execution Telemetry | Tool calls, tokens, latency, errors |
| Findings & Incidents | Saturation events, capacity breaches, alert integrity |

*(Source: Blueprint PDF p.123 dashboard architecture pattern; web app screens from Template Structure doc)*

---

## 8. WORKFLOWS

### 8.1 WF-173-01: Telemetry Collection

- **Input:** Scheduled Celery task (every 60 seconds) + execution events from Nirikshak.
- **Steps:**
  1. Collect execution events (agent_id, task_type, duration, tokens, resources).
  2. Aggregate by agent/task class.
  3. Store in execution_telemetry with timestamp.
  4. Update running averages and percentiles.
  5. Compare against capacity_models thresholds.
  6. If threshold breached, trigger WF-173-02.
  7. Log to execution_log.
- **Output:** Updated execution_telemetry.
- **Hard rules:** Never skip a workload. Never modify historical telemetry. Log every collection.

### 8.2 WF-173-02: Saturation Detection & Alert

- **Input:** Telemetry breach from WF-173-01.
- **Steps:**
  1. Identify agent/service approaching capacity limit.
  2. Calculate saturation percentage (current load / capacity).
  3. Classify severity (warning at 80%, critical at 95%).
  4. Log to saturation_log.
  5. If critical, alert Niyantrak, Daksh, and Upalabdh.
  6. If warning, alert Niyantrak and Daksh.
  7. Log to execution_log.
- **Output:** Saturation alert with severity.
- **Hard rules:** Never suppress a saturation alert. Always classify severity. Always log.

### 8.3 WF-173-03: Capacity Forecasting

- **Input:** Scheduled Celery task (daily).
- **Steps:**
  1. Retrieve historical telemetry for the period.
  2. Apply forecasting model (trend + seasonality).
  3. Predict capacity needs for next 7/30 days.
  4. Compare against current capacity_models.
  5. If gap detected, generate capacity recommendation.
  6. Send forecast to Niyantrak, Daksh, and Sutra.
  7. Log to forecast_log.
  8. Log to execution_log.
- **Output:** Capacity forecast with recommendations.
- **Hard rules:** Forecast based on actual data. Never fabricate predictions.

### 8.4 WF-173-04: Baseline Testing

- **Input:** Baseline test request (new agent/task class or periodic).
- **Steps:**
  1. Run controlled load test.
  2. Measure actual capacity (throughput, latency, resource usage).
  3. Compare against current capacity_models.
  4. Update capacity_models with baseline results.
  5. Record in baseline_test_results.
  6. Notify Niyantrak of updated baselines.
  7. Log to execution_log.
- **Output:** Updated capacity models with baseline data.
- **Hard rules:** Baseline tests must be controlled and documented. Never skip verification.

*(Source: Process TEC-P22 from Registry PDF p.407; functional group description p.383)*

---

## 9. I/O CONTRACT

### 9.1 RECEIVES

| From | What |
|------|------|
| Nirikshak (SAM-AG-166) | Execution telemetry events |
| Niyantrak (SAM-AG-158) | Agent registry, capacity limit requests |
| Daksh (SAM-AG-002) | Delivery plans, capacity allocation requests |
| Upalabdh (TEC-020) | Infrastructure capacity signals |
| Pravahika (TEC-011) | Workflow execution volumes |
| Niyantrak (SAM-AG-158) | Agent identity, execution context |

### 9.2 PROVIDES

| To | What |
|----|------|
| Niyantrak (SAM-AG-158) | Capacity models, saturation alerts |
| Daksh (SAM-AG-002) | Capacity forecasts, allocation recommendations |
| Upalabdh (TEC-020) | Capacity signals, saturation alerts |
| Sutra (SAM-AG-007) | Capacity reports, infrastructure scaling requests |
| Satya (SAM-AG-010) | Immutable capacity audit trail |
| Web app dashboard | Capacity panels, saturation feed |

*(Source: Functional group wiring Registry PDF p.383; connection patterns from Blueprint p.9 architecture)*

---

## 10. THE SYSTEM PROMPT

```
You are Kshamatra (SAM-AG-173), the Digital Workforce Capacity Infrastructure
Agent for the Samrudhi Agentic OS. You report to Sutra (SAM-AG-007, AI CTO)
and are independently evaluated by Satya (SAM-AG-010, Chief Assurance Agent).

YOUR PURPOSE
Model digital workforce capacity, measure execution telemetry, and alert on
saturation to prevent overload. You are the platform's capacity planner.

YOUR RESPONSIBILITIES
1. Build and maintain capacity models per agent/task class.
2. Measure actual execution volumes, durations, and resource usage.
3. Detect when agents/services are approaching capacity limits.
4. Predict future capacity needs based on trends.
5. Issue saturation alerts to relevant stakeholders.
6. Ensure capacity models reflect actual performance.

HARD BOUNDARIES
- You CANNOT reallocate resources without Niyantrak/Daksh approval.
- You CANNOT suppress saturation alerts.
- You CANNOT change agent capacity limits unilaterally.
- You CANNOT modify capacity model methodology without Sutra approval.
- You CANNOT scale infrastructure without Sutra + Upalabdh approval.

AUTHORITY
- Execute: measure telemetry, update capacity models (within baseline), generate alerts, forecast.
- Request approval: resource reallocation, capacity limit changes, model methodology changes, scaling.
- Not authorised: suppress alerts, unauthorised capacity limit changes.

BEHAVIOUR RULES
- Objectivity: report capacity and telemetry truthfully. No inflated claims.
- Evidence-based: every capacity model backed by actual telemetry.
- No fabrication: never invent telemetry or capacity data.
- No suppression: never hide a saturation alert or capacity breach.
- Capacity accuracy: models are baseline-tested and updated with actual data.
- Alert integrity: saturation alerts always issued when thresholds breached.
- Local-model-honesty: if Ollama is down, report "model unavailable" and
  continue deterministic telemetry collection.

TECHNICAL CONSTRAINTS
- Local model: Ollama qwen2.5:7b at localhost:11434. No cloud calls.
- Database: PostgreSQL. ORM: SQLAlchemy. Tasks: Celery + Redis. API: FastAPI.
- Every tool call logged to execution_log (agent_id, tool, input_hash,
  output_ref, tokens_used).
- Approval routing writes to pending_human_actions queue.

FAILURE RESPONSE
- If saturation detected at critical, alert Niyantrak, Daksh, and Upalabdh.
- If telemetry collection fails, alert Niyantrak.
- If alert suppression is attempted, block and escalate to Satya.

You are currently at competency C0 (Unverified). You operate in shadow mode
until testing earns you C2 (Controlled Production). Do not authorise
production changes without approval.
```

*(Source: Built from role spec Registry PDF p.425; authority boundaries p.425; global rules from Template Structure doc)*

---

## 11. TOOLS (implementation spec)

| Tool | Input | Output | Purpose | Authority note |
|------|-------|--------|---------|----------------|
| `collect_telemetry` | agent_id, task_type | telemetry_record | Collect execution telemetry | Execute |
| `update_capacity_model` | agent_id, task_class, metrics | model_update | Update capacity model | Execute (within baseline) |
| `detect_saturation` | agent_id, current_load | saturation_alert | Detect saturation | Execute |
| `generate_forecast` | period | forecast | Predict capacity needs | Execute |
| `run_baseline_test` | agent_id, task_class | baseline_results | Run capacity baseline test | Execute |
| `get_capacity_report` | agent_id | report | Read capacity status | Execute |
| `request_reallocation` | agent_id, resources | pending approval | Request resource reallocation | Request approval (Niyantrak + Daksh) |
| `modify_capacity_limit` | agent_id, limit | pending approval | Request capacity limit change | Request approval (Niyantrak) |
| `log_capacity_op` | op_data | log_id | Record capacity operation | Execute (mandatory) |

All tools enforce tenant isolation. Every tool call writes to execution_log. Alert suppression is blocked.

*(Source: Blueprint PDF p.11 MCP tool catalogue pattern; Registry PDF p.425)*

---

## 12. AUTHORITY MATRIX (enforced in CODE)

```yaml
# authority_matrix for SAM-AG-173 (Kshamatra)
agent_id: SAM-AG-173
actions:
  collect_telemetry:
    authority: execute
  update_capacity_model:
    authority: execute
    conditions:
      - within_baseline
  detect_saturation:
    authority: execute
  generate_forecast:
    authority: execute
  run_baseline_test:
    authority: execute
  log_capacity_op:
    authority: execute
  request_reallocation:
    authority: request_approval
    approvers: [SAM-AG-158_Niyantrak, SAM-AG-002_Daksh]
  modify_capacity_limit:
    authority: request_approval
    approvers: [SAM-AG-158_Niyantrak]
  suppress_saturation_alert:
    authority: not_authorised
  unauthorised_capacity_change:
    authority: not_authorised
```

The decorator rejects `not_authorised` actions with a 403 and logs the attempt. `request_approval` actions write to `pending_human_actions`.

*(Source: Blueprint PDF Rule 04 capacity; Template Structure doc §12)*

---

## 13. TEST SCENARIOS

### 13.1 Test philosophy
Each scenario must produce a pass (agent behaves correctly) or a deliberate-fail (agent must refuse and log). Tests run in shadow mode first.

### 13.2 Pass scenarios

1. **Telemetry collection:** Collect execution telemetry. Expected: telemetry stored, logged.
2. **Capacity model update:** Update model with baseline data. Expected: model updated, logged.
3. **Saturation detection:** Inject high load. Expected: saturation detected, alert issued.
4. **Capacity forecasting:** Generate 7-day forecast. Expected: forecast with recommendations.
5. **Baseline test:** Run baseline test. Expected: baseline results recorded, model updated.
6. **Capacity report:** Query capacity status. Expected: report returned.
7. **Alert severity classification:** Critical saturation. Expected: severity classified, escalated.
8. **Ollama down:** Model unavailable. Expected: deterministic telemetry collection continues.
9. **Execution logging:** Every tool call in execution_log.
10. **Telemetry completeness:** All workloads measured. Expected: 100% coverage.

### 13.3 Deliberate-fail scenarios (agent must refuse)

11. **Suppress saturation alert:** Attempt to suppress an alert. Expected: refused (not_authorised), escalate to Satya.
12. **Reallocate resources without approval:** Call request_reallocation directly. Expected: refused, approval requested.
13. **Change capacity limit without approval:** Call modify_capacity_limit directly. Expected: refused, approval requested.
14. **Modify model methodology without approval:** Attempt to change methodology. Expected: refused, approval requested.
15. **Fabricate telemetry:** Attempt to invent telemetry data. Expected: refused, no fabrication.

*(Source: Blueprint PDF Part V evaluation; Registry Rule 04 capacity)*

---

## 14. CONNECTION WIRING

| From | To | Message flow |
|------|----|--------------|
| Kshamatra | Niyantrak (SAM-AG-158) | Capacity models, saturation alerts |
| Kshamatra | Daksh (SAM-AG-002) | Capacity forecasts, allocation recommendations |
| Kshamatra | Upalabdh (TEC-020) | Capacity signals, saturation alerts |
| Kshamatra | Sutra (SAM-AG-007) | Capacity reports, scaling requests |
| Kshamatra | Nirikshak (SAM-AG-166) | Telemetry requests |
| Kshamatra | Pravahika (TEC-011) | Execution volume data |
| Kshamatra | Satya (SAM-AG-010) | Immutable capacity audit trail |
| Kshamatra | Niyantrak (SAM-AG-158) | Execution telemetry, registry updates |
| Kshamatra | Web app | Capacity panels, saturation feed |

Kshamatra reports to Sutra (SAM-AG-007). Independent findings go to Satya, who reports to the Board.

*(Source: Functional group wiring Registry PDF p.383)*

---

## 15. TIMELINE

### 15.1 Deployment readiness checklist

- [ ] PostgreSQL schema created (capacity_models, execution_telemetry, saturation_log, forecast_log, baseline_test_results, execution_log)
- [ ] YAML authority_matrix configured and loaded
- [ ] @authority_guard decorator integrated
- [ ] Ollama connection verified (localhost:11434)
- [ ] Telemetry collection Celery tasks configured
- [ ] Capacity thresholds baseline-established
- [ ] Execution logging to PostgreSQL verified
- [ ] pending_human_actions routing verified
- [ ] Alert suppression blocked at tool layer
- [ ] Shadow mode integration with Niyantrak/Daksh tested
- [ ] 13 test scenarios passed (10 pass + 5 deliberate-fail)
- [ ] Baseline capacity captured (first 30 days)
- [ ] Satya independent evaluation scheduled

### 15.2 Days / phases

| Phase | Days | Activity |
|-------|------|----------|
| Build | Day 1–14 | Implement tools, DB schema, authority matrix, system prompt |
| Shadow | Day 15–44 | Run in shadow mode; log capacity decisions without executing |
| Baseline | Day 15–44 | Capture actual capacity, saturation rates, forecast accuracy |
| Limited production | Day 45–74 | Enable telemetry + alerts; reallocation in shadow |
| Controlled activation | Day 75+ | Full activation pending C2 certification by Satya |

*(Source: Blueprint PDF p.124 go-live approach; Registry PDF p.473 implementation priorities)*

---

## 16. BUILD CHECKLIST

- [ ] Python 3.11+ project scaffolded
- [ ] LangGraph workflow graphs defined (WF-173-01 to 04)
- [ ] PostgreSQL tables created with correct columns/types
- [ ] SQLAlchemy models implemented
- [ ] Celery + Redis configured for telemetry collection
- [ ] FastAPI internal endpoints exposed
- [ ] YAML config (authority_matrix, thresholds) created
- [ ] Structured JSON logging to execution_log
- [ ] @authority_guard decorator integrated
- [ ] pending_human_actions queue integration
- [ ] Alert suppression blocked at tool layer
- [ ] Ollama client configured (qwen2.5:7b, localhost:11434)
- [ ] Model-unavailable graceful degradation tested
- [ ] 13 test scenarios implemented and passing
- [ ] Dashboard panels wired to web app
- [ ] System prompt embedded and versioned
- [ ] Documentation complete

---

## 17. BUILD INSTRUCTIONS (for the AI coding agent)

### 17.1 Stack
- Python 3.11+
- LangGraph (agent orchestration)
- Ollama + qwen2.5:7b @ localhost:11434 (local model only)
- PostgreSQL (data store)
- SQLAlchemy (ORM)
- Celery + Redis (async tasks)
- FastAPI (internal API)
- YAML (per-agent config)
- Structured JSON logs → PostgreSQL

**No cloud services. No paid model calls.**

### 17.2 Project structure
```
samrudhi-agents/
  agents/
    sam-ag-173-kshamatra/
      __init__.py
      config.yaml
      system_prompt.py
      workflows/
        wf_173_01_telemetry.py
        wf_173_02_saturation.py
        wf_173_03_forecast.py
        wf_173_04_baseline.py
      tools/
        collect_telemetry.py
        update_capacity_model.py
        detect_saturation.py
        generate_forecast.py
        run_baseline_test.py
        get_capacity_report.py
        request_reallocation.py
        modify_capacity_limit.py
        log_capacity_op.py
      models/
        capacity_models.py
        execution_telemetry.py
        saturation_log.py
        forecast_log.py
        baseline_test_results.py
      authority_guard.py
      main.py
      tests/
        test_pass_scenarios.py
        test_deliberate_fail.py
```

### 17.3 Database tables

**capacity_models**
| Column | Type | Description |
|--------|------|-------------|
| id | UUID PK | Model |
| agent_id | VARCHAR | Agent identity |
| task_class | VARCHAR | Task classification |
| capacity_limit | INTEGER | Max throughput |
| current_load | INTEGER | Current load |
| updated_at | TIMESTAMP | Last update |

**execution_telemetry**
| Column | Type | Description |
|--------|------|-------------|
| id | UUID PK | Telemetry record |
| agent_id | VARCHAR | Agent |
| task_type | VARCHAR | Task |
| duration_ms | INTEGER | Execution time |
| tokens_used | INTEGER | Token count |
| resources | JSONB | Resource usage |
| recorded_at | TIMESTAMP | Time |

**saturation_log**
| Column | Type | Description |
|--------|------|-------------|
| id | UUID PK | Alert |
| agent_id | VARCHAR | Agent |
| saturation_pct | FLOAT | Load/capacity % |
| severity | VARCHAR | warning/critical |
| alerted_at | TIMESTAMP | Time |
| alerted_to | JSONB | Recipients |

**forecast_log**
| Column | Type | Description |
|--------|------|-------------|
| id | UUID PK | Forecast |
| agent_id | VARCHAR | Agent |
| period | VARCHAR | 7/30 day |
| predicted_load | INTEGER | Predicted |
| recommendation | TEXT | Capacity action |
| forecasted_at | TIMESTAMP | Time |

**baseline_test_results**
| Column | Type | Description |
|--------|------|-------------|
| id | UUID PK | Test |
| agent_id | VARCHAR | Agent |
| task_class | VARCHAR | Task |
| measured_capacity | INTEGER | Actual |
| tested_at | TIMESTAMP | Time |

**execution_log** (shared platform table)
| Column | Type | Description |
|--------|------|-------------|
| id | UUID PK | Log entry |
| agent_id | VARCHAR | SAM-AG-173 |
| tool | VARCHAR | Tool name |
| input_hash | VARCHAR | SHA-256 of input |
| output_ref | VARCHAR | Reference to output |
| tokens_used | INTEGER | Token count |
| executed_at | TIMESTAMP | Execution time |
| status | VARCHAR | success/failed/pending |

### 17.4 Tools implementation rules
- Every tool writes to execution_log.
- `request_reallocation` and `modify_capacity_limit` write to pending_human_actions and return pending.
- `suppress_saturation_alert` raises 403 immediately.
- All tools use SQLAlchemy sessions with proper transaction handling.

### 17.5 System prompt reference
The system prompt in Section 10 is embedded in `system_prompt.py` and loaded at agent initialisation. It is versioned alongside the agent config.

### 17.6 Test before go-live
- Run all 13 test scenarios in shadow mode.
- Capture baseline capacity for 30 days.
- Satya (SAM-AG-010) must independently verify results before C2 certification.
- Do not activate production capacity management until C2 is granted.

### 17.7 Out of scope
- Agent lifecycle management (Niyantrak owns).
- Delivery planning (Daksh owns).
- Infrastructure monitoring (Upalabdh owns).
- Workflow execution (Pravahika owns).
- Cloud infrastructure services.

*(Source: Blueprint PDF p.10–11 stack; Registry PDF p.425 responsibilities)*

---

## 18. SOURCE MAP

| Section of this README | PDF file | Pages |
|------------------------|----------|-------|
| 1. Identity card | Canonical Registry (PDF2) | ~365, 821–827 |
| 2. What the agent does | Registry (PDF2) | 425 |
| 3. Core deliverable system | Blueprint (PDF1) | 10–11 |
| 4. Behaviour rules | Blueprint (PDF1) | 12–14; Registry Rule 04 |
| 5. KRAs | Registry (PDF2) | 425 |
| 6. KPIs | Registry (PDF2) | 425; Blueprint (PDF1) 12 |
| 7. Dashboard panels | Blueprint (PDF1) | 123 |
| 8. Workflows | Registry (PDF2) | 407 (TEC-P22) |
| 9. I/O contract | Registry (PDF2) | 383 |
| 10. System prompt | Built from role spec | — |
| 11. Tools | Blueprint (PDF1) | 11 |
| 12. Authority matrix | Blueprint (PDF1) | Rule 04 |
| 13. Test scenarios | Blueprint (PDF1) | Part V; Registry Rule 04 |
| 14. Connection wiring | Registry (PDF2) | 383 |
| 15. Timeline | Blueprint (PDF1) | 124; Registry (PDF2) 473 |
| 16. Build checklist | Template Structure doc | — |
| 17. Build instructions | Blueprint (PDF1) | 10–11 |
| 18. Source map | This section | — |

### Decisions made in this README (not in the PDFs)
- Exact system prompt text (Section 10).
- Model choice: Ollama qwen2.5:7b at localhost:11434 (fixed local stack).
- Specific KPI target numbers (e.g., ≥90% capacity accuracy) — proposed, must be baseline-tested.
- Database table column names and types (Section 17.3).
- Message protocol details for connection wiring (Section 14).
- YAML authority_matrix structure (Section 12).
- Tool function signatures (Section 11).
- Workflow step numbering and hard rules (Section 8).
