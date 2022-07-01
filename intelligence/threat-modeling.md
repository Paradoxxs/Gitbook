---
description: >-
  Threat modeling is about creating an representation of the threat and how it
  relate to the consumer
---

# Threat modeling



Threat modelling is analysing the design of a system to highlight concerns about security and privacy characteristics.

The purpose of performing threat modelling is to identify what can go wrong in a system by pinpointing design and implementation issue, that needs mitigation. Weather is it early in the acquirement processes or through-out it life-cycle. The output of the threat model informs decisions that you make in subsequent design, development, testing and post-deployment phases

## Threat Models and frameworks

### Threat modelling manifesto

[Threat Modeling Manifesto](https://www.threatmodelingmanifesto.org/)

Guidelines

* Value
  * **A culture of finding and fixing design issues** over checkbox compliance.
  * **People and collaboration** over processes, methodologies and tools.
  * **A journey of understanding** over security or privacy snapshot
  * Action over words
  * **Continuous refinement** over single delivery
* Principles
  * The best use of threat modeling is to improve the security and privacy of a system through early and frequent analysis.
  * Threat modeling must align with an organization’s development practices and follow design changes in iterations that are each scoped to manageable portions of the system.
  * The outcomes of threat modeling are meaningful when they are of value to stakeholders.
  * Dialog is key to establishing the common understandings that lead to value, while documents record those understandings, and enable measurement.

### Stride - Software focus

1. Spoofing
2. Trampering
3. Repudiation
4. Information of disclosure
5. Denial of service
6. Elevation of privilege

### PASTA - 7 Steps risk centric methodology, gives a assets value

* Stage 1: Definition of objection
* Stage 2: Definition of technical scope
* stage 3: Application analysis
* stage 4: threat analysis
* stage 5: Weakness and vulnerability analysis
* stage 6: Attack simulation
* stage 7: Risk analyse and management

### VAST - agile PM principles

1. Visual
2. Agile
3. Simple
4. Threat

### Dread

* Damage potential
* Repeatability
* Exploitability - How difficult is it perform
* Affected user
* Discoverability - How easy is it for attacker to discover the weakness

### COBIT - Control objective for information and related technology

```
    - Principle 1 - Meeting stakeholder needs
    - Principle 2 covering the neterprise end to end
    - Principe 3 Applying a single, integrated framework
    - Principle4 Enabling a holistic approach
    - Principle 5 Separating governance from management.
```

### Reduction analysis The processes of reducing the threat to it components.

1. Trust boundaries; location where trust or security changes
2. Data flow path; movement of data between two points
3. Input points; external input is received
4. Privileged operations; any actions that required greater privileged then standard users
5. Details about security stance and approach; declaration of security policy, security foundations and security assumptions.
