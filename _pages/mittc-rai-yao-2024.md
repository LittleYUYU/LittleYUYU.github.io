---
layout: page
permalink: /mittc-rai-yao-2024/
title: English Translate of MIT Technology Review China's Interview of Rai and Yao's ACL 2024 Paper
nav: false
---

<h1>How does Chain-of-Thought (CoT) stimulate the arithmetic reasoning ability of large models? Scientists provide an answer from the perspective of neuron activation.</h1>

_This article is an English translate of MIT Technology Review China's article interviewing Rai and Yao's ACL 2024 paper. The source article can be found at: https://www.mittrchina.com/news/detail/13615. The English translation is assisted with ChatGPT._


Large models have received widespread attention over the past one to two years, particularly for their achievements in solving arithmetic and mathematical problems.

In fact, as early as 2022, researchers from the Google Research team proposed the Chain-of-Thought (CoT) prompting method, which effectively improves the mathematical reasoning of large models. This method's effectiveness was validated in few-shot learning contexts.

Although this method was quickly adopted, researchers still know little about how it stimulates the arithmetic reasoning ability of large models.

Previous explorations mainly focused on experimentally observing the impact of different components of CoT prompts on the arithmetic reasoning of large models.

Specifically, they tried replacing or removing components of CoT prompts, such as removing the textual reasoning part and leaving only the critical mathematical formulas. By observing performance differences before and after the replacement or removal on existing arithmetic reasoning benchmarks, they assessed whether the removed part contributed significantly to the arithmetic reasoning ability of the large model.

Although researchers have discovered several interesting phenomena, they still cannot explain how CoT stimulates the arithmetic reasoning ability of large models from the internal mechanism of neural networks.

These studies also raised more questions, such as why different components of CoT bring different degrees of impact on the arithmetic reasoning of large models.

To solve these problems, <a href="https://ziyuyao.org/">Professor Ziyu Yao</a> and her team at George Mason University conducted a series of explorations on the open-source Llama2 model from the perspective of "model interpretability" and proposed using "neuron activation" to systematically explain the phenomena observed in CoT.

Recently, the related paper titled <a href="https://arxiv.org/pdf/2406.12288">"An Investigation of Neuron Activation as a Unified Lens to Explain Chain-of-Thought Eliciting Arithmetic Reasoning of LLMs"</a> was accepted by <a href="https://2024.aclweb.org/">the Annual Meeting of the Association for Computational Linguistics (ACL) 2024</a>.

The research first focused on exploring whether the Transformer feedforward layer expressed neurons representing arithmetic reasoning concepts.

The relevant concepts include arithmetic operations (addition, subtraction, multiplication, division), logical links in arithmetic reasoning (such as "therefore," "next"), and other arithmetic calculation concepts (such as "percentage," "algorithm," "formula").

To discover the concepts represented by each neuron, they mapped neurons to the model's vocabulary space and annotated the concept weights on each word after mapping. This way, they summarized the meanings represented by the neurons.

They proposed using GPT-4 to read and understand neuron vocabulary mappings to automate this neuron annotation and discovery process.

Experiments showed that the Transformer feedforward layer contains neurons representing arithmetic concepts. When these neurons are disrupted, the arithmetic reasoning ability of the large model is impaired.

Researchers also observed a positive correlation between the activity level of these neurons and the arithmetic reasoning ability of the large model. This positive correlation explains why different prompt sentences bring different effects on the arithmetic reasoning of large models.

Based on these neurons, the team systematically explained four CoT-related phenomena observed in previous studies:

When the mathematical formula is removed from the CoT sample, leaving only the calculation result, the model's arithmetic reasoning ability is impaired.
When textual reasoning is removed from the CoT sample, leaving only the mathematical formula, the model's ability is also impaired.
When the CoT sample lacks operational diversity (e.g., all samples only involve addition), the model's ability is impaired.
When the operational result in the CoT sample is incorrect, but the reasoning process is correct, the model's ability is not significantly affected.
"We see that these phenomena can be explained by the activation level of neurons. For example, the number of activated neurons decreases before and after the mathematical formula is removed, explaining why the model's arithmetic reasoning ability is impaired," the researchers explained.

From an application perspective, this achievement has two potential applications.

First, it can be used to predict the ability of large models.

In experiments, researchers have already seen a positive correlation between the activation level of neurons representing arithmetic reasoning and the arithmetic reasoning ability of the Llama2 model. This means that in the future, benchmark tests might not be necessary to predict a large model's ability in specific tasks.

Second, it can enhance or weaken the model's ability by controlling the model's internal mechanisms.

"This application will become an important method to improve the safety of large models in the future. It also has the potential to achieve more efficient large model training by locating neurons with small data and then controlling neuron activation to achieve model training," the research team said.

In the second half of 2023, OpenAI proposed the "super alignment" proposal, aiming to help humans regulate and control superhuman AI models by encouraging scientific innovation. Predicting and controlling model capabilities are two important tasks to achieve this goal.

"This result is a preliminary exploration in this direction, and we hope that we or other researchers can continue to explore in this direction," the team said. This research is inspired by "mechanism interpretability."

This is a subfield of model interpretability that has rapidly emerged and received widespread attention in recent years. Unlike previous interpretability methods, mechanism interpretability attempts to understand the behavioral mechanisms of models by reverse engineering neural networks.

Currently, this type of method has been applied to explain the behavior and structural functions of large models.

"One particularly enlightening study for us is the exploration of the Transformer feedforward layer by researchers from the Allen Institute for AI and Bar-Ilan University in Israel," the researchers said.

This study found that during the process of predicting the next token, the Transformer feedforward layer constructs predictions by continuously reinforcing related concepts in the vocabulary space. This concept reinforcement is achieved by activating the neurons of the Transformer feedforward layer.

"This mechanistic discovery inspired our hypothesis: CoT might effectively activate neurons representing arithmetic reasoning concepts in the Transformer feedforward layer, thereby enhancing the large model's arithmetic reasoning ability," the research team said.

Based on this, the team conceived whether a mechanism exists that can directly enhance the arithmetic reasoning ability of language models, especially small-scale language models.

The team pointed out: "This is very meaningful because small-scale language models enjoy unique computational efficiency, economic efficiency, and safety."

During the same period, they also saw some research improving the capabilities of small-scale language models in specific fields or tasks by collecting high-quality data or modifying training objective functions. However, the application of mechanism interpretability in this area is still in its emerging stage.

Nevertheless, the team's research process was not smooth and faced difficulties from the start.

The biggest challenge was that they did not fully understand the internal mechanisms of language models' arithmetic reasoning, and naturally could not realize the envisioned model control.

"Therefore, my student Rai, the first author of the paper, and I decided to focus on explaining the arithmetic reasoning of language models first," Ziyu Yao said.

But they soon encountered the next challenge.

"Arithmetic reasoning" is a highly abstract concept, while the language model's predictive execution is at the specific token level.

To understand the arithmetic reasoning ability of large models from the perspective of "concept reinforcement of neurons in the vocabulary space," they first had to implement this highly abstract concept into specific token-level concepts.

To bridge this gap, the team summarized several lower-level concepts related to arithmetic reasoning, including arithmetic operators, logical language expressions in arithmetic reasoning, and other arithmetic calculation concepts.

By efficiently annotating and searching neurons expressing these lower-level concepts with GPT-4, they referred to previous studies to validate these discovered neurons.

"Experimental results prove that these neurons indeed play an important role in the language model Llama2 we experimented with," the team said.

This gave them more confidence to continue exploring in this direction.

They thought of using the activation state of these neurons to uniformly explain the effect of CoT on the arithmetic reasoning ability of large models, including explaining several phenomena observed in previous work.

The results basically confirmed their hypothesis that the activation of relevant neurons could explain the stimulating effect of different components of CoT on the arithmetic reasoning ability of large models.

However, the study also pointed out that neuron activation cannot explain all the arithmetic reasoning performances of language models. Additionally, whether the findings on Llama2 apply to other language model families remains to be further validated.

It is also reported that Ziyu Yao's lab currently has several fully-funded PhD positions for Fall 2025 enrollment. For details, please check our her website https://ziyuyao.org/ and email inquiries.
