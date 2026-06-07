---
title: "CovMatch: Cross-Covariance Guided Multimodal Dataset Distillation with Trainable Text Encoder"
title_zh: CovMatch：交叉协方差引导的多模态数据集蒸馏与可训练文本编码器
authors: "Yongmin Lee, Hye Won Chung"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2dpiR9fqUk"
tags: ["query:affective-ai"]
score: 8.0
evidence: 通过交叉协方差对齐和可训练文本编码器实现多模态数据集蒸馏
tldr: 现有冻住文本编码器的多模态蒸馏严重限制语义对齐，制约性能扩展。本文提出CovMatch，通过对齐真实与合成特征的交叉协方差，并让文本编码器参与训练，大幅提升合成数据的语义质量。在多个基准上，以更少的合成样本取得更高性能。它为高效多模态学习提供了紧凑、高保真的数据集蒸馏新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1462, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1381, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 745, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1161, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1428, \"height\": 1198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 687, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1318, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 588, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 997, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1045, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1175, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1217, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1271, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1340, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 827, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 709, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1194, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 631, \"height\": 141, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1423, \"height\": 821, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1458, \"height\": 849, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1454, \"height\": 1377, \"label\": \"Table\"}]"
motivation: 冻结文本编码器的多模态蒸馏方法严重限制语义对齐，成为性能瓶颈。
method: 提出CovMatch，对齐交叉协方差并训练文本编码器，实现可扩展数据集蒸馏。
result: 实验表明CovMatch在少数据下达到优越的视觉语言模型性能。
conclusion: 交叉协方差对齐与文本编码器联合训练是提升多模态蒸馏效果的关键。
---

## Abstract
Multimodal dataset distillation aims to synthesize a small set of image-text pairs that enables efficient training of large-scale vision-language models. While dataset distillation has shown promise in unimodal tasks, extending it to multimodal contrastive learning presents key challenges: learning cross-modal alignment and managing the high computational cost of large encoders. Prior approaches address scalability by freezing the text encoder and update only the image encoder and text projection layer.  However, we find this severely limits semantic alignment and becomes a bottleneck for performance scaling.
We propose CovMatch, a scalable dataset distillation framework that aligns the cross-covariance of real and synthetic features while regularizing feature distributions within each modality. Unlike prior approaches, CovMatch enables joint optimization of both encoders, leading to stronger cross-modal alignment and improved performance. Evaluated on Flickr30K and COCO, CovMatch outperforms state-of-the-art multimodal distillation methods and achieves up to 6.8\% absolute gains in retrieval accuracy using only 500 synthetic pairs.

---

## 论文详细总结（自动生成）

## 1. 论文核心问题与整体含义（研究动机和背景）
- 多模态数据集蒸馏旨在从大规模图像–文本对中合成少量高质样本，使在其上训练的视觉语言模型获得与在全量数据上相近的多模态对齐能力。
- 现有方法多采用冻结文本编码器、仅更新图像编码器和文本投影层的策略，以降低大型编码器（如 BERT、NFNet）带来的巨量显存和时间开销。
- 该文发现，冻结文本编码器会严重限制跨模态语义对齐，成为性能随合成样本量增加而扩展的瓶颈，导致检索精度饱和甚至下降。
- 为此，提出 **CovMatch**——一个可扩展的多模态数据集蒸馏框架，关键是让文本编码器也参与蒸馏，从而在极小合成集上实现更强的对齐与性能。

## 2. 方法论：核心思想与关键技术细节
- **整体思路**： 简化双级优化中的内层训练，在固定图像和文本编码器、仅优化线性投影层的假设下，将内层线性对比损失转化为闭式解，从而把蒸馏目标简化为 **对齐真实与合成特征的交叉协方差矩阵**。
- **关键方程与损失**：
  - 线性对比损失可等价为交叉协方差项与正则项的差： \(L_{\text{lin}} = -\text{Tr}(G_v C_D G_l^\top) + \frac{\rho}{2}\|G_v^\top G_l\|_F^2\)，其中 \(C_D\) 是跨模态特征的交叉协方差。
  - 内层最优解满足 \(\hat{G}_v^\top \hat{G}_l = \frac{1}{\rho} C_S\)，代入外层损失后得到最大化 \(\text{Tr}(C_T^\top C_S)\)。
  - 为训练稳定，采用 Frobenius 范数的形式定义 **交叉协方差匹配损失**：  
    \(L_{\text{cov}} = \|\rho \cdot C_T - C_S\|_F^2\)，其中 \(\rho\) 用于缩放真实交叉协方差以适应合成数据规模。
  - 由于仅对齐二阶统计量可能不足，引入 **特征匹配正则损失**，分别对图像和文本模态最小化投影后特征的均值最大均值差异（MMD）：  
    \(L_{\text{feat}}^m = \left\|\frac{1}{|T|}\sum_i G_m f_m(x_i^m) - \frac{1}{|S|}\sum_j G_m f_m(\hat{x}_j^m)\right\|^2\)。
  - 最终总损失：\(L_{\text{CovMatch}} = L_{\text{cov}} + \lambda (L_{\text{feat}}^v + L_{\text{feat}}^l)\)。
- **训练流程**：
  1. 初始化合成数据 \(S\)（从真实训练集随机采样）。
  2. 每一步先用一小批真实数据对图像、文本编码器和投影层做一次梯度更新（在线模型更新），避免过拟合于固定模型状态。
  3. 采样真实批次 \(B_T\) 和合成批次 \(B_S\)，计算 \(L_{\text{CovMatch}}\)，反向传播更新合成图像像素和文本嵌入。
  4. 每 \(T\) 步将编码器重置回预训练权重，投影层随机初始化，以增强稳定性。

## 3. 实验设计：数据集、基准与对比方法
- **数据集与任务**：
  - Flickr30K（约 29K 训练对）和 COCO（约 113K 训练对），采用 Karpathy 划分。
  - 评价任务为跨模态检索：图像到文本（TR@K）和文本到图像（IR@K），报告 R@1、R@5、R@10 及平均值。
- **网络架构**：
  - 图像编码器：NFNet（默认）、NF-ResNet、NF-RegNet、ViT。
  - 文本编码器：BERT-base（默认）、DistilBERT。
  - 每个编码器后接可训练的线性投影层。
- **对比方法**：
  - 核心集选择：Random、Herding、K-Center。
  - 多模态蒸馏方法：MTT-VL（基于轨迹匹配，冻结文本编码器）、LoRS（低秩相似度挖掘，同样冻结文本编码器）。
- **合成样本数**：100、200、500 对，分别占全数据集约 0.3%~0.4% 至 1.7%。

## 4. 资源与算力
- 文中表 1 对比了不同方法在单个 A100 80GB GPU 上的资源需求：
  - 以蒸馏 COCO 为例，MTT-VL/Tesla 需预存专家轨迹（120 GB 存储、132 小时训练），蒸馏时内存 22–71 GB，每迭代 16.9–19.2 秒。
  - CovMatch **无需存储专家轨迹**，蒸馏内存仅 15 GB，每迭代 1.2 秒。
- 具体超参：批大小（真实）128，合成批大小在 500 对时用 256（其余整个合成集），学习率 1.0（SGD+momentum），蒸馏迭代 10k–20k。

## 5. 实验数量与充分性
- **主实验**：两个数据集 × 三种合成规模（100、200、500 对）的检索性能比较，每个结果报告五次运行的平均值和标准差，公平透明。
- **跨架构泛化**：使用 NFNet+BERT 蒸馏的数据，在多种未见过的图像编码器（NF-ResNet、NF-RegNet、ViT）和文本编码器（DistilBERT）上评估，对比其他蒸馏方法。
- **消融实验**（均在 Flickr30K 上）：
  - 缩放因子 \(\rho\) 的影响。
  - 特征匹配权重 \(\lambda\) 的影响。
  - 在线模型更新策略（固定、用合成数据更新、用真实数据更新）。
  - 文本编码器在蒸馏/评估阶段的冻结/解冻组合。
  - 批大小、投影层维度与深度、单模态蒸馏。
- **附加任务**：在视频-文本检索（WebVid-10M 子集）上验证 CovMatch 的通用性。
- 整体实验覆盖核心声明、消融充分、对比公平，结果可靠。

## 6. 主要结论与发现
- 通过引入可训练的文本编码器和对齐交叉协方差，CovMatch 在所有合成规模和两个数据集上均显著优于冻结文本编码器的 SOTA 方法。
- 在仅 500 对合成数据下，平均检索准确率绝对提升 **Flickr30K +6.8%**、**COCO +6.1%**。
- 与冻结文本编码器的方案不同，CovMatch 随合成数据增多性能持续增长，不会饱和或退化。
- 蒸馏出的数据集具有良好的跨架构泛化能力，而此前方法在该设置下性能接近甚至差于随机选择。
- 在线模型更新（用真实数据）和特征匹配正则对防止过拟合和目标约束不足至关重要。

## 7. 优点
- **效率极高**：无需存储和匹配专家轨迹，显存与时间开销远低于基于轨迹匹配的方法。
- **可扩展性**：成功将文本编码器纳入蒸馏，突破了以往方法因冻结文本端而造成的性能瓶颈。
- **理论简洁**：将双级优化转化为交叉协方差对齐的简单损失，推导清晰。
- **泛化性强**：跨架构泛化表现突出，具有实际应用价值。
- **实验扎实**：多数据集、多对比、方差报告、消融全面，结果可信。

## 8. 不足与局限
- 假设已有预训练好的图像与文本编码器（如 ImageNet 预训练 NFNet、BERT），未探索在无预训练模型时从零蒸馏以支撑视觉语言预训练的场景。
- 优化基于线性对比损失的近似，当真实训练中的对比温度较小时，近似误差可能增大，但文中通过实验表明在大模型中近似仍然有效。
- 合成图像呈现高频、近乎“DeepDream”式的风格，其对人类可解释性及下游语义泛化的影响未深入讨论。
- 所有实验均限于图像/视频-文本检索，尚未在更复杂的 VQA、推理等多模态理解任务上验证。

（完）
