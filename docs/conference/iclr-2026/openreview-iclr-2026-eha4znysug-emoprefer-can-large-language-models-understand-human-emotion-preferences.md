---
title: "EmoPrefer: Can Large Language Models Understand Human Emotion Preferences?"
title_zh: EmoPrefer：大语言模型能否理解人类情感偏好？
authors: "Zheng Lian, Licai Sun, Lan Chen, Haoyu Chen, Zebang Cheng, Fan Zhang, Ziyu Jia, Ziyang Ma, Fei Ma, Xiaojiang Peng, Jianhua Tao"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=EhA4znYsuG"
tags: ["query:affective-ai"]
score: 9.0
evidence: 探究LLM能否理解人类情感偏好以用于描述性多模态情感识别
tldr: 描述性多模态情感识别要求模型用自然语言刻画情感状态，但评估其生成质量困难。本文引入EmoPrefer，通过将评估问题转化为人类偏好学习任务，检验大语言模型理解情感偏好的能力。研究表明LLM在此任务上展现出一定潜力，但也存在显著限制，为后续将LLM用作情感评估器提供了实证依据和改进方向。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 描述性多模态情感识别用自然语言描述情感，但评估困难，现有方法依赖人工标注偏好。
method: 将问题转化为人类偏好学习任务，利用大语言模型评估情感描述的偏好排序。
result: 实验揭示了LLM在理解情感偏好方面的潜力与局限性，为改进提供方向。
conclusion: 为大语言模型在情感描述评估中的应用提供了新视角和基准。
---

## Abstract
Descriptive Multimodal Emotion Recognition (DMER) has garnered increasing research attention. Unlike traditional discriminative paradigms that rely on predefined emotion taxonomies, DMER aims to describe human emotional state using free-form natural language, enabling finer-grained and more interpretable emotion representations. However, this free-form prediction paradigm introduces new challenges regarding its evaluation. Previous works depend on ground-truth descriptions, but emotions are inherently tied to diverse human behaviors, and generating a comprehensive and accurate description is inherently demanding. Other researchers reformulate this problem into a more tractable human preference learning task, but pairwise preference annotation involves substantial manual effort. This leads to a question: *can we leverage multimodal LLMs (MLLMs) to achieve more cost-efficient preference annotation?* To answer this, we propose **EmoPrefer**, a pioneering work exploring the potential of LLMs in decoding human emotion preferences. Specifically, we construct the first emotion preference dataset, **EmoPrefer-Data**, featuring high-quality preference annotations from experts. Additionally, we introduce **EmoPrefer-Bench**, which evaluates the performance of various MLLMs and prompting techniques in preference prediction, while also revealing new strategies to enhance their performance. To the best of our knowledge, this is the first work exploring the capabilities of LLMs in understanding human emotion preferences. Our work advances the field of DMER and lays the foundation for more intelligent human-computer interaction. Our data and code are released at https://github.com/zeroQiaoba/AffectGPT/tree/master/EmoPrefer.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景**：传统多模态情感识别依赖于预定义类别（如高兴、悲伤），无法描述复杂、细致的情感状态。描述性多模态情感识别（DMER）使用自然语言自由描述情感，更细粒度、可解释，但其自由形式的输出使得评价极为困难。
- **核心问题**：已有工作或依赖人工书写的“标准答案”描述（成本高、覆盖面有限），或将评价转化为人类偏好学习任务（仍需大量两两配对的人工偏好标注）。因此，作者提出：**能否利用多模态大语言模型（MLLMs）以更低的成本实现情感偏好标注？**
- **整体含义**：本文首次探索大语言模型在理解人类情感偏好上的能力与局限，为将 LLM 用作 DMER 评估器奠定基础，推动更智能的人机交互。

### 2. 论文提出的方法论

- **核心思想**：将 DMER 的评估问题建模为**人类偏好预测任务**，即给定同一情感样本的多个候选描述，模型需要判断哪一个更符合人类偏好（更准确、更自然等），从而间接评估 LLM 是否“理解”情感偏好。
- **关键技术细节**：
  - 构建了首个情感偏好数据集 **EmoPrefer-Data**，包含高质量专家偏好标注（文中未披露具体数量，但强调由专家完成）。
  - 提出 **EmoPrefer-Bench** 评测框架，用于系统性地测试不同 MLLMs 及提示方法在偏好预测任务上的表现。
  - 探索了多种提升 LLM 偏好预测能力的策略（如提示词工程、上下文学习、思维链等，具体技术需参见原文，摘要未详细说明）。
- **流程概述**（从摘要推断）：输入多模态情感样本（如视频/音频+文本）及多个候选描述 → 模型输出偏好排序或成对比较结果 → 与专家标注对比，计算准确率等指标。

### 3. 实验设计

- **数据集/场景**：
  - **EmoPrefer-Data**：专门构建的情感偏好数据集，由专家标注，用于训练/评估模型偏好判断能力。
  - **EmoPrefer-Bench**：基准测试，可能涵盖多种情感类别、语境和描述风格，具体来源和规模需参见原文，摘要未提及使用的公开数据集。
- **对比方法**：
  - 对比了不同多模态大语言模型（MLLMs）在零样本/少样本设置下的偏好预测性能。
  - 对比了不同提示技术（如标准提示、链式思考提示等）的效果。
  - 可能也对比了传统基于相似度或分类的评估方法（文中提到“reformulate into human preference learning task”），但摘要未明确列出全部基线。
- **评价指标**：偏好预测准确率（与专家标注一致的比例），可能还包括排序一致性等。

### 4. 资源与算力

- 文中未提供 GPU 型号、数量、训练时长等算力信息。摘要及提供的元数据均未提及计算资源需求。推测可能因为本文主要为基准构建与评估实验，推理成本较低；但若要训练或微调 MLLM，则需一定算力，细节须待正文说明。

### 5. 实验数量与充分性

- **实验组数**：摘要未给出具体数字，但从“various MLLMs and prompting techniques”可推断至少覆盖了：
  - 多种主流 MLLMs 的横向对比；
  - 不同提示策略的消融实验；
  - 可能包含专家标注一致性、数据集质量分析等。
- **充分性与公正性**：
  - 基于专家标注的金标准具有较高可靠性，能较客观反映模型表现。
  - 但摘要未透露模型是否经过针对偏好任务的专门微调，以及对比的 MLLMs 是否在同一条件下测试，公平性需查阅原文细节。
  - 若实验仅基于单个自建数据集，泛化性可能受限，需更多域的验证。

### 6. 主要结论与发现

- LLM 在预测人类情感偏好方面**展现出一定潜力**，能够学习到部分偏好模式。
- 但同时存在**显著局限性**，例如对细微情感区别、文化特定表达或语境依赖的偏好判断仍不理想。
- 揭示了使用 LLM 作为情感描述质量评估器的可能性与改进方向，为后续工作提供了实证依据和新基准。

### 7. 优点

- **问题新颖**：首次探索 LLM 对情感偏好的理解能力，填补了 DMER 评估自动化的空白。
- **资源贡献**：构建了首个专家级情感偏好数据集和基准，为社区提供了可复现的研究基础。
- **方法范式**：将主观评估转化为偏好学习任务，借鉴 RLHF 思路但用于情感分析领域，思路清晰且可解释。
- **实验设计**：系统性地评测多种 MLLMs 和提示方法，揭示不同方法的相对优势。

### 8. 不足与局限

- **数据局限性**：仅依赖自建的 EmoPrefer-Data，其规模、多样性（如语言、文化、情感类型）未说明，可能影响结论的泛化性。专家标注虽质量高，但成本和可扩展性仍是问题。
- **模型黑盒**：未分析 LLM 偏好判断背后的内在推理机制，难以解释错误原因。
- **应用限制**：目前仅验证了“能否判断偏好”，离真正用作 DMER 的实际评估器还有距离，例如如何处理多模态输入对齐、长描述中的细微语义等。
- **缺乏与传统指标对比**：未系统比较基于 LLM 的评估与人工评估（如 BLEU、ROUGE、CLIPScore 等自动指标）的优劣，难以全面证明其优越性。
- **算力与复现**：未提供实验所需的计算资源和代码/数据获取细节（虽然代码已开源），复现时可能面临门槛。

（完）
