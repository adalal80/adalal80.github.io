---
layout: post
title: "If You Build It, Will They Come? — Part 1: The Trust Problem
---

### Why did the model make that prediction?
I shipped a deep learning model to internal users, 85% accurate, validated against a test set, and signed off by end users during feedback sessions. I had showcased it to stakeholders, walked through the problem it solved, shared the performance metrics, and explained how it was validated. By every measure I was tracking, we were ready.

After it went live, adoption sat at 20%. I asked myself why people weren't using it. The benefits were real. It automated manual decision making and delivered recommendations instantaneously, saving users significant time. So I talked to several users. They asked me: why did the model make that prediction? They told me they had spent significant time trying to understand how the inputs affected the output, but couldn't reconcile it. The model had 12 inputs. They were overwhelmed trying to understand which ones actually drove the prediction they were looking at.

#### Explainability Matters!
Explainability was just as important as accuracy. Data scientists and PMs alike focus on making the model as accurate as possible, and I get that. From a development standpoint, more accurate is better. That's not what users cared about. They wanted to understand the model so they could trust it. Nothing we built gave them that.
PMs, especially AI PMs, focus on building the best model possible. We measure accuracy, F1 score, latency. What we don't factor in, as I didn't initially, is that there is no quantifiable metric for whether a user feels confident enough to act on a prediction. PMs defer to data scientists on model performance, even though it's the PM's job to ensure the model meets user needs, not just technical thresholds. Explainability never came up as a requirement in any of my conversations with users or stakeholders, and so neither I nor the data science team ever considered it.

Why didn't it come up? I met with users and stakeholders to map the manual workflow, accounting for various data sources and inputs. The data scientists built model variations and selected a champion based on model performance. That champion model was then used to predict a sample of data, which users reviewed, again evaluated solely on model performance. At no stage did explainability come up. Users were only responding to what I asked them: do you agree or disagree with this prediction? That feedback loop was designed to measure accuracy. So accuracy is all it ever returned. That is until adoption told me otherwise.

#### The Fix
That changed when we looked at incorporating the top 3 positive and negative drivers behind each prediction. Think of it like a diagnostic check at a mechanic. When a mechanic tells me everything is fine, I don't feel reassured. But when I can see the oil level, transmission fluid, brake pad wear, I feel informed even if I don't fully understand every detail. Did each check truly matter? Not always. But the visibility gave me assurance. My team built MVP2, where every prediction was accompanied by the top 3 positive and negative drivers. Adoption increased by 20% in the first month.

#### This wasn't New
This wasn't the first time I learned this lesson, though it took me a while to connect the dots. In an earlier role, I built rule-based features in Python integrated into an application, including a report that flagged compliance-driven due dates for users. They kept asking why something was due when it was due. At first I thought they didn't trust my work. Then I realized it was uncertainty driving their confusion, not distrust. I added an explainability component that told users exactly why a due date was generated. It took me a while to come full circle. I had to learn that lesson again.

#### Model Selection Is a Product Decision
This is less of a concern for generative AI, where the output can itself serve as the explanation. It's a real concern for non-generative models. Some models I shipped were based on RoBERTa, a black box where extracting the main drivers behind a prediction is genuinely difficult. Others used boosting algorithms like XGBoost and CatBoost, which support feature importance natively. That difference matters more than most PMs realize.

If explainability is a user requirement, and it should be, then model selection is not purely a data science decision. It's a product decision. PMs need to be in that conversation, not just signing off on accuracy thresholds after the fact. The type of model selected should not be determined by performance metrics alone. It should be weighed against a simpler question, one that should be asked during user research, alongside questions about workflow and model performance:

#### "What would you need to see from this model to not only use it, but trust it?"

This is Part 1 of a two-part series, "If You Build It, Will They Come?" Part 2 looks at the same problem from a different angle.
