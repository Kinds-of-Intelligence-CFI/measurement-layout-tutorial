# Measurement Layouts for Capability-Oriented AI Evaluation at AAAI-24

Lab materials for LH3: Measurement Layouts for Capability-Oriented AI Evaluation at AAAI-24 (Vancouver)

**Authors**: J. Burden, J. Hernández-Orallo, M. Tešić, K. Voudouris

## Abstract

Recent years have witnessed an explosion in the general-purpose capabilities of AI systems. These advancements pose unique challenges to how AI systems should be evaluated. Estimating capabilities, rather than performance, is necessary for systems that are not built for specific tasks, but for general-purpose use, and to anticipate the fit of an AI system for situations and occupations requiring particular cognitive skill levels to cope with the expected demands. The techniques and methodologies from the cognitive sciences are more appropriate than task-oriented benchmarks for this evaluation of capability, but require a common language and toolkit to facilitate cross-disciplinary collaboration. One promising approach in this regard is the Measurement Layouts framework, which leverages large, hierarchical Bayesian Networks to infer the capabilities of AI systems. We propose a half-day lab to introduce AAAI-24 participants to the Measurement Layouts framework, demonstrate the powerful evaluation inferences we can make for different kinds of AI systems (RL agents, language models, etc.) and support building a diverse community of interdisciplinary researchers interested in improving AI evaluation.

# Programme

## Introduction (*15 Minutes*)

**Time**: 14:00 - 14:15

**Presenter**: J. Burden, J. Hernández-Orallo, M. Tešić, K. Voudouris

This short opening will consist of the Lab team introducing themselves to the participants. We will likewise encourage participants to introduce themselves and their research interests to the rest of the Lab attendees. The agenda and goals of the lab will be briefly explained.

## Motivating Capability-Oriented Evaluation (*20 Minutes*)

**Time**: 14:15 - 14:35

**Presenter**: J. Hernández-Orallo

This session will establish the motivation for what we refer to as capability-oriented evaluation. We will begin with a discussion of the limitations of current AI evaluation practices, especially for changing distributions and general-purpose AI.  We will identify robust experimental practices from the cognitive sciences that can address the shortcomings of AI evaluation. Specifically, we will frame task performance as a function of task demands and system capabilities. This framing, when combined with appropriate domain knowledge regarding the requirements for success within a task, allows us to estimate actual capabilities that are independent of the distribution of the task's test-set. This requires two inferences, a backwards estimation of the capabilities from test results and task demands, and a forwards inference of predicted performance from the capabilities and the demands of new tasks. 

## The Measurement Layout Framework in PyMC (*50 minutes*)

**Time**: 14:35 - 15:25

**Presenter**: J. Burden

In this session, we will present the measurement layout framework as a model that expresses the connection between the demands of the tasks and the capabilities of the agent, while also accounting for bias introduced by surface feature variations and measurement noise. We will describe the two inferential procedures of the framework for the simultaneous estimation of capabilities (backward inference) and derivation of performance (forward inference). 

We will explain how to leverage hierarchical Bayesian models to express the measurement layout, and next we we will demonstrate how to implement them using the popular probabilistic programming library, PyMC. We will provide a step-by-step guide on how to harness PyMC's powerful Bayesian inference approximation algorithms to learn capabilities, biases, and noise values from experimental data. Additionally, we will show how to implement forward inference techniques to enable performance prediction on new, unseen tasks. We will also explore methods for evaluating the accuracy of our learned models and illustrate several visualization techniques for identifying capabilities.

Participants will then have the opportunity to apply the framework themselves to the scenario of an agent navigation task in a 3D environment. They will be provided with experimental data containing the results of various agents attempting to complete the navigation task and will be tasked with inferring the capabilities and biases of each agent. To successfully accomplish this, participants will need to construct a measurement layout in PyMC using the techniques and methodologies outlined earlier in the session. To guide participants through this process, we will provide a Google Colab template that will handle the more routine aspects of data wrangling and offer a structured approach to the task. The task and experimental data will be designed to allow for success at various levels, with multiple ways of applying the layout that will yield differing levels of certainty regarding the agents' capabilities. We invite participants to collaborate and share measurement layout structures that they find effective or intuitive.

## Break

**Time**: 15:30 - 16:00

## Building Complex Measurement Layouts (*55 minutes*)

**Time**: 16:00 - 16:55

**Presenter**: K. Voudouris

This session will tackle a more complex domain for building measurement layouts, extending the approach introduced in the previous session. The session will centre around an example benchmark, built to systematically study whether reinforcement learning agents can track objects under occlusion (object permanence). We will examine the key criteria for designing principled measureent layouts for robust capability evaluation with measurement layout. Participants will be able to incrementally build a complex measurement laout for studying object permanence as we describe the test battery.

We will emphasise the importance of explicitly defining the capability that we seek to measure. In our example, the test battery is explicitly designed to emulate existing studies of object permanence in comparative and developmental psychology. Conceptualising and defining capabilities and their interactions is crucial to the development of a measurement layout that makes robust evaluations. We will also introduce the notions of internal and construct validity as key criteria for effective evaluation. The internal validity of a benchmark is the extent to which it contains tasks that control for alternative explanations of performance that do not appeal to the capability of interest. For instance, there might exist behavioural policies that produce object-permanence-like behaviour, while lacking the crucial capability. Our example benchmark contains thousands of systematically varied instances to maximise internal validity. The construct validity of a benchmark is the degree to which it measures the capability of interest. We will impart to participants the importance of background theory in evaluating this criterion, as well as the role of empirical study with reference agents, including humans. Our example is accompanied by behavioural data which confirm its construct validity. Maximising internal and construct validity is imperative to robust inferences about capability using measurement layouts.

Participants will be encouraged to consider and discuss how the concepts raised in this session can be applied to evaluate other complex capabilities.

## Learning The Capabilities of Large Language Models (*35 Minutes*)

**Time**: 16:55 - 17:30

**Presenter**: M. Tešić

This session focuses on constructing measurement layouts to understand the capabilities of large language models (LLMs) through benchmark datasets. Building upon the material covered in the previous session, we will delve into a detailed example of creating a measurement layout using PyMC for evaluating LLMs' ability to perform the task of adding two numbers. The session aims to equip participants with the knowledge to assess and apply measurement layouts to predict LLM performance on various tasks.

We will discuss the essential characteristics of benchmarks required for developing these measurement layouts. We will explore the relationship between the abilities assessed by the benchmarks and the meta-features or demands that describe the benchmark instances. Participants will be presented with comprehensive background information regarding the benchmark in question. The benchmark performance data will be used to construct a measurement layout in PyMC to learn the capabilities of 10 different LLMs. Using the measurement layout, we will also be able to infer the likely performance of LLMs on new tasks. We will compare the predictive performance of the measurement layouts to common predictive methods and baselines that we constructed.

Participants will be encouraged to consider and discuss the trade-offs of the capability-oriented evaluation approach, especially concerning the assessment of LLM capabilities using performance data from existing benchmarks. Some key questions include whether current benchmarks adequately and effectively guide the estimation of LLM capabilities, and whether these translate meaningfully into predicted performance in complex and dynamic ``real world'' applications. Participants will also be encouraged to deliberate on the applicability of the capability-oriented approach to their own work.

## Group Discussions (*30 Minutes*)

**Time**: 17:30 - 18:00

**Presenter**: J. Hernández-Orallo

This final session is dedicated to group reflection and discussion. Participants will be encouraged to consider the following questions:
- How could capability-oriented evaluation benefit your own work? 
- How can this approach be applied when there are a large number of relevant features? 
- What can be done in scenarios where domain knowledge is limited? Can we compensate to ensure an incomplete model is still helpful?
- How can these limitations be addressed?

This session is also a natural point for participants to ask any remaining questions or share any other thoughts about the approach and framework. We hope to incite and foster vibrant discussions about the potential of this evaluation schema and its application to rich, real-world domains. We will also use this time to encourage future opportunities for collaboration with interested participants on developing both measurement layouts and other capability-oriented
evaluation techniques.

# Requirements

Participants will require a laptop with a browser and a WiFi connection to access the Google Colaboratory notebooks in this repository. Participants can save their notebooks to their own Google Drive.

# Reference

If you build on top of this tutorial and want to cite it, please use the following bib entry:

```
@misc{mlayoutstutorial2024,
  title =        "Measurement Layouts for Capability-Oriented AI Evaluation",
  author =       "J. Burden, L. Cheke, J. Hernández-Orallo, M. Tešić, K. Voudouris",
  booktitle =    "AAAI: Tutorial",
  year =         "2024",
  abstract =     "Recent years have witnessed an explosion in the general-purpose capabilities of AI systems. These advancements pose unique challenges to how AI systems should be evaluated. Estimating capabilities, rather than performance, is necessary for systems that are not built for specific tasks, but for general-purpose use, and to anticipate the fit of an AI system for situations and occupations requiring particular cognitive skill levels to cope with the expected demands. The techniques and methodologies from the cognitive sciences are more appropriate than task-oriented benchmarks for this evaluation of capability, but require a common language and toolkit to facilitate cross-disciplinary collaboration. One promising approach in this regard is the Measurement Layouts framework, which leverages large, hierarchical Bayesian Networks to infer the capabilities of AI systems. We propose a half-day lab to introduce AAAI-24 participants to the Measurement Layouts framework, demonstrate the powerful evaluation inferences we can make for different kinds of AI systems (RL agents, language models, etc.) and support building a diverse community of interdisciplinary researchers interested in improving AI evaluation."
}
```
