# Bowtie Logic: Temporal Control Mapping for Security Events

The bowtie model in GROVE maps how controls operate across time—**before** and **after** a security event. It is structurally aligned with the survivability model and reflects its four-layer onion logic, grouped into two temporal domains:
- **Pre-Event Phase**: Predict → Prevent → Control and Assure
- **Post-Event Phase**: Disrupt → Recovery

This document focuses only on the essential bowtie-specific logic, assuming readers have reviewed the main framework and survivability documents.

---

## Why Bowtie Logic?

GROVE treats incidents as expected states, not failures. The bowtie model:
- Clarifies control timing and ownership
- Identifies gaps across the event lifecycle
- Aligns with the 7-scenario matrix
- Encodes decision rights and failure thresholds

---

## Bowtie Structure (Aligned to Survivability Layers)

[Predict] → [Prevent] → [Control and Assure] → [Event] → [Disrupt] → [Recovery]

---

## Pre-Event Phase

### [Predict]
- **Purpose**: Anticipate threats before they materialize
- **Ownership**: Strategy, intelligence, red teams
- **Examples**:
  - Threat actor profiling
  - Counterintelligence
  - Horizon scanning

### [Prevent]
- **Purpose**: Block threats from forming or accessing targets
- **Ownership**: Engineering, architecture, policy
- **Examples**:
  - Access control
  - Network segmentation
  - Personnel vetting

### [Control and Assure]
- **Purpose**: Stop threat actions even if access is gained
- **Ownership**: Security operations, SOC teams
- **Examples**:
  - Encryption
  - Authentication
  - Monitoring and alerting
  - Process integrity

---

## Event Node

- **Definition**: Threshold of control failure
- **Function**: Transition from pre-event to active threat state
- **Implication**: May be latent, cascading, or externally triggered

---

## Post-Event Phase

### [Disrupt]
- **Purpose**: Respond in real time to reduce impact
- **Ownership**: Incident response, crisis teams
- **Examples**:
  - Tactical containment
  - Threat actor neutralisation
  - Communications and escalation

### [Recovery]
- **Purpose**: Restore operations and learn from the event
- **Ownership**: Business continuity, reform teams
- **Examples**:
  - Backup and restore
  - Root cause analysis
  - Strategic redesign

---

## Integration with GROVE

- Bowtie logic is the **temporal spine** of the survivability model
- Each scenario in the 7-scenario matrix maps to a position on the bowtie
- Enables **event-oriented planning**, **gap analysis**, and **resilience engineering**

---

© Kelvin Chau, 2025  
Based on work from the GROVE Framework by Kelvin Chau, licensed under CC BY 4.0. Available at: https://github.com/kfkchau/Grove-Framework/  
LinkedIn: https://au.linkedin.com/in/kfkchau
