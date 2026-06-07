---
title: Multi-dataset Joint Pre-training of Emotional EEG Enables Generalizable Affective Computing
title_zh: 情绪脑电多数据集联合预训练实现可泛化的情感计算
authors: "Qingzhu Zhang, Jiani Zhong, Li ZongSheng, Xinke Shen, Quanying Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=xaxuzubN31"
tags: ["query:affective-ai"]
score: 10.0
evidence: 跨数据集预训练框架实现脑电情绪识别，含协方差对齐
tldr: 针对脑电情绪识别中的跨数据集分布偏移、标签不一致和个体差异问题，提出多数据集联合预训练框架。通过跨数据集协方差对齐损失和任务特定设计，实现鲁棒的跨域泛化。实验表明方法在多个数据集上显著提升情感识别准确率，为普适化情感计算奠定基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xaxuzubn31/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 689, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xaxuzubn31/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 1093, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xaxuzubn31/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xaxuzubn31/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1125, \"height\": 741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xaxuzubn31/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1464, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xaxuzubn31/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1482, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xaxuzubn31/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1147, \"height\": 1829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xaxuzubn31/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 948, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xaxuzubn31/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1459, \"height\": 1191, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1539, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1469, \"height\": 1459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1187, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 455, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1306, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1308, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 857, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1184, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1437, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1437, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1475, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1422, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 739, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1609, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 499, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xaxuzubn31/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 495, \"height\": 256, \"label\": \"Table\"}]"
motivation: 脑电情感识别面临跨数据集分布偏移与个体差异挑战。
method: 设计跨数据集协方差对齐损失和多集联合预训练框架。
result: 方法在跨数据集情绪识别任务中取得鲁棒泛化性能。
conclusion: 为通用化情感脑机接口提供了有效的预训练方案。
---

## Abstract
Task-specific pre-training is essential when task representations diverge from generic pre-training features. Existing task-general pre-training EEG models struggle with complex tasks like emotion recognition due to mismatches between task-specific features and broad pre-training approaches. This work aims to develop a task-specific multi-dataset joint pre-training framework for cross-dataset emotion recognition, tackling problems of large inter-dataset distribution shifts, inconsistent emotion category definitions, and substantial inter-subject variability. We introduce a cross-dataset covariance alignment loss to align second-order statistical properties across datasets, enabling robust generalization without the need for extensive labels or per-subject calibration. To capture the long-term dependency and complex dynamics of EEG, we propose a hybrid encoder combining a Mamba-like linear attention channel encoder and a spatiotemporal dynamics model. Our method outperforms state-of-the-art large-scale EEG models by an average of 4.57% in AUROC for few-shot emotion recognition and 11.92% in accuracy for zero-shot generalization to a new dataset. Performance scales with the increase of datasets used in pre-training. Multi-dataset joint pre-training achieves a performance gain of 8.55\% over single-dataset training. This work provides a scalable framework for task-specific pre-training and highlights its benefit in generalizable affective computing. Our code is available at https://github.com/ncclab-sustech/mdJPT_nips2025.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

*   **核心问题**：脑电（EEG）情绪识别通用模型中，由于训练数据的异质性与任务表征的不匹配，导致模型在复杂情绪识别任务及跨数据集泛化上性能不佳。具体挑战包括：
    *   跨数据集分布偏移大（采集设备、实验范式不同）。
    *   情绪类别定义不一致（离散 vs 维度、类别数量不同）。
    *   被试间变异性高。
*   **整体含义**：论文提出一种面向情绪识别任务的**任务特定多数据集联合预训练框架**，旨在通过仅利用无标签脑电数据的统计对齐，学习可迁移的情绪表征，实现对新被试、新数据集甚至新情绪类别的鲁棒泛化，为普适化情感计算提供可扩展的方案。

## 2. 方法论

### 2.1 核心思想
通过多数据集联合预训练获得任务特定的 EEG 特征表示。训练不依赖显式情绪标签，而是借助**跨数据集协方差对齐（CDA）** 与**跨被试对齐（ISA）** 两个自监督损失，同时捕捉 EEG 信号的二阶统计一致性和跨被试的情绪状态排列不变性。

### 2.2 关键技术细节

*   **混合时空编码器**
    *   **MLLA 通道编码器**：基于类 Mamba 的线性注意力机制，对每个导联独立建模长程时间依赖。将 EEG 切分成重叠补丁，经含线性注意力、遗忘门和输入门的模块处理后，输出单导联时序特征。
    *   **时空动力学模型**：通过空间投影将多导联特征映射到隐空间；再应用膨胀空间转移卷积提取不同时间尺度的空间模式，配合局部注意力机制动态加权整合时空信息。
*   **跨数据集对齐损失（CDA Loss）**
    *   在一个批次中，对不同被试及数据集，计算隐空间表示 $p$ 的协方差矩阵（每个被试所有试次的平均）。
    *   对齐损失衡量批次中所有被试协方差矩阵两两之间的欧氏距离（Frobenius 范数），并求和取对数，迫使模型拉近不同数据集/被试的特征二阶统计量。
*   **被试间对齐损失（ISA Loss）**
    *   将同一情绪刺激同一时间段内来自不同被试的 EEG 片段作为正样本对，不同刺激的片段作为负样本对。
    *   利用对比学习损失（温度缩放交叉熵）让模型区分是否属于相同刺激，从而学习情绪相关的被试不变表征。

### 2.3 预训练与部署流程
*   **预训练**：在多个数据集的原始 EEG 上，以总损失 $L = L_{ISA} + \lambda L_{CDA}$ 训练混合编码器。
*   **few‑shot 微调**：冻结预训练编码器，在目标数据集少量被试上训练 MLP 分类器，测试其余被试。
*   **zero‑shot 泛化**：直接使用冻结编码器提取特征，通过最近邻搜索评估识别准确率。

## 3. 实验设计

*   **数据集**：使用6个公开情绪脑电数据集——SEED、SEED‑IV、SEED‑V、SEED‑VII、FACED、DEAP（共涵盖从2类别至9类别的离散/维度情绪）。
*   **评价设置**：
    *   **留一数据集交叉验证**：任选一个数据集作为目标，其余五个用于预训练。
    *   **few‑shot 分类**：目标数据集按被试 1:3 划分训练/测试集，训练线性分类器。
    *   **zero‑shot 泛化**：不在目标数据集做任何微调，直接计算余弦相似度的最近邻准确率。
*   **对比方法**：与三种通用的 EEG 预训练大模型（MMM、LaBraM、EEGPT）以及无预训练的传统微分熵（DE）特征基线进行比较。所有下游分类均采用相同的 LDS 平滑和 MLP 分类器。
*   **评估指标**：准确率、精确率、召回率、F1 分数、AUROC。

## 4. 资源与算力

*   **硬件**：所有实验在 **NVIDIA GeForce RTX 3090 GPU** 上运行。
*   **软件**：Python 3.12.3，PyTorch 2.3.1。
*   **训练开销**：论文未提供具体的单次训练时长或总 GPU 时数，仅列明了超参数（预训练20 epoch，学习率5e-4等）。模型参数量仅1.0M，极为轻量。

## 5. 实验数量与充分性

*   **实验总量**：5个数据集上的留一交叉验证（共5×2种设置），涵盖 few‑shot（含5指标）和 zero‑shot；预训练数据集数量影响分析（多种组合）；消融实验（CDA权重、ISA有无、MLLA vs Transformer、时空模型 vs Transformer、对比学习策略、采样策略）；域外泛化（DEAP<->离散数据集互换、想象情绪数据集验证）；以及特征可视化、解释性分析等，实验极为丰富。
*   **充分性与公平性**：
    *   对比基线均为已发表且公开权重的强模型，手动对齐训练测试流程，评价指标多元，随机种子重复实验。
    *   消融研究系统分析了各模块贡献，并通过可视化（t‑SNE、Silhouette Score、重要性归因）佐证了跨数据集对齐效果。
    *   实验设计支持对“任务特定预训练优于通用预训练”的核心主张的验证，评估客观公正。

## 6. 主要结论与发现

*   **性能优势**：mdJPT 在few‑shot情绪识别上平均AUROC比最强基线提升 **4.57%**，在zero‑shot泛化上平均准确率提升 **11.92%**（相对提升约40%），并在大部分数据集上取得最优或次优结果。
*   **数据规模效应**：预训练数据集的增加会单调提升下游性能；使用全部5个数据集相比单数据集预训练，准确率绝对提升 **8.55%**。
*   **对齐损失的必要性**：CDA损失有效减轻域偏移，ISA损失对学习情绪相关表征至关重要（移除ISA后性能骤降）。
*   **架构有效性**：MLLA 通道编码器优于普通 Transformer 编码器，时空动力学模型同样优于传统自注意力层。
*   **通用性**：预训练表征在视频诱发情绪以外的想象诱发任务上也显示出正面效果，且对情绪维度（效价、唤醒度）的切换具有一定泛化能力。

## 7. 优点

*   **任务聚焦**：首次在EEG情绪识别中引入“任务特定多数据集联合预训练”范式，针对性解决跨数据集漂移和标签不一致问题。
*   **新颖的对齐机制**：CDA损失直接对齐二阶协方差统计量，简单有效且无需情感标签；ISA损失利用时间对齐的对比学习，隐式捕捉情绪结构。
*   **高效架构**：参数仅1.0M，却超越多个重参数大模型，展示出极高的计算性价比。
*   **强泛化能力**：同时支持 zero‑shot 和 few‑shot 设置，对未见数据集和新情绪类别具备一定的鲁棒性。
*   **充分的实验验证**：设计全面，涵盖多数据集、多基线、消融、域外评估和可解释性分析，结论可信度高。

## 8. 不足与局限

*   **细粒度情绪性能不足**：在9类别的FACED数据集上准确率仍较低（~23%），表明高质量细粒度情绪表征的学习仍是挑战。
*   **情绪诱导范式局限**：主要基于视频诱发情绪进行评估，对想象、音乐等不同诱发的泛化能力仅进行了初步探索，需更多验证。
*   **被试差异性建模缺失**：未建模个体情绪体验的差异（如个性化评分），可能忽略微妙情感状态。
*   **人口多样性有限**：现有EEG情绪数据集的人口统计学多样性不足（年龄、文化、健康状况等），可能限制模型在更广泛人群上的表现。
*   **硬件部署复杂**：模型依赖多导联湿电极脑电帽，日常化应用仍受设备便携性制约。
*   **伦理风险**：情绪识别技术存在被滥用于情绪监控或分析的风险，论文虽提及但未给出具体防护方案。

（完）
