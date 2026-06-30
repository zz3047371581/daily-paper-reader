---
title: "CH-CEMS: A Chinese Multi-Concept Benchmark Dataset Towards Explainable Multi-Modal Sentiment Analysis"
title_zh: CH-CEMS：面向可解释多模态情感分析的中文多概念基准数据集
authors: "Zhuohang Li, Hua Xu, Peiwu Wang, Yingying Wang, Hanlei Zhang, Qianrui Zhou, Yuetian Zou, Long Xiao"
date: 2025-09-17
pdf: "https://openreview.net/pdf?id=ZFAFZyohqL"
tags: ["query:affective-ai"]
score: 10.0
evidence: 首个面向可解释多模态情感分析的数据集
tldr: CH-CEMS提出首个中文可解释多模态情感分析数据集，包含3715个视频段，标注极性和强度以及三种语义概念，填补了可解释情感分析的数据空白。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 可解释多模态情感分析缺乏高质量数据资源，标注推理线索成本高。
method: 构建CH-CEMS，采集视频段并标注极性、强度及三种语义概念。
result: 提供首个中文可解释多模态情感分析数据集，含3715段视频。
conclusion: CH-CEMS将促进可解释情感分析研究。
---

## Abstract
Explainable Multimodal Sentiment Analysis (EMSA) is a booming research area aimed at advancing robust and faithful multimodal language understanding. Recent explainable datasets and methods based on multimodal large language models (MLLMs) have introduced a new paradigm that produces chain-of-thought–style explanations within affective computing. However, high-quality data resources for EMSA remain scarce, largely because annotating reliable reasoning cues is costly and difficult. To address this gap, we introduce CH-CEMS, the first multimodal sentiment dataset for explainable multimodal sentiment analysis. It contains 3,715 curated video segments with polarity and intensity annotations. In addition, we annotate three semantic concepts for each sample (i.e., speaking style, tone of voice, and facial expression), which serve as explicit reasoning cues to enable process-level supervision. To fully leverage these concept cues, we propose a concept-guided reinforcement learning framework with Group Relative Policy Optimization (GRPO) for MLLMs, in which concept-level supervision explicitly constrains cross-modal semantic relations and guides the model to infer sentiment from verifiable concepts. We further establish baselines with state-of-the-art multimodal machine learning methods and MLLMs via zero-shot inference and supervised fine-tuning. Experiments show that MLLMs outperform feature-based methods, typically by 4–12\% in accuracy for three-class sentiment analysis, and that our concept-guided GRPO yields a further 8.5\% improvement, even surpassing closed-source model such as GPT-5. We believe CH-CEMS and the benchmark will facilitate future research on explainable multimodal sentiment analysis. The dataset and codes are avaliable for use at https://anonymous.4open.science/r/CH-CEMS-C34F.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义
- **研究动机**：可解释多模态情感分析（EMSA）旨在为情感推断提供透明的推理线索，但高质量标注数据稀缺，主要因为人工标注可靠的推理概念成本高、难度大。
- **问题定位**：现有数据集大多缺乏显式的中间推理概念，导致模型往往成为“黑箱”，难以验证情感结论的合理性。
- **整体含义**：本文提出首个面向中文的可解释多模态情感分析基准数据集 CH‑CEMS，同时配套一种概念引导的强化学习训练框架，力图推动情感分析从“结果可接受”走向“过程可验证”。

## 方法论
- **数据集构建**：
  - 从公开来源整理 3,715 个视频片段。
  - 每个样本标注情感极性（三分类）和强度。
  - 额外引入三种语义概念作为显式推理线索：**说话风格**、**语调**、**面部表情**。这些概念为模型提供可验证的中间监督信号。

- **概念引导的强化学习框架（GRPO）**：
  - 核心思想：利用概念级监督显式约束不同模态之间的语义关系，引导多模态大语言模型（MLLM）从可验证的概念出发推断情感。
  - 关键技术：采用分组相对策略优化（Group Relative Policy Optimization，GRPO），使模型在生成情感结论的同时，能够符合中间概念的语义约束，从而提升推理的忠实度。
  - 流程：MLLM 接收视频多模态输入 → 生成概念描述（说话风格、语调、面部表情）→ 基于概念推理情感 → 使用 GRPO 优化生成策略，确保概念生成既准确又有助于最终情感判别。

## 实验设计
- **数据集与场景**：
  - 主数据集：CH‑CEMS（3,715 个中文视频片段，三分类情感，极性与强度标注，三种概念标注）。
  - 场景：可解释多模态情感分析，兼顾零样本、有监督微调与强化学习多种训练范式。

- **基准方法**：
  - **基于特征的传统多模态方法**（state-of-the-art multimodal machine learning methods，文中未列出具体名称）。
  - **MLLM 零样本推理**（未指名具体模型，但包含闭源模型如 GPT‑5 的对比）。
  - **MLLM 监督微调**（Supervised Fine‑Tuning）。
  - **概念引导 GRPO 训练**（本文提出）。

- **评价指标**：以三分类情感准确率（accuracy）为主要指标进行对比。

## 资源与算力
- 论文摘要中**未明确说明**使用的 GPU 型号、数量、训练时长或显存消耗等细节。读者如需了解计算开销，需参考完整论文中的实验配置部分。

## 实验数量与充分性
- **实验组数**：摘要未给出具体实验组数，但从描述可推断至少包括：
  1. 传统多模态方法与 MLLM 的对比（零样本/微调）。
  2. 有/无概念引导 GRPO 的消融（因为 GRPO 带来 8.5% 额外提升）。
  3. 与闭源模型 GPT‑5 的横向对比。
- **充分性评价**：从摘要看，实验覆盖了**不同范式**（特征融合、MLLM prompt、微调、强化学习）、**不同规模模型**（开源/闭源），对比维度较全面；但消融实验仅提及概念引导 GRPO 的整体收益，更细粒度的概念拆分实验或模态消融未在摘要中展示，需待正文确认。
- **公平性**：在同等 CH‑CEMS 测试集上统一评估，保证了对比基础的公平。

## 主要结论与发现
- MLLM 显著优于传统特征融合方法，三分类准确率高出 **4–12%**。
- 引入概念引导 GRPO 后，MLLM 准确率再次提升 **8.5%**，甚至超过闭源大模型 GPT‑5。
- 显式的概念级监督能有效规范跨模态语义关系，使情感推理过程更具可解释性与可信度。
- CH‑CEMS 数据集为后续 EMSA 研究提供了高质量、可验证的基准。

## 优点
- **数据创新性**：首个面向中文的可解释多模态情感分析数据集，弥补领域空白。
- **标注深度**：在极性与强度之外，提供三种语义概念作为推理线索，支持过程级监督。
- **方法巧妙性**：GRPO 利用概念约束进行强化学习，避免传统训练中概念与情感脱节的问题，提升推理忠实度。
- **结果出色**：零样本/微调 MLLM 已大幅领先传统方法，所提框架还能进一步超越 GPT‑5，证明其有效性。
- **资源开放**：数据集与代码已公开，有利于复现与后续研究。

## 不足与局限
- **概念粒度有限**：仅标注三类概念（说话风格、语调、面部表情），可能无法覆盖所有情感解释线索（如场景信息、上下文互动等）。
- **模态限定**：关注视觉（表情）与听觉（语调、风格），未涉及文本的语义深度分析，或存在模态交互未充分挖掘。
- **规模限制**：3,715 个样本对于深度 MLLM 训练仍偏小，模型泛化能力需在更大规模数据上验证。
- **偏倚风险**：中文单语种、单文化背景，数据与模型在跨语言、跨文化场景的迁移性未知。
- **实验细节缺失**：摘要仅给出性能提升幅度，未展示详细的消融、统计检验或错误分析，无法判断提升是否稳健、实验数量是否充足。

（完）
