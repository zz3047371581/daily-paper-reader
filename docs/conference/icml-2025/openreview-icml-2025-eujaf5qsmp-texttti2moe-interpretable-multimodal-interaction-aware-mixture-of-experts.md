---
title: "$\\texttt{I$^2$MoE}$: Interpretable Multimodal Interaction-aware Mixture-of-Experts"
title_zh: I2MoE：可解释的多模态交互感知混合专家
authors: "Jiayi Xin, Sukwon Yun, Jie Peng, Inyoung Choi, Jenna L. Ballard, Tianlong Chen, Qi Long"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=EuJaF5QsMP"
tags: ["query:affective-ai"]
score: 9.0
evidence: 提出可解释的多模态交互感知混合专家框架，显式建模多样化模态交互
tldr: 针对现有多模态融合方法忽视模态间异构交互且缺乏可解释性的问题，提出可解释多模态交互感知混合专家框架I2MoE，通过显式建模多种多模态交互来增强融合，并为数据中的多模态交互提供可解释的洞察，为多模态情感分析等任务中的跨模态对齐提供了新方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eujaf5qsmp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eujaf5qsmp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1750, \"height\": 836, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eujaf5qsmp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 804, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eujaf5qsmp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1725, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eujaf5qsmp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1688, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eujaf5qsmp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1563, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eujaf5qsmp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1582, \"height\": 783, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eujaf5qsmp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1551, \"height\": 766, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 839, \"height\": 917, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 833, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1783, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1612, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1416, \"height\": 627, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1414, \"height\": 624, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1413, \"height\": 515, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1414, \"height\": 625, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eujaf5qsmp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 800, \"height\": 317, \"label\": \"Table\"}]"
motivation: 现有融合方法仅关注模态对应，忽略异构交互，且缺乏可解释性。
method: 提出端到端MoE框架，显式建模多种多模态交互，并输出可解释的交互见解。
result: 增强了模态融合效果，并提供了多模态交互的可解释性分析。
conclusion: 该方法为可解释的多模态融合开辟了新路径，有助于理解跨模态信息整合。
---

## Abstract
Modality fusion is a cornerstone of multimodal learning, enabling information integration from diverse data sources. However, existing approaches are limited by $\textbf{(a)}$ their focus on modality correspondences, which neglects heterogeneous interactions between modalities, and $\textbf{(b)}$ the fact that they output a single multimodal prediction without offering interpretable insights into the multimodal interactions present in the data. In this work, we propose $\texttt{I$^2$MoE}$ ($\underline{I}$nterpretable Multimodal $\underline{I}$nteraction-aware $\underline{M}$ixture-$\underline{o}$f-$\underline{E}$xperts), an end-to-end MoE framework designed to enhance modality fusion by explicitly modeling diverse multimodal interactions, as well as providing interpretation on a local and global level. First, $\texttt{I$^2$MoE}$ utilizes different interaction experts with weakly supervised interaction losses to learn multimodal interactions in a data-driven way. Second, $\texttt{I$^2$MoE}$ deploys a reweighting model that assigns importance scores for the output of each interaction expert, which offers sample-level and dataset-level interpretation. Extensive evaluation of medical and general multimodal datasets shows that $\texttt{I$^2$MoE}$ is flexible enough to be combined with different fusion techniques, consistently improves task performance, and provides interpretation across various real-world scenarios. Code is available at https://github.com/Raina-Xin/I2MoE.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
多模态学习的核心挑战之一是模态融合，即整合来自图像、文本、音频等多种数据源的信息以提升预测性能。然而，现有的大多数融合方法存在以下两个主要局限：
- **忽视模态间的异构交互**：传统方法（如早期融合、晚期融合）通常使用同一组参数处理所有模态间的信息，未能区分并显式建模不同模态间存在的互补、冗余、协同和独特信息。
- **缺乏可解释性**：这些方法往往输出一个单一的多模态预测结果，难以揭示数据中固有的多模态交互模式，导致模型的决策过程如同一只“黑箱”。

针对上述问题，本文提出了**I²MoE**框架，旨在通过显式建模多样化的模态交互来增强融合效果，并为数据中的多模态交互提供可解释的洞察.

### 2. 论文提出的方法论
I²MoE 的核心是一个端到端的**混合专家**架构，其设计要点如下：

- **核心思想**：利用多个交互专家来分别捕获不同类型的模态交互。
- **关键技术细节**：
  - **交互专家**：对于两个模态的场景，框架包含四个交互专家，分别建模**独特信息 1**、**独特信息 2**、**协同信息**和**冗余信息**。扩展到多于两个模态时，专家数量变为“模态数+2”（每个模态一个独特专家，加一个协同专家和一个冗余专家）。
  - **弱监督交互损失**：为使专家实现专业化，训练时使用一种弱监督策略。通过将部分模态替换为随机向量来模拟模态缺失的预测（例如，用随机向量替换某个模态后，其独特的交互信息应消失），并基于扰动输出与完整输出的相似性/差异性设计损失函数（如 Triplet Margin Loss 或 Cosine Similarity），引导专家专注于特定类型的交互。
  - **重加权模型**：引入一个多层感知机模型，为每个交互专家的预测结果动态分配重要性权重，最终预测是所有专家预测的加权和。
  - **可解释性**：重加权模型分配的权重和专家的预测日志，分别在**样本级**和**数据集级**提供了关于不同交互类型如何贡献于最终决策的解释。

### 3. 实验设计
- **数据集与场景**：论文在五个真实世界的多模态数据集上进行了评估，覆盖医疗和通用领域。
  - **ADNI**：阿尔茨海默病分类 (4个模态)
  - **MIMIC-IV**：重症监护患者一年死亡率预测 (3个模态)
  - **IMDB**：电影类型多标签分类 (2个模态)
  - **MOSI**：情感分析 (3个模态)
  - **ENRICO**：UI设计分类 (2个模态)
- **基准对比方法**：将 I²MoE 与多种融合方法进行了比较，包括：
  - 基础方法：**早期融合**、**晚期融合**、**低秩多模态融合**、**多模态Transformer**。
  - 先进方法：**条件计算**、**Switch Transformer**、**稀疏混合专家**。
- **评估指标**：根据任务类型，使用了准确率、AUROC、Micro F1、Macro F1 等指标。

### 4. 资源与算力
- **硬件配置**：所有实验均在**单个 NVIDIA A100 GPU** 上运行。
- **计算开销**：论文对比了 I²MoE 与基线模型的计算开销。以多模态 Transformer 为基线，I²MoE 在训练时间、推理延迟和参数量上均有成比例的增加，这是为实现交互建模和可解释性所付出的代价。

### 5. 实验数量与充分性
实验设计较为全面和充分，主要包含以下几类：
1.  **主实验**：在5个数据集上，将提出的方法（I²MoE 结合多模态 Transformer）与7种现有融合方法进行性能对比。
2.  **泛化性实验**：将 I²MoE 与另外3种不同的融合架构（MoE++， SwitchGate， InterpretCC）结合，验证其在不同骨干网络上的泛化能力。
3.  **深度分析实验**：
    - 分析了单个交互专家的准确率与整体模型效果的对比。
    - 量化了交互专家之间的分歧程度与模型准确率的关系。
4.  **消融实验**：通过移除或修改关键组件（消除交互损失、改变损失应用位置、替换重加权模型、减少扰动、移除特定专家），验证各个设计组件的有效性。
5.  **可解释性评估**：
    - 提供了样本级的定性案例分析。
    - 提供了数据集级别的全局权重分布分析。
    - 进行了**人工评估**（15位参与者，300次评价），验证局部解释的合理性。

这些实验不仅覆盖了不同领域和规模的数据集，还通过横向（不同方法）、纵向（消融各类组件）和深度分析（分歧、可解释性）确保了评估的客观与公平。

### 6. 论文的主要结论与发现
- **性能优越性**：I²MoE 能显著提升多模态任务的性能。例如，在 ADNI 数据集上，相比原版多模态 Transformer 准确率提升 **5.5%**。
- **方法灵活性**：I²MoE 是“骨干无关”的，可以无缝集成到多种不同的模态融合架构中，并普遍带来性能增益。
- **可解释性强**：该框架能有效地在样本级（通过专家预测和权重）和数据集级（通过权重分布）提供关于模态交互模式的清晰解释，且其解释的合理性获得了人工评估的支持。
- **专家多样性的价值**：显式建模异构交互和专家间的多样性对模型性能至关重要，移除交互损失或特定类型专家会导致性能大幅下降。

### 7. 优点
- **创新性的交互建模**：首次将信息分解理论与端到端的混合专家框架相结合，通过弱监督损失显式建模不同类型的模态交互，填补了领域空白。
- **双重可解释性机制**：重加权模型与交互专家输出的结合，提供了一种新颖、量化且可验证的多模态解释方案，并通过了人工评估。
- **高度灵活的即插即用**：方法设计为融合骨干无关，能与现有及未来先进的融合架构兼容，具有很高的实用价值。

### 8. 不足与局限
- **计算开销增加**：由于需要维护多个交互专家并进行多次前向传播，模型在训练/推理时间和参数量上相比简单融合方法有明显增加。
- **随机掩码策略依赖**：依靠随机向量来屏蔽模态信息的弱监督方式，可能在一些场景下引入噪声或不够精确，其有效性高度依赖于此策略。
- **宏观交互类型的局限**：目前仅将模态交互分解为“唯一、冗余、协同”三种宏观类型。可能错过更细粒度或更复杂的交互模式。
- **数据集偏差风险**：实验所用数据集多为特定领域（医疗、电影），其在其他类型多模态数据（如具身智能、遥感）上的表现有待进一步验证。

（完）
