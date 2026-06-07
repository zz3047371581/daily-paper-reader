---
title: "With Limited Data for Multimodal Alignment, Let the STRUCTURE Guide You"
title_zh: 数据有限时的多模态对齐：让结构引导你
authors: "Fabian Gröger, Shuo Wen, Huyen Le, Maria Brbic"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=IkvQqD7hk3"
tags: ["query:affective-ai"]
score: 9.0
evidence: 利用极少量成对数据实现多模态对齐；结构正则化保持邻域结构
tldr: "针对多模态对齐通常需要数百万成对样本的依赖，本文探索了在极少量数据（通常数据的1%以下）下实现对齐的可能性。提出结构正则化技术STRUCTURE，通过保持预训练单模态模型的邻域结构来指导对齐过程。实验证明，仅需数万对样本即可达到以往海量数据下的对齐质量，大幅降低了多模态模型构建的数据门槛。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1401, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 802, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 535, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 718, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1178, \"height\": 981, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1425, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1510, \"height\": 1254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1512, \"height\": 1257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ikvqqd7hk3/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1506, \"height\": 497, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1111, \"height\": 792, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1311, \"height\": 1068, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1105, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 916, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 933, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 720, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1151, \"height\": 1511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1171, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1454, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ikvqqd7hk3/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1449, \"height\": 1042, \"label\": \"Table\"}]"
motivation: 多模态对齐过度依赖海量成对数据，在数据稀缺领域应用受限。
method: 提出STRUCTURE正则化，通过保持单模态嵌入的局部邻域结构来约束跨模态对齐。
result: "在零样本分类和跨模态检索任务上，用不到1%的数据实现了与全数据方法相当的性能。"
conclusion: 该研究为数据高效的多模态对齐提供了理论依据和实用技术。
---

## Abstract
Multimodal models have demonstrated powerful capabilities in complex tasks requiring multimodal alignment, including zero-shot classification and cross-modal retrieval. However, existing models typically rely on millions of paired multimodal samples, which are prohibitively expensive or infeasible to obtain in many domains. In this work, we explore the feasibility of building multimodal models with limited amount of paired data by aligning pretrained unimodal foundation models. We show that high-quality alignment is possible with as few as tens of thousands of paired samples$\unicode{x2013}$less than 1\% of the data typically used in the field. To achieve this, we introduce STRUCTURE, an effective regularization technique that preserves the neighborhood geometry of the latent space of unimodal encoders. Additionally, we show that aligning last layers is often suboptimal and demonstrate the benefits of aligning the layers with the highest representational similarity across modalities. These two components can be readily incorporated into existing alignment methods, yielding substantial gains across 24 zero-shot image classification and retrieval benchmarks, with average relative improvement of 51.6\% in classification and 91.8\% in retrieval tasks. Our results highlight the effectiveness and broad applicability of our framework for limited-sample multimodal learning and offer a promising path forward for resource-constrained domains.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义
- **研究动机**：现有跨模态对齐模型（如CLIP）依赖数百万对成对数据，在医疗、生物等领域获取如此大量配对样本成本高昂甚至不可行。
- **核心问题**：探索在仅拥有**数万对**样本（通常数据量的1%以下）的情况下，通过冻结预训练单模态基础模型，学习轻量对齐函数，实现高质量的多模态对齐。
- **整体含义**：为资源受限领域提供一种数据高效的多模态学习路径，显著降低对大规模配对数据的依赖。

## 论文提出的方法论
- **两个关键组件**：
  - **STRUCTURE正则化**：
    - 核心思想：对齐时保留每个单模态编码器预训练潜在空间的**多尺度邻域结构**。
    - 技术细节：对归一化、中心化的嵌入计算温度缩放相似度矩阵，经softmax转化为概率分布矩阵，通过幂次（l‑hop）捕捉多步关系。对每个层级使用Jensen‑Shannon散度度量分布差异，正则项为多层级散度的加权平均（低层级权重更大）。最终损失为任一对齐损失L<sub>A</sub>加上各模态正则项，λ为超参数。
    - 特点：不依赖全局缩放、平移和正交旋转，且理论上有O(1/√N)的泛化界。
  - **相似性驱动的层选择**：
    - 不用默认的末层对齐，而是选择两个编码器中**相互k近邻相似度最高**的层对进行对齐（k用Rice准则选定）。
- **即插即用性**：上述两个组件可无缝融入现有对齐方法（线性映射、MLP、CSA、FuseMix等），无需改动原有架构。

## 实验设计
- **训练数据**：MS COCO训练集80K图像‑文本对；部分实验下采样至1K~80K或扩充LAION‑15M子集。
- **评估基准**：
  - **零样本分类**：22个数据集（包括CIFAR10/100、ImageNet、Food101、SUN397等）。
  - **跨模态检索**：Flickr30、MS COCO测试集（I2T、T2I的R@1）。
- **对比方法**：线性映射（Linear）、多层感知机（MLP）、CSA、FuseMix，以及各自的变种（末层 vs 相似层，有无STRUCTURE）。
- **模型组合**：RoBERTa、Llama3‑8B、Llama‑13B等语言模型，搭配ViT‑B/L/G等视觉模型；另含音频‑文本、单细胞图像‑转录组等跨领域实验。
- **额外分析**：缩放训练数据量、添加域内样本、不同层选择策略、信任度与连续性监视等。

## 资源与算力
- **硬件**：使用包含8块NVIDIA GeForce RTX 3090 GPU的集群，**单次训练仅需1块GPU、低于4 GB显存，最长2小时**。提取嵌入阶段单GPU批大小16，约3秒/迭代。
- **实验规模**：由于训练冻住编码器且对齐模块极轻量，整体计算开销非常小。

## 实验数量与充分性
- **广覆盖多维度**：在24个基准上评估，包括22个分类和2个检索数据集；涉及多种对齐方法、模型组合、数据量级、域偏移场景。
- **丰富消融**：对正则化层级L、权重λ、层选择指标、批大小、子集类型、归一化方式、距离函数等均进行消融实验，验证鲁棒性。
- **公平性**：统一使用冻结编码器、相同训练配置（如余弦调度、AdamW等），对比基线清晰，无特殊调整，实验结果客观。

## 主要结论与发现
- **数据效率极强**：仅用80K配对样本，线性+STRUCTURE+相似层即实现平均相对提升51.6%（分类）和91.8%（检索），甚至在CIFAR10上超越CLIP（用0.02%的数据）。
- **几何保持是关键**：STRUCTURE正则化使训练全程信任度、连续性维持>0.99，避免过扭曲，性能大幅优于无正则化基线。
- **层选择效果稳定**：选择最高相似度层始终优于末层，且对子集大小和重复试验鲁棒，提升约2%~18%相对性能。
- **域内样本威力**：加入极少域内样本（如3张/类）即可让零样本性能比肩或超越海量数据训练的CLIP，揭示域覆盖比数据量更重要。
- **跨模态泛化**：在音频‑文本和生物成像‑转录组对齐中同样有效，证明方法通用性。

## 优点
- **简单高效**：作为一个即插即用的正则项，代码量少，不影响原有对齐框架。
- **理论支撑**：提供泛化界分析（O(1/√N)）和几何保持性的可视化证据。
- **低资源友好**：显存、训练时间极小，单GPU即可完成，适合实际应用。
- **可扩展性**：可自然推广到三模态或更多，只需为每个模态添加对应正则项。

## 不足与局限
- **极难任务的差距**：在更复杂任务上与海量数据训练的CLIP仍有性能差距，尽管可通过少量域内样本弥补。
- **模态数量有限**：目前仅验证两模态，虽理论上可扩展，但未给出多模态联合训练的实证。
- **数据分布依赖**：当训练数据与目标域分布差异大时，零样本性能较低，需额外域内样本校正。
- **未涉及生成或复杂推理**：评估局限于分类和检索，未测试图像描述、问答等生成式跨模态任务。

（完）
