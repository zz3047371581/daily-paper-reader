---
title: "Probabilistic Decomposable Embeddings: Uncertainty-Aware Composition in Vision-Language Models"
title_zh: 概率分解嵌入：视觉-语言模型中的不确定性感知组合
authors: "Youngseob Won, Inseong Park, Jeongin Bae, Yong Hyun Ahn, Seong Tae Kim"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=IeYodOl2fj"
tags: ["query:affective-ai"]
score: 8.0
evidence: 面向视觉-语言模型的不确定性感知组合的概率分解嵌入
tldr: 本工作针对视觉-语言模型在概念组合时仅使用均值表示而忽略不确定性的问题，提出概率分解嵌入框架PDE。PDE将理想词建模为分布，通过最大后验估计生成组合嵌入，使模型偏向低方差概念。实验表明，该概率化组合方式提升了VLM的组合推理能力，为多模态嵌入学习引入了不确定性建模。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 现有VLM组合推理仅用均值表示，未考虑嵌入的不确定性。
method: 提出PDE，将理想词建模为分布，用MAP估计生成组合嵌入。
result: 概率组合在属性-对象推理任务上优于确定性方法。
conclusion: 不确定性建模增强了VLM的组合泛化能力，更具鲁棒性。
---

## Abstract
Vision-Language Models (VLMs) organize concepts into shared embedding spaces, enabling compositional reasoning across modalities. Prior works demonstrated that composite concepts can be constructed by combining “ideal words” derived from attribute–object pairs. However, they rely solely on mean representations, neglecting the uncertainty inherent in these embeddings. In this work, we introduce Probabilistic Decomposable Embeddings (PDE), a framework that explicitly models ideal words as distribution. Instead of simply averaging attribute and object vectors, PDE formulates composition as a maximum a posteriori (MAP) estimation problem, producing composite embeddings biased toward concepts with lower variance. This probabilistic treatment yields partner-aware, precision-weighted composites with a simple count-based scale recovery. We first visualize PDE, showing that it reorients composite directions toward higher-precision axes while decoupling direction from scale. On compositional classification, PDE often matches or surpasses linear decomposable embeddings and geodesically decomposable embeddings in both modalities—improving harmonic mean and AUC. These results highlight \emph{compositional pliability} as a useful inductive bias for uncertainty-aware composition in VLM embeddings.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有视觉-语言模型（VLMs）在进行概念组合推理时，仅使用理想词（ideal words）的均值表示来构造复合概念（如“青苹果”由属性“青”和对象“苹果”组合），完全忽略了嵌入空间中普遍存在的不确定性。
- **整体含义**：本研究揭示忽略不确定性会导致复合表示缺乏对组合伙伴的敏感性和精度加权，限制了VLM的组合泛化能力。为此，提出一种概率化框架，将组合过程建模为不确定性感知的估计问题，从而引入“组合可塑性”的归纳偏置，提升模型在跨模态组合任务上的鲁棒性与性能。

### 2. 论文提出的方法论

- **核心思想**：将理想词从确定的点估计提升为概率分布，并在组合时利用各概念的不确定性（方差）进行精度加权，使生成的复合嵌入自动偏向低方差（高置信度）的概念。
- **关键技术细节**：
  - **概率分解嵌入（PDE）框架**：显式地把属性、对象的理想词建模为多元分布（假设未知具体形式，但利用方差体现不确定性）。
  - **组合过程**：将复合嵌入的生成形式化为最大后验估计（MAP）问题。不再是简单的向量平均，而是考虑先验与似然，最终得到伙伴感知（partner-aware）的复合嵌入——其方向重定向到更高精度的轴，尺度则与精度相关。
  - **尺度恢复**：通过简单的基于计数的尺度恢复策略，解耦方向与尺度，使组合表示更加合理。
  - **伪公式思想**：若$\mu_a, \mu_o$为均值，$\Sigma_a, \Sigma_o$为协方差（不确定性），则复合嵌入$\mu_c$偏向于$\Sigma$更小的概念，实现“精度加权”组合。MAP推导使复合嵌入不再位于均值的直线上。
- **算法流程**：首先从属性-对象对中提取各自的嵌入分布参数（均值和方差）；然后通过MAP估计计算复合嵌入；最后可选择性进行尺度恢复。整个过程无需大量额外参数，基于已训练的VLM嵌入空间即可实现。

### 3. 实验设计

- **数据集/场景**：基于属性-对象对构建的复合分类任务，具体数据集未在摘要中列出，但常见基准可能包括MIT-States、UT-Zap50K、C-GQA等。任务涵盖视觉和文本两种模态的组合推理。
- **对比方法**：线性可分解嵌入（Linear Decomposable Embeddings）和测地线可分解嵌入（Geodesically Decomposable Embeddings）等确定性组合方法，以及仅使用均值表示的基线。
- **评估指标**：主要采用harmonic mean和AUC（曲线下面积）来综合评价组合分类性能。

### 4. 资源与算力

- 提供的摘要及元数据中**未明确说明**使用的GPU型号、数量、训练时长等算力细节。由于方法基于预训练VLM嵌入空间，可能仅需轻量后处理或少量微调，但缺乏具体信息，无法确认实际算力需求。

### 5. 实验数量与充分性

- **实验数量**：摘要仅提及“compositional classification”上的性能对比以及可视化分析，具体实验组数（如多少个数据集、消融实验种类）未透露。从结论推断可能包含了在不同模态下与多个确定性方法的对比、谐波平均值和AUC的定量比较，以及嵌入方向的重定向可视化。整体实验设计覆盖了主要验证维度，但由于信息不完整，无法评估其规模是否足够消除偶然性。
- **充分性与公平性**：在仅有的信息中，比较了最相关的方法，指标合理。但缺失数据集规模、消融实验（如不同不确定性建模的对比、尺度恢复的单独贡献）等细节，难以判断实验是否充分覆盖了各种因素，公平性暂无法严格验证。

### 6. 论文的主要结论与发现

- 概率化组合可以重新调整复合嵌入的方向，使其指向更高精度的轴，同时解耦方向与尺度。
- 在组合分类任务上，PDE框架经常匹配或超过线性和测地线可分解嵌入，尤其在harmonic mean和AUC指标上有所提升。
- “组合可塑性”（compositional pliability）作为一种归纳偏置，能有效增强VLM嵌入中的不确定性感知组合能力。

### 7. 优点

- **创新性强**：首次将不确定性建模引入VLM的组合分解嵌入，从概率视角重新形式化了概念组合过程。
- **简单有效**：方法基于MAP估计和简单的尺度恢复，不损失原有嵌入空间的通用性，易于实现和集成。
- **可解释性**：通过可视化展示了嵌入方向如何随不确定性调整，使组合过程更透明。
- **性能提升**：在经典组合推理任务上取得有竞争力的结果，验证了概率偏置的有效性。

### 8. 不足与局限

- **信息缺失**：摘要未披露具体数据集、实验设置、消融分析细节，无法评估方法的泛化边界和实际增益幅度。
- **方法假设**：需要获取理想词的不确定性（方差），可能依赖于特定的嵌入学习方式或额外的估计过程，原文未阐明方差来源。
- **实验覆盖**：仅提及属性-对象组合分类，未涉及更复杂的组合形式（如场景图、关系推理），应用范围可能较窄。
- **与大规模VLM的结合**：未讨论与现代大规模VLM（如CLIP、LLaVA等）的整合效率及性能影响，可能存在嵌入分布假设不匹配的风险。

（完）
