---
layout: project-detail
name: "PII Detection Platform"
tech: ["Data Privacy", "Pipeline Security", "Automated Redaction", "Regulatory Compliance"]
---

### The Problem
PII detection relied heavily on fragile, rules-based logic that was incredibly hard to maintain, prone to missing sensitive data, and incapable of adapting as data formats and writing patterns evolved. For regulated workflows, missed PII isn’t just a technical defect, it creates immediate legal and regulatory exposure.

### My Role
I owned the product delivery of an ML-based PII detection engine, starting from a single, tightly regulated use case and evolving it into a shared internal capability adopted across multiple enterprise teams and applications.

### Key Decisions
* **Strategic Sequencing:** The core tension was optimizing for a single use case versus expanding into a broadly reusable model without degrading trust or performance for existing consumers. I chose to integrate first into the application with the highest user volume, focusing detection explicitly on freeform text fields rather than attachments—maximizing risk mitigation while minimizing early engineering effort.
* **Architecture Governance:** As adoption grew, I made the call to enforce a general core model rather than spin up fragmented, bespoke versions for each individual team, protecting the long-term engineering roadmap and keeping operational maintenance manageable.
* **The Specialty Exception:** I intentionally scoped a specialty model exclusively for Financial Crimes Monitoring that focused solely on credit card data. The narrow scope and high regulatory importance of this data fully justified a dedicated solution.
* **Defensive Product Guardrails:** When early expansion work caused a slight degradation in recall for the original root use case, I paused the rollout. I introduced strict backward-compatibility checks and automated validation gates to ensure no future scope expansion could compromise existing baselines.

### Business Outcomes
* **Enterprise Scaling:** The shared capability was successfully adopted across 8 major internal applications and downstream teams.
* **High-Throughput Impact:** The Financial Crimes Monitoring application actively leverages the model to highlight and redact credit card data across millions of transactions per day.
* **Risk Posture Alignment:** Successfully replaced duplicated, fragmented rule-based approaches with a unified, auditable capability that significantly enhanced the organization's compliance posture.
