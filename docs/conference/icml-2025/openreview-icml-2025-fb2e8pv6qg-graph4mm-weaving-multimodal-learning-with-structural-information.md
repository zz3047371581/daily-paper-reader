---
title: "Graph4MM: Weaving Multimodal Learning with Structural Information"
title_zh: "Graph4MM: 编织多模态学习中的结构信息"
authors: "Xuying Ning, Dongqi Fu, Tianxin Wei, Wujiang Xu, Jingrui He"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=FB2e8PV6qg"
tags: ["query:affective-ai"]
score: 6.0
evidence: 利用图结构整合模态内与模态间关系，实现多模态融合
tldr: 真实多模态数据存在复杂结构关系，传统图文对模型难以捕捉多跳邻居依赖。Graph4MM提出用图建模模态内与模态间关联，设计能区分多跳邻居的结构信息融合方法，将其注入基础模型。该方法在多个多模态任务上验证了结构化信息对增强跨模态表示的有效性，为视觉语言融合提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fb2e8pv6qg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 797, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fb2e8pv6qg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 713, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fb2e8pv6qg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1729, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fb2e8pv6qg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1267, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fb2e8pv6qg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1169, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fb2e8pv6qg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1117, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fb2e8pv6qg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1193, \"height\": 454, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 969, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 991, \"height\": 769, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1096, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 814, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1133, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1184, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fb2e8pv6qg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1340, \"height\": 304, \"label\": \"Table\"}]"
motivation: 现有多模态学习忽略多跳邻居关系，将图视为独立模态，无法整体建模结构信息。
method: 提出Graph4MM框架，利用图定义多模态实体间的结构关系，设计多跳信息聚合与模态融合策略。
result: 在多个多模态理解任务上，结构信息的融入显著提升性能。
conclusion: 图结构为多模态学习提供了有效的先验，有助于构建更全面的跨模态理解。
---

## Abstract
Real-world multimodal data usually exhibit complex structural relationships beyond traditional one-to-one mappings like image-caption pairs. Entities across modalities interact in intricate ways, with images and text forming diverse interconnections through contextual dependencies and co-references. Graphs provide powerful structural information for modeling intra-modal and inter-modal relationships. However, previous works fail to distinguish multi-hop neighbors and treat the graph as a standalone modality, which fragments the overall understanding. This limitation presents two key challenges in multimodal learning: (1) integrating structural information from multi-hop neighbors into foundational models, and (2) fusing modality-specific information in a principled manner. To address these challenges, we revisit the role of graphs in multimodal learning within the era of foundation models and propose Graph4MM, a graph-based multimodal learning framework. To be specific, we introduce Hop-Diffused Attention, which integrates multi-hop structural information into self-attention through causal masking and hop diffusion. Furthermore, we design MM-QFormer, a multi-mapping querying transformer for cross-modal fusion. Through theoretical and empirical analysis, we show that leveraging structures to integrate both intra- and inter-modal interactions improves multimodal understanding beyond treating them as a standalone modality. Experiments on both generative and discriminative tasks show that Graph4MM outperforms larger VLMs, LLMs, and multimodal graph baselines, achieving a 6.93% average improvement.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
这篇论文旨在解决**真实多模态数据中复杂结构关系建模不足**的问题。传统模型多局限于处理图像-文本等一对一映射，而忽略了多实体、多跳间的复杂上下文依赖与共指关系。虽然图能提供强大的结构信息表达能力，但现有方法要么无法区分多跳邻居的重要性，要么简单将图视为独立模态拼接，导致语义碎片化。作者提出 **Graph4MM** 框架，重新审视图在基础模型时代的作用：不再孤立对待图，而是利用图的结构关系引导模态内与模态间融合，从而获得更完整的跨模态理解。

### 2. 论文提出的方法论
Graph4MM 的核心是通过图结构指导多模态数据的选择与融合，它包含三大关键技术：

- **多模态图建模**
  - 将每个数据实体建模为节点，包含可选文本属性与可选图像属性。
  - 边关系包含文本-文本、图像-图像、文本-图像三种，用来反映文档结构、共购等真实场景关联。

- **Hop-Diffused Attention**
  - 在自注意力中，通过 **因果掩码** 保证每个节点仅能在有边连接的邻居上进行注意力计算。
  - 随后利用 **扩散机制** 在注意力矩阵上运行指数衰减的多步加权求和（类似 Personalized PageRank），实现多跳邻居信息的软性聚合。
  - 理论上证明该方式比堆叠 GAT 层更好地避免过平滑（Proposition 3.1），且不会丢失注意力矩阵的有效性。

- **MM-QFormer**
  - 采用可学习的 Query Tokens，与文本嵌入拼接后进入共享自注意力层，实现文本条件下的查询表示。
  - 再通过交叉注意力从Hop-Diffused后的视觉嵌入中有选择地提取视觉特征。
  - 最终输出多模态令牌，送入冻结的大语言模型（如OPT、LLaMA）完成生成或分类。

文中也提供了一种轻量级替代方案 **Hop-Aware Attention**，仅通过将可学习的跳数嵌入加到节点表示上来注入结构信息，以降低计算复杂度。

### 3. 实验设计
- **数据集**
  - 生成式任务：**WikiWeb2M**（网页级多模态数据，任务为基于页面内容和邻居信息生成缺失的节首句）。
  - 判别式任务：**Ele-Fashion**（电子商务产品分类，利用节点文本与图像以及共购关系进行零样本分类）。
  - 附录中还补充了 **Amazon‑Sports** 上的链接预测实验。

- **对比基线**
  - 仅用节点文本或子图文本的 **PLM**（OPT‑125M、LLaMA‑1B）。
  - **VLM**（BLIP2‑OPT‑2.7B，Qwen2‑VL‑7B‑Instruct，推理时不微调）。
  - **MMGL** 的多个变体（Node’s T&I，Subgraph’s T&I，以及额外用GCN建模图的版本）。

- **评价指标**
  - 生成任务：BLEU‑4、ROUGE‑L、CIDEr。
  - 判别任务：ROUGE‑L、准确率、召回率、精确率。

### 4. 资源与算力
- 所有实验在 **2 块 NVIDIA A100** 或 **2 块 NVIDIA Ada A6000** GPU 上进行。
- 生成任务中 OPT‑125M 训练 50 个 epoch，LLaMA‑1B 训练 3 个 epoch；判别任务上 OPT‑125M 训练 5 个 epoch。
- 使用了参数高效微调（Prefix‑Tuning 用于 OPT‑125M，LoRA 用于 LLaMA‑1B），视觉编码器为CLIP，批次大小较小（per device 2），但使用了16步梯度累积以稳定训练。
- 每张图像被压缩为 4 个多模态令牌，注意力扩散步数设为 2，MM‑QFormer 块数为1，这些配置使得整体算力需求可控。

### 5. 实验数量与充分性
论文进行了相当充分的实验验证：
- 主结果在两个不同规模的语言模型主干（OPT‑125M，LLaMA‑1B）上对比了 PLM、VLM、MMGL 多种变体。
- 对 **Hop‑Diffused Attention** 和 **Hop‑Aware Attention** 进行了详尽的消融实验（移除文本侧结构信息、移除视觉侧结构信息、混合使用两种策略）。
- 讨论了 **图作为独立模态** 是否有效，比较了 GCN 嵌入、全局图令牌、节点令牌等方案。
- 进行了 **图密度影响**、**随机种子鲁棒性**、**不同未见过类数量** 等额外实验。
- 在附录中还补充了链接预测的额外任务和 Dirichlet 能量的仿真实验。
  
对比公平性方面：PLM、MMGL 与本文方法均使用相同的PEFT配置、相同的最大输入长度、同一视觉编码器，基线覆盖了从无结构到有图的代表性方法，总体较为客观。

### 6. 论文的主要结论与发现
- **利用图结构引导多模态交互** 比将图作为独立模态注入更有效，直接叠加 GCN 嵌入反而可能因语义不对齐而损害性能。
- **Hop‑Diffused Attention** 可以有效利用多跳邻居结构，抑制过平滑，在生成与判别任务上持续提升基础模型的性能。
- **MM‑QFormer** 通过可学习查询令牌的交叉注意力能更好地融合图文信息。
- 在 WikiWeb2M 和 Ele‑Fashion 上，Graph4MM 全面超过更大规模的 VLM、LLM 以及 MMGL，平均提升 6.93%。

### 7. 优点
- **创新的结构建模思路**：将图视为含结构先验的“上下文选择器”而非额外模态，规避了与预训练模型语义空间不匹配的问题。
- **理论分析扎实**：对注意力的数学性质、与GAT的过平滑对比、图嵌入与预训练嵌入的信息差距进行了理论推导。
- **轻量级替代方案**：Hop‑Aware Attention 在显著降低计算开销的同时仍保持较好的性能，实用价值高。
- **任务覆盖广**：包含生成、零样本分类、链接预测三种任务，展示方法对不同面向的适配性。
- **实验对比公平、消融细致**：严格控制PEFT策略、输入长度等关键变量，消融实验清楚揭示了结构先验在视觉侧的更大作用。

### 8. 不足与局限
- **数据与领域有限**：主要在两份特定数据集上验证，尚未覆盖对话、视频等多模态图场景，不同领域上的通用性有待进一步检验。
- **图结构依赖人工定义**：图中边的定义（如节‑子节、共购）需要领域专家预先构建，对缺乏现成结构数据的任务适应性弱。
- **视觉邻居数量较少**：WikiWeb2M 仅取 4 个视觉邻居，对于富图环境可能未充分发掘视觉多跳上下文。
- **未与更先进的多图文本融合范式对比**：未涉及基于图提示或图‑文本联合预训练的最新范式，进一步对齐能力未被探索。
- **轻量方案跳数嵌入固定共享**：所有同跳邻居共享同一嵌入，可能忽略同一跳数内邻居的重要性差异。
- **资源需求细节不够完整**：未报告完整训练时长，大规模LLaMA‑1B训练成本缺乏量化说明，不利复现。

（完）
