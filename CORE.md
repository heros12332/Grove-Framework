# GROVE Core

> Distinguish the parts, integrate the view—then decide.

## 0) Purpose
This document defines GROVE’s core concepts and how they compose into a single, decision-ready view. It is the canonical source for definitions, scenario states, minimal scoring, and the data contract used by examples and templates.

---

## 1) Core Risk Model (distinguish, then link)
Security Risk = Threat × Vulnerability × Asset

- Asset — anything of value (service, system, data, platform). No asset, no risk.
- Threat — a concrete harm pathway (mechanism/event) executed by a threat actor with intent and capability. Model who (actor) and how (mechanism) separately.
- Vulnerability — a state of exposure caused by absent/weak/misaligned controls on that specific pathway. In GROVE this is operationalized as control adequacy.

Decision chain template:
Asset + actor + threat pathway + control adequacy ⇒ scenario state ⇒ decision (one change, owner, due, metric)

---

## 2) Seven Scenario States — Canonical Rubric (asset-first, pathway-centric)
Anchor on one asset × one credible pathway (actor + mechanism). Classify the current operational state using the rubric below.

State | Description | Primary lever | Exit criterion
----- | ----------- | ------------- | --------------
1 | No credible actor pressure | Horizon scanning | Actor signal emerges or scope changes
2 | Actor present; pathway not viable | Drift watch; architecture guardrails | Evidence of a viable pathway appears
3 | Pathway viable; controls absent (adequacy 0) | Establish baseline pathway-cutting control(s) | ≥ one key control at adequacy 1
4 | Pathway viable; controls partial (adequacy 1–2) | Close coverage gaps; raise adequacy | Pathway-cutting controls at adequacy 3
5 | Prevention proven; detect/respond weak | Improve detection/response (MTTD/MTTR) | MTTD/MTTR within target thresholds
6 | Disruption manual | Automate containment/disruption | Automated disruption in place and tested
7 | Layered controls proven + automated disruption (target) | Sustain and verify | Periodic tests confirm state; guardrails prevent drift

Notes:
- States are asset-first and pathway-specific; do not use truth-table rows that include “no asset.”
- Assign exactly one current state per record; plan movement along the ladder (e.g., 3→4→5→6→7).

---

## 3) Survivability Model (assume failure, layer for endurance)
Predict → Prevent → Control → Disrupt

- Predict — anticipate threats before they materialize (intel, actor profiling, horizon scanning).
- Prevent — block formation or access (identity, segmentation, hardening, governance).
- Control — contain even after access (authorization, process integrity, encryption, throttling).
- Disrupt — reduce impact at event time (detection, response playbooks, automated containment).

A threat must penetrate all layers to cause harm. Lessons from Disrupt feed back into Predict (recursive improvement).

---

## 4) Bowtie Logic (time-mapping of controls)
[Actor + Pathway] → [Pre-event controls] → (Event) → [Post-event controls] → [Outcome]

- Left side: Predict/Prevent owners (architecture, identity, network, app).
- Event node: where prevention fails and response must take over.
- Right side: Detect/Respond/Disrupt owners (IR, SecOps, SRE/platform).

Minimum artifacts:
- Pathway sketch (plain text or diagram)
- List of pathway-cutting controls with adequacy (0–3) and evidence
- Disruption actions (manual vs automated) and their owners

---

## 5) Control Adequacy Rubric (0–3, minimal v0) + confidence
- 0 — Absent: not deployed/disabled
- 1 — Ad-hoc: inconsistent; no monitoring; exceptions common
- 2 — Defined: standardized config; partial coverage; periodic checks
- 3 — Proven: enforced; monitored; tested; alerts drive response

Tag each score with confidence (low | med | high) based on evidence quality:
- Nil: no evidence
- Low: policy/docs only
- Med: config + occasional checks
- High: enforced config + continuous telemetry + tested playbook

Prioritise 0→1 and 1→2 moves on pathway-cutting controls; they deliver the largest risk delta.

---

## 6) Single Decision View (data contract per asset × pathway)
Use this schema in examples/templates; store as YAML or JSON.
asset:
  name: "<string>"
  owner: "<string>"
  criticality: "high|med|low"

actor:
  description: "<string>"
  capability: "opportunistic|capable|targeted"

threat:
  pathway: "<plain language>"
  att&ck:
    - "<technique ID>"
    # e.g., T1525

controls:
  - name: "<string>"
    layer: "predict|prevent|control|disrupt"
    adequacy: 0 # 0..3
    evidence:
      - "<config|test|telemetry|runbook>"
    confidence: "low|med|high"

survivability:
  single_points_of_failure:
    - "<describe sPoF>"
  notes: "<string>"

scenario_state: 1 # 1..7

decision:
  change: "<one action that collapses the pathway or automates disruption>"
  owner: "<role/person>"
  due: "YYYY-MM-DD"
  metric: "<how we’ll know it worked>"
  
---

## 7) Interoperability (keep your stack; make it decisive)
- MITRE ATT&CK — map pathway steps/techniques
- NIST CSF / ISO 27001 — map controls for governance and audits
- FAIR — feed adequacy and scenario state when quantifying loss exposure
- Risk register — sync decision, owner, due date, and metric

See also:
- INTEGRATION-GUIDE.md — how the pieces fit (threat, adequacy, risk; bowtie + onion + scenarios)
- DECISION-PLAYBOOK.md — 30–90 minute workflow and one-page brief

---

## 8) Definition of Done (quality bar)
A record is DONE when:
- The pathway is concrete (ATT&CK-mapped if applicable).
- At least three pathway-cutting controls are scored with evidence and confidence.
- A scenario state (1–7) is assigned and justified in one sentence.
- One decision is named with owner, due date, and metric.

---

© Kelvin Chau, 2025 — Content licensed under CC BY 4.0: https://github.com/kfkchau/Grove-Framework/  
LinkedIn: https://au.linkedin.com/in/kfkchau
