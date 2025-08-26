# MasterSpec (V4.1-optimized) — Azure Infra Engineer 8‑Week Transformation

**Single source of truth.** Controls daily execution, acceptance, and Go/No‑Go for a \$155K–\$170K remote Azure Infra role. Market “must‑haves”: **Terraform/Bicep, AKS, CI/CD, monitoring/KQL & SRE, Entra (MFA/PIM/CA), Defender/Sentinel, FinOps, DR<15m**; proof via 3 polished repos + demos. &#x20;

---

## 0) Operating Rules (V4.1)

* **Default mode = SPEED.** Use GUIDE MODE only when you type “GUIDE MODE” or for high‑risk steps (PIM/CA, policy‑as‑code, DR).&#x20;
* **Budgets & ephemerals:** Subscription budget **\$150/mo** (80/100% alerts); RG budgets **\$25** for each `rg-ephemeral-*`; one‑command `make up`/`make down`; nightly destroy. Weekends = low‑cost work only. &#x20;
* **Progress is a gate:** After any sub‑step, append `YYYY‑MM‑DD – Completed <Week><Day>-<StepID>` to `progress/progress-log.md`, then commit/push. Missing entry = build failure.&#x20;
* **OpenAI fallback:** If Azure OpenAI isn’t available, continue Week 5; do not block acceptance. Record ADR. &#x20;

---

## 1) Coaching Protocol (enforce every session)

Big picture → Concrete steps → Verify understanding (quiz) → Error prevention (top‑3 pitfalls) → Evidence required → Time awareness → Job relevance → No assumptions → Progressive difficulty → Real‑world focus → Troubleshooting‑first → Performance pressure → Interview readiness → Incident response. &#x20;

---

## 2) Weekly Plan (optimized scope)

**Week 1 – Foundations & Identity**
Entra MFA/CA/PIM; Mgmt Groups + Policy; hub‑spoke + NSGs + Firewall; budgets; Monitor/KQL base. Evidence: `flagship-1-landing-zone/`, 5 troubleshooting logs, peer review + ELI5.&#x20;

**Week 2 – IaC Mastery**
Terraform module library; remote state; CI/CD (validate→plan→apply) with Checkov/tfsec; Key Vault + MI; blue‑green; policy‑as‑code gates; cost checks. Evidence: CI badges, pipelines, ADRs, demo. &#x20;

**Week 3 – AKS Platform**
Prod AKS (zonal HA, RBAC/Workload Identity, network policy); GitOps (Flux); supply‑chain security; spot pools + autoscaler; **Chaos = single manual event** (node drain/kill) instead of full Chaos Mesh lab. Evidence: GitOps repo, app rollout, cost analysis.&#x20;

**Week 4 – Enterprise & FinOps**
**Front Door *or* Traffic Manager + WAF (choose one)**; Azure SQL/storage replication; **DR test proving RTO <15m**; Defender configured; Sentinel minimal viable set (2 analytics + 1 playbook); Arc **servers‑only**; FinOps engine (chargeback, optimization jobs, dashboard). Week‑4 **Go/No‑Go checkpoint**. &#x20;

**Week 5 – Advanced (order fixed)**

1. **Event‑Driven** (Event Grid, Service Bus, Functions), 2) **SRE** (SLOs/error budgets, runbooks), 3) **Performance** (baseline + single optimization + CDN), 4) **AI/ML infra** (ADR fallback allowed). Freeze docs + full demo. &#x20;

**Week 6 – Portfolio & Applications (practice only)**
Polish GitHub; 2 technical blogs; 3–4 demos (2–4 min, ≥12/20 score); **2 practice applications** for reps (allowed per V4.1); resume/LinkedIn. &#x20;

**Week 7 – Interview Lab**
≥8 mocks; last 3 ≥80%; whiteboarding artifacts; STAR bank (10). &#x20;

**Week 8 – 20 Incident Sims**
All resolved ≤2h; RCA + prevention; interview‑ready explanations.&#x20;

---

## 3) Acceptance Checklist (all 3 flagship repos)

Diagram + ADR; one‑command deploy (Make/GHA) + status badge; CI/CD with lint/scan/plan/apply/verify; MI/Key Vault, least‑priv RBAC (+ PIM note); **policy‑as‑code** pipeline; **observability** (Log Analytics, 5 KQL, alert); **cost table + budget/alert**; **demo (2–4 min) scored ≥12/20**; README incl. **CAF mapping**.&#x20;

---

## 4) Go/No‑Go (no real apps until all pass)

Identity solid; **IaC mastery**; **AKS production‑ready + GitOps**; **Event‑Driven** proven; **FinOps ≥20%** savings; **DR <15m**; **SRE** (SLOs, dashboards, alerts, error budgets); **Defender score ≥85%**; public portfolio/blogs/videos; **mocks ≥80%**; **100+ fixes** + **20/20 incidents**; **6 peer validations**; fix speed <30m.&#x20;

---

## 5) Evidence Paths (repo layout)

```
/azure-infrastructure-portfolio/
├── flagship-1-landing-zone/
├── flagship-2-aks-platform/
├── flagship-3-finops-engine/
├── docs/ (adrs/, caf-mapping.md, cost-estimates/)
├── progress/ (progress-log.md, troubleshooting-log.md, peer-reviews/, eli5-recordings/, flashcards/)
├── incidents/, rca/, runbooks/, metrics/
└── portfolio/, blogs/, applications/, interviews/, star-stories/, feedback/
```

Log every sub‑step to `progress/progress-log.md`. **Artifact or it didn’t happen.** &#x20;

---

## 6) Cut List (locked) — **85 hours (22%) saved**

* **Drop support project** (dup acceptance/docs/pipelines) — **36.0 h** (risk: none; 3 flagships cover portfolio bar).&#x20;
* **Cut GPU/AI day** (keep ADR fallback) — **7.5 h** (AI infra = nice‑to‑have, not required at this band).&#x20;
* **Cut IoT/Edge** entirely — **3.5 h** (niche; not a must‑have).&#x20;
* **Azure Arc**: servers‑only proof (skip Arc‑K8s deep dive) — **2.0 h** (Arc is differentiator, not core).&#x20;
* **Chaos**: replace Chaos Mesh with **1 manual chaos event** — **1.5 h**.
* **Performance**: keep **1 baseline + 1 optimization + CDN** — **4.0 h**.
* **Observability stack**: skip OTEL/Jaeger lab; use KQL + Container Insights — **2.5 h**.&#x20;
* **Global routing**: implement **Front Door OR Traffic Manager**, not both — **5.0 h**.&#x20;
* **Consolidate budgets/policy scaffolding** once and reuse across repos — **16.0 h**.&#x20;
* **Demo/video**: remove one extra deep‑dive beyond the 3 repo demos — **2.0 h**.
* **VMSS/backup**: demo once, reference elsewhere — **3.5 h**.
* **Practice apps**: **2** reps instead of 5 — **1.5 h** (practice apps allowed per V4.1; reps > volume).&#x20;

**Total saved: 85.0 h.** All **must‑haves** remain intact (IaC, AKS/GitOps, CI/CD, SRE/KQL, Entra, Defender/Sentinel, FinOps, **DR<15m**, portfolio). Market data confirms cut items are **nice‑to‑haves**. &#x20;

---

## 7) ADRs to add now (record trade‑offs)

* `adr-009-frontdoor-vs-trafficmgr.md` — decision + revisit criteria.&#x20;
* `adr-010-arc-scope-servers-only.md`
* `adr-011-chaos-minimal-manual-event.md`
* `adr-012-ai-fallback-no-gpu.md` (AML/OSS or API stubs).&#x20;
* `adr-013-budgets-policies-shared-modules.md`&#x20;

---

## 8) Daily & Weekend Templates

Use V4.1 Daily Execution and Weekend templates (unchanged) and log every sub‑step; missing log entry = build failure.&#x20;

---

## 9) Week‑4 Checkpoint Protocol (unchanged)

Proceed if ≥2 repos passed acceptance **OR** design‑mock #2 ≥75%; else pause new features 48h and close gaps. Document decision in `/progress/week4-checkpoint-decision.md`.&#x20;

---

## Verify understanding (answer in one sentence each)

* Which **one** of Front Door vs Traffic Manager will you implement, and what’s the **revisit** trigger in ADR‑009?&#x20;
* What two artifacts **prove** DR <15m and FinOps ≥20% in your repos? (Be specific.)&#x20;
* Where do you log sub‑step completion, and what happens if an entry is missing?&#x20;

---

## Evidence required (now)

* Paste the **Git branch link** that contains `MasterSpec.md` and ADRs 009–013, and the **progress-log** line `W0D0-MasterSpec-Init`. (Review for drift vs. V4.1.)&#x20;