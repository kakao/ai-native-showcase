---
layout: default
title: '2.5. Bias Detection, Fairness Verification, and Transparency Assurance, AI Guardrails'
lang: en
parent: 'Chapter 2. AI collaboration culture'
nav_order: 5
permalink: /en/part-03/ch02-collab-culture/bias-detection/
author: albert.hoon
---

# 2.5. Bias Detection, Fairness Verification, and Transparency Assurance, AI Guardrails

Simply establishing a policy system makes it difficult to fully secure the safety and reliability of complex AI systems. After all, since it is people who create and use AI, it is possible to secure fairness and objectivity about AI ethics practices by developing and applying value-neutral technology.

Here, we would like to explain Kakao's technical efforts to make its AI ethical principles measurable or manipulable.

## AI Bias Detection and Mitigation Efforts

- **Recognizing the various sources of bias**: We recognize that AI bias is not only a problem with learning data, but also from various causes, such as the limitations of the algorithms that design models themselves, and the unconscious bias of those who develop and operate AI systems.
- **Reviewing and mitigating biases at the data stage**: The datasets used for AI model training are carefully examined to ensure that there is no bias against specific genders, ages, races, regions, etc. If necessary, we try to reduce data imbalances by improving data collection methods or using techniques such as data augmentation and weight control.
- **Bias detection and correction at the model stage**: Various technical tools and methodologies to verify whether developed AI models do not make unfavorable or unfair predictions for specific groups, or whether they produce results that reinforce socially sensitive stereotypes (e.g.: Fairness metrics¹, counterfactual explanations², etc.) are being studied and applied. If biases are discovered, we try to correct them through algorithm modifications or post-processing techniques.

## Efforts to verify fairness and ensure transparency

- **Application-specific fairness definition and verification**: The concept of “fairness” can be defined differently depending on the field or context in which AI is applied. Therefore, Kakao sets specific standards of fairness by considering the characteristics of each AI application, and has established a process to continuously verify that the model meets these standards.
- **Introduction of explainable AI (XAI, eXplainable AI) technology**: We aim to increase the transparency of AI systems and gain the trust of users by actively researching and introducing XAI technology, which explains the basis for AI making specific decisions or predictions in a form that humans can understand. This explainability is very important, especially when applying AI to sensitive fields such as finance, healthcare, and recruitment.

## Building an AI guardrail system to respond to harmful or inappropriate content

With the recent development of LLM, concerns about the possibility of AI generating harmful or inappropriate content are growing, and as a result, technical and institutional responses to prevent dangerous AI output are becoming increasingly important. To solve these problems and improve the safety of AI services, Kakao has developed its own AI guardrail model and system. Kakao's AI guardrail model is covered in detail in Part 2, Chapter 7.

Securing AI ethics and reliability is not a task that ends once and for all; it is a continuous journey that requires constant consideration and improvement in line with technological advances and changes in social demands.

-----

## Footnotes

1) Fairness Metrics are criteria used to quantitatively evaluate whether a machine learning model makes discriminatory or biased decisions against specific groups (such as gender, race, etc.).

2) Counterfactual Explanations are a method of explanation that answers the question, “What would the model’s prediction have been if the input values had been different?” To help understand why a particular outcome occurred, it presents hypothetical scenarios in which that outcome would not have occurred.