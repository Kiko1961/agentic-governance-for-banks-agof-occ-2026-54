# Agentic Governance for Banks — AGOF™ and OCC Bulletin 2026-54

AGOF™ (Agentic Governance & Orchestration Framework) is an architectural specification, licensed as intellectual property, that the bank’s own engineers implement inside the bank’s infrastructure — independent of any platform or model provider, with no dependency on PRASOL. A conformant implementation gives the bank limits set by named people; a response decided in advance for when an agent reaches a limit; and a record of every action, in the bank’s own infrastructure, that internal audit and examiners can read.

## Correspondence with OCC Bulletin 2026-54, “Super Intelligence: Supervisory Framework”

Version 1 · 20 November 2026 · PUBLIC

### Purpose of this document

On 4 November 2026 the Office of the Comptroller of the Currency issued Bulletin 2026-54 with a framework that its examiners may use when they review a bank’s use of generative and agentic systems. The framework has sixteen components in six pillars. It does not set new requirements; it shows the lens an examiner may apply.

This document places each of the sixteen components beside what a conformant implementation of AGOF™ provides. Quoted statements about AGOF™ are taken word for word from the public AGOF™ Executive Summary — Banking Edition, Version 7; the correspondence judgments are PRASOL’s.

### How to read the table

Each row carries one of three kinds of correspondence.

- **Native.** For agent actions, the specification itself defines what the component describes. A conformant implementation provides it.

- **Enforcement point.** The component describes a policy that the bank defines. AGOF™ is where that policy is applied to every action an agent attempts.

- **Complementary.** The component belongs to a process the bank already runs. AGOF™ supplies the record that process can read.

### The sixteen components

| **OCC component (pillar)** | **What the framework describes** | **What a conformant AGOF™ implementation provides** | **Kind** |
| --- | --- | --- | --- |
| **2.1 Defined Purpose and Permitted Use** (Purpose) | A bank may document what an agent is designed to do and not do, who or what may invoke it, the data and systems it may reach and the actions it may take. Activity outside the approved purpose may be treated as a control failure even when the result appears reasonable. | The permitted scope is a boundary “defined by named human authority before the agent runs”; “agents do not define or modify their own limits.” “An out-of-bounds action never reaches the execution state.” | **Native** |
| **2.2 Risk Classification and Criticality Assessment** (Risk) | A bank may assess each use by its consequences, reversibility, customer and financial impact, autonomy, data sensitivity and scope of permissions, so that stronger controls may apply where the consequences are greater. | The classification is the bank’s. The bank can express its result as the boundary each agent receives and the response decided in advance for that boundary; the boundary is applied on every action the agent attempts. | **Enforcement point** |
| **2.3 Human-in-the-Loop and Human-on-the-Loop Controls** (Control; Oversight) | Human involvement may be review and approval before use or execution, or active monitoring with authority and practical ability to intervene. Reviewers may need the authority to reject, modify, pause or halt, and overrides may be logged. | Named people set every boundary before the agent runs. When a request reaches a boundary, “the response comes from a closed set defined at design time and applied by the architecture — never selected by the agent.” That set includes referring the request to a designated person for decision. Each request leaves a record. Native for human authority over agent actions; review of a model’s outputs remains the bank’s. | **Native** |
| **2.4 Governance & Accountability** (Oversight) | Boards and senior management may identify accountable executives and owners for each use, and define decision rights and approval authority at meaningful points of the lifecycle. Accountability for managing the bank’s risk generally remains with the bank when a vendor develops or hosts the system. | “Authority that stays with the bank. Boundaries are versioned and every change is cryptographically attributable to a named human. No autonomous system can change them.” | **Complementary** |
| **2.5 Model Risk Management Extensions** (Control) | Certain model risk management principles may be instructive for development, validation and monitoring, and those activities may be adapted to systems whose outputs vary. Retraining, prompt changes or vendor updates can alter behavior between reviews. | Model risk management remains the bank’s process for the model. AGOF™ addresses the action: whatever the model produces, the agent’s action stays within its boundary, and model risk can read the record of each request. | **Complementary** |
| **2.6 Data Governance** (Control) | Reliability depends on the quality, lineage and permitted use of data. Technical controls may limit a system to approved data sources and prevent access outside its purpose or authorization. | The data policy is the bank’s. What each agent may act upon is part of its boundary, and enforcement “is placed in the bank’s own infrastructure”, not in the agent. | **Enforcement point** |
| **2.7 Privacy** (Control) | Privacy considerations such as minimization, access, retention, deletion, vendor use of bank data and cross-border processing may be mapped to each use and revisited when the model, provider, data or purpose changes. | The privacy policy is the bank’s. The bank can express the limits it places on what an agent may act upon in that agent’s boundary, and each request leaves a record the bank keeps in its own environment. | **Enforcement point** |
| **2.8 Compliance** (Control) | Using these systems does not change the bank’s underlying legal obligations. The framework mentions BSA and sanctions contexts, consumer compliance, and inaccurate statements about fees, rates, account status or policies. A bank may consider controls that limit automated representations and require verification in higher-impact contexts. | Compliance determinations are the bank’s. Where the bank limits what an agent may do on its own in higher-impact contexts, that limit is a boundary applied on every action. The record shows “which agent acted, under whose authority, within which limits, and what happened.” The record concerns actions; the content of an agent’s statements stays with the bank’s own controls. | **Enforcement point** |
| **2.9 Third-Party & Vendor Risk** (Assurance) | A bank may define the scope of authority, identity, permitted tool use, data use and escalation limits for provider agents that interact with bank systems and data, and may monitor and potentially limit what those agents do. Incident definitions, contracts and notice of changes are also mentioned. | In AGOF™, “no agent — the bank’s own, a vendor’s, or one acting on behalf of a customer — obtains special privileges. Every agent whose actions reach the bank’s systems is governed by the bank’s authority, not its own.” Native for authority over provider agents; contracts, incident definitions and notices remain the bank’s. | **Native** |
| **2.10 Operational Resilience** (Resilience) | An agent can remain available while acting harmfully. For more consequential or autonomous uses, a bank may document and test its ability to detect and contain; the means mentioned include deterministic rules, least-privilege permissions and the ability to stop an agent. For external agents from customers, fintechs or agentic commerce, identity, authentication, monitoring, suspension and revocation may be calibrated to the action requested. | AGOF™ defines agent systems “as deterministically governed execution environments”. An out-of-bounds action does not execute, the response is decided in advance, and an external agent is governed by the bank’s authority like any other, “whoever deploys it.” Native for keeping agent actions within their boundary; recovery, continuity and customer remediation remain the bank’s processes. | **Native** |
| **2.11 Cybersecurity** (Control; Resilience) | Prompts, inputs, connected tools and non-human identities add attack surface. Agent permissions and tool access can be treated as part of it, and agent identities and credentials may be governed in a manner comparable to privileged users. | “An agent’s identity does not by itself confer authority in AGOF™”. Because enforcement sits in the bank’s infrastructure and not in the agent, an agent whose inputs were manipulated still acts only within its boundary. Native for agent authority and permissions; the bank’s security program covers the rest. | **Native** |
| **2.12 Performance Monitoring** (Oversight) | Metrics, thresholds, reporting and escalation can be scaled to the consequences of each use. Monitoring can also identify version, prompt, configuration or permission changes that alter behavior without a traditional model release. | Monitoring is the bank’s process. The record of each action request — produced “by the architecture, not by the agent” — is immutable, tamper-evident data for it. | **Complementary** |
| **2.13 Testing** (Assurance) | Testing may span design, pre-deployment and production, with depth and independence that may depend on the consequences of the use. | “Conformance is verifiable. The bank’s own engineers test their implementation against the specification and keep the result as evidence.” The result is evidence for the bank’s testing of the control; testing of the model remains the bank’s. | **Complementary** |
| **2.14 Documentation & Auditability** (Assurance) | Records of inputs, outputs, retrieved sources, tool calls, approvals, overrides and actions may support the reconstruction of a material decision or event. Changes to models, prompts, data, tools and permissions can be logged. | AGOF™ supplies the part that concerns actions and authority: an “immutable, tamper-evident record” of each action request and versioned boundaries whose every change is attributable to a named person. The bank remains responsible for records of inputs, outputs and model versions. | **Complementary** |
| **2.15 Internal Audit & Independent Challenge** (Assurance) | Independent audit could provide additional assurance, and effective challenge may depend on independence from those who develop, own, validate or monitor a system. It may need the underlying evidence rather than only management summaries. | The audit function is the bank’s. The record is primary evidence: it “is produced by the architecture, not by the agent, and internal audit, model risk and examiners can read it.” | **Complementary** |
| **2.16 Reporting & Transparency** (Oversight) | Internal reporting may cover material uses, accountable owners, significant changes, control exceptions, incidents and assurance results, and can be reconciled with the inventory. | Reporting is the bank’s process. The record lets it rest on the bank’s own evidence of “which agent acted, under whose authority, within which limits, and what happened when a limit was reached.” | **Complementary** |

### What the correspondence shows

Five components are native (2.1, 2.3, 2.9, 2.10, 2.11), four are enforcement points (2.2, 2.6, 2.7, 2.8) and seven are complementary (2.4, 2.5, 2.12, 2.13, 2.14, 2.15, 2.16).

The framework looks at what an agent is permitted to do, under whose authority, and with what evidence. That is the ground AGOF™ defines.

Its highest illustrative tier combines direct action, little or no reversibility, high financial or customer impact, and full or partial autonomy: autonomous payments, real-time credit decisions, release of fraud holds, market access. When an agent attempts such an action within the bank’s systems, an AGOF™ boundary governs it.

Components 2.9 and 2.10 reach agents the bank did not build: a provider’s agents and external agents acting for customers. “A conformant implementation governs every agent that acts within the institution’s systems, whoever deploys it.”

### Sources and limits

- OCC Bulletin 2026-54, “Super Intelligence: Supervisory Framework”, 4 November 2026, and the framework attached to it (occ.gov). The framework is a resource for examiners, written in permissive terms, and the OCC treats it as a living document. The second column restates it in summary; the OCC text governs.

- AGOF™ Executive Summary — Banking Edition, Version 7, 1 November 2026, PRASOL LLC. Passages in quotation marks in the third column are taken from it.

- AGOF™ is licensed as a set of normative architectural specifications. The bank’s own engineers implement it within the bank’s environment. This document is not legal or regulatory advice.

Contact PRASOL LLC — rafatala@prasol-logic.com.

This document contains only public information.

---

Rafael Talavera · Author of AGOF™ · Manager, PRASOL LLC · prasol-logic.com

AGOF™ — conceived February 2026; first specification documents March 2026. © 2026 PRASOL LLC.
