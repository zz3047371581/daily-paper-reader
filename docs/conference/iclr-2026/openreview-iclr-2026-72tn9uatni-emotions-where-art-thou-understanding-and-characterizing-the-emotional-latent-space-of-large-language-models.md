---
title: "Emotions Where Art Thou: Understanding and Characterizing the Emotional Latent Space of Large Language Models"
title_zh: 情感何处觅：理解与表征大语言模型的情感潜在空间
authors: "Benjamin Reichman, Adar Avsian, Larry Heck"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=72TN9UAtNI"
tags: ["query:affective-ai"]
score: 9.0
evidence: 识别LLM隐藏状态中的低维情感流形，展示跨语言的通用情感子空间
tldr: 本文深入探究大语言模型对情感的隐式表征：利用情感改写数据集，通过奇异值分解识别出低维情感流形，发现情感方向编码分散在不同层中，且跨层一致、跨语言和跨数据集泛化。基于此情感子空间，可操控模型的内部情感感知。该研究为构建情感智能LLM提供了可解释的几何表征和操控路径。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 大语言模型内部如何表征情感尚不清晰，缺乏对情感空间几何结构的理解。
method: 利用情感改写联合数据集，通过奇异值分解发现低维情感流形，探究方向编码和层次分布。
result: 情感表征跨层稳定，可跨五个语言八个数据集泛化，线性探测性能强，情感感知可操控。
conclusion: 揭示LLM具有通用情感子空间，为情感计算提供可解释的几何基础。
---

## Abstract
This work investigates how large language models (LLMs) internally represent emotion by analyzing the geometry of their hidden-state space. Using a synthetic dataset of emotionally rewritten sentences, we identify a low-dimensional emotional manifold via singular value decomposition and show that emotional representations are directionally encoded, distributed across layers, and aligned with interpretable dimensions. These structures are stable across depth and generalize to eight real-world emotion datasets spanning five languages. Cross-domain alignment yields low error and strong linear probe performance, indicating a universal emotional subspace. Within this space, internal emotion perception can be steered while preserving semantics using a learned intervention module, with especially strong control for basic emotions across languages. These findings reveal a consistent and manipulable affective geometry in LLMs and offer insight into how they internalize and process emotion.

---

## 论文详细总结（自动生成）

# 论文总结：《情感何处觅：理解与表征大语言模型的情感潜在空间》

## 1. 论文的核心问题与整体含义
- **研究动机**：大语言模型是否以及如何在其内部表征情感？现有研究多关注外显的情感分类任务，对模型隐藏状态中情感信息的几何结构缺乏理解。这种“隐式情感空间”的发现与刻画，对于构建真正具备情感智能的AI至关重要。
- **整体含义**：本文旨在揭示LLM内部存在一个**低维、可解释的情感流形（emotional manifold）**，该空间具有跨任务、跨语言、跨数据集的通用性，并可被外部操控。这为情感计算提供了可解释的几何基础，也为模型内部情感感知的定向干预开辟了新路径。

## 2. 论文提出的方法论
- **核心思想**：通过分析LLM隐藏状态的几何特性，寻找一个普适的情感子空间，而非依赖下游分类头。
- **关键技术细节**：
  - **情感改写数据集**：构造一个合成数据集，其中包含大量将同一句子改写为不同情感版本的正负样本对，用以激发模型深层的情感表征差异。
  - **低维流形辨识**：对隐藏层激活进行**奇异值分解（SVD）**，识别出占主导作用的情感方向向量，从而构建一个低维情感流形。
  - **方向编码与层次分布**：探究情感信息如何以方向形式编码，以及这些编码在Transformer层间的分布规律，验证其跨层一致性。
  - **通用子空间验证**：通过跨数据集、跨语言的线性探测（linear probing）和对齐实验，证明该子空间的可迁移性和通用性。
  - **情感感知操控**：设计一个可学习的介入模块，在保留原始语义的前提下，沿情感方向操控模型的内部表征，实现对基本情绪的强效控制。

## 3. 实验设计
- **数据集与场景**：
  - **合成数据集**：情感改写联合数据集，用于主干实验。
  - **真实世界数据集**：覆盖**5种语言、8个真实情感数据集**，用于泛化和跨语言验证。
- **评测基准（Benchmark）**：
  - 低维流形重构误差；
  - 跨域情感方向对齐误差；
  - 线性探测性能（情感分类准确率）；
  - 干预前后语义保持度与情感感知变化量。
- **对比方法**：文中未明确列举对比基线，但隐含对照包括随机方向、与任务无关子空间、不同层的激活等，标准的情感分析模型形成隐式比较。

## 4. 资源与算力
- **文中提及情况**：根据所提供的元数据和摘要，**未明确说明**所用的GPU型号、数量及训练时长。仅能推断实验中涉及对多个LLM（如多语言模型）进行全层激活提取和SVD分解，对算力有一定需求，但具体计算资源细节缺失。

## 5. 实验数量与充分性
- **实验组数**：
  - 合成数据主实验（情感流形发现、层次分布）；
  - 跨8个真实数据集、5种语言的泛化实验；
  - 消融类分析（跨层稳定性、方向编码贡献）；
  - 情感操控实验（基本情感及跨语言操控）。
- **充分性与客观性**：多数据集、多语言、跨领域的系统验证使结论具有较好的稳健性。实验设计兼顾内部几何分析与外部干预评估，逻辑链条完整。但缺少与现有可解释性方法（如探测任务以外的其他情感归因技术）的直接定量对比，可能使绝对优势论证稍弱。

## 6. 论文的主要结论与发现
- LLM隐藏状态中存在一个**低维、方向编码的情感流形**，且该流形**跨层稳定**。
- 该情感表征具备**强泛化能力**：可对齐至8个现实情感数据集、5种语言，表现出极低的对齐误差和极高的线性探测性能，揭示出一个**通用情感子空间**。
- 基于该子空间，可在**不破坏语义**的前提下，通过学得的干预模块有效操控模型内部的情感感知，尤其对基本情感的控制力显著，且跨语言有效。
- 整体表明LLM已内化了一套**结构化、可操作的情感几何表征**。

## 7. 优点
- **问题新颖**：聚焦LLM内部隐式情感几何，填补了情感可解释性的空白。
- **方法简洁有力**：利用SVD发现低维流形，兼具计算高效性和几何可解释性。
- **实验全面**：跨8个数据集、5种语言的设置，充分验证了通用性。
- **双向验证**：既分析自然的表征结构，又通过操控证明其因果性，论证严密。
- **应用前景明确**：为构建可控制、情感对齐的LLM提供了可操作的几何路径。

## 8. 不足与局限
- **算力与实施细节缺失**：未提供GPU资源、具体模型参数规模及训练时长，复现难度增大。
- **合成数据的生态效度**：情感改写数据集虽可控制变量，但与自然情感情境可能存在分布差异，子空间是否完全反映真实情感模式需进一步验证。
- **情感操控的粒度**：重点验证了基本情绪的操控，对于更微妙、混合或文化依赖的情感，操控效果未知。
- **对比基线有限**：未与基于提示工程或微调的情感控制方法进行直接、系统的比较，难以完全确立该几何干预的优越性。
- **偏差风险**：跨语言数据集可能偏向高资源语言，对小众语言的情感泛化未涉及。

（完）
