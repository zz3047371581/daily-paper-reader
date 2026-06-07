---
title: Adaptive Re-calibration Learning for Balanced Multimodal Intention Recognition
title_zh: 自适应重校准学习实现均衡多模态意图识别
authors: "Qu Yang, Xiyang Li, Fu Lin, Mang Ye"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=k71nsscO9b"
tags: ["query:affective-ai"]
score: 6.0
evidence: 针对多模态意图识别中模态不平衡的自适应重校准方法，可迁移至多模态情感识别
tldr: 针对多模态意图识别中由模态信息量差异导致的过度依赖主流模态问题，该文提出自适应重校准学习（ARL），一种双路径框架，从样本级和结构级两方面建模模态重要性。实验证明ARL在多个基准上有效缓解模态不平衡，提升了多模态融合的泛化能力。该方法对多模态情感识别中类似的模态异质性挑战具有方法论借鉴意义。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-k71nssco9b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-k71nssco9b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 627, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-k71nssco9b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 714, \"height\": 504, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 736, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1470, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 567, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 802, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 495, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 662, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1426, \"height\": 1486, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 808, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-k71nssco9b/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 522, \"height\": 205, \"label\": \"Table\"}]"
motivation: 现实多模态系统中不同模态信息量差异导致模型偏向优势模态，限制了泛化性和鲁棒性。
method: 提出ARL双路径框架，包含样本级重要性建模和结构级重校准机制，自适应调节各模态的贡献。
result: 在多模态意图识别数据集上，ARL有效平衡了模态利用，提升了在各种噪声条件下的性能。
conclusion: ARL通过多层级重校准为多模态不平衡问题提供了一种有效解决思路，可推广至情感计算等任务。
---

## Abstract
Multimodal Intention Recognition (MIR) plays a critical role in applications such as intelligent assistants, service robots, and autonomous systems. However, in real-world settings, different modalities often vary significantly in informativeness, reliability, and noise levels. This leads to modality imbalance, where models tend to over-rely on dominant modalities, thereby limiting generalization and robustness. While existing methods attempt to alleviate this issue at either the sample or model level, most overlook its multi-level nature. To address this, we propose Adaptive Re-calibration Learning (ARL), a novel dual-path framework that models modality importance from both sample-wise and structural perspectives. ARL incorporates two key mechanisms: Contribution-Inverse Sample Calibration (CISC), which dynamically masks overly dominant modalities at the sample level to encourage attention to underutilized ones; and Weighted Encoder Calibration (WEC), which adjusts encoder weights based on global modality contributions to prevent overfitting. Experimental results on multiple MIR benchmarks demonstrate that ARL significantly outperforms existing methods in both accuracy and robustness, particularly under noisy or modality-degraded conditions.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究背景**：多模态意图识别（MIR）是智能助手、服务机器人和自主系统的关键任务，旨在融合视觉、语言和音频等多源信号推断用户意图。
- **核心问题**：现实场景中各模态的信息量、可靠性和噪声水平差异巨大，导致**模态不平衡**——模型过度依赖某一“主导”模态，忽视其他可能包含关键信息的弱模态，严重损害泛化性与鲁棒性。
- **现有方法不足**：当前方法仅在样本级（如重加权）或模型级（如梯度调制）处理不平衡，未同时考虑该问题的多层次本质；基于Shapley值的精确贡献估计虽有效，但计算复杂度随模态数指数增长，难以扩缩。
- **本文目标**：设计一种兼顾**样本级与结构级（模型架构级）** 的双路径自适应重校准框架，以高效、动态地平衡模态贡献。

### 2. 论文提出的方法论
- **总体架构**：Adaptive Re‑calibration Learning (ARL) 是一个轻量级即插即用框架，包含三个核心组件：留一法（LOO）模态贡献评估、贡献逆样本校准（CISC）和加权编码器校准（WEC）。
- **LOO模态贡献评估**：
  - 对每个样本，分别掩码各模态（用零向量替换），计算掩码前后的融合表示之间的余弦相似度。
  - 采用 softmax 归一化得到每个模态的贡献分数 $\delta_i^{(m)}$，敏感参数 $\eta$ 控制贡献差异的尖锐程度。
  - 与Shapley值相比，复杂度从 $O(2^M)$ 降为 $O(M)$，仅需 $M$ 次前向传播。
- **贡献逆样本校准 (CISC)**：
  - 若某模态的贡献 $\delta_i^{(m)} \ge \tau$，则认为该模态过于主导，将其特征硬掩码置零（hard masking），促使模型关注其他未充分使用的模态。
  - 校准后的特征重新融合并用于损失计算，实现样本级动态平衡。
- **加权编码器校准 (WEC)**：
  - 定义**纯度分数**衡量每个模态编码器在聚类中的类别一致性，并计算训练集与验证集纯度差的绝对值 $P_m$ 作为一致性缺口。
  - 结合平均LOO贡献 $\bar{\delta}^{(m)}$，通过 $\tanh$ 函数生成动态权重 $w_m$。
  - 每 $T$ 轮次用该权重调整编码器参数：$\theta^{(m)}_{new} = w_m \cdot \theta^{(m)}_{init} + (1-w_m) \cdot \theta^{(m)}_{current}$，防止对强模态的过拟合并提升长期稳定性。
- **协同作用**：CISC 在每个批次中实现短期、样本层的强硬平衡；WEC 定期从全局结构与统计层面进行长期、架构层的校准，二者互补。

### 3. 实验设计
- **数据集与场景**：
  - **MIntRec**：多模态意图识别基准，2224个样本，支持粗粒度二分类（表达情感 vs. 实现目标）和细粒度20类分类。
  - **CMU‑MOSI**：多模态情感分析基准，2199个样本，情感分数被离散为7类，作为额外不平衡验证。
- **基准模型**：将 ARL 作为插件模块插入三个代表性方法：**MAG‑BERT**、**MulT**、**TCL‑MAP**。
- **对比方法**：
  - 主要对比上述三个基线的原始性能与加入ARL后的性能提升。
  - 额外与针对不平衡学习的现有方法进行对比，例如 Curriculum Dropout、OGM、OPM、InfoReg，并在更近期模型如 CAGC、DMD 上验证即插即用能力。
- **评价指标**：准确率（ACC）、宏观/加权 F1、精确率、召回率。

### 4. 资源与算力
- **硬件配置**：所有实验在 **4 块 NVIDIA 4090 GPU** 上进行。
- **训练时间与开销**：论文未提供具体的训练耗时，但明确指出：
  - 相较于无需贡献评估的基线，LOO 评估需每样本增加额外前向传播（模态数次），且 WEC 的定期校准带来训练时间与资源消耗的增加。
  - 特征维度为：MIntRec 文本 768、视觉 256、声学 768；MOSI 文本 768、视频 20、音频 5。

### 5. 实验数量与充分性
- **实验组数**：论文设计了极其充分的实验矩阵：
  - **主实验**：2个数据集 × 3个基线 × 2种分类粒度（MIntRec）或单一分类（MOSI），共展示多张结果表；
  - **消融实验**：在 MIntRec 上对 CISC 与 WEC 独立及联合作用进行定量分析，共计约 3×4 种配置；
  - **超参数敏感性**：对 WEC 权重 $\alpha$ (6个值) 和 CISC 阈值 $\tau$ (6个值) 分别在 MOSI 和 MIntRec 上进行网格搜索；
  - **掩码策略对比**：硬掩码 vs. 软掩码；
  - **缺失模态鲁棒性**：在 MOSI 上测试 3 种模态对组合 ($\{a,v\}, \{v,t\}, \{a,t\}$) 下 ARL 的增益；
  - **计算效率对比**：可视化 LOO 与 Shapley 方法的计算时间随模态数和特征维度变化的曲线；
  - **扩展对比**：与其他不平衡学习方法和近期 SOTA 模型的集成能力验证。
- **充分性与客观性**：
  - 实验覆盖了不同任务（意图、情感）、多种基线和评价指标，并包含细致的消融与敏感性分析。
  - 对比对象涵盖梯度调制、正则化等不同技术路线，且在同一基线上公平比较，结果通过多维指标（ACC/F1/P/R）交叉验证，能支撑论文论证。

### 6. 论文的主要结论与发现
- ARL 在所有基线上均带来稳定且显著的提升。例如在 MIntRec 二十类任务中，TCL‑MAP 的准确率从 73.62% 提升至 75.28%（+1.66%），加权 F1 增益达 1.85%。
- 在噪声或模态缺失条件下，ARL 展现出更强的鲁棒性和泛化能力，证实其适用于真实世界部署。
- 双路径联合（CISC+WEC）能够比单独使用任一组分取得更优的协同效果，表明从样本级和结构级共同处理不平衡的必要性。
- 硬掩码策略比软掩码更能迫使模型学习被忽略的模态，显著提升召回率和 F1。
- LOO 评估方式在保持线性复杂度的同时，达到与指数级复杂度的 Shapley 法相当的平衡效果，具有更高的实用性。

### 7. 优点
- **多层级联合优化**：首次同时从样本级（CISC）和模型结构级（WEC）对模态不平衡进行显式建模与校正，视角新颖。
- **高效且可扩展**：用留一法替代 Shapley 值，计算复杂度降为线性，易于扩展到更多模态。
- **即插即用设计**：ARL 不改变基线模型的融合结构，可作为插件轻松嵌入多种 SOTA 多模态框架，通用性强。
- **实验设计全面且扎实**：包含意图与情感任务、多种基线、细粒度消融、超参数分析、缺失模态和扩展对比，且对硬/软掩码、计算代价等关键设计选择进行了实证论证。
- **鲁棒性突出**：在模态缺失、噪声等真实场景下优势明显，展示了较高的应用价值。

### 8. 不足与局限
- **依赖基础模型**：ARL 的平衡效果受限于基座模型的特征表达能力与融合机制，若基座本身存在严重偏置，补偿可能有限。
- **额外计算/资源开销**：LOO 贡献评估需额外前向传播，WEC 周期性统计与调整带来训练成本增加；文中未给出具体的增量训练时间，难以量化额外负担。
- **超参数敏感性**：CISC 的阈值 $\tau$ 和 WEC 的系数 $\alpha, \lambda$ 需针对不同数据集和基座模型调优，且极端取值（如过小的 $\tau$）可能导致性能衰减。
- **解释性下降**：引入两套校准模块使模型决策过程更复杂，透明度降低，在安全敏感应用中可能带来信任问题。
- **隐私风险未深入讨论**：多模态融合不可避免地涉及多种感知信号，论文在更广泛的社会影响中提及了潜在滥用和隐私风险，但未在方法论层面提供缓解机制。
- **实验局限**：主要在两个主流数据集（MIntRec 和 MOSI）上验证，缺少更多样化的大规模或更复杂场景的评估；对数基模型（如 MAG‑BERT）的对比未涉及更近期超大模型（如基于大语言模型的意图理解）。  
- **硬掩码的双刃性**：虽然硬掩码有助于打破依赖，但也可能因过度压制有价值的信息而损害性能，论文在极端 $\tau$ 下的实验已有所体现。

（完）
