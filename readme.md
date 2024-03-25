# Awesome LLM Unlearning

[![Awesome](https://awesome.re/badge-flat.svg)](https://github.com/YuyangXueEd/Awesome-LLM-VLM-VGM-unlearning)

A collection of papers and resources about Machine Unlearning on LLMs.

Another collection of Vision Language Models and Vision Generative models can be found [here](vlm.md).

---

Large language models (LLMs) have demonstrated remarkable capabilities across various tasks, but their training typically requires vast amounts of data, raising concerns in legal and ethical domains. Issues such as potential copyright disputes, data authenticity, and privacy concerns have been brought to the forefront. Machine unlearning offers a potential solution to these challenges, even though it presents new hurdles when applied to LLMs. In this repository, we aim to collect and organize surveys, datasets, approaches, and evaluation metrics pertaining to machine unlearning on LLMs, with the hope of providing valuable insights for researchers in this field.

## Survey

| Paper Title                                                  | Venue | Year    |
| ------------------------------------------------------------ | ----- | ------- |
|[Knowledge unlearning for LLMs: Tasks, methods, and challenges](http://arxiv.org/abs/2311.15766)| ArXiv |2023.11|
| [Machine Unlearning of Pre-trained Large Language Models](http://arxiv.org/abs/2402.15159)  | ArXiv | 2024.02 |
| [Rethinking Machine Unlearning for Large Language Models](https://arxiv.org/abs/2402.08787) | ArXiv | 2024.02 |
| [Machine Unlearning: Taxonomy, Metrics, Applications, Challenges, and Prospects](http://arxiv.org/abs/2403.08254) | ArXiv| 2024.03|

## Regulations

* [The EU general data protection regulation (GDPR)](https://gdpr-info.eu/), 2017
- [Executive Order on the Safe, Secure, and Trustworthy Development and Use of Artificial Intelligence](https://www.whitehouse.gov/briefing-room/presidential-actions/2023/10/30/executive-order-on-the-safe-secure-and-trustworthy-development-and-use-of-artificial-intelligence/), 2023

## Datasets

|Name|Description|Used By|
|----|-----|--|
|[BBQ (Bias Benchmark for QA)](https://github.com/nyu-mll/BBQ)|a dataset of question sets constructed by the authors that highlight attested social biases against people belonging to protected classes along nine social dimensions relevant for U.S. English-speaking contexts. |[Zhao et al.](https://arxiv.org/abs/2312.12736), |
|[HarmfulQA](https://huggingface.co/datasets/declare-lab/HarmfulQA)|a ChatGPT-distilled dataset constructed using the Chain of Utterances (CoU) prompt. |[Zhao et al.](https://arxiv.org/abs/2312.12736)|
|[CategoricalHarmfulQA](https://huggingface.co/datasets/declare-lab/CategoricalHarmfulQA)| Thus, the dataset consists of 550 harmful questions, 55 such questions are shown in the table. | [Bhardwaj et al.](https://arxiv.org/pdf/2402.11746.pdf)|
|[Pile](https://arxiv.org/abs/2101.00027)|an 825 GiB English text corpus targeted at training large-scale language models.|[Zhao et al.](https://arxiv.org/abs/2312.12736)|
|[Detoxify](https://docs.unitary.ai/detoxify)|Detoxify is a simple, easy to use, python library to detect hateful or offensive language. It was built to help researchers and practitioners identify potential toxic comments.|[Zhao et al.](https://arxiv.org/abs/2312.12736)|
|[Enron Email Dataset](https://www.cs.cmu.edu/~enron/)||[Wu et al.](https://aclanthology.org/2023.emnlp-main.174)|
| [Training Data Extraction Challenge](https://github.com/google-research/lm-extraction-benchmark)| | [Jang et al.](https://aclanthology.org/2023.acl-long.805), |
| [Harry Potter book series dataset](https://huggingface.co/microsoft/Llama2-7b-WhoIsHarryPotter)| | [Eldan et al.](http://arxiv.org/abs/2310.02238), [Shi et al.](http://arxiv.org/abs/2310.16789) |
| [Real Toxicity Prompts](https://aclanthology.org/2020.findings-emnlp.301/)| |[Lu et al.](http://arxiv.org/abs/2205.13636), [Liu et al.](https://arxiv.org/abs/2105.03023)  |
| [TOFU](https://huggingface.co/datasets/locuslab/TOFU) | |[Maini et al.](http://arxiv.org/abs/2401.06121)|
| [WMDP](https://wmdp.ai) | |[Li et al.](https://arxiv.org/abs/2403.03218.pdf) |

## Methods

### Gradient-ascend and its variants

| Paper Title | Author | Paper with code | Key words  | Venue | Time |
| ------------| -------| -----------| -----------------| ------| -----|
| [Composing Parameter-Efficient Modules with Arithmetic Operations](https://arxiv.org/abs/2306.14870) | Zhang et al. | [Github](https://github.com/hkust-nlp/PEM_composition) | use LoRA to create task vectors and accomplish unlearning by negating tasks under these task vectors. | NeurIPS 2023 | 2023-06|
| [Knowledge Unlearning for Mitigating Privacy Risks in Language Models](https://aclanthology.org/2023.acl-long.805)| Jang et al. |  [Github](https://github.com/joeljang/knowledge-unlearning) |updating the model parameters by maximizing the likelihood of mis-prediction for the samples within the forget set $D_f$| ACL 2023 | 2023-07|
|[Unlearning Bias in Language Models by Partitioning Gradients](https://aclanthology.org/2023.findings-acl.375) | Yu et al. | [Github](https://github.com/CharlesYu2000/PCGU-UnlearningBias) | aims to minimize the likelihood of predictions on relabeled forgetting data | ACL 2023 | 2023-07|
| [Who’s Harry Potter? Approximate Unlearning in LLMs](https://arxiv.org/abs/2310.02238) | Eldan et al. | [HuggingFace](https://huggingface.co/microsoft/Llama2-7b-WhoIsHarryPotter) | descent-based fine-tuning, over relabeled or randomly labeled forgetting data, where generic translations are used to replace the unlearned texts.             | ICLR 2024        | 2023-10 |
| [Unlearn What You Want to Forget: Efficient Unlearning for LLMs](https://aclanthology.org/2023.emnlp-main.738) | Chen and Yang | [Github](https://github.com/SALT-NLP/Efficient_Unlearning) |  fine-tune an adapter over the unlearning objective that acts as an unlearning layer within the LLM. | EMNLP | 2023-12 |
| [Machine Unlearning of Pre-trained Large Language Models](http://arxiv.org/abs/2402.15159)| Yao et al. |  [Github](https://github.com/yaojin17/Unlearning_LLM) |incorporate random labeling to augment the unlearning objective and ensure utility preservation on the retain set $D_r$ | ArXiv | 2024-02 |


### Localisation-informed unlearning

| Paper Title | Author | Paper with code | Key words  | Venue | Time |
| ------------| -------| -----------| -----------------| ------| -----|
|[Locating and Editing Factual Associations in GPT](http://arxiv.org/abs/2202.05262)| Meng et al. | [Github](https://github.com/EleutherAI/knowledge-neurons)| the process of localization can be accomplished through representation denoising, also known as causal tracing, focusing on the unit of model layers.| ArXiv | 2022-02|
|[Unlearning Bias in Language Models by Partitioning Gradients](https://aclanthology.org/2023.findings-acl.375) | Yu et al. | [Github](https://github.com/CharlesYu2000/PCGU-UnlearningBias) | gradient-based saliency is employed to identify the crucial weights that need to be fine-tuned to achieve the unlearning objective. | ACL 2023 | 2023-07|
| [DEPN: Detecting and Editing Privacy Neurons in Pretrained Language Models](https://arxiv.org/abs/2310.20138) | Wu et al. | [Github](https://github.com/flamewei123/DEPN)|neurons that respond to unlearning targets are identified within the feed-forward network and subsequently selected for knowledge unlearning. | EMNLP 2023   | 2023-10 |
| [Can Sensitive Information Be Deleted From LLMs? Objectives for Defending Against Extraction Attacks](http://arxiv.org/abs/2309.17410)| Patil et al. | [Github](https://github.com/Vaidehi99/InfoDeletionAttacks) | it is important to delete information about unlearning targets wherever it is represented in models in order to protect against attacks| ArXiv | 2023-09|

### Influence function-based method

| Paper Title | Author | Paper with code | Key words  | Venue | Time |
| ------------| -------| -----------| -----------------| ------| -----|
| [Studying Large Language Model Generalization with Influence Functions](http://arxiv.org/abs/2308.03296)| Grosse et al. | [No Code Avaialble] | the potential of influence functions in LLM unlearning may be underestimated, given that scalability issue, and approximation errors can be mitigated by focusing on localized weights that are salient to unlearning.| ArXiv | 2023-08|

### Other model-based method

| Paper Title | Author | Paper with code | Key words  | Venue | Time |
| ------------| -------| -----------| -----------------| ------| -----|
| [Can Sensitive Information Be Deleted From LLMs? Objectives for Defending Against Extraction Attacks](http://arxiv.org/abs/2309.17410) | Hase et al. | [Github](https://github.com/Vaidehi99/InfoDeletionAttacks?utm_source=catalyzex.com)|Defending attacks.|ICLR 2024|2023-09|
| [Learning and Forgetting Unsafe Examples in Large Language Models](https://arxiv.org/abs/2312.12736)|Zhao et al.|[No Code Available] |Fine-tuning based.|  ArXiv| 2023-12|
| [Second-Order Information Matters: Revisiting Machine Unlearning for Large Language Models](http://arxiv.org/abs/2403.10557)| Gu et al. | [No Code Available] |sequential editing of LLMs may compromise their general capabilities.| ArXiv | 2024-03|
| [Towards Efficient and Effective Unlearning of Large Language Models for Recommendation](https://arxiv.org/pdf/2403.03536.pdf) | Wang et al. |  [Github](https://github.com/justarter/E2URec)                  |**Using LLM Unlearning in Recommendation** | ArXiv        | 2024-03 |
| [The WMDP Benchmark: Measuring and Reducing Malicious Use With Unlearning](https://arxiv.org/abs/2403.03218.pdf) | Li et al. |They control the model towards having a novice-like level of hazardous knowledge, designed a loss function with a forget loss an a retrain loss. The forget loss bends the model representations towards those of a noive, while the retain loss limits the amount of general capabilities removed. |[Homepage](https://wmdp.ai) | ArXiv | 2024-03 | 


### Input-based method

| Paper Title | Author |  Paper with code |Key words |  Venue | Time |
| ------------| -------| -----------| -----------------| ------| -----|
| [Memory-assisted prompt editing to improve gpt-3 after deployment](https://arxiv.org/abs/2201.06009) | Madaan et al. | [Github](https://github.com/madaan/memprompt?utm_source=catalyzex.com)| have also shown promise in addressing the challenges posed by the restricted access to black-box LLMs and achieving parameter efficiency of LLM unlearning.| EMNLP 2022 | 2022-01|
|[Alignment Studio: Aligning Large Language Models to Particular Contextual Regulations](https://arxiv.org/abs/2403.09704)| Achintalwar et al.|[No Code Available]()|aligning a company's internal-facing enterprise chatbot to its business conduct guidelines|ArXiv| 2024-03|






## Evaluation

### Attacking and Defending

| Paper Title | Author | Paper with code |                                                  Key words               | Venue | Year    |
| ------------|--------|---------------------------------------- | ----------------------- | ----- | ------- |
| [Can Sensitive Information be Deleted from LLMS? Objectives for Defending Against Extration Attacks](http://arxiv.org/abs/2309.17410) |Patil et al. | [Github](https://github.com/Vaidehi99/InfoDeletionAttacks)| | ArXiv| 2023.09 |
| [Detecting Pretraining Data from Large Language Models](https://arxiv.org/abs/2310.16789) | Shi et al. | [Github](https://github.com/swj0419/detect-pretrain-code)| pretrain data detection | ArXiv | 2023.10 |
| [Practical Membership Inference Attacks against Fine-tuned Large Language Models via Self-prompt Calibration](https://arxiv.org/abs/2311.06062) | Fu et al. | [No Code Available] | finetune data detection | ArXiv | 2023.11 |
| [Tensor trust: Interpretable prompt injection attacks from an online game](https://arxiv.org/abs/2311.01011)|  Toyer et al. | [Github](https://github.com/HumanCompatibleAI/tensor-trust-data/tree/main) | input-based methods may not necessarily yield genuinely unlearned models, leading to weaker unlearning strategies compared to model-based methods because modifying the inputs of LLMs alone may not be sufficient to completely erase the influence of unlearning targets| ArXiv | 2023-11|

### Benchmarks

| Paper Title| Author| Paper with code |                                                  Key words | Venue | Year    |
| -----------|-------|------------------------------------------ | --------- | ----- | ------- |
| [TOFU: A Task of Fictitious Unlearning for LLMs](https://arxiv.org/abs/2401.06121.pdf) |  Maini et al. |  [Homepage](https://locuslab.github.io/tofu/?utm_source=catalyzex.com)|        | ArXiv | 2024.01 |
| [Machine Unlearning of Pre-trained Large Language Models](https://arxiv.org/pdf/2402.15159.pdf) | Yao et al. | [Github](https://github.com/yaojin17/Unlearning_LLM?utm_source=catalyzex.com)|          | ArXiv | 2024.02 |
| [Eight Methods to Evaluate Robust Unlearning in LLMs](http://arxiv.org/abs/2402.16835) | Lynch et al. | [No Code Available] || ArXiv | 2024.02 |
| [The WMDP Benchmark: Measuring and Reducing Malicious Use With Unlearning](https://arxiv.org/abs/2403.03218.pdf) | Li et al. | [Homepage](https://wmdp.ai) |Biology, Cyber and Chemical| ArXiv | 2024.03 | 
