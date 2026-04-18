---
layout: post
title: "If You Build It, Will They Come? — The Problem With How Leadership Thinks About AI"
---

I am a Senior PM who has spent the last several years building AI and data products in a regulated environment, and what I am about to describe is a pattern I have watched repeat itself. The push is almost always top down. Leadership decides the organization needs to be doing AI, sets a target, and the teams below them start building. The problem is that the demand for most of what gets built was never really there. A goal was set and the goal was activity.
Part of what drives this is that leadership is competing internally to show leadership above them how they are pushing the AI agenda. The result is a race to ship more and ship faster, and nobody stops to ask whether any of it is working.

#### Racing stripes on a Honda Accord

In the end, it is a lot of tools that look like AI transformation but function more like decoration. It is like putting racing stripes and a spoiler on a Honda Accord and calling it an F1 car. The optics are there but the engineering underneath has not changed. Quantity becomes the proof of progress, and quality never enters the conversation. And because each team is competing to show their own results, you end up with redundant tools solving the same problem in slightly different ways, cannibalizing each other's adoption before either one has a chance to prove its value.

#### Looking for nails

The way I think about it is that the approach is backwards. It should not be a case of having a hammer and looking for something to hit. It should be the other way around, where you see a nail sticking out of the wood and you reach for the right tool to drive it in. AI is not the answer to every problem, and treating it like one is how you end up with a catalog of tools that nobody asked for and nobody uses.
What that produces at the user level is cognitive overload. When there are too many prompts and too many tools, users do not know which one to trust or which one applies to their situation. Instead of reducing friction, you have added to it. The tool was supposed to make the job easier and instead it made the decision harder, because now the user has to figure out which tool to use before they can even start the work.

#### Show metrics versus impact metrics

What gets measured makes it worse. The metrics that get tracked are the ones that show activity, such as the number of models built, the number of prompts deployed, and how many teams have adopted AI in some form. These are show metrics because they demonstrate that something happened, not that anything changed. The impact metrics, whether users are actually using the tools, whether the tools are driving the outcome they were built for, and what the return on investment looks like, are rarely defined and almost never tracked.

A simple example from my own work illustrates this. One of my models flags descriptions that fail a data quality check. The overall pass rate is an important metric because it tells you about the health of the data, but it cannot tell you whether the model had anything to do with it. To quantify the value of the model specifically, you need a different signal, which is whether a user who received a failing result actually updated their description afterward. Both metrics matter, but only one tells you whether the AI is driving the outcome it was built for.

#### The question that should come first

I build anyway when the decision has already been made above me, and I recognize that is the reality for most people in this position. By the time it reaches the PM, the conversation is over. But that does not mean the question should stop being asked earlier in the process, before the work starts and before the resources are committed.

Before any AI use case gets approved, someone should have to answer a few questions. What do you consider the value of the tool we are about to build, and how will it impact the users it is built for? Not in a vague sense, but specifically. What behavior are you trying to change, how will you know if it changed, and what does success look like beyond the number of people who have access to it.

AI is a capable tool. The problem is not the technology, it is the framing. When the goal is to show AI is happening rather than to solve a problem worth solving, the tools that get built reflect that. They exist to be counted, not to be used. And users, eventually, can tell the difference.

Author: Adam Dalal
