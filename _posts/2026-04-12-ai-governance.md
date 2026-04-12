---
layout: post
title: "If You Can't Measure It, You Can't Govern It"
---

In a previous post I wrote about how chemical engineering shaped how I think as a product manager. The short version: before anything went live on a refinery, we had to define every operating limit, every alert condition, and every sequence of actions the system would take if something went wrong. You couldn't bolt that on after the fact. The consequences were too significant.

I think about AI governance the same way. Most teams don't.

#### Governance is a design requirement
When I build an AI model, I think about governance before the model is built. In the requirements phase, I am already asking what outcome we are trying to achieve, how we will know we have reached it, and how we will know when we haven't.

The signal that matters most is not just whether a description passes or fails. It is whether a user who received a failing result updated it. That tells you the model is driving the outcome it was built for, not just generating a result nobody acts on. Most teams don't track this. They look at pass rates and stop there.
This is how I thought as a chemical engineer. My job was governance around the unit. If any part deviated from its safety limits, actions were triggered to resolve the situation. In the most serious cases, that meant shutting down a portion of the unit to prevent further damage.

AI governance works the same way. If a model starts drifting, producing inaccurate results, or behaving in ways it shouldn't, you need a defined response. In some cases that means taking it offline to prevent bad outputs from reaching users. But you can only execute that response if you defined it before the model went live.

#### What most teams do instead

Most teams don't think about governance this way. They build the model, ship it, and then figure out what to monitor. The outcome they were trying to achieve was never precisely defined, so there is no baseline, no threshold, no way to know if the system is performing correctly or drifting toward failure.

I see this in my own work. My models are API based. I don't own the application. I can advise, but I can't always control what gets implemented. The application team decides what to track, what to store, and how to surface it. When those decisions are made without a governance framework in place, you end up with blind spots.
The way users interacted with one of my models changed over time. Originally the model was triggered manually by the user when they chose to run it. It became preemptive, running automatically before the user even began their review. I advised the team to track whether a user fixed a failed result when they saved, and to store a monthly snapshot of how the model was being used so we could do trend analysis over time. They stored only the latest run. Now we can't measure month over month change. We can see the current state but we can't see the direction of travel. That is a governance gap, and it exists because nobody defined what needed to be measured before the system was built.

#### What to do instead

AI governance is not a compliance exercise that happens after the model is built. It is a design requirement that has to be defined before anything goes live.
Before anything goes live, you need to know what good looks like and how you will measure it. You need to know what deviation looks like and at what point you act. And you need to know what happens when that point is reached, who is responsible, and what the options are: retrain the model, update the prompt, or take it offline.
You cannot govern what you have not defined. A refinery unit with no operating limits is not a controlled system. It is a risk waiting to materialize. An AI model with no defined outcome, no monitoring thresholds, and no response sequence is the same thing.
Author: Adam Dalal
