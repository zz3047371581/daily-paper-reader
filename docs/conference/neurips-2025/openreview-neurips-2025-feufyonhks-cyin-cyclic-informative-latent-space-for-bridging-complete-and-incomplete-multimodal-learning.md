---
title: "CyIN: Cyclic Informative Latent Space for Bridging Complete and Incomplete Multimodal Learning"
title_zh: CyIN：用于桥接完整与不完整多模态学习的循环信息潜在空间
authors: "Ronghao Lin, Qiaolin He, Sijie Mai, Ying Zeng, Aolin Xiong, Li Huang, Yap-Peng Tan, Haifeng Hu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=feuFyonHks"
tags: ["query:affective-ai"]
score: 7.0
evidence: 通过信息潜在空间桥接完整与不完整多模态学习，对模态缺失鲁棒
tldr: 现实部署中，多模态数据常常存在模态缺失，导致预训练模型性能骤降。本文模拟人脑的多模态整合能力，提出CyIN框架，通过循环信息学习构建一个信息瓶颈驱动的潜在空间，使模型在完整和不完整模态下均能保持鲁棒的表征。该方法通过令牌级和标签级信息瓶颈，迫使潜在空间保留模态共有信息和判别性信息，同时引入循环重建机制保证模态之间的协同。实验表明，CyIN在多种模态缺失场景下显著优于现有方法，有效弥合了完整与不完整多模态学习之间的鸿沟。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-feufyonhks/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1369, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feufyonhks/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 703, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1387, \"height\": 988, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1408, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 648, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1379, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 653, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1423, \"height\": 809, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1387, \"height\": 1954, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1349, \"height\": 2282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1462, \"height\": 735, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1113, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1431, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 816, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 685, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 652, \"height\": 203, \"label\": \"Table\"}]"
motivation: 多模态预训练模型在模态缺失时性能大幅下降，人脑却能在信息不全时有效整合。
method: 提出 CyIN 框架，用信息瓶颈构建压缩性潜在空间，并通过循环学习强化模态融合。
result: 在多个数据集上，CyIN 在完整性变化动态中大幅超越基线，对缺失模态高度鲁棒。
conclusion: 该研究为不完整多模态学习提供了统一框架，有望推动多模态模型的实际部署。
---

## Abstract
Multimodal machine learning, mimicking the human brain’s ability to integrate various modalities has seen rapid growth. Most previous multimodal models are trained on perfectly paired multimodal input to reach optimal performance. In real‑world deployments, however, the presence of modality is highly variable and unpredictable, causing the pre-trained models in suffering significant performance drops and fail to remain robust with dynamic missing modalities circumstances. In this paper, we present a novel Cyclic INformative Learning framework (CyIN) to bridge the gap between complete and incomplete multimodal learning. Specifically, we firstly build an informative latent space by adopting token- and label-level Information Bottleneck (IB) cyclically among various modalities. Capturing task-related features with variational approximation, the informative bottleneck latents are purified for more efficient cross-modal interaction and multimodal fusion. Moreover, to supplement the missing information caused by incomplete multimodal input, we propose cross-modal cyclic translation by reconstruct the missing modalities with the remained ones through forward and reverse propagation process. With the help of the extracted and reconstructed informative latents, CyIN succeeds in jointly optimizing complete and incomplete multimodal learning in one unified model. Extensive experiments on 4 multimodal datasets demonstrate the superior performance of our method in both complete and diverse incomplete scenarios.

---

## 论文详细总结（自动生成）

# CyIN: 循环信息潜在空间——桥接完整与不完整多模态学习 论文总结

## 1. 论文的核心问题与整体意义
- **核心问题**：多模态模型通常假设训练和推理时所有模态均完整配对，但现实应用中常因传感器故障等原因导致模态随机缺失，使预训练模型性能急剧下降，且多数现有方法需要为每种缺失组合单独训练模型。
- **整体目标与意义**：提出**循环信息学习框架**，构建一个**统一的信息潜在空间**，在完整和不完整输入下联合优化多模态学习，显著提升模型对动态模态缺失的鲁棒性，弥合完整与不完整多模态学习之间的鸿沟。

## 2. 方法论核心
- **总体架构**：CyIN 包含信息瓶颈潜在空间、跨模态循环翻译和多模态融合三个模块，分两阶段训练。
- **信息瓶颈潜在空间（核心创新）**：
  - **令牌级IB**：在任意两个模态的未融合表征之间应用变分信息瓶颈，压缩源模态令牌嵌入并预测目标模态令牌嵌入，通过**循环选择源/目标对**增强模态内和模态间的交互。
  - **标签级IB**：将每个模态的潜在表征与任务标签通过IB连接，注入高层语义监督，进一步净化瓶颈潜在变量。
  - **可微采样**：使用重参数化技巧从学习到的均值、方差中采样瓶颈潜在变量。
- **跨模态循环翻译**：
  - **前向传播**：利用级联残差自编码器从保留的模态潜在变量翻译至缺失模态潜在变量，实现信息重建。
  - **反向传播**：将重建的潜在变量再翻译回源模态，形成循环一致性学习，提升翻译质量。
  - **多模态泛化**：通过叠加高斯分布的加性性质，集成任意数量保留模态的翻译信息，生成统一的缺失模态补充信号。
- **多模态融合**：采用多层交叉注意力Transformer融合所有模态的瓶颈潜在变量。
- **联合优化**：总损失 = 任务损失 + (1/β)(令牌级IB+标签级IB) + γ×翻译损失，其中β控制IB权衡，γ控制重建强度。第一阶段仅优化IB损失以稳定信息空间，第二阶段引入翻译损失联合训练。

## 3. 实验设计
- **数据集与场景**：
  - **多模态回归**：MOSI、MOSEI 情感分析（连续分数[-3,3]）。
  - **多模态分类**：IEMOCAP（六类情感）、MELD（七类情感）情绪识别。
  - 模态均为语言、音频、视觉。
- **评估协议**：
  - **完整输入**：u∈{l, a, v}。
  - **固定缺失**：缺失1个或2个模态（如u∈{l}、{a,v}等）。
  - **随机缺失**：随机缺失率MR从0.1至0.7。
- **对比基准**：CCA、DCCA、DCCAE、CPM-Net、CRA、MCTN、MMIN、GCNet、IMDer、LNLN等近年主流对齐式及生成式不完整多模态学习方法。

## 4. 资源与算力
- **硬件**：使用NVIDIA H800 GPU，未明确注明数量。
- **训练时间**：CyIN 在 MOSI 上训练约 1.61 小时，推理每迭代 22.41 秒，参数量和 FLOPs 均低于对比方法。
- **软件栈**：PyTorch 2.4.1，CUDA 12.4。

## 5. 实验充分性与公平性
- **实验量**：在4个数据集上，评估了完整、6种固定缺失、7种随机缺失共约14种输入条件，均重复10次随机种子取平均，同时报告标准差。
- **消融实验**：移除令牌级IB、标签级IB、循环交互、循环翻译、整个信息空间、重建潜在变量等组件。
- **超参数敏感度分析**：验证了IB权重β、翻译权重γ、CRA层数比等参数的影响。
- **额外验证**：与不同基座语言模型（BERT、RoBERTa、DeBERTa）组合，并在推荐、人脸防伪、密集预测、医疗分割等6个非情感多模态任务上验证泛化性。
- **公平性**：所有基线均采用50次随机网格搜索寻找最优超参，统一评估协议，代码开源。

## 6. 主要结论与发现
- CyIN 在完整和多类缺失场景下均**显著优于所有对比方法**，且在高随机缺失率下性能衰减极小，鲁棒性突出。
- **信息瓶颈**有效滤除了任务无关噪声，使跨模态交互和缺失信息重建更高效。
- **循环交互**和**循环翻译**分别增强了融合质量和重建一致性。
- 通过统一框架，CyIN 在不牺牲完整模态性能的前提下，可应对任意未知的模态缺失组合。

## 7. 方法亮点
- **统一性**：首次在单模型中同时优化完整与不完整多模态学习，无需为特定缺失模式定制模块。
- **神经启发性**：模拟人脑信息筛选与跨感官想象能力，利用信息论原则压缩冗余、保留判别特征。
- **可解释的潜在空间**：两者IB与循环翻译形成清晰的信息流约束，有利于分析模态关联。
- **轻量化部署**：参数量小、推理速度快，适合资源受限的真实场景。

## 8. 不足与局限
- **模态贡献均等假设**：框架默认各模态重要性相同，未自适应分配权重，可能未充分利用主导模态。
- **翻译模块可进一步强化**：目前使用的级联残差自编码器可能被扩散模型等更先进的生成方法替代，以取得更优重建效果。
- **规模扩展探索有限**：尽管在中小型数据集上表现优异，但在更大规模多模态数据集和与 LLM 融合的场景下性能尚待验证。
- **潜在偏差风险**：在模态缺失情况下，重建的信息可能引入偏差或伪影，影响下游公平性。

（完）
