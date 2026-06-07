---
title: "An Empirical Study on Configuring In-Context Learning Demonstrations for Unleashing MLLMs' Sentimental Perception Capability"
title_zh: 配置上下文学习示例以释放多模态大语言模型情感感知能力的实证研究
authors: "Daiqing Wu, Dongbao Yang, Sicheng Zhao, Can Ma, Yu Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DTdtM53iag"
tags: ["query:affective-ai"]
score: 10.0
evidence: 直接针对多模态情感分析，研究通过配置上下文学习示例释放MLLMs的情感感知能力。
tldr: 针对现有多模态大语言模型在零样本多模态情感分析中表现不佳的问题，通过深入研究上下文学习示例的配置策略，显著提升了模型的情感感知能力，验证了MLLMs在情感分析任务中的潜力，为无需微调的情感分析提供了实用方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dtdtm53iag/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtdtm53iag/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtdtm53iag/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1765, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtdtm53iag/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 834, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtdtm53iag/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtdtm53iag/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1782, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtdtm53iag/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 862, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtdtm53iag/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 613, \"height\": 295, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 693, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 874, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 746, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1777, \"height\": 879, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 896, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1251, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1770, \"height\": 445, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1770, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1772, \"height\": 669, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtdtm53iag/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1067, \"height\": 257, \"label\": \"Table\"}]"
motivation: 多模态情感分析是通用人工智能的关键挑战，但MLLMs的零样本范式在此任务上表现不佳。
method: 将零样本范式扩展为上下文学习，并深入实验探究示例的配置（如选择、排序、模态组合）对情感感知的影响。
result: 经合理配置的ICL能大幅提升MLLMs的情感分析性能，使之与监督模型媲美。
conclusion: 该研究为多模态情感分析提供了无需微调的有效范式，揭示了MLLMs在情感计算中的应用潜力。
---

## Abstract
The advancements in Multimodal Large Language Models (MLLMs) have enabled various multimodal tasks to be addressed under a zero-shot paradigm. This paradigm sidesteps the cost of model fine-tuning, emerging as a dominant trend in practical application. Nevertheless, Multimodal Sentiment Analysis (MSA), a pivotal challenge in the quest for general artificial intelligence, fails to accommodate this convenience. The zero-shot paradigm exhibits undesirable performance on MSA, casting doubt on whether MLLMs can perceive sentiments as competent as supervised models. By extending the zero-shot paradigm to In-Context Learning (ICL) and conducting an in-depth study on configuring demonstrations, we validate that MLLMs indeed possess such capability. Specifically, three key factors that cover demonstrations' retrieval, presentation, and distribution are comprehensively investigated and optimized. A sentimental predictive bias inherent in MLLMs is also discovered and later effectively counteracted. By complementing each other, the devised strategies for three factors result in average accuracy improvements of 15.9% on six MSA datasets against the zero-shot paradigm and 11.2% against the random ICL baseline.

---

## 论文详细总结（自动生成）

# 论文《An Empirical Study on Configuring In-Context Learning Demonstrations for Unleashing MLLMs’ Sentimental Perception Capability》结构化总结

## 1. 核心问题与研究动机
- **核心问题**：多模态大语言模型（MLLMs）在零样本（zero-shot）范式下处理多模态情感分析（MSA）任务时表现不佳，与全监督模型存在显著差距，引发对 MLLMs 是否具备足够情感感知能力的质疑。
- **研究动机**：零样本范式虽免去微调成本和任务特定标注，却在 MSA 上失效；而上下文学习（In-Context Learning, ICL）只需少量标注样本，无需梯度更新，有望以极小代价释放 MLLMs 的情感潜能。因此，系统研究 ICL 示例的配置策略对 MSA 性能的影响，成为一项迫切且有价值的工作。

## 2. 方法论
### 2.1 核心思想
将 MLLMs 的零样本范式扩展为 ICL，通过精心设计和优化三个关键因素（示例的检索、呈现、分布），提升 MLLMs 在多模态情感分析中的准确率，并揭示和缓解 MLLMs 内在的情感预测偏差。

### 2.2 关键技术细节与策略
- **任务定义**：将图文帖子的情感分类模板化为多模态序列 \(S = \{P; (I_1, O_1); \ldots; (I_n, O_n); \hat{I}\}\)，MLLM 预测下一标记作为输出 \(\hat{O} = \arg\max_T M(T|S)\)。
- **三个关键因素及优化策略**：
  1. **相似度测量（Similarity Measurement）**
     - 提出六种新策略（A, IA, TA, ITA, WIT, WITA），在传统 I、T、IT 基础上引入方面（aspect）相似度和模态加权。
     - **关键发现**：简单聚合图像和文本相似度的 IT/ITA 并非最优；需要动态平衡所有权重。
     - **最优方案**：post‑level MSA 用 `WIT (α:β = 2:8)`，aspect‑level MSA 用 `WITA (α:β = 7:3, (α+β):γ = 2:8)`。
  2. **模态呈现（Modality Presentation）**
     - 研究原始图像/文本与辅助模态（图像字幕、文本生成图像）的不同组合对 ICL 性能的影响。
     - 分析“任务学习”（Task Learning）效应：通过将情感标签替换为无关动物，定量衡量 MLLMs 从输入-输出映射中学习的能力。
     - **最优方案**：**仅使用原始图像和文本**，在信息丰富度和输入复杂性之间达到最佳平衡。
  3. **情感分布（Sentiment Distribution）**
     - 提出五类分布协议（Ideal, Contrary to Ideal, Unlimited, Category Balanced, Identical to Support Set）调节示例的情感标签分布。
     - 定义“相同标签率”（Same Label Rate, SLR）量化示例分布对预测的影响。
     - **关键发现**：MLLMs 存在**规避负面情感预测的内在偏差**。当负面样本稀少时，采用 **Category Balanced 协议**可抵消该偏差，促进公平预测；否则 **Unlimited 协议**更优。

### 2.3 流程与整合
各因素单独探索后，根据任务类型和数据分布，将各自最优策略组合形成最终方案（如表5所示，不同数据集采用不同的检索、呈现、分布策略）。

## 3. 实验设计
### 3.1 数据集与场景
- **Post‑level MSA**：MVSA‑S, MVSA‑M, TumEmo
- **Aspect‑level MSA**：Twitter‑15, Twitter‑17, MASAD
- **支持集**：训练集的 1%（约 16 样本），另开展全训练集消融。
- **评价**：以准确率（Accuracy）为主，部分实验同时报告精确率和召回率。

### 3.2 对比方法
- **MLLM 基线**：零样本范式、随机 ICL、RICES (Yang et al., 2022)、SQPA (Li et al., 2024)、MMICES (Chen et al., 2024)。
- **传统模型**：当前最先进的 Few‑Shot 模型和全监督模型。
- **MLLM 种类**：主要实验用 IDEFICS‑9B，通用性验证用 Open‑Flamingo‑9B。

## 4. 资源与算力
- 论文仅报告了推理阶段的时间开销，使用 **单张 NVIDIA GeForce RTX 4090 GPU**。
- **未提及训练过程**，因为研究基于冻结参数的 MLLMs 进行 ICL，无需微调，因此没有训练算力。
- 时间开销对比显示，优化后的 ICL 每样本推理耗时约 382 ms（16‑shot），略高于随机 ICL，但远低于全监督训练。

## 5. 实验数量与充分性
- **实验规模庞大**：
  - 6 个数据集 × 至少 4 个 shot 数（4, 8, 16）的多组实验。
  - 相似度测量：12 种策略对比。
  - 模态呈现：16 种组合对比。
  - 情感分布：5 种协议对比，并详细分析 SLR 与性能的关系。
  - 额外设计“任务学习”评估实验。
  - 消融实验：支持集大小、不同 MLLM、各策略组合的整体效能。
- **充分性与公正性**：在同一声明下固定其他变量，系统探究单一因素影响，对比基线广泛且方法公开，实验设计严谨、客观。

## 6. 主要结论与发现
- **MLLMs 具备情感感知能力**：通过精心配置 ICL 示例，平均准确率较零样本提升 **15.9%**，较随机 ICL 提升 **11.2%**，在部分数据集上媲美全监督模型。
- **相似度需加权平衡**：简单聚合图像和文本相似度不利；post‑level 重文本，aspect‑level 重方面特征。
- **原始图文模态最优**：辅助模态虽能提供额外信息，但引入噪声并损害“任务学习”效应，反而降低性能。
- **MLLMs 存在内在情感预测偏差**：偏向预测正面和中性，回避负面。采用**类别平衡分布**可有效对抗此偏差，提升公平性。
- **综合策略对多模型、多数据集具通用性**：IDEFICS 和 Open‑Flamingo 均获显著提升。

## 7. 优点
- **系统性**：首次全面考察 ICL 在 MSA 中的三大配置因子，提供了清晰的优化路径和理论解释。
- **洞察深刻**：发现 MLLMs 的情感预测偏差，并提出通过分布协议进行推理层面的缓解，为公平性研究提供新视角。
- **实用性强**：方法无需微调，仅需极少量标注样本（16 个），具备良好的实际部署潜力。
- **实验详实**：大量消融与对比实验，结合定量的“任务学习”和 SLR 指标，增强结论的可信度。

## 8. 不足与局限
- **模型覆盖范围有限**：主要针对 9B 规模的 IDEFICS 和 Open‑Flamingo，未涉及更大或更先进的 MLLMs，通用性有待进一步验证。
- **ICL 研究的深度盲区**：仅探讨三个因素，文本提示的敏感性、示例顺序、示例多样性、负样本策略等未作深入分析。
- **理论机制探讨不足**：对 MLLMs 内在偏差来源的解释较为初步，未触及预训练数据或模型架构层面的根源分析。
- **领域泛化未验证**：所有实验限定在图像‑文本情感分析，缺乏对视频、语音等多模态情感或更广泛情感理解任务的考察。

（完）
