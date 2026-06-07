---
title: "MANGO: Multimodal Attention-based Normalizing Flow Approach to Fusion Learning"
title_zh: MANGO：基于多模态注意力归一化流的融合学习方法
authors: "Thanh-Dat Truong, Christophe Bobda, Nitin Agarwal, Khoa Luu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cd2MWwIIHu"
tags: ["query:affective-ai"]
score: 7.0
evidence: 提出可逆交叉注意力实现可解释多模态融合
tldr: 针对现有多模态融合方法难以捕获各模态本质特征的问题，提出基于归一化流和可逆交叉注意力层的显式可解释融合模型MANGO。方法可高效建模复杂结构，实验表明其在多模态任务上的有效性。该工作为多模态融合提供了可溯源的框架。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cd2mwwiihu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 727, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cd2mwwiihu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1174, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cd2mwwiihu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 733, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cd2mwwiihu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 737, \"height\": 148, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cd2mwwiihu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 592, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cd2mwwiihu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 592, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cd2mwwiihu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 323, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cd2mwwiihu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 729, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cd2mwwiihu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 727, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cd2mwwiihu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 586, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cd2mwwiihu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 728, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cd2mwwiihu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 729, \"height\": 150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cd2mwwiihu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 726, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cd2mwwiihu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 735, \"height\": 125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cd2mwwiihu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 724, \"height\": 206, \"label\": \"Table\"}]"
motivation: 当前多模态注意力融合难以显式捕获各模态本质特征。
method: 提出可逆交叉注意力层构建归一化流融合模型。
result: 实现可解释且易于追踪的多模态融合。
conclusion: MANGO为多模态学习提供了新的显式融合范式。
---

## Abstract
Multimodal learning has gained much success in recent years. However, current multimodal fusion methods adopt the attention mechanism of Transformers to implicitly learn the underlying correlation of multimodal features. As a result, the multimodal model cannot capture the essential features of each modality, making it difficult to comprehend complex structures and correlations of multimodal inputs. This paper introduces a novel Multimodal Attention-based Normalizing Flow (MANGO) approach to developing explicit, interpretable, and tractable multimodal fusion learning. In particular, we propose a new Invertible Cross-Attention (ICA) layer to develop the Normalizing Flow-based Model for multimodal data. To efficiently capture the complex, underlying correlations in multimodal data in our proposed invertible cross-attention layer, we propose three new cross-attention mechanisms: Modality-to-Modality Cross-Attention (MMCA), Inter-Modality Cross-Attention (IMCA), and Learnable Inter-Modality Cross-Attention (LICA). Finally, we introduce a new Multimodal Attention-based Normalizing Flow to enable the scalability of our proposed method to high-dimensional multimodal data. Our experimental results on three different multimodal learning tasks, i.e., semantic segmentation,  image-to-image translation, and movie genre classification, have illustrated the state-of-the-art (SoTA) performance of the proposed approach.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究背景**：多模态学习近年来非常成功，主流融合方法（如基于 Transformer 的注意力机制）通过隐式建模捕获跨模态相关性，但存在明显不足。
- **核心问题**：隐式建模难以明确捕捉各模态的本质特征，无法充分理解多模态输入的复杂结构和互补关系，导致某一模态信息可能被淹没，且缺乏可解释性。
- **整体含义**：论文旨在提出一种**显式、可解释、可追踪**的多模态融合方法，利用**归一化流（Normalizing Flows）**对联合分布进行精确建模，克服现有多模态融合的黑箱问题，并解决流模型在表达力与高维扩展性上的固有局限。

## 2. 论文提出的方法论

- **总体框架**：将多模态数据视为联合分布，使用双射网络 \( G \) 映射到潜在空间，再通过任务头输出预测。即 \( Z = G(X) \)，\( p(X) = \pi(Z) \left| \frac{\partial G(X)}{\partial X} \right| \)，其中 \( \pi(Z) \) 为标准正态先验。
- **核心模块——可逆交叉注意力层（ICA）**：
  - 将输入 token 分为两部分 \( X_1, X_2 \)，利用 \( X_1 \) 生成 Query 和 Key，\( X_2 \) 作为 Value，计算注意力输出 \( Y_2 \)。
  - 通过引入**自回归掩码（上三角矩阵）**确保可逆性：\( Y_2 = \text{softmax} (QK^T/\sqrt{d} \odot M) V \)，其逆过程可解析计算。
  - 雅可比行列式简化为 \( \det(A)^{N/2} \)，满足归一化流可追踪性要求。
- **三种跨模态分区注意力机制**：
  - **模态到模态交叉注意力（MMCA）**：将第一模态所有 token 作为 \( X_1 \)，第二模态所有 token 作为 \( X_2 \)，实现模态间的单向或双向信息注入。
  - **跨模态交叉注意力（IMCA）**：将每模态 token 均分并混合组成 \( X_1 \) 与 \( X_2 \)，使注意力在多模态 token 间更细粒度流动。
  - **可学习跨模态交叉注意力（LICA）**：引入可学习的置换矩阵 \( W_{per} \)（通过 LU 分解保证置换性质），自动优化 token 分组，进一步提升跨模态交互的灵活性。
- **多模态潜在归一化流**：
  - 使用感知压缩编码器 \( E \)（如自编码器）将高维输入投影到低维特征空间 \( F = E(X) \)。
  - 在低维特征上构建归一化流模型 \( p(F) = \pi(Z) \left| \frac{\partial G(F)}{\partial F} \right| \)，避免在高维像素空间直接建模，降低计算开销并提升扩展性。
- **网络结构**：\( G \) 包含 \( L=12 \) 个块，每块由 8 个 ICA 层（依次为 2 个 MMCA、4 个 IMCA、2 个 LICA）和 1 个传统耦合层组成。
- **训练目标**：同时优化负对数似然与下游任务损失：  
  \[
  \theta^* = \arg\min_{\theta} \mathbb{E}_{X,Y} \left[ - \left( \log \pi(Z) + \log \left| \frac{\partial G(F)}{\partial F} \right| \right) + \mathcal{L}_{\text{task}}(\hat{Y}, Y) \right]
  \]

## 3. 实验设计

- **语义分割**：
  - 数据集：NYUDv2（795 train / 654 test）和 SUN RGB-D（5285 train / 5050 test）。
  - 输入：RGB 和深度图。
  - 对比方法：FCN-32s、RefineNet、FuseNet、RDFNet、CEN、TokenFusion、GeminiFusion 等 CNN 与 Transformer 融合方案。
  - 评价指标：像素精度、平均精度、mIoU。
- **图像到图像翻译**：
  - 数据集：Taskonomy 子集（1000 train / 500 val）。
  - 输入/输出对：如 Shader + Texture → RGB、Depth + Normal → RGB、RGB + Shader → Normal 等五组任务。
  - 对比：CEN、TokenFusion、GeminiFusion 等；评价指标包含 FID/KID（↓）和 MAE/MSE（↓）。
- **电影类型分类**：
  - 数据集：MM-IMDB（15552 train / 2608 val）。
  - 输入：电影海报图像和情节文本。
  - 对比：Late Fusion、LRTF、DynMM、COCA、BridgeTow 等。
  - 指标：Micro F1 和 Macro F1。

## 4. 资源与算力

- 硬件：4 块 NVIDIA A100 GPU。
- 输入尺寸：256×256（分割和翻译任务）。
- 训练超参数：遵循 TokenFusion 的设定以保证公平对比。
- 文中未明确给出总训练时长。

## 5. 实验数量与充分性

- **三大任务 + 多种设定**：3 个任务涵盖同质（RGB-D）和异质（图像-文本）多模态，多个输入-输出组合。
- **消融实验**：
  - ICA 层 vs 耦合层、Glow、Flow++、AttnFlow（表 4）。
  - 不同分区方法组合（MMCA、IMCA、LICA）（表 5）。
  - 是否使用潜在模型（表 6）。
  - 不同块数（6、8、12、16）（表 6、表 7）。
  - 计算开销对比（参数、GFLOPs、推理时间）（表 8）。
- **评价**：实验设计较为丰富，覆盖主流基线，消融分析较为完整，具有客观性与公平性。

## 6. 论文的主要结论与发现

- MANGO 在三个多模态任务上均取得 SOTA 或可比性能，尤其在 NYUDv2 分割上 mIoU 达 59.2%，超越 GeminiFusion。
- 提出的 ICA 层及其三种分区策略能有效捕获跨模态的长程依赖和复杂结构。
- 潜在建模可在保持高性能的同时降低计算负担，提升对高维数据的扩展性。
- 整体框架提供了显式、可解释的融合方式，归一化流的严格可逆性和易处理性得以保留。

## 7. 优点

- **首次将归一化流系统应用于多模态融合**，为显式概率建模开辟新方向。
- **ICA 层设计精巧**，利用自回归性质保证可逆和行列式易算，同时具备 Transformer 的全局建模能力。
- **三种分区注意力机制**从粗到细、从固定到可学习，逐步增强跨模态交互。
- **潜在空间建模策略**有效分离感知压缩与语义学习，缓解高维流模型的计算压力。
- 实验覆盖同构/异构模态、生成/判别任务，对比基线全面，消融实验扎实。
- **可解释性**较隐式方法有明显提升，有助于理解模态贡献。

## 8. 不足与局限

- **模态数量限制**：实验仅涉及两类模态的融合，尚未验证多于两种模态的场景。
- **超参数敏感性与目标平衡**：文中提到损失平衡权重尚未充分探索。
- **实验规模**：所用数据集虽为标准 benchmark，但均属中等规模，未在大规模预训练场景下验证。
- **计算开销仍存在**：尽管使用潜在压缩，整体参数量和推理时间仍高于某些轻量方案（如 TokenFusion）。
- **泛化性验证不足**：缺失对更复杂的多模态任务（如视频、音频融合）的测试。
- **编码器依赖**：感知压缩依赖于预训练自编码器，若编码器质量不佳可能影响整体性能。

（完）
