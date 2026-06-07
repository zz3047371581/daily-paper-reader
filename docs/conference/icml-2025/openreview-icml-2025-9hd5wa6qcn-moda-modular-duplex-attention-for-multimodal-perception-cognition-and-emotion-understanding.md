---
title: "MODA: MOdular Duplex Attention for Multimodal Perception, Cognition, and Emotion Understanding"
title_zh: MODA：面向多模态感知、认知与情感理解的模块化双工注意力
authors: "Zhicheng Zhang, Wuyou Xia, Chenxi Zhao, Zhou Yan, Xiaoqiang Liu, Yongjie Zhu, Wenyu Qin, Pengfei Wan, Di ZHANG, Jufeng Yang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=9hd5WA6QCn"
tags: ["query:affective-ai"]
score: 8.0
evidence: 提出模块化双工注意力机制，用于多模态大模型的情感理解
tldr: 现有多模态大语言模型在注意力混合上存在缺陷，导致跨模态注意力不一致和逐层衰减，影响细粒度认知与情感理解。本文提出MODA，通过模块化双工注意力同时进行模态内精炼与模态间融合，有效缓解注意力缺陷问题。实验表明MODA在多模态情感理解等多类任务上取得性能提升，为情感智能化多模态模型提供关键注意力机制。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-9hd5wa6qcn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9hd5wa6qcn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1766, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9hd5wa6qcn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1779, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9hd5wa6qcn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9hd5wa6qcn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 286, \"height\": 264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9hd5wa6qcn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 286, \"height\": 177, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9hd5wa6qcn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9hd5wa6qcn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 850, \"height\": 204, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-9hd5wa6qcn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9hd5wa6qcn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9hd5wa6qcn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 872, \"height\": 757, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9hd5wa6qcn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 710, \"label\": \"Table\"}]"
motivation: 现有多模态大模型存在注意力缺陷障碍，即跨模态注意力不一致且逐层激活衰减，阻碍高级情感认知任务。
method: 提出模块化双工注意力（MODA），并行执行模态内特征精炼与模态间融合，引入模块化设计增强注意力交互。
result: MODA在多个多模态基准上提升表现，尤其在细粒度情感理解任务上显著优于基线方法。
conclusion: 所提注意力机制为多模态大模型注入更强的情感理解能力，推动情感智能化发展。
---

## Abstract
Multimodal large language models (MLLMs) recently showed strong capacity in integrating data among multiple modalities, empowered by generalizable attention architecture. Advanced methods predominantly focus on language-centric tuning while less exploring multimodal tokens mixed through attention, posing challenges in high-level tasks that require fine-grained cognition and emotion understanding. In this work, we identify the attention deficit disorder problem in multimodal learning, caused by inconsistent cross-modal attention and layer-by-layer decayed attention activation. To address this, we propose a novel attention mechanism, termed MOdular Duplex Attention (MODA), simultaneously conducting the inner-modal refinement and inter-modal interaction. MODA employs a correct-after-align strategy to effectively decouple modality alignment from cross-layer token mixing. In the alignment phase, tokens are mapped to duplex modality spaces based on the basis vectors, enabling the interaction between visual and language modality. Further, the correctness of attention scores is ensured through adaptive masked attention, which enhances the model's flexibility by allowing customizable masking patterns for different modalities. Extensive experiments on 21 benchmark datasets verify the effectiveness of MODA in perception, cognition, and emotion tasks.

---

## 论文详细总结（自动生成）

# MODA 论文深度总结

## 1. 核心问题与整体含义
- **核心问题**：现有多模态大语言模型（MLLMs）在需要细粒度跨模态对齐的高层认知与情感理解任务上表现不佳，其根源被作者定义为 **“注意力缺陷障碍（Attention Deficit Disorder, DDA）问题”**。
- **具体表现**：
  - 模型注意力存在 **模态偏向**：语言模态的注意力激活远强于视觉模态。
  - **逐层衰减**：跨模态注意力贡献随网络层数增加呈指数式衰减，导致深层网络无法有效融合多模态信息。
  - 直接后果：模型忽略视觉中的微表情、细粒度细节，造成情绪误判或幻觉，例如无法正确理解人物眼神、讽刺或幽默。
- **研究动机**：突破语言中心调优的局限，从注意力机制设计上解决模态不一致和表征退化，使 MLLM 具备更接近人类的感知、认知与情感理解能力。

## 2. 方法论核心
提出 **MOdular Duplex Attention (MODA)**，采用 “先对齐后校正” 的策略解耦模态对齐与跨层令牌混合。

- **双工注意力对齐 (Duplex Attention Alignment)**：
  - 包含 V‑Aligner 与 T‑Aligner，分别负责视觉、语言模态。
  - 基于各模态键值（Key）计算的 **标准化格拉姆矩阵** 提取模态空间基向量，将另一模态的令牌映射到当前模态空间，实现核化跨模态投影：\(\mathbf{K}^{\bar{m}\to m} = \mathbf{K}^{\bar{m}} \| \mathbf{G}^m \|\)。
  - 对齐后通过可学习的融合器（基于LoRA微调）将映射特征与原始特征融合，增强跨模态相似性。

- **模块化注意力掩码 (Modular Attention Mask)**：
  - 将注意力显式分解为 **自模态注意力**（\(O_\text{self}\)）与 **跨模态注意力**（\(O_\text{cross}\)），分别应用独立的掩码矩阵。
  - 引入 **伪注意力分数** 与 **衰减率** \(\beta\)，构造固定长度的注意力行 \(p_{ij} = p_{\text{base}} - (j-1)\beta\)，防止注意力矩阵坍塌并控制令牌流向。
  - 使用标准化格拉姆矩阵作为模态位置先验，指导模型自适应调整不同模态的掩码模式。

- **整体流程**：每个 Transformer 块中，视觉与文本令牌流经双工对齐器后，进行模块化掩码注意力计算，最终通过前馈网络输出，形成“内模态精炼 + 跨模态交互”的双通道处理。

## 3. 实验设计
- **数据集与基准**（共 21 个）：
  - 感知：16 个基准，涵盖通用 QA（MME, MMBench, SEED, GQA）、知识 QA（ScienceQA, MMMU）、OCR/图表 QA（MathVista, AI2D, ChartQA, OCRBench, TextVQA, DocVQA）、视觉中心 QA（MMVP, RealworldQA, CV‑Bench 2D/3D）。
  - 认知：MMRole（8 个维度：指令遵循、流畅度、连贯性、图文相关性、回答准确性、人格一致性、知识一致性、语气一致性）。
  - 情感：MVSA‑S, MVSA‑M（二分类）、TumEmo（六类基本情绪）、HFM（高层隐式情绪/讽刺检测）。
- **对比方法**：
  - 开放源 MLLM：Mini‑Gemini‑HD, LLaVA‑NeXT, Cambrian‑1 (均分别基于 8B/34B 基座模型)。
  - 专有模型：GPT‑4V, Gemini‑1.0/1.5 Pro, Claude 3 Opus, QWen‑VL‑Max。
  - 任务特化 SOTA：认知任务 MMRole‑9B；情感任务 M2CL, MULSER, CMGCN, SPFVTE。
- 基座模型：视觉编码器为 CLIP ViT‑L/14；LLM 使用 Llama‑3‑Instruct‑8B 与 Hermes2‑Yi‑34B。所有模型均使用 700K 数据训练 1 epoch，公平比较。

## 4. 资源与算力
- 文中 **未明确提及** 具体的 GPU 型号、卡数以及训练总时长。
- 可获取的训练配置信息如下：
  - 批次大小：2048
  - 优化器：AdamW，学习率 LLM 2e‑5，视觉编码器 2e‑6，warmup 比率 0.03，余弦学习率衰减。
  - 微调策略：使用 LoRA 以降低全量训练开销。

## 5. 实验数量与充分性
- **实验组数**：至少包括 4 张主结果表格（感知 16 基准、认知、情感）及消融研究 1 张表格，外加注意力分布分析、可视化定性实验等，实验规模可观。
- **消融实验** 围绕四个关键模块展开：
  - (a) 模块有效性（仅双工对齐 / 仅模块掩码 / 两者全用）；
  - (b) 对齐方式（MLP、协方差矩阵等变体）；
  - (c) 融合策略（X_a, X_p, Con 等）；
  - (d) 掩码类型（Inf, Fix, 注意力学习, [M] 掩码）。
- **公平性**：对比实验均采用相同训练数据量、批次大小与 epoch；基座模型规模完全对齐（8B 与 34B）。实验覆盖了通用、视觉、认知、情感等多元任务，并能与专有模型及领域特化模型对比，整体设计 **较为充分且客观**。

## 6. 主要结论与发现
- MODA 有效解决了注意力缺陷障碍，**消除了深层网络中的注意力衰减**，使各层保持均衡的跨模态交互。
- 在感知基准上，MODA 以相近规模显著超过 LLaVA‑NeXT、Cambrian‑1，尤其在 OCR/图表与视觉中心任务上取得最高分。
- 认知方面，MODA 超越同期开源模型，与专有模型 Claude 3 Opus 持平；经任务微调后进一步超越认知特化方法。
- 情感理解上，MODA 优于所有通用 MLLM，并在 TumEmo、HFM 等细粒度情绪识别中 **匹敌甚至超越专门的情感特化模型**。
- 可视化证明 MODA 能捕捉微表情、语境玩笑及角色性格，具备为《教父》式对话进行情绪感知与策略规划的潜力。

## 7. 优点
- **创新性显著**：首次明确定义并分析 MLLM 的注意力缺陷障碍，并提出双工对齐 + 模块掩码的解决范式。
- **设计精巧**：解耦模态对齐与令牌混合，利用格拉姆矩阵实现线性复杂度的跨模态映射，可插拔且无需改造原模型架构（LoRA）。
- **实验全面**：在感知、认知、情感三个维度、21 个基准上进行验证，包含定量对比、消融分析与定性案例，支撑充分。
- **性能提升明确**：在细粒度视觉任务和高级情感任务上取得突破，对 MLLM 走向情感智能有重要推动。

## 8. 不足与局限
- **算力细节缺失**：未报告训练时长、硬件配置及推理延迟，难以评估实际落地成本。
- **适用范围受数据与基座影响**：文中承认模型输出质量受微调数据和基座模型限制，可能产生幻觉；禁止商用。
- **理论分析局限**：注意力衰减的分析基于实验观察，虽引用了纯注意力秩塌缩理论，但未对 MODA 自身的收敛性与稳定性提供深入理论证明。
- **基线比较**：未对比近期其他高效注意力或跨模态注意力机制（如 Agent Attention 等），比较对象主要为完整 MLLM 框架，无法完全分离注意力模块本身的贡献。
- **数据集规模**：情感数据集相对较小（如 MVSA 系列），且在感知基准上距离专有模型 GPT‑4V 仍有差距，大模型潜力未完全发挥。

（完）
