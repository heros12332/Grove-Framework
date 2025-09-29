# GROVE Integration Guide — From Parts to One Decision

> Distinguish the parts, integrate the view—then decide.

## Purpose
This guide shows how to integrate **threat**, **vulnerability (control adequacy)**, and **risk** into one pathway-centric view, and how to use **Bowtie**, the **Survivability Onion**, and the **Seven Scenario States** to drive a single, defensible decision.

---

## The Decision Chain (canonical)
**Asset** + **Actor + Threat pathway** + **Control Adequacy (0–3)** → **Survivability Layers** → **Scenario State (1–7)** → **Decision** (one change, owner, due, metric)

- Keep the terms distinct:
  - **Threat** = mechanism/event (mapped to ATT&CK where possible)
  - **Threat actor** = who (intent/capability)
  - **Vulnerability** = *state of control adequacy on this pathway*
  - **Risk** = potential for loss to the asset, given the above

---

## Data Contract (per asset × pathway)
See `CORE.md → Single Decision View` for the YAML schema. Required fields: `asset`, `actor`, `threat`, `controls[] {layer, adequacy, evidence}`, `scenario_state`, `decision`.

---

## How to Integrate — Step-by-Step

### 1) Frame the pathway (Bowtie: left side)
- Name the **actor** (opportunistic | capable | targeted).
- Describe the **threat mechanism** in plain language; add ATT&CK IDs if applicable.
- Sketch entry vectors and **pre-event** controls (Predict/Prevent).

### 2) Score vulnerability as **control adequacy**
- Identify **pathway-cutting controls** only (3–7 max).
- Score each **0–3** with **evidence** and **confidence** (low/med/high).
- Note **single points of failure** (one control whose failure re-opens the pathway).

### 3) Map **Survivability Layers** (the onion)
- Predict → Prevent → Control → Disrupt.
- For each, list what’s real today and what’s missing; mark what is **manual vs automated** on Disrupt.

### 4) Time-map the right side (Bowtie: event + post-event)
- Define the **Event** (where prevention fails).
- List **Detect/Respond/Disrupt** actions and whether they are **automated**.

### 5) Assign the **Scenario State (1–7)**
Use the canonical rubric in `CORE.md`. State reflects the *current interaction* of adequacy + layering + disruption, not a truth table.

### 6) Choose **one decision**
- Pick the **highest-leverage lever**:
  - 0→1 or 1→2 adequacy on a pathway-cutting control,
  - elimination of a single point of failure,
  - automation of a manual disruption step.
- Record **owner, due date, metric**.

---

## Heuristics (to avoid endless debate)
- Prefer **specific pathway** over generic “threat theme.”
- Prefer **evidence-backed adequacy** over opinion.
- Prefer **automation of disruption** when prevention is already ≥2.
- Prefer **0→1** and **1→2** moves before polishing 2→3.

---

## Example (compressed)

**Asset:** Finance M365 mail  
**Actor:** BEC crew (capable)  
**Threat:** OAuth consent grant abuse (ATT&CK T1525)  

**Pathway-cutting controls (adequacy/evidence):**  
- Admin consent workflow — **0** (no policy)  
- Phishing-resistant MFA for Finance — **1** (pilot only)  
- Conditional Access (high-risk sign-ins) — **2** (partial coverage)

**Survivability:** Detect ok; **Disrupt is manual** (helpdesk revokes tokens).  
**Scenario state:** **3 → 4** (viable pathway; baseline controls missing/partial).  

**Decision (one):** Enforce admin-consent workflow; **owner:** IAM; **due:** 30 days;  
**metric:** % risky app grants blocked; policy exceptions tracked.

---

## Common Pitfalls (and fixes)
- **Asset not specified** → Fix: name the service/data and owner.  
- **Too many controls** → Fix: score only *pathway-cutting* ones.  
- **Truth-table states** (incl. “no asset”) → Fix: use the seven **asset-first** states only.  
- **Hand-wavy vulnerability** → Fix: require evidence & confidence tag.  
- **No exit criteria** → Fix: every state has an explicit exit; every decision has a metric.

---

## Interoperability (how to plug your stack)
- Map **pathway steps** to **MITRE ATT&CK** techniques.  
- Map **controls** to **NIST CSF / ISO 27001** for governance.  
- Feed **adequacy + scenario** into **FAIR** for quantification.  
- Sync the **decision** to your **risk register** (owner, due, status).

---

© Kelvin Chau, 2025 — Content licensed under CC BY 4.0: https://github.com/kfkchau/Grove-Framework/  
LinkedIn: https://au.linkedin.com/in/kfkchau
