---
layout: project-detail
name: "Data Quality AI Models"
tech: ["Data Quality AI", "Model Validation", "Deterministic Workflows", "Risk Governance"]
---

### The Problem
Operational reviewers were manually reading roughly 175,000 unstructured descriptions to determine whether each one answered all required regulatory questions. This manual process took several minutes per item, varied significantly across reviewers, and simply could not scale. Working against a fixed regulatory deadline, the existing approach could not demonstrate the consistency, defensibility, or auditability that regulators required.

### My Role
I owned this product end-to-end—from initial problem framing through to final delivery. This included defining the core model strategy, aligning cross-functional stakeholders across compliance, engineering, data science, and UX design, and making all key prioritization and sequencing decisions throughout the product lifecycle.

### Key Decisions
* **Architecture Strategy:** Rule-based approaches were unviable given the high variability in how descriptions were written. Early prototypes also revealed that a single, monolithic model performed unevenly across different data fields. I made the strategic call to architect individual models per field and sequenced the roadmap to prioritize the highest-risk fields first.
* **User-Centric Prioritization:** The system involved two distinct user personas with competing needs: operational reviewers (determining pass/fail) and description editors (fixing structural deficiencies). Engineering estimated that fully automating the reviewer workflow would require several months due to fluid requirements, whereas the editor workflow could be delivered in weeks. I prioritized shipping the editor experience first to deliver immediate value, while supporting reviewers with a clean bulk-export capability so they could consume model outputs without waiting for a full workflow rebuild.

### Business Outcomes
* **Regulatory Compliance:** Achieved a sustained increase in descriptions passing rigorous data quality requirements, directly supporting the formal closure of a major regulatory finding.
* **Operational Efficiency:** Slashed manual review effort materially, eliminating processing bottlenecks ahead of the deadline.
* **Long-Term Durability:** The solution remained highly durable as writing patterns evolved. By relying on a planned annual retraining cadence rather than constant, brittle rule updates, we minimized ongoing engineering overhead.

> "Trust, not just accuracy, determines whether AI products work."
