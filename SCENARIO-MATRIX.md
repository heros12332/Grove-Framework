# Scenario Matrix for Executive Decision-Making

The GROVE Framework defines seven canonical security scenarios. These are not arbitrary—they are derived from a complete and exhaustive analysis of all possible system states based on the presence or absence of three elements:
- **Threat**: Present or absent
- **Vulnerability**: Present or absent
- **Asset**: Present or absent

## Why Exactly Seven Scenarios?

The model is:
- **Exhaustive**: Covers all operationally relevant combinations
- **Minimal**: No redundant or overlapping categories
- **Actionable**: Each scenario maps to distinct control logic and decision posture

## Scenario Matrix — Exhaustive Risk States (TVA view)

This section enumerates the seven operationally relevant scenarios derived from binary presence/absence of **Threat (T)**, **Vulnerability (V)**, and **Asset (A)**. There are 2^3 = 8 combinations; one is null (no T, no V, no A), leaving **seven scenarios**.

### Seven-Scenario Matrix: Exhaustive Risk States

| Scenario | Threat | Vulnerability | Asset | Risk Level | Example                                | Strategic Action             |
|----------|--------|---------------|-------|------------|----------------------------------------|------------------------------|
| 1        | ✅     | ✅            | ✅    | High       | Unlocked office with sensitive documents | Deploy controls immediately  |
| 2        | ❌     | ✅            | ✅    | Medium     | Unsecured area with no known threat     | Investigate & prepare        |
| 3        | ✅     | ❌            | ✅    | Low        | Locked server room with known threat actor | Maintain vigilance        |
| 4        | ❌     | ❌            | ✅    | Minimal    | Secured asset with no threat            | Monitor for changes          |
| 5        | ✅     | ✅            | ❌    | No Risk    | Threat actor targeting non-existent asset | Maintain threat awareness |
| 6        | ❌     | ❌            | ❌    | No Risk    | Controls in place but no asset or threat | Reassess control necessity |
| 7        | ❌     | ✅            | ❌    | No Risk    | Controls protecting non-existent asset  | Reallocate resources         |

## How to use
- Use the table to quickly **triage** areas across your portfolio and assign a **strategic action**.
- For concrete decisions on specific assets, pair this with:
  - `RISK-BOWTIE.md` (timing: pre/post event)
  - `CONTROL-ONION.md` (layering: Predict → Prevent → Control → Disrupt)
  - `CORE.md` (definitions; control adequacy rubric; data contract)

This matrix supports real-time decision-making under pressure, enabling leaders to act with clarity, speed, and accountability.

---

© Kelvin Chau, 2025  
Based on work from the GROVE Framework by Kelvin Chau, licensed under CC BY 4.0. Available at: https://github.com/kfkchau/Grove-Framework/
LinkedIn: https://au.linkedin.com/in/kfkchau
