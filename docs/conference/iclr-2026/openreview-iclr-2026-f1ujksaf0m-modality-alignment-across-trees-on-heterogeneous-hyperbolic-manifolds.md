---
title: Modality Alignment across Trees on Heterogeneous Hyperbolic Manifolds
title_zh: 异质双曲流形上的树状模态对齐
authors: "Wu Wei, Xiaomeng Fan, Yuwei Wu, Zhi Gao, Pengxiang Li, Yunde Jia, Mehrtash Harandi"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=F1uJKsaf0M"
tags: ["query:affective-ai"]
score: 10.0
evidence: 提出在双曲流形上进行层次化特征对齐，用于视觉-语言表征学习
tldr: 针对现有视觉-语言模型仅用单一图像特征与文本层次特征对齐导致不对称问题，提出跨树对齐方法，通过语义感知视觉特征提取框架从Transformer层中提取由粗到细的视觉特征树，与文本特征树一起嵌入异构双曲空间并对齐。实验表明该方法在下游多模态任务中取得性能提升，为跨模态表征学习提供了新的几何视角。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 视觉-语言模型对齐存在模态不对称，文本有层次特征而图像缺乏。
method: 通过语义感知交叉注意力提取视觉层次特征，在异构双曲流形上对齐模态树。
result: 在多模态任务上性能提升，对齐效果更优。
conclusion: 该工作引入了树状结构和双曲几何，推进了跨模态对齐研究。
---

## Abstract
Modality alignment is critical for vision-language models (VLMs) to effectively integrate information across modalities. However, existing methods extract hierarchical features from text while representing each image with a single feature, leading to asymmetric and suboptimal alignment. To address this, we propose Alignment across Trees, a method that constructs and aligns tree-like hierarchical features for both image and text modalities. Specifically, we introduce a semantic-aware visual feature extraction framework that applies a cross-attention mechanism to visual class tokens from intermediate Transformer layers, guided by textual cues to extract visual features with coarse-to-fine semantics. We then embed the feature trees of the two modalities into hyperbolic manifolds with distinct curvatures to effectively model their hierarchical structures. To align across the heterogeneous hyperbolic manifolds with different curvatures, we formulate a KL distance measure between distributions on heterogeneous manifolds, and learn an intermediate manifold for manifold alignment by minimizing the distance. We prove the existence and uniqueness of the optimal intermediate manifold. Experiments on taxonomic open-set classification tasks across multiple image datasets demonstrate that our method consistently outperforms strong baselines under few-shot and cross-domain settings.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景**  
  视觉-语言模型（VLMs）需要对齐不同模态的信息，以完成跨模态理解与推理。现有方法往往从文本中抽取层次化特征（如从词到句、从粗到细的语义），而对图像仅使用单一的全局特征（如 CLS token）。这种不对等的特征表示导致模态间的对齐不对称、次优。

- **核心问题**  
  如何同时为图像和文本构建**层次化（树状）特征**，并在几何上适当地对齐这些特征，从而使模态对齐更对称、更有效。

- **整体含义**  
  该工作将**树结构**与**双曲几何**相结合，提出在异质双曲流形上对齐两种模态的层次化特征。通过这一新视角，模态对齐能够更好地保留数据的潜在层次关系，提升下游多模态任务性能。

### 2. 论文提出的方法论

- **核心思想**  
  1. 构建**语义感知的视觉特征提取框架**：利用交叉注意力机制，从视觉 Transformer 的中间层提取由粗到细（coarse-to-fine）的视觉特征，形成**视觉特征树**。  
  2. 将文本的层次特征也组织成一棵**文本特征树**。  
  3. 把两棵特征树分别嵌入具有**不同曲率**的双曲流形中，以更好地建模各自的层次结构。  
  4. 通过**跨异质双曲流形的对齐**来拉近两个模态的特征分布：定义一种不同曲率流形上分布之间的 KL 距离度量，并学习一个**中间流形**，通过最小化该距离实现流形对齐，最终使模态特征在中间流形上匹配。

- **关键技术细节**  
  - **视觉特征树**：利用 Transformer 各层的视觉类 token，以文本线索为引导，通过交叉注意力提取多粒度的语义特征。  
  - **双曲嵌入**：文本树和图像树各自嵌入具有独立曲率的双曲空间（弯曲程度不同），以更好地保留层级关系。  
  - **异质流形对齐**：定义一种 KL 散度，衡量两个不同曲率双曲流形上概率分布之间的差异；通过优化寻找最优的中间流形，使两个原始流形映射到该中间流形后分布距离最小。论文还证明了该最优中间流形**存在且唯一**。

- **公式/算法流程说明**  
  （摘要未给出具体公式，但文字表明）方法包括：  
  1. 视觉 Transformer 中间层类 token 提取 + 交叉注意力 → 视觉特征树。  
  2. 文本层次特征 → 文本特征树。  
  3. 分别在各自的双曲流形上嵌入，并参数化曲率。  
  4. 定义一个与分布间 KL 距离相关的目标函数，优化中间流形的参数，从而对齐两个分布。

### 3. 实验设计

- **数据集**  
  多个图像数据集上的**分类（taxonomic open-set classification）任务**。具体数据集名称尚未在摘要中列出，但提到“跨多个图像数据集”。

- **场景与基准**  
  在 **few-shot（小样本）** 和 **cross-domain（跨域）** 设置下评估，这属于开放集分类中具有挑战性的条件。

- **对比方法**  
  比较对象为“strong baselines”（强基线方法），可能包括当前主流的视觉-语言对齐方法（如 CLIP 类方法及层次对齐变体）。具体方法名未在摘要中给出。

### 4. 资源与算力

- 摘要中**未明确提及**所用 GPU 型号、数量、训练时长等计算资源信息。无法根据现有文本进行总结。

### 5. 实验数量与充分性

- 摘要提到：  
  - 实验覆盖**多个图像数据集**。  
  - 在 **few-shot 和 cross-domain** 两种设置下进行测试。  
  - 与 strong baselines 对比，并展示了“consistently outperforms”的结果。  
- **充分性评价**：从摘要看，实验设计包含多数据集、多设置，且消融实验（未具体说明但通常此类工作会有）可能隐含在“method consistently outperforms”的结论中。但由于未给出具体数据集数量、消融项、统计检验等细节，难以完全判断是否足够全面。客观性方面，与 strong baselines 对比且使用标准任务设定，可认为比较公平。

### 6. 论文的主要结论与发现

- 提出的**跨树对齐方法**在异质双曲流形上对齐视觉和文本层次特征，能够有效解决模态不对称问题。
- 在开放集分类任务的 few-shot 和跨域设定下，方法**一致优于**已有的强基线方法。
- 从理论上证明了最优中间流形的存在性与唯一性，为跨模态流形对齐提供了数学保障。

### 7. 优点

- **新颖的双几何视角**：首次将不同曲率双曲流形用于跨模态层次对齐，比单一流形更灵活。  
- **树状特征构建方式**：利用 Transformer 中间层和交叉注意力，使视觉特征也具备细粒度语义层次，弥补了以往方法的缺陷。  
- **理论贡献**：证明了最优中间流形的存在唯一性，提升了方法的理论基础。  
- **实验设置充分**：涵盖了 few-shot 和跨域两个困难场景，展示了方法的泛化能力。

### 8. 不足与局限

- **实验覆盖细节不足**：从摘要看不到具体数据集名称、baseline 方法、消融实验模块，无法评估实验是否能覆盖足够多的领域（如文本到视频、更复杂的推理任务）。  
- **应用场景较窄**：目前仅报告了开放集分类任务，尚未在其他典型 VLM 任务（如图文检索、VQA、字幕生成）上验证通用性。  
- **计算复杂度未知**：双曲空间嵌入与最优中间流形学习可能引入额外计算开销，摘要未讨论效率问题。  
- **偏差风险**：未提供训练细节（如数据增强、超参数），无法判断对特定数据集的过拟合风险或对比公平性。

（完）
