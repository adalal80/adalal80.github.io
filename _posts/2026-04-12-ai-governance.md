---
layout: post
title: "If You Can't Measure It, You Can't Govern It"
---


Most teams treat AI governance as a compliance exercise. Something you bolt on after the model is built, a checklist you run through before launch, a box you check so the right people feel comfortable. That is the wrong frame entirely.

Governance is a design requirement. It has to be defined before anything goes live.

#### The Autobahn is fast because it has structure

Think about the difference between driving on the Autobahn and driving on a dirt road. The dirt road feels like freedom. No rules, no structure, just go. But you can't go fast because the road won't let you. Every bump slows you down and every turn is a risk because nothing was built to handle speed.

The Autobahn has guardrails, lane discipline, and engineering underneath it. That structure is what enables speed. Slow is smooth, smooth is fast.

Most AI deployments are dirt roads dressed up as Autobahns. They move fast in the beginning because nothing is in the way. But without defined operating limits, monitoring thresholds, and response sequences, you are not going fast. You are just going without control.

#### Governance tells you when something is wrong

I came up in chemical engineering before I moved into product. Before a refinery unit goes live, every operating limit is defined, every alert condition is mapped, and every response sequence is documented. You cannot bolt that on after the fact. The consequences are too significant.

I think about AI governance the same way. At its core this is product thinking. Before a model is built, in the requirements phase, I am already asking what outcome we are trying to achieve, how we will know we have reached it, and how we will know when we haven't. An AI PM is still a product person. The discipline does not change because the technology did.

In chemical engineering, laminar flow is controlled and predictable, moving in one direction. Turbulent flow is chaotic and hard to course correct once it starts. I think about AI model performance the same way. Governance is how you know which state your model is in. Without defined thresholds and monitoring, you cannot tell the difference between a model performing as expected and one that is quietly drifting toward failure.

If a model starts drifting, producing inaccurate results, or behaving in ways it shouldn't, you need a defined response. In some cases that means taking it offline to prevent bad outputs from reaching users. But you can only execute that response if you defined it before the model went live.

#### What happens when nobody defines success

Most teams build the model, ship it, and then figure out what to monitor. The outcome they were trying to achieve was never precisely defined, so there is no baseline, no threshold, no way to know if the system is performing correctly or drifting toward failure.

I have seen this in my own work. My models are API based. I don't own the application. I can advise, but I can't always control what gets implemented. The application team decides what to track, what to store, and how to surface it. When those decisions are made without a governance framework in place, you end up with blind spots.

The way users interacted with one of my models changed over time. Originally the model was triggered manually by the user when they chose to run it. It became preemptive, running automatically before the user even began their review. I advised the team to track whether a user fixed a failed result when they saved, and to store a monthly snapshot of how the model was being used so we could do trend analysis over time. They stored only the latest run. Now we can't measure month over month change. We can see the current state but we can't see the direction of travel. That is a governance gap, and it exists because nobody defined what needed to be measured before the system was built.

#### The metric you are tracking is not the metric that matters

Most teams look at usage, adoption, and top line metrics like overall pass rate. Those are not bad metrics. But they do not quantify value and they do not tell you whether the AI is driving the outcome it was built for.

Here is what I track instead.

Which descriptions failed, the user saw the result, and then updated it. That is behavior change. That is the model doing its job. I also track when the result was surfaced and when the user made the change. Now I can measure time to resolution and age the backlog. And I look at which specific questions within a description are driving failures across the firm. If five questions are required and one is consistently failing, that is not always a data quality problem. Sometimes the question needs to be rewritten or users need to be educated on how to answer it. The model just told you something the program team did not know.

That level of insight is only possible if you stored the right data before the model went live. If you stored only the latest run, you have a snapshot. You do not have a story.

#### Trust = Accuracy + Explainability

A model can be accurate and still not be trusted. I have seen this firsthand.

We built a model using RoBERTa to classify which global legal obligations should apply to a given process at a bank. The model went through internal validation, end user feedback, and passed the minimum success criteria. It was accurate. But usage was low. When we asked users why, they told us they were spending significant time trying to figure out which of the twelve input features drove the prediction. SHAP, a method that quantifies how much each input feature contributed to a specific prediction, had not been implemented and adding it would have required additional engineering effort. The model was right but users could not see why, so they did not trust it.

A sister model using XGBoost included feature importance out of the box. Users could see exactly which inputs drove the classification. They were grateful for it. Same use case, different trust outcome.

Trust = Accuracy + Explainability

Explainability looks different depending on the model type. For traditional ML and deep learning models it means surfacing feature importance so users can compare the model's reasoning to their own mental model. For GenAI it means surfacing a concise reasoning alongside the output so users are not left with a black box result.

For one of my GenAI models I was evaluating fields to determine whether consistency was present. The JSON output included three things: a consistency flag, which fields were inconsistent if any, and a plain language explanation of why. Users could read the reasoning, evaluate it against their own judgment, and decide whether to act. That is explainability in practice. The model is not asking to be trusted blindly. It is showing its work.

SMEs do not want to reverse engineer a model. They want to look under the hood, confirm the reasoning matches how they would have done it manually, and then move on. Explainability is what makes that possible. Without it, even an accurate model is fighting for adoption.

#### You cannot govern what you have not defined

AI governance is not a compliance exercise. It is a design requirement.

Before anything goes live you need to know what good looks like and how you will measure it. You need to know what deviation looks like and at what point you act. You need to know who is responsible and what the options are: retrain the model, update the prompt, or take it offline. And you need to store the inputs, outputs, user actions, and timestamps that will make ongoing performance monitoring possible.

The teams that govern well are not moving slower. They are on the Autobahn.

Author: Adam Dalal
