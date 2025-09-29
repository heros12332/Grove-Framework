# GROVE Decision Playbook — 30–90 Minutes to a Defensible Move

## Inputs
- One **asset** (crown-jewel) and owner
- One **actor + threat pathway**
- Evidence for 3–7 **pathway-cutting controls**

## Workflow
1) **Bowtie (5–10 min):** Sketch pathway and pre-/post-event controls.  
2) **Adequacy (10–20):** Score 0–3 with evidence + confidence.  
3) **Onion (5–10):** Note gaps across Predict → Prevent → Control → Disrupt; mark manual vs automated.  
4) **State (5):** Assign **Scenario State (1–7)** per `CORE.md`.  
5) **Decision (10–20):** Pick **one** change with the largest risk delta.  
6) **Brief (10):** Fill the 1-page template below.

## Levers & Exit Criteria
- **0→1 / 1→2 adequacy** on a pathway-cutting control → exit state 3/4.  
- **Improve detect/respond MTTD/MTTR** to target → exit state 5.  
- **Automate disruption** (token revoke, session kill, network isolate) → exit state 6.  
- **Periodic tests + telemetry** guardrails → sustain state 7.

## One-Page Decision Brief (template)
**Title:** <Asset + pathway + date>  
**Situation:** <Actor + pathway + current state + adequacy summary>  
**Assessment:** <Onion gaps + single points of failure>  
**Decision:** <One change> — **Owner:** <name> — **Due:** <YYYY-MM-DD>  
**Impact:** <Expected risk delta / where state should land>  
**Metric:** <How we’ll know it worked>  
**Next review:** <Date>

## Filled Example (BEC / M365)
**Title:** Finance M365 mail — OAuth consent abuse — 2025-10-15  
**Situation:** Capable BEC actor; viable pathway; Admin-consent=0, PR-MFA=1; **state 3→4**  
**Assessment:** Disruption manual; single point of failure = consent policy missing  
**Decision:** Enforce admin-consent workflow (block user consent; admin approve only)  
**Owner/Due:** IAM lead — 30 days  
**Impact:** Cuts primary pathway; expect **state 4** on completion, **state 5** after response rules  
**Metric:** % risky grants blocked; # of admin approvals; PR-MFA adoption %  
**Next review:** 2025-11-15

---

© Kelvin Chau, 2025 — Content licensed under CC BY 4.0: https://github.com/kfkchau/Grove-Framework/  
LinkedIn: https://au.linkedin.com/in/kfkchau
