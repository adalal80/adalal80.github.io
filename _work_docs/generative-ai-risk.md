---
layout: project-detail
name: "Generative AI for Risk Event Submissions"
tech: ["Generative AI", "Risk Operations", "Prompt Engineering", "Workflow Optimization"]
---

### The Problem
When a risk loss event was created in the platform, users had to complete a highly structured set of questions before submission. The event then passed through multiple manual validation stages, culminating in a Quality Control (QC) review. Nearly 45% of submissions were being kicked back—not because users lacked the information, but because expectations for what constituted acceptable detail weren't clear at submission time. This created massive operational rework, severe cycle delays, and frustration across teams.

### My Role
I led product discovery to isolate the highest-friction point in the database workflow, defined the generative AI solution approach, and drove cross-functional execution across product design, prompt engineering, machine learning engineering, and the core application team.

### Key Decisions
* **Root Cause Intervention:** The strategic question wasn't whether to use GenAI, but exactly where to insert it in the workflow and how much to automate. I chose to intervene at submission time rather than at review or QC, deliberately targeting the root cause of the friction rather than treating the downstream symptom.
* **Guided Generation over Automation:** To maintain safety, transparency, and auditability in a regulated environment, I chose guided generation over full automation. The framework drafts responses using uploaded documentation, explicitly shows users what it sourced, and dynamically flags what information is still missing. Users review, edit, and submit the final content. 
* **Cross-Functional Alignment:** The core application team was initially hesitant to integrate GenAI into their workflow. Rather than pushing the technology itself, I reframed the discussion around outcomes—demonstrating how guided generation at submission time would structurally reduce downstream rework and lower their team's overall operational load. Once trade-offs and guardrails were made explicit, the teams aligned.

### Business Outcomes
* **First-Pass Efficiency:** First-pass acceptance rate for risk event submissions dramatically improved from 55% to 85%.
* **Operational Friction Reduction:** Drastically reduced manual rework for submitters and eliminated avoidable, administrative kickbacks for QC reviewers.
* **Velocity Gains:** Significantly shortened the complete cycle time from initial event creation to final QC approval.
* **Behavioral Change:** Users naturally developed a clearer understanding of submission expectations, which structurally improved data quality even in scenarios where the tool wasn't used directly.
