# GROVE — Governed Risk-Oriented Visibility for Executives

> **An interop-first decision layer.** GROVE composes your existing standards and tools (NIST/ISO/FAIR/ATT&CK) into one pathway-centric view—asset → actor/threat → control adequacy → survivability layers → scenario state → executive decision.

---

## Why GROVE exists (the 20-second pitch)
Traditional risk programs optimize for registers and audits. GROVE optimizes for **decisions**: posture shifts, incident response, and governance alignment. It replaces generic likelihood×impact tables with **asset-first logic**, **control adequacy**, **survivability layering**, and **scenario-complete coverage** you can brief to a board.

---

## Key ideas at a glance
- **Asset-first logic** → *No asset, no risk.*
- **Actor vs. threat separation** → Model who vs how.
- **Control adequacy as “vulnerability”** → Maturity/coverage as the lever leaders can change.
- **Survivability layering** → Predict → Prevent → Control → Disrupt.
- **Bowtie backbone** → Pre-/post-event controls mapped to threat pathways.
- **Interop-first** → Composes NIST/ISO/FAIR/ATT&CK; keep your stack, make it decisive.

---

## 2. Seven-Scenario Matrix: Exhaustive Risk States

By applying binary logic (present/absent) to each of the three elements (Threat, Vulnerability, Asset), we derive **eight combinations**. One is null (no asset, no threat, no vulnerability), leaving **seven operationally relevant scenarios**.

| Scenario | Threat | Vulnerability | Asset | Risk Level | Example                                | Strategic Action             |
|----------|--------|---------------|-------|------------|----------------------------------------|------------------------------|
| 1        | ✅     | ✅            | ✅    | High       | Unlocked office with sensitive documents | Deploy controls immediately  |
| 2        | ❌     | ✅            | ✅    | High     | Unsecured area with no known threat     | Investigate & prepare        |
| 3        | ✅     | ❌            | ✅    | Low        | Locked server room with known threat actor | Maintain vigilance        |
| 4        | ❌     | ❌            | ✅    | Low    | Secured asset with no threat            | Monitor for changes          |
| 5        | ✅     | ✅            | ❌    | No Risk    | Threat actor targeting non-existent asset | Maintain threat awareness |
| 6        | ❌     | ❌            | ❌    | No Risk    | Controls in place but no asset or threat | Reassess control necessity |
| 7        | ❌     | ✅            | ❌    | No Risk    | Controls protecting non-existent asset  | Reallocate resources         |

---

## Quickstart (15 minutes)
1. Pick one **crown-jewel asset**.
2. Name the **actor + threat pathway** (plain language; add ATT&CK IDs if you want).
3. Sketch the **bowtie**: pre-event (Predict/Prevent/Control) → **Event** → post-event (Disrupt).
4. Score **control adequacy (0–3)** on 3–7 *pathway-cutting* controls (add evidence & confidence).
5. Decide **one change** that collapses the pathway or automates disruption; record owner/due/metric.

---

## Repository structure
- `README.md` — you are here
- `CORE.md` — core definitions and data contract
- `CONTROL-ONION.md` — survivability layers (Predict → Prevent → Control → Disrupt)
- `RISK-BOWTIE.md` — bowtie timing, event definition, owners, adequacy, automation
- `SCENARIO-MATRIX.md` — TVA matrix (this section in full) and usage notes
- `STRATEGIC-POSITION.md`, `INTEGRATION-GUIDE.md`, `DECISION-PLAYBOOK.md`, `VISUAL.pdf`

---

© Kelvin Chau, 2025 — Content licensed under CC BY 4.0: https://github.com/kfkchau/Grove-Framework/  
LinkedIn: https://au.linkedin.com/in/kfkchau

## Control adequacy rubric (minimal v0)
| Score | Anchor  | Evidence examples |
|------:|---------|-------------------|
| 0     | Absent  | Not deployed/disabled |
| 1     | Ad-hoc  | Inconsistent; no monitoring |
| 2     | Defined | Standardized; partial coverage |
| 3     | Proven  | Enforced; monitored; tested; alerts drive response |

