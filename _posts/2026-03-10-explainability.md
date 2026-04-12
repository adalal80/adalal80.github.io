---
layout: post
title: "If You Build It, Will They Come? - Why Your AI Model's Explainability Might Be the Problem"
---

#### Why did the model make that prediction?
I shipped a deep learning model to internal users, 85% accurate, validated against a test set and signed off by end users. The users reviewing its recommendations were the same people who had been making those decisions manually for years. I presented it to stakeholders, walked through the problem it solved, shared the performance metrics, and explained how it was validated. By every measure I was tracking, we were ready.

After it went live, adoption sat at 20%. I asked myself why people weren't using it. So I talked to several users. They asked me: why did the model make that prediction? They told me they had spent significant time trying to understand how the inputs affected the output, but couldn't reconcile it. The model had 12 inputs. They were overwhelmed trying to understand which ones actually drove the prediction they were looking at. They ultimately told us they were not going to use a model they could not reverse engineer. These were experts who had been doing this work manually for years.

#### Explainability was never part of the conversation
Explainability is just as important as accuracy, but it never came up once, not in user research, not in stakeholder reviews, not in model validation. That's because every conversation I had with users was designed to measure one thing: do you agree or disagree with this prediction? That feedback loop only ever returned accuracy. I didn't know what I wasn't asking.

#### Model Selection Is a Product Decision
Low adoption was the symptom. The root cause was that explainability was never considered.

For this deep learning model, extracting what drove a specific prediction is possible but not straightforward. Techniques exist, but they require additional effort and the results are not always clean or intuitive for end users. A traditional ML model with native feature importance tells you how much each input contributed to the prediction, out of the box. When explainability is a requirement, that difference has a real cost.

This is where it gets uncomfortable. What if the black box model is more accurate than the interpretable one? That is a real tradeoff, and there is no universal answer. But it is a product decision, not a data science decision. The right model depends on your user, not just your benchmark.

If explainability is a user requirement, and it should be, then model selection is not purely a data science decision. PMs need to be in that conversation, not just signing off on accuracy thresholds after the fact. The type of model selected should not be determined by performance metrics alone. It should be weighed against a simpler question, one that should be asked during user research alongside questions about workflow and model performance:

"What would you need to see from this model to not only use it, but trust it?"

Author: Adam Dalal
