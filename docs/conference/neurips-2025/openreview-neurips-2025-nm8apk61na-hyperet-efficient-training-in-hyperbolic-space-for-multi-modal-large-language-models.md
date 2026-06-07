---
title: "HyperET: Efficient Training in Hyperbolic Space for Multi-modal Large Language Models"
title_zh: HyperET：多模态大语言模型在双曲空间中的高效训练
authors: "Zelin Peng, Zhengqin Xu, Qingyang Liu, Xiaokang Yang, Wei Shen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NM8Apk61NA"
tags: ["query:affective-ai"]
score: 9.0
evidence: 利用双曲空间在任意粒度级别对齐视觉与文本模态
tldr: 多模态大语言模型因视觉编码器缺乏多粒度语言对齐导致训练效率低下。本文提出HyperET，首次利用双曲空间建模层级结构，在任意粒度上桥接视觉与文本模态，无需增加计算量即可实现高效对齐。实验证明，该方法大幅减少训练资源，同时维持甚至提升跨模态任务性能。此项工作为高效多模态对齐提供了理论新颖且实用的解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nm8apk61na/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nm8apk61na/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 721, \"height\": 434, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nm8apk61na/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nm8apk61na/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 722, \"height\": 692, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nm8apk61na/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nm8apk61na/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 720, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nm8apk61na/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 718, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nm8apk61na/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 818, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nm8apk61na/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1458, \"height\": 225, \"label\": \"Table\"}]"
motivation: 多模态大模型训练资源消耗巨大，视觉编码器与语言的多粒度对齐是效率瓶颈。
method: 提出HyperET，利用双曲空间的层级特性在任意粒度上对齐视觉与文本，实现高效训练。
result: 在多个基准上验证，HyperET提升训练效率且保持对齐性能。
conclusion: 双曲空间为多模态多粒度对齐提供了有效途径，显著降低计算资源需求。
---

## Abstract
Multi-modal large language models (MLLMs) have emerged as a transformative approach for aligning visual and textual understanding. They typically require extremely high computational resources (e.g., thousands of GPUs) for training to achieve cross-modal alignment at multi-granularity levels. We argue that a key source of this inefficiency lies in the vision encoders they widely equip with, e.g., CLIP and SAM, which lack the alignment with language at multi-granularity levels. To address this issue, in this paper, we leverage hyperbolic space, which inherently models hierarchical levels and thus provides a principled framework for bridging the granularity gap between visual and textual modalities at an arbitrary granularity level. Concretely, we propose an efficient training paradigm for MLLMs, dubbed as \blg, which can optimize visual representations to align with their textual counterparts at an arbitrary granularity level through dynamic hyperbolic radius adjustment in hyperbolic space. \alg employs learnable matrices with M\"{o}bius multiplication operations, implemented via three effective configurations: diagonal scaling matrices, block-diagonal matrices, and banded matrices, providing a flexible yet efficient parametrization strategy. Comprehensive experiments across multiple MLLM benchmarks demonstrate that \alg consistently improves both existing pre-training and fine-tuning MLLMs clearly with less than 1\% additional parameters. Code is available at \url{https://github.com/godlin-sjtu/HyperET}.

---

## 论文详细总结（自动生成）

# HyperET 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）
- 多模态大语言模型（MLLMs）如 LLaVA、InternVL 等，虽然性能强大，但训练需要极其高昂的算力（如 640 块 GPU），这对多数研究者不友好，可持续性差。
- 本文提出，训练低效的核心原因在于常用的视觉编码器（如 CLIP、SAM）**仅在单一粒度层级上与语言对齐**（例如图像级或对象级），难以应对需要多粒度对齐的下游任务。
- 双曲空间因天然能够建模数据的层级结构，其**双曲半径**（与原点之间的距离）可直接量化表示粒度的粗细：小半径对应低层特征，大半径对应高层语义。
- 论文的整体含义是：通过在双曲空间中动态调整视觉表征的双曲半径，可以在**任意粒度**上桥接视觉与文本的鸿沟，从而在几乎不增加参数量的情况下大幅提升训练效率和跨模态对齐效果。

## 2. 论文提出的方法论
**核心思想**：利用双曲空间中的 Möbius 运算和可学习的缩放矩阵，对视觉表征的“双曲半径”进行连续、高效的调整，使视觉特征能自动匹配文本所要求的粒度量级。

**关键技术细节**：
- 将预训练的视觉权重  \(W_0\) （欧氏空间）通过指数映射投影至双曲空间 \(D^n_c\) 。
- 在双曲空间中，通过一个**可学习的缩放矩阵**  \(W_s\)  与预训练权重进行 Möbius 矩阵乘法  \(\otimes_c\) ，精确控制双曲半径的缩放，再经对数映射回欧氏空间。
- 缩放矩阵  \(W_s\)  设计了三种参数高效形式：
  - **对角阵**（仅对角元素可学习，最轻量）
  - **块对角阵**（引入块内交互）
  - **带状阵**（允许对角线附近带宽内的元素可学习）
- 亦可扩展为**全矩阵**，进一步增强灵活性。
- 该模块被命名为 **HRA（Hyperbolic Radius Adjustment）**，可即插即用地插入注意力层，参数增量通常少于总可训练参数的 1%。

**理论依据**：
- 定理 1：双曲半径的调整可通过标量的 Möbius 标量乘法实现。
- 定理 2：灵活的半径缩放可通过矩阵形式的 Möbius 矩阵乘法实现，从而支持任意形式的半径调控。

## 3. 实验设计
实验覆盖两种典型的 MLLM 训练范式：

### 微调场景
- **任务与数据集**：ScienceQA（科学问答，涵盖自然、社会、语言等子域）。
- **基准对比**：LaVIN、MemVP 等参数高效微调方法，使用 LLaMA-7B/13B 作为语言模型，CLIP ViT‑L/14 作为视觉编码器。

### 预训练场景
- **基准模型**：LLaVA‑1.5、LLaVA‑Next。
- **下游评估**：**12 个**标准 MLLM 基准，包括 VQAv2、GQA、VisWiz、ScienceQA‑IMG、TextVQA、POPE、MME、MMBench、SEED‑Bench、LLaVA‑Bench 等，涵盖 VQA、幻觉检测、基准综合测试等。

### 消融与分析实验
- 缩放矩阵的灵活性对比（对角 vs 块对角 vs 带状 vs 全矩阵）。
- 欧氏空间与双曲空间的对比（控制同等额外参数量）。
- Möbius 矩阵乘法的必要性（与标准矩阵乘法的比较）。
- 与其他双曲训练方法（MERU）的比较。
- 在不同视觉编码器（SAM、DINOv2）上的表现。
- 在非 Transformer 架构（Mamba‑based Cobra）上的验证。

## 4. 资源与算力
- 微调实验：明确使用**最多 8 张 NVIDIA H800 GPU**。
- 预训练实验：文中仅说明遵从 LLaVA‑1.5 的实验设置，**未披露具体的 GPU 数量、单次训练时长或总 GPU 时**，这一点在算力透明度上有所欠缺。

## 5. 实验数量与充分性
- 整体实验数量丰富，包含约 **15+ 个不同配置/组合**，覆盖微调和预训练两大类、多个基准、多种语言模型尺寸、多种视觉编码器以及非 Transformer 架构。
- 消融设计**严格且公平**：通过保持相同额外参数量、仅切换空间（欧氏 vs 双曲）或操作（标准乘法 vs Möbius 乘法），有效分离了“参数增加”与“空间几何”的贡献。
- 实验在多个维度上验证了方法的通用性和鲁棒性，达到了较充分的客观性要求。

## 6. 论文的主要结论与发现
- 双曲半径的灵活调整能显著缓解视觉编码器与语言模型之间的多粒度对齐鸿沟，从而**提升 MLLM 的跨模态理解和抗幻觉能力**（如 POPE 指标明显上升）。
- HyperET 在微调和预训练上均能带来**一致且显著**的性能提升，且引入的额外参数量**少于 1%**，展示了极高的参数效率。
- 训练后视觉表征的双曲半径确实发生了符合任务需求的变化，验证了模型对多粒度信息的自适应能力。
- 双曲空间（而非单纯的参数增加）是实现这一增益的核心因素，Möbius 乘法也是不可或缺的操作。

## 7. 优点（方法或实验亮点）
- **理论+实践的紧密结合**：从双曲几何的天然层级属性出发，推导出简洁有效的半径调整范式，并用定理证明其可行性。
- **极致的参数效率**：在几乎所有实验中，仅增加不到 1% 的可训练参数，却能带来媲美甚至超越模型规模升级的性能。
- **即插即用的模块化设计**：HRA 可无缝嵌入主流微调方法（如 LoRA），无需改动原有架构。
- **实验设计严谨**：通过多组对照实验（欧氏空间、相同参数量、Möbius 消融）强有力地证明了所提方法的独特贡献。
- **跨架构、跨编码器的广泛验证**：涵盖 Transformer 和 Mamba 架构，覆盖 CLIP、SAM、DINOv2 等编码器，增强了结论的普遍性。

## 8. 不足与局限
- **算力信息不完整**：预训练场景未交代具体 GPU 数量和训练时长，难以精确评估新增模块的实际计算开销。
- **视觉编码器覆盖尚有限**：在预训练实验中仅使用 CLIP，并未在更大规模的 MLLM 或更先进的视觉编码器（如 SigLIP、InternViT）上进行验证。
- **任务粒度量化不足**：虽提出“双曲半径”可表征粒度，但未给出任务粒度的定量定义或标注，对“任意粒度对齐”的验证偏间接。
- **缺乏与大规模训练的直接效率对比**：文中未给出如“训练步骤减少 X%”或“达到相同性能所需算力降低多少”的量化效率收益。
- **矩阵形式可能带来额外的推理延迟**：全矩阵  \(W_s\)  在推理时引入的额外计算未被分析，实际部署的轻量性还需进一步测试。
- **安全性与社会影响**：文中未讨论方法的潜在偏见或安全风险，例如在幻觉减少方面的局限性。

（完）
