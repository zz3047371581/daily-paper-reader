---
title: "ConceptAttention: Diffusion Transformers Learn Highly Interpretable Features"
title_zh: ConceptAttention：扩散变换器学习高度可解释的特征
authors: "Alec Helbling, Tuna Han Salih Meral, Benjamin Hoover, Pinar Yanardag, Duen Horng Chau"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Rc7y9HFC34"
tags: ["query:affective-ai"]
score: 5.0
evidence: 分析扩散变换器（DiT）的可解释性，有助于视觉Transformer的理解
tldr: 多模态扩散变换器（DiTs）的丰富表征是否具有独特可解释性？本文提出ConceptAttention，利用DiT注意力层的输出空间进行线性投影，生成高度上下文化的概念嵌入和清晰的显著性图。该方法无需额外训练即能在图像中准确定位文本概念，甚至超过专用定位模型。该发现揭示了DiT内在的可解释特征，为视觉Transformer的表示研究提供了新工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 1139, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1681, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1752, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 815, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1698, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 817, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 815, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1706, \"height\": 766, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1775, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1751, \"height\": 853, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1495, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1505, \"height\": 925, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1786, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1782, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1680, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1622, \"height\": 2016, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rc7y9hfc34/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1622, \"height\": 2018, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-rc7y9hfc34/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1699, \"height\": 822, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rc7y9hfc34/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 627, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rc7y9hfc34/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 739, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rc7y9hfc34/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 658, \"height\": 244, \"label\": \"Table\"}]"
motivation: 探究多模态扩散变换器（DiTs）的表征是否具备独特可解释性，现有方法未能充分利用其注意力层。
method: 提出ConceptAttention，重新利用DiT注意力层的参数，在输出空间进行线性投影以产生概念嵌入。
result: 在文本到图像定位任务上取得最先进效果，生成的显著性图比常用的交叉注意力图更清晰。
conclusion: DiT具有高度的内在可解释性，ConceptAttention方法为理解视觉生成模型提供了新途径。
---

## Abstract
Do the rich representations of multi-modal diffusion transformers (DiTs) exhibit unique properties that enhance their interpretability? We introduce ConceptAttention, a novel method that leverages the expressive power of DiT attention layers to generate high-quality saliency maps that precisely locate textual concepts within images. Without requiring additional training, ConceptAttention repurposes the parameters of DiT attention layers to produce highly contextualized *concept embeddings*, contributing the major discovery that performing linear projections in the output space of DiT attention layers yields significantly sharper saliency maps compared to commonly used cross-attention maps. ConceptAttention even achieves state-of-the-art performance on zero-shot image segmentation benchmarks, outperforming 15 other zero-shot interpretability methods on the ImageNet-Segmentation dataset. ConceptAttention works for popular image models and even seamlessly generalizes to video generation. Our work contributes the first evidence that the representations of multi-modal DiTs are highly transferable to vision tasks like segmentation.

---

## 论文详细总结（自动生成）

### 核心问题与整体含义
多模态扩散变换器（DiTs）已成为文生图领域的最先进架构，但其内部表征的可解释性仍是一个黑箱。现有解释方法主要针对 UNet 架构，无法充分利用 DiT 注意力层的独特结构。本文的核心动机是探究：**DiT 的丰富表征是否具有增强可解释性的独特属性，以及如何在不额外训练的情况下将这些表征转化为定位文本概念的工具。**  
研究的整体含义在于：通过揭示 DiT 注意力输出空间的高度可迁移性，为生成式模型的透明化、可控性以及下游视觉任务（如分割）提供了新的视角和工具。

### 方法论
**核心思想**：  
ConceptAttention 通过对 DiT 的多模态注意力层（MMATTN）进行即插即用的改造，引入一组“概念嵌入”，使模型能够在保持图像生成质量的前提下，为任意文本概念生成高保真显著性图。关键发现是：**在注意力输出空间进行线性投影，得到的显著性图远比常用的交叉注意力图更清晰。**

**关键技术细节**：
- **概念嵌入初始化与流动**：用户指定一系列单令牌概念（如“猫”、“天空”），经 T5 编码得到初始嵌入 `c0`。在每个 MMATTN 层中，概念嵌入利用文本提示的投影矩阵 `Kp, Qp, Vp` 生成键、值、查询，并通过自适应归一化和调制进行更新。
- **单方向注意力操作**：为保证概念不影响图像生成，只允许概念查询图像和自身（即交叉注意力+自注意力），公式为：  
  `oc = softmax(qc k^T_xc) v_xc`  
  其中 `k_xc` 和 `v_xc` 是图像与概念键、值的拼接。图像和文本令牌则照常进行多模态自注意力，完全忽略概念令牌。
- **概念残差流**：概念输出经过线性投影和 MLP（复用文本流的参数），并通过调制出的缩放、偏移和门控值进行残差更新（公式 9-10）。
- **显著性图生成**：在注意力输出空间，计算图像输出向量 `ox` 与概念输出向量 `oc` 的点积相似度，并应用 Softmax 归一化：  
  `ϕ(ox, oc) = softmax(ox o^T_c)`  
  最终，将多个层的概念图进行平均，得到空间定位结果。

### 实验设计
- **数据集与基准**：  
  - ImageNet-Segmentation（4276 张图像，445 个类别，对象中心化）  
  - PascalVOC 2012 单类子集（930 张，仅含一类物体）和多类子集（1449 张）  
  - 评估指标：像素准确率（Acc）、平均交并比（mIoU）、平均精度均值（mAP）
- **对比方法（15 种以上）**：  
  - 基于 CLIP：LRP、Partial-LRP、Rollout、ViT Attention、GradCAM、TextSpan、CLIPasRNN、TransInterp  
  - 基于 UNet 扩散模型：DAAM（SDXL、SD2）、OVAM（SDXL）  
  - 基于自监督视觉模型：DINOv1、DINOv2、DINOv2 with registers、iBOT 的自注意力图  
  - 基于 DiT：Flux 原始交叉注意力、SD3.5 原始交叉注意力  
- **场景扩展**：定性验证了在视频生成模型 CogVideoX 上的通用性。

### 资源与算力
论文未明确报告所使用 GPU 的型号、数量以及推理耗时。由于 ConceptAttention 是一种免训练的推理时方法，它无需额外的训练计算资源，仅需在现有模型的前向传播中插入额外计算。但文中未对额外的内存占用或延迟进行量化分析。

### 实验数量与充分性
实验设计十分系统和全面，主要包括：
- **2 个主数据集上共 3 种评估设置**（单类、多类、视频），与 15+ 个基准方法全面比较。
- **6 组消融实验**：  
  1）不同表征空间（交叉注意力 vs 值空间 vs 输出空间，以及 Softmax 影响）  
  2）注意力操作类型（纯交叉、纯自、二者结合、无注意力）  
  3）MMA T T N 层深度对分割性能的影响  
  4）扩散时间步（噪声水平）对分割性能的影响  
  5）用 SD3.5 复现主要结果（架构可迁移性）  
  6）多概念同时定位的定性展示
实验设置公平，在相同零样本条件下使用标准数据集和指标，消融研究有力地支撑了核心主张。

### 主要结论与发现
- **DiT 注意力输出空间优于交叉注意力**：在输出向量上进行线性投影得到的显著性图，在零样本分割任务上大幅超越传统的交叉注意力图和其他可解释性方法。
- **ConceptAttention 达到零样本分割的最优水平**：在 ImageNet-Segmentation 上，Flux 版本的 mIoU 达 71.04，Acc 达 83.07，均显著超越所有对比方法（包括 DINO、CLIP 等强基线）。
- **概念交互至关重要**：同时进行从图像到概念的交叉注意力和概念间的自注意力，比单一操作效果更好，使概念嵌入能相互推离，减少冗余。
- **高层表征更具可迁移性**：更深的 MMATTN 层对分割更有效，且融合多层信息能进一步提升性能。最优的噪声水平并非零噪声，而是扩散过程的中后段。

### 优点
- **无需额外训练**：完全复用 DiT 已有参数，即插即用，实施成本低。
- **高可解释性**：能精准定位任意开放词汇的文本概念，显著性图质量高，甚至在某些情况下优于人工标注的边界。
- **多架构、跨模态通用性**：在 Flux、SD3.5 两个主流 DiT 架构上复现结果，并可无缝扩展至视频生成。
- **实验严谨扎实**：对比基线广泛，消融研究深入，定量与定性分析结合，结论具有说服力。
- **重要发现**：首次揭示 DiT 注意力输出空间的高度可解释性与可迁移性，为后续研究提供了新方向。

### 不足与局限
- **相近语义混淆**：难以区分高度重叠的概念（如“天空”与“太阳”），边界易模糊。
- **无概念时的回退行为**：当图像中不存在任何待查概念时，模型会错误地选择最相似概念进行高亮。
- **评估任务单一**：仅在零样本语义分割上进行了定量验证，未探索其他下游任务（如分类、目标检测）的迁移效果。
- **计算开销未量化**：虽声称影响微小，但未报告推理延迟或显存占用的具体增长。
- **未覆盖更多 DiT 变体**：实验主要集中在 Flux 和 SD3.5，对其他种类的多模态 DiT 模型（如 PixArt-α 等）的验证缺失。
- **统计稳健性不足**：未提供多次运行的均值与标准差，无法排除随机性波动。

（完）
