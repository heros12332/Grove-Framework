# Bowtie Logic — Temporal Control Mapping for Security Events

GROVE uses a bowtie to map **when** controls act around an event. It aligns 1:1 with the survivability onion:

**Predict → Prevent → Control → (Event) → Disrupt**

> Canonical layers are exactly those four. “Recovery” is a programme that follows Disrupt; keep it out of the bowtie lanes to avoid drift.

---

## Why a Bowtie
- Clarifies **timing** and **ownership** of controls
- Exposes **gaps** and **single points of failure**
- Anchors the **seven scenario states** in time
- Produces a **single decision** with owner, due date, and metric

---

## Bowtie in One Sentence (template)
[Actor] using [pathway/mechanism] against [asset], prevented by [key controls]; if prevention fails at **(Event = …)**, we detect and **disrupt** via [actions] to avoid [outcome].

---

## Minimum Fields (per asset × pathway)
- **Asset:** name • owner • criticality
- **Actor:** description • capability (opportunistic | capable | targeted)
- **Pathway (Threat):** plain language (+ ATT&CK IDs if applicable)
- **Event (failure definition):** when prevention has failed (be specific)
- **Pre-event controls**
  - *Predict/Prevent:* name • owner • **adequacy (0–3)** • evidence • confidence
  - *Control:* name • owner • **adequacy (0–3)** • evidence • confidence
- **Post-event controls**
  - *Disrupt:* action • owner • **manual|automated** • runbook link • test cadence
- **Single points of failure:** list
- **Scenario state:** 1..7  • **Exit criterion:** what changes this state
- **Decision:** one change • owner • due (YYYY-MM-DD) • metric

> Adequacy = maturity/coverage on **this pathway** (0 Absent, 1 Ad-hoc, 2 Defined, 3 Proven).

---

## Pre-Event Lanes

### Predict
- **Purpose:** anticipate threats before they materialize
- **Owners:** CTI/Threat Intel, Strategy, Architecture
- **Examples:** actor profiling, horizon scanning, watchlists, design guardrails
- **Evidence:** TI reports, watchlist entries, design standards

### Prevent
- **Purpose:** block formation or access
- **Owners:** IAM, Network, Platform, Policy
- **Examples:** phishing-resistant MFA, segmentation, admin consent, hardening
- **Evidence:** enforced configs, policy exceptions, change history

### Control
- **Purpose:** contain even after access is gained
- **Owners:** Application/Data/Platform Engineering
- **Examples:** authorization, encryption, rate limits, process integrity
- **Evidence:** enforcement logs, tests, SLOs

---

## Event Node
- **Definition:** the precise condition at which prevention has failed (e.g., “risky OAuth grant created for Finance mailbox”)
- **Function:** hand-off to Disrupt; defines the **earliest actionable signal**
- **Implication:** can be latent, cascading, or externally triggered—write it specifically

---

## Post-Event Lane

### Disrupt (Detect/Respond embedded)
- **Purpose:** reduce impact at event time; detect, contain, and neutralise
- **Owners:** SecOps/IR/SRE
- **Examples:** token/session revoke, host isolate, network quarantine, account disable
- **Evidence:** runbooks, automation jobs, SIEM rules, playbook test results
- **Automation:** mark each action **manual** or **automated** and target dates to automate

> “Recovery” (restore + learn) is tracked in crisis/BCM programmes and feeds back to **Predict**; it is not a control lane in the bowtie.

---

## Mapping the Seven Scenario States to the Bowtie
- **1 – No credible actor pressure:** Predict active; no bowtie to build yet
- **2 – Actor present; pathway not viable:** Prevent/Control close the route; guardrails/watch drift
- **3 – Pathway viable; controls absent:** no effective Prevent/Control; define the Event and add baseline controls
- **4 – Controls partial:** some Prevent/Control at 1–2; prioritize 0→1 and 1→2 moves
- **5 – Prevention proven; detect/respond weak:** left side at 3; strengthen Disrupt (MTTD/MTTR)
- **6 – Disruption manual:** automate the Disrupt actions tied to the Event
- **7 – Layered controls proven + automated disruption:** sustain; periodic tests prevent drift

Each state has an **exit criterion** (e.g., “Admin consent workflow at adequacy 1” to move 3→4; “Automated token revoke in place and tested” to move 6→7).

---

## Compact Example (copy/paste)

**Asset:** Finance M365 mail  
**Actor:** BEC crew (capable)  
**Pathway:** OAuth consent abuse (ATT&CK T1525)  
**Event:** Risky app granted permission to Finance mailbox

**Predict/Prevent:**  
- Admin consent workflow — **Adeq 0** — Owner: IAM — Evidence: none — Conf: low  
- Conditional Access (high-risk sign-ins) — **Adeq 2** — Owner: IAM — Evidence: policy export — Conf: med  

**Control:**  
- Phishing-resistant MFA (Finance) — **Adeq 1** — Owner: IAM — Evidence: pilot list — Conf: med

**Disrupt:**  
- Detect risky grant (SIEM rule) — **Adeq 2** — Owner: SecOps — Evidence: rule + weekly review — Conf: med  
- Revoke tokens on risky grant — **Manual** (target automate in 60d) — Owner: SecOps — Evidence: runbook — Conf: low

**Single point of failure:** No admin-consent workflow (user grants allowed)

**Scenario state:** 3 → **Decision:** Enforce admin-consent; Owner: IAM; Due: 2025-11-15;  
**Metric:** % risky grants blocked; # admin approvals; PR-MFA adoption %

---

## Quality Bar (Definition of Done)
A bowtie record is **DONE** when:
- Event is **concrete** and earliest actionable signal is defined
- ≥3 pathway-cutting controls scored with adequacy + evidence + confidence
- Disrupt actions marked **manual/automated** with test cadence
- Scenario state + **exit criterion** captured
- One decision recorded with **owner, due, metric**
- 
---

© Kelvin Chau, 2025 — Content licensed under CC BY 4.0: https://github.com/kfkchau/Grove-Framework/  
LinkedIn: https://au.linkedin.com/in/kfkchau
