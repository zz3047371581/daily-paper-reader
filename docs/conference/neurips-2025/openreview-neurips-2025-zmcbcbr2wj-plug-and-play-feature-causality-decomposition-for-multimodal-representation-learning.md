---
title: Plug-and-play Feature Causality Decomposition for Multimodal Representation Learning
title_zh: 即插即用的特征因果分解多模态表示学习方法
authors: "Ye Liu, Zihan Ji, Hongmin Cai"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=zmCBCbr2Wj"
tags: ["query:affective-ai"]
score: 10.0
evidence: 提出因果分解以分离噪声和互补信息，提升多模态情感分析
tldr: 多模态情感分析等任务中，如何同时利用模态间一致性和互补性信息并消除噪声是关键挑战。本文提出一种即插即用的特征因果分解方法，将多模态特征分解为一致性、互补性和噪声成分，并通过因果干预策略消除由噪声引入的虚假相关性。实验表明，该方法在多个多模态情感分析数据集上表现最优，且易于集成到现有模型中。该工作从因果推断角度为多模态表征学习提供了新思路，不仅提升了情感识别性能，还增强了模型的可解释性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-zmcbcbr2wj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 526, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zmcbcbr2wj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1376, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zmcbcbr2wj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 624, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zmcbcbr2wj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 629, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zmcbcbr2wj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 831, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zmcbcbr2wj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 906, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-zmcbcbr2wj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1399, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zmcbcbr2wj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 719, \"height\": 445, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zmcbcbr2wj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 907, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zmcbcbr2wj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 676, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zmcbcbr2wj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 807, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zmcbcbr2wj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1378, \"height\": 560, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zmcbcbr2wj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 953, \"height\": 561, \"label\": \"Table\"}]"
motivation: 多模态表示学习中常将噪声作为互补信息，导致一致性和互补性信息利用不足。
method: 提出即插即用的因果分解方法，将特征分为一致、互补和噪声，并通过因果干预去噪。
result: 在多模态情感分析任务上，该方法显著提升性能，且易于集成到现有框架。
conclusion: 因果视角下的特征分解为多模态学习提供了新的解释和提升手段，具有广泛应用前景。
---

## Abstract
Multimodal representation learning is critical for a wide range of applications, such as multimodal sentiment analysis. Current multimodal representation learning methods mainly focus on the multimodal alignment or fusion strategies, such that the complementary and consistent information among heterogeneous modalities can be fully explored. However, they mistakenly treat the uncertainty noise within each modality as the complementary information, failing to simultaneously leverage both consistent and complementary information while eliminating the aleatoric uncertainty within each modality. To address this issue, we propose a plug-and-play feature causality decomposition method for multimodal representation learning from causality perspective, which can be integrated into existing models with no affects on the original model structures. Specifically, to deal with the heterogeneity and consistency, according to whether it can be aligned with other modalities, the unimodal feature is first disentangled into two parts: modality-invariant (the synergistic information shared by all heterogeneous modalities) and modality-specific part. To deal with complementarity and uncertainty, the modality-specific part is further decomposed into unique and redundant features, where the redundant feature is removed and the unique feature is reserved based on the backdoor-adjustment. The effectiveness of noise removal is supported by causality theory. Finally, the task-related information, including both synergistic and unique components, is further fed to the original fusion module to obtain the final multimodal representations. Extensive experiments show the effectiveness of our proposed strategies.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：多模态表征学习中，现有方法往往将各模态内的偶然不确定性噪声（aleatoric uncertainty）错误地当作互补信息加以利用，无法在捕捉一致性与互补性信息的同时消除噪声，从而损害融合性能。
- **研究动机**：模态数据采集过程与传感器特性的差异导致单模态特征中混杂任务无关的冗余噪声，而现有方法多侧重对齐或融合策略，未能从因果角度同时处理异质性、互补性与不确定性。
- **整体含义**：提出一种即插即用的**特征因果分解（Feature Causality Decomposition, FCD）** 模块，从因果推断的视角将单模态特征显式分解为协同（synergistic）、独特（unique）和冗余（redundant）三部分，去除噪声并保留任务相关信息，可无损嵌入现有中间融合模型。

### 2. 方法论核心思想与关键技术细节
- **核心流程**：
  1. **因果成分分解（CCD）**：将单模态特征 $z_{mn}$ 通过 MLP 分解为模态不变部分 $s_{mn}$（协同特征）和模态特定部分 $h_{mn}$。
  2. **独特-冗余分解（URD）**：从 $h_{mn}$ 中通过可逆双射函数进一步拆解出任务相关的独特特征 $u_{mn}$ 和冗余噪声 $r_{mn}$。
  3. **后门调整与互信息最大化**：基于结构因果模型，利用后门调整切断 $h_{mn}$ 带来的混杂路径，将剔除冗余后的 $u_{mn}$ 与标注 $y_n$ 的互信息最大化，实际优化时采用 InfoNCE 下界。
  4. **协同分布对齐（SDA）**：使用参数共享的 MLP 和 Sinkhorn 散度对齐各模态的协同特征 $s_{mn}$，并辅以捷径连接保留原始语义。
  5. **冗余判别约束**：对不同模态的冗余特征 $r_{mn}$ 施加对比损失，以保证模态特定判别性。
  6. **特征聚合**：最终将去噪后的协同特征 $\hat{z}_{mn}$ 与独特特征 $u_{mn}$ 相加，送入原始融合模块。
- **公式与理论**：定理 4.1 证明了在提取函数为测度保持双射时，最大化条件互信息等价于最大化干预后的互信息 $I(do(u_{mn}); y_n)$，从而为噪声去除提供了因果理论基础。

### 3. 实验设计
- **数据集**：
  - 多模态情感分析：CMU‑MOSI、CMU‑MOSEI（回归与分类任务）。
  - 图文分类/情感：MVSA‑Single、UPMC‑Food101、HFM（分类任务）。
- **基准方法**：
  - 情感分析：Self‑MM、MMIM、MCL‑MCF、AtCAF、MMML。
  - 图文任务：MMBT、CLMLF、MVCN、URMF。
  - 所有基线均在其官方实现与原始超参数下复现，再进行**加上FCD**的重跑（Ours）。
- **评估指标**：MAE（↓）、Pearson 相关（↑）、Acc‑2、F1、Acc 等，部分指标区分是否排除零样本。

### 4. 资源与算力
- **硬件环境**：实验在 4 块 NVIDIA RTX 4090 24GB GPU 上完成。
- **框架**：PyTorch。
- **训练时长**：论文给出了每 epoch 的训练时间对比（如 Self‑MM 在 MOSI 上 Base 约 3.92 s/epoch，FCD 后约 5.12 s/epoch），可见额外开销可控。但未报告完整训练的总时长或总 GPU 小时数。

### 5. 实验数量与充分性
- **实验组数较多**：
  - 在 5 个数据集、9 个已有 SOTA 方法上进行了“加 FCD”与“不加 FCD”的对比，合计约 18 组主要实验。
  - 消融实验：逐一剔除 $L_{MI}$、$L_{Dis}$、$L_{SDA}$，以及去除独特特征、去除捷径连接，验证各模块贡献。
  - 敏感性分析：对 batch size 在 {8,16,32,64,128} 上进行测试。
  - 超参数敏感性分析：对 λ₁, λ₂, λ₃ 进行缩放与细粒度搜索，并绘制指标变化曲线。
- **实验充分性**：实验覆盖多任务、多模态、多种基线，消融与敏感性分析较全面，对比方式控制变量（相同基线复现），相对公平。
- **潜在局限**：未报告多次运行的均值和方差，缺少统计显著性检验（如误差棒）；未对非中间融合方法进行扩展评估。

### 6. 主要结论与发现
- FCD 能够显著提升多种现有方法的性能，在所有测试数据集和指标上均取得一致增益。
- 将协同与独特信息同时纳入融合、利用因果干预消除冗余噪声，是提升多模态表征质量的有效途径。
- 消融实验表明，三个损失项（$L_{MI}$、$L_{Dis}$、$L_{SDA}$）及捷径连接和独特特征的加入均对性能有正向贡献，任意模块缺失都会导致性能下降。
- 通过 Grad‑CAM 可视化案例，证实 FCD 能够成功分离出语义一致的协同信息与模态特定的独特信息，增强了可解释性。

### 7. 优点
- **即插即用**：不修改原始模型结构，可直接嵌入已有中间融合模型，普适性强。
- **因果理论支撑**：用结构因果模型和后门调整形式化地处理噪声与混杂，为分解提供理论保证。
- **模块设计清晰**：分别处理一致性、互补性和噪声，各部分约束明确（互信息、对比、Sinkhorn）。
- **实验扎实**：复现多种基线并统一附加 FCD，对比公平，消融与敏感性分析详尽。
- **可解释性**：可视化展示了协同与独特特征在原始数据中的对应，增强对模型行为的理解。

### 8. 不足与局限
- **实验统计信息缺失**：文中未提供多次运行的均值和标准差，无法判断结果波动和显著性。
- **依赖单模态特征质量**：FCD 的有效性高度依赖原始单模态编码器的输出质量，未探讨特征提取不佳时的表现。
- **应用范围**：声明仅适用于中间融合方法，未在早期或晚期融合、缺失模态等场景验证。
- **超参数敏感性**：不同基线下 λ₁ ~ λ₃ 最优值差异较大，需要较细致的调参才能达到最佳效果。
- **计算开销**：虽然每 epoch 时间增加有限，但引入的子模块和额外损失会增加显存和训练复杂度，未分析推理阶段开销。

（完）
