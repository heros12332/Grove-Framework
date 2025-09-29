# GROVE — Governed Risk-Oriented Visibility for Executives

> **A decision-first security framework for executive clarity** in post-AI, cloud-native, cyber-resilient environments. GROVE turns asset-anchored analysis into fast, defensible decisions under pressure.

---

## Why GROVE exists (the 20-second pitch)
Traditional risk programs optimize for registers and audits. GROVE optimizes for **decisions**: posture shifts, incident response, and governance alignment. It replaces generic likelihood×impact tables with **asset-first logic**, **control adequacy**, **survivability layering**, and **scenario-complete coverage** you can brief to a board.

---

## Key ideas at a glance
- **Asset-first logic** → *No asset, no risk.* Forces concrete scope and crown-jewel focus.
- **Actor vs. threat separation** → Models who is acting and how, across blended campaigns.
- **Control adequacy as “vulnerability”** → Measures maturity/coverage as the lever executives can change.
- **Survivability layering (the “control onion”)** → Defense-in-depth framed as *will we survive failures?*
- **Bowtie backbone** → Pre-/post-event controls mapped to threat pathways for traceability.
- **Scenario matrix** → MECE-style coverage so you don’t miss what you didn’t think of.
- **Disruption layer** → Names the live, real-time containment/decision layer during incidents.

---

## When to use GROVE
Use GROVE when you need:
- A **board-ready narrative** for a changing risk posture (mergers, new platforms, new threats).
- **Fast, defensible choices** on control investments or incident containment.
- A **structure** that connects assets → actors/threats → controls → scenarios → decisions.

**Not a fit** if you only need a control checklist or compliance workbook with no decision context.

---

## Quickstart (15 minutes)
1. **Pick one crown-jewel asset** (e.g., Payments API, M365 mail, Patient DB).
2. **Name the actor + threat** pair driving concern (e.g., BEC actor → OAuth consent grant).
3. **Sketch the bowtie**: 
   - *Left side*: entry vectors and pre-event controls.
   - *Right side*: consequences and post-event/response controls.
4. **Score control adequacy** (0–3) for the few controls that matter:
   - 0 = absent; 1 = ad-hoc; 2 = defined/partial coverage; 3 = proven/monitored.
5. **Map survivability layers** (identity, endpoint, network, data, app, detect/respond, disruption) and note single-points-of-failure.
6. **Place it in a scenario matrix** (see below) to ensure coverage and find gaps.
7. **Decide**: What single change would most reduce pathways or increase survivability? Write a 5-sentence exec brief.

> Tip: Use the docs below as prompts. Start small; depth beats breadth.

---

## Repository structure
- `README.md` — you are here
- `1st-PRINCIPLES.md` — design principles and philosophy
- `CORE.md` — the core concepts and definitions
- `CONTROL-ONION.md` — survivability layering model (defense-in-depth as a decision object)
- `RISK-BOWTIE.md` — how to build and use bowties for traceable decisions
- `SCENARIO-MATRIX.md` — the MECE scenario coverage method with examples
- `STRATEGIC-POSITION.md` — expressing posture shifts and decision options for executives
- `VISUAL.pdf` — one-page visual (export to PNG for slide decks)

> **Planned** (PRs welcome): `/examples` (worked cases), `/templates` (worksheets & briefs), `/docs/crosswalk.md` (standards mapping).

---

## Worked example (outline)
> A minimal example you can reproduce in one sitting; contribute a full version under `/examples`.

- **Asset:** Microsoft 365 mail for Finance
- **Actor/Threat:** BEC actor → MFA-bypass via AiTM phishing; OAuth consent abuse
- **Bowtie (sketch):**
  - *Pre-event controls:* Conditional Access, phishing-resistant MFA, Defender Safe Links, admin consent policy
  - *Post-event controls:* Defender for Office 365 hunting, SIEM rules, automated token revocation, user comms playbook
- **Adequacy (0–3):** CA=2, PR-MFA=1, Safe Links=2, Admin Consent=0, Token Revocation=1, Playbook=1
- **Survivability layers:** Identity strong? (weak), Email filtering (moderate), Disruption (manual only)
- **Decision:** Enforce admin consent workflow + FIDO2 for finance + auto-revoke tokens → reduces two main pathways in under 30 days.

---

## Control adequacy rubric (minimal v0)
Use this until a fuller rubric lands in `/templates`.

| Score | Anchor | Evidence examples |
|---|---|---|
| **0** | Absent | Control not deployed or disabled |
| **1** | Ad-hoc | Config exists but inconsistent; no monitoring; local exceptions |
| **2** | Defined | Standardized config; partial coverage; periodic monitoring |
| **3** | Proven | Enforced, monitored, alerting tied to response; tested regularly |

Roll-up guidance: focus on **pathway-cutting controls** first; treat 0→1 and 1→2 as the highest value moves.

---

## Scenario matrix (starter)
Choose two simple axes and enumerate the cells to force coverage:
- **Axis A:** Actor sophistication (opportunistic, capable, targeted)
- **Axis B:** Impact locus (availability, integrity, confidentiality)

Fill each cell with: primary pathway(s), key controls, adequacy deltas, survivability notes, decision trigger.

---

## How GROVE relates to existing standards
GROVE doesn’t replace standards; it *frames decisions* alongside them.

- **NIST CSF 2.0** — GROVE’s survivability layers and adequacy scoring map to Identify/Protect/Detect/Respond/Recover.
- **ISO/IEC 27001/27005** — Use GROVE to justify Annex A control selections and show risk treatment rationale.
- **MITRE ATT&CK** — Populate bowtie left-side pathways with ATT&CK techniques; use to test coverage.
- **FAIR** — If you quantify, feed GROVE’s adequacy deltas and scenario structure into your FAIR modeling.

A dedicated `/docs/crosswalk.md` is welcome as a contribution.

---

## Decision briefs (one page)
Every GROVE artifact should ladder into a short brief:

**Title:** Asset + actor/threat + decision date  
**Situation:** What scenario and pathway worry us?  
**Assessment:** Adequacy & survivability in one paragraph  
**Recommendation:** The one change that most improves outcomes  
**Impact:** Time, cost, risk reduction, dependencies  
**Next review:** Date and metric to revisit

---

## Contributing
We welcome issues and PRs that:
- Add **worked examples** and **templates** (XLSX/CSV/MD/DOCX).
- Improve the **adequacy rubric** and **scenario matrices**.
- Draft the **standards crosswalk** and **metrics** (time-to-decision, scenario coverage, residual exposure by asset).

Please include:
- A short rationale (what decision the artifact enables)
- Evidence of use (even a quick narrative)
- Clear licensing (see below)

---

## License
- **Content (docs):** Creative Commons **CC BY 4.0** — attribution required.

Please include a header in contributed files stating which license applies.

---

## Project status & versioning
- Current maturity: **v0 (concept-complete, artifact-light)**
- Semantic versioning for docs: **0.y.z** until first stable template set lands.
- Roadmap milestones (proposed):
  1) `/examples` with 2 complete cases  
  2) `/templates` worksheets + decision brief  
  3) `/docs/crosswalk.md`  
  4) Adequacy rubric v1 with scoring guide and confidence bands

---

## FAQ
**Is GROVE a replacement for my ISMS?**  
No. It’s a decision layer that helps you use your ISMS and standards to choose *what to do next*.

**Can I quantify with FAIR?**  
Yes—use the scenario matrix and adequacy deltas to parameterize FAIR inputs.

**What if I don’t have a SIEM/XDR?**  
Model the disruption layer explicitly. Decision clarity often reveals the highest-leverage, low-cost moves.

**How do I show progress?**  
Track: time-to-decision, adequacy trend on pathway-cutting controls, and survivability minutes at risk per asset.

---

## Acknowledgements
Thanks to the open community of risk, resilience, and incident-response practitioners whose ideas inform defense-in-depth, bowtie analysis, and scenario-based planning. GROVE’s contribution is composition and decision focus.

---

## Attribution

This framework is open-source under **CC BY 4.0**. You are free to use, adapt, and extend it with attribution.

> Based on work from the GROVE Framework by Kelvin Chau, licensed under CC BY 4.0. Available at: https://github.com/kfkchau/Grove-Framework/  
> LinkedIn: https://au.linkedin.com/in/kfkchau
