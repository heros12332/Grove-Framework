# Survivability Model: Layered, Recursive Defense

The GROVE survivability model defines how systems endure, adapt, and recover from threats. It assumes that **controls will fail**, and that resilience—not perfection—is the goal. The model is structured as a **layered onion**, where each layer represents a distinct function in the defense lifecycle.

## Why Survivability?

Traditional frameworks focus on prevention. GROVE focuses on **survivability**—the system’s ability to continue operating despite disruption. This model:
- Assumes adversaries will breach outer defenses
- Designs for containment, response, and recovery
- Enables recursive learning and adaptation

## The Four Layers

Each layer assumes the failure of the previous. Together, they form a recursive, adaptive system.

### Layer 1: Predict
- **Purpose**: Anticipate threats before they materialize
- **Strategic Rationale**: Intelligence superiority is the highest form of defense
- **Actions**:
  - Threat actor profiling
  - Counterintelligence
  - Horizon scanning
  - Red teaming and simulation

### Layer 2: Prevent
- **Purpose**: Block threats from forming or accessing targets
- **Actions**:
  - Access controls
  - Network segmentation
  - Personnel vetting
  - Policy enforcement

### Layer 3: Control and Assure
- **Purpose**: Stop threat actions even if access is gained
- **Actions**:
  - Encryption
  - Authentication
  - Process integrity
  - Monitoring and alerting

### Layer 4: Disrupt
- **Purpose**: Respond at the moment of eventuation to reduce impact
- **Clarification**: Disruption is not post-incident recovery—it is the last-moment chance to stop the threat
- **Actions**:
  - Incident response
  - Tactical containment
  - Threat actor neutralisation

## Onion Model Logic

- **Outer layers** (Predict, Prevent) are proactive and probabilistic
- **Inner layers** (Control, Disrupt) are reactive and deterministic
- **Recursion**: Lessons from Disrupt feed back into Predict
- **Failure assumption**: Each layer is designed with the expectation that the previous may fail

## Integration with GROVE

- Each layer maps to specific scenarios in the 7-scenario matrix
- Survivability layers inform the **bowtie model** (pre/post-event control logic)
- Layer maturity can be assessed independently or as a system

---

© Kelvin Chau, 2025  
Based on work from the GROVE Framework by Kelvin Chau, licensed under CC BY 4.0. Available at: https://github.com/kfkchau/Grove-Framework/  
LinkedIn: https://au.linkedin.com/in/kfkchau
