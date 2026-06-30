---
title: Latent Structure of Affective Representations in Large Language Models
title_zh: 大语言模型中情感表征的潜在结构
authors: "Benjamin J. Choi, Melanie Weber"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=pi9m9SZKtd"
tags: ["query:affective-ai"]
score: 9.0
evidence: 研究LLM中情感表征的潜在结构
tldr: 针对大语言模型表征研究缺乏验证依据的局限，本文利用情感处理这一具有坚实心理学理论支撑的领域，探究LLM中情感表征的潜在几何结构。研究发现，LLM内部的情感空间同时展现出类别化和连续维度两种组织特征，与人类情感认知高度一致。这一发现为提升LLM的透明度和安全性提供了重要见解。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 现有LLM表征研究缺乏验证，情感处理提供有结构先验的测试平台。
method: 分析LLM中情感表征的潜在几何结构，检验其与心理学情感模型的对应关系。
result: 发现LLM内部存在与人类情感理论一致的组织模式。
conclusion: 为LLM情感智能的可解释性与安全性奠定基础。
---

## Abstract
The geometric structure of latent representations in large language models (LLMs) is an active area of research, driven in part by its implications for model transparency and AI safety. Existing literature has focused mainly on general geometric and topological properties of the learnt representations, but due to a lack of ground-truth latent geometry, validating the findings of such approaches is challenging. Emotion processing provides an intriguing testbed for probing representational geometry, as emotions exhibit both categorical organization and continuous affective dimensions, which are well-established in the psychology literature. Moreover, understanding such representations carries safety relevance. In this work, we investigate the latent structure of affective representations in LLMs using geometric data analysis tools. We present three main findings. First, we show that LLMs learn coherent latent representations of affective emotions that align both with widely used valence–arousal models from psychology. Moreover, a comparison with latent structure in human brainwave (EEG) data suggests possible similarities. Second, we find that these representations exhibit nonlinear geometric structure that can nonetheless be well-approximated linearly, providing empirical support for the linear representation hypothesis commonly assumed in model transparency methods. Third, we demonstrate that the learned latent representation space can be leveraged to quantify uncertainty in emotion processing tasks. Our results are based on experiments with the GoEmotions corpus, which contains $\sim$58,000 text comments with manually annotated sentiment.

---

## 论文详细总结（自动生成）

# 大语言模型中情感表征的潜在结构

## 1. 论文的核心问题与整体含义
- **研究动机**：大语言模型（LLM）学到的潜在表征的几何结构是当前热点，与模型透明度和AI安全相关。但现有研究多关注一般几何/拓扑性质，缺乏真实世界的潜在几何验证依据（ground truth），使得验证困难。
- **整体含义**：本文利用情感处理这一具有坚实心理学理论支撑的领域作为测试平台。心理学已确认情绪同时具有离散类别组织和连续的效价-唤醒维度结构。探究LLM中的情感表征不仅具有可解释性价值，也直接关联安全性和情感理解。核心目标是揭示LLM中情感表征的潜在几何结构，并检验其与人类情感理论的一致性。

## 2. 论文提出的方法论
- **核心思想**：用几何数据分析工具探测LLM内部情感表征的潜在空间，并将其与心理学中的情感模型（如效价-唤醒模型）进行对比，验证其结构。同时评估该空间的线性近似程度，以检验“线性表征假说”，并利用其进行情感处理的不确定性量化。
- **关键技术细节**（基于摘要推断）：
  - 使用情感标签明确的语料库（GoEmotions）输入LLM，提取对应情感概念的内部表征向量。
  - 通过几何分析（如流形学习、主成分分析、维度约简等）揭示表征空间的全局结构（类别性与连续性维度共存）和局部非线性程度。
  - 与人类脑电图（EEG）数据中的情感表征结构进行对比，寻找跨模态相似性。
  - 利用学习到的潜在空间进行情感任务的不确定性量化（可能基于概率建模或几何距离）。
- **公式或算法流程**：原文未提供具体公式，描述为“geometric data analysis tools”，可理解为多种几何与拓扑数据分析方法组合。

## 3. 实验设计
- **数据集**：GoEmotions 语料库，包含约58,000条文本评论，带人工标注的情绪标签。
- **场景与Benchmark**：情感表征几何结构分析（不是传统分类/回归性能对比），主要与心理学理论（效价-唤醒模型）和人类神经表征（EEG数据）进行一致性对比，而非与其他NLP方法对比。
- **对比方法**：文中提及主要是与心理学理论和EEG表征结构进行比较，可能还包括线性近似与非线性几何表征的对比。

## 4. 资源与算力
- 摘要和元数据中未提及GPU型号、数量、训练时长等具体算力信息。仅指出实验基于GoEmotions ~58k文本评论，推测所需的LLM推理计算量中等，但未量化说明。

## 5. 实验数量与充分性
- **实验数量**：摘要仅概述三大发现，即（1）LLM学到的情感表征与心理学效价-唤醒模型对齐并与EEG相似；（2）这些表征虽有非线性但可被线性很好地近似，支持线性表征假说；（3）潜在空间可用于情感不确定性量化。推测在每一个发现下可能包含多组子实验（不同模型、不同维度分析等），但摘要未详述。
- **充分性与公平性**：实验设计具有客观依据（心理学模型），比较对象明确（理论模型与EEG数据）；但由于仅有摘要，无法判断模型数量、种子数、统计检验等，难以全面评估充分性和公平性。若缺乏多个LLM的交叉验证或更系统的消融实验，可能受限。

## 6. 论文的主要结论与发现
- LLM学习到了连贯的情感潜在表征，这些表征与心理学的效价-唤醒模型高度一致。
- LLM情感表征的几何结构虽本质上是非线性的，但可以被线性工具较好地近似，这为模型透明度方法中常用的线性表征假说提供了实证支持。
- 学到的潜在表征空间可用于量化情感处理任务中的不确定性。
- 与人类EEG数据的对比提示可能存在跨物种/跨模态的结构相似性。

## 7. 优点
- **选题新颖**：将心理学中成熟的情感结构理论（离散-连续双重组织）作为验证依据，弥补了当前表征几何研究缺乏ground truth的空白。
- **多维验证**：不仅与心理学模型对比，还与神经成像（EEG）数据对比，增加了发现的可信度。
- **实用导向**：将几何结构分析用于不确定性量化，为安全关键应用提供了工具性贡献。

## 8. 不足与局限
- **摘要信息有限**：无法获知具体分析工具、消融实验、LLM类型和规模、统计显著性和效应量等关键细节。
- **外部效度**：仅使用GoEmotions数据集，其情绪标签和领域可能局限；是否在其他文化背景或语言中成立未知。
- **关联 vs. 因果关系**：虽然发现了与人类理论结构的一致性，但不能直接证明LLM“理解”情感的方式与人类相同，可能只是表面统计对齐。
- **线性近似局限**：尽管线性近似良好，但非线性结构的存在可能在某些精细任务或分布外数据上造成偏差，实际应用需谨慎。

（完）
