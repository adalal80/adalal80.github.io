---
layout: archive
title: Portfolio
permalink: /Portfolio/
category: "Portfolio"
tagline: "Products I've built. Problems I've solved."
---

## Data Quality AI Models
**Compliance and Operational Risk Platform · JPMorgan Chase**

### The Problem
Operational reviewers were manually reading roughly 175,000 unstructured descriptions to determine whether each one answered all required regulatory questions — a process that took several minutes per item, varied across reviewers, and didn't scale. We were working against a fixed regulatory deadline, and the manual process couldn't demonstrate the consistency or defensibility regulators required.

### My Role
I owned this product end-to-end — from problem framing through delivery. That included defining the model strategy, aligning stakeholders across compliance, engineering, data science, and design, and making the key prioritization and sequencing calls throughout.

### Key Decisions
Rule-based approaches weren't viable given how inconsistently descriptions were written. Early prototypes showed a single combined model performed unevenly across fields, so I made the call to build individual models per field and prioritize the highest-risk fields first.

There were two user personas with different needs: operational reviewers (determining pass/fail) and description editors (fixing deficiencies). Engineering estimated that fully automating the reviewer workflow would take several months due to unclear requirements, while the editor workflow could be delivered in weeks. I prioritized the editor experience first and supported reviewers with a bulk export so they could still consume model outputs without a full workflow rebuild.

### Outcome
- Sustained increase in descriptions passing data quality requirements, directly supporting closure of a regulatory finding.
- Manual review effort dropped materially.
- Solution remained durable as writing patterns evolved — retrained on a planned annual cadence, not constant rule updates.

> *"Trust, not just accuracy, determines whether AI products work."*

---

## PII Detection Platform
**Compliance and Operational Risk Platform · JPMorgan Chase**

### The Problem
PII detection relied on rules-based logic that was hard to maintain, prone to missing sensitive data, and didn't adapt as data formats and writing patterns evolved. For regulated workflows, missed PII isn't just a technical issue — it creates legal and regulatory exposure.

### My Role
I owned the delivery of an ML-based PII detection model, starting from a single regulated use case and evolving it into a shared internal capability adopted across multiple teams and applications.

### Key Decisions
The core tension was optimizing for one use case versus expanding into a broadly reusable model without degrading trust or performance for existing consumers.

I chose to integrate first into the application with the highest user volume, focusing detection on freeform text fields rather than attachments — maximizing impact while minimizing engineering effort and risk. As adoption grew, I made the call to maintain a general model rather than create fragmented versions for each team, protecting the roadmap and keeping maintenance manageable.

One exception: I scoped a specialty model exclusively for Financial Crimes Monitoring, focused solely on credit card data — a case where the narrow scope and regulatory importance justified a dedicated solution.

When early expansion work slightly degraded recall for the original use case, I paused rollout and introduced backward-compatibility checks and explicit sign-off requirements before any future scope changes.

### Outcome
- Model adopted across 8 internal applications and teams
- Financial Crimes Monitoring application uses the model to highlight and redact credit card data across millions of transactions per day
- Replaced duplicated, fragmented rule-based approaches with a shared capability that improved compliance posture across the organization

---

## Generative AI for Risk Event Submissions
**Risk Event Database Platform · JPMorgan Chase**

### The Problem
When a risk loss event was created in the platform, users had to answer a structured set of questions before submission. The event then passed through multiple validation stages, ending in QC review. Nearly 45% of submissions were being kicked back — not because users lacked the information, but because expectations for acceptable detail weren't clear at submission time. This created significant rework, delays, and frustration across teams.

### My Role
I led product discovery to identify the highest-friction point in the workflow, defined the GenAI solution approach, and drove cross-functional execution across design, prompt engineering, ML, and the application team.

### Key Decisions
The key question wasn't whether to use GenAI — it was where in the workflow and how much to automate.

I chose to intervene at submission time rather than at review or QC, targeting the root cause rather than the symptom. On automation level, I chose guided generation over full automation: GenAI drafts responses from uploaded documents, shows users what it sourced, and flags what's still missing. Users review and submit the final content. This kept the workflow safe, transparent, and defensible in a regulated environment.

The application team was initially hesitant to integrate GenAI into their workflow. Rather than pushing on the technology, I reframed the discussion around outcomes — showing how guided generation at submission time would reduce downstream rework and lower their team's overall operational load. Once tradeoffs and guardrails were explicit, they aligned.

### Outcome
- First-pass acceptance rate improved from 55% to 85%
- Reduced rework for submitters, fewer avoidable kickbacks for QC reviewers
- Shortened cycle time from event creation to QC approval
- Users developed a better understanding of submission expectations, improving quality even when the tool wasn't used directly

---

## Fork It — Group Restaurant Decision Tool
**Side Project · [stickaforkinit.lovable.app](https://stickaforkinit.lovable.app)**

A lightweight tool I built after watching friend groups spend more time deciding where to eat than actually eating. The core problem isn't finding a good restaurant — it's getting a group to agree on one.

The organizer creates a session and shares a link. No accounts, no login. Participants add restaurant picks and express preferences using tiers — Favorites, Top Choices, Okay With, Dislike — rather than a single vote. The app surfaces a winner based on where the group overlaps, not just what individuals want.

I scoped deliberately. Reservations, menus, and discovery stay offline for now. The hard part is consensus, and that's what I'm solving first.

*Built with Lovable. Read more in the [blog post](/2026/01/25/Forkit.html).*
