---
title: Guiding Cross-Modal Representations with MLLM Priors via Preference Alignment
title_zh: 利用 MLLM 先验通过偏好对齐指导跨模态表示学习
authors: "Pengfei Zhao, Rongbo Luan, Wei Zhang, Peng Wu, Sifeng He"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=jZs26lJ0pl"
tags: ["query:affective-ai"]
score: 9.0
evidence: 利用 MLLM 先验细化视觉-语言跨模态对齐
tldr: 现有对比语言-图像预训练模型（CLIP）在跨模态检索中表现出色，但其特征空间仍存在显著的模态鸿沟。本文发现现成的多模态大语言模型（MLLM）具有内在的模态对齐能力，进而提出 MAPLE 框架，通过偏好对齐的方式将 MLLM 的细粒度对齐先验注入到嵌入学习过程中，有效缩小了图像与文本之间的表示差异。实验表明，该方法在多项跨模态任务上取得了优越的性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jzs26lj0pl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jzs26lj0pl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1421, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jzs26lj0pl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jzs26lj0pl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jzs26lj0pl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jzs26lj0pl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 523, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jzs26lj0pl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 586, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jzs26lj0pl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 938, \"height\": 1867, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jzs26lj0pl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1359, \"height\": 729, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jzs26lj0pl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1413, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jzs26lj0pl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1405, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jzs26lj0pl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1268, \"height\": 748, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jzs26lj0pl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1342, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jzs26lj0pl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jzs26lj0pl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 930, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jzs26lj0pl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1095, \"height\": 315, \"label\": \"Table\"}]"
motivation: 现有 CLIP 模型在图像和文本特征空间中仍存在明显的模态鸿沟，阻碍了跨模态对齐效果。
method: 提出 MAPLE 框架，将 MLLM 的细粒度对齐先验转化为偏好信号，通过偏好对齐优化跨模态嵌入。
result: 在多个跨模态检索和表示学习任务中，MAPLE 有效缩小了模态差距，性能优于基线方法。
conclusion: 利用 MLLM 的内在对齐先验是一种高效提升跨模态表示的方法，未来可拓展到多模态下游任务。
---

## Abstract
Despite Contrastive Language–Image Pre-training (CLIP)'s remarkable capability to retrieve content across modalities, a substantial modality gap persists in its feature space. Intriguingly, we discover that off-the-shelf MLLMs (Multimodal Large Language Models) demonstrate powerful inherent modality alignment properties. While recent MLLM-based retrievers with unified architectures partially mitigate this gap, their reliance on coarse modality alignment mechanisms fundamentally limits their potential. In this work, We introduce MAPLE (Modality-Aligned Preference Learning for Embeddings), a novel framework that leverages the fine-grained alignment priors inherent in MLLM to guide cross-modal representation learning. MAPLE formulates the learning process as reinforcement learning with two key components: (1) Automatic preference data construction using off-the-shelf MLLM, and (2) a new Relative Preference Alignment (RPA) loss, which adapts Direct Preference Optimization (DPO) to the embedding learning setting. Experimental results show that our preference-guided alignment achieves substantial gains in fine-grained cross-modal retrieval, underscoring its effectiveness in handling nuanced semantic distinctions.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
尽管对比语言‑图像预训练模型（如 CLIP）在跨模态检索上成就显著，其嵌入空间中仍存在明显的**“模态鸿沟”**（modality gap），即图像与文本特征在共享隐空间中出现分布偏移，限制了细粒度语义匹配的能力。  
作者发现，现成的**多模态大语言模型**（MLLM）即使不依赖显式嵌入，也已具备强大的内在模态对齐能力。于是，论文旨在**利用 MLLM 的细粒度对齐先验来引导跨模态表示学习**，以缩小检索模型中的模态鸿沟，并提升对细微语义差别的分辨力。

### 2. 论文提出的方法论
作者提出 **MAPLE (Modality‑Aligned Preference Learning for Embeddings)** 框架，将 MLLM 的对齐先验转化为偏好信号，并用类似直接偏好优化（DPO）的方式训练嵌入模型。核心流程如下：  
- **偏好数据构建（Pipeline）**  
  - **离线阶段**：用 DINOv2 提取图像嵌入，通过语义去重（SemDeup）去除冗余，对每张图检索 top‑K 最近邻作为困难负样本；用 MLLM 为每组图像对生成带有差异对比的文本描述，扩充负例文本池。  
  - **在线阶段**：训练时，用冻结的奖励 MLLM 对当前锚点（图像或文本）与候选集（正例+困难负例）计算对齐得分（询问“该图文是否匹配”，取“Yes/No”logit 的 softmax），得分排序后构造 **成对偏好**（pairwise，高分项优于低分项）或 **列表偏好**（listwise，整个排序列表作为整体结构）。  

- **偏好对齐损失**：将 DPO 损失定制为 **相对偏好对齐（RPA）损失**。  
  - 消除参考模型，简化为类似对比偏好优化（CPO）的形式。  
  - 将 log 概率替换为锚点与候选嵌入的缩放相似度 \( \beta (z_{\text{anchor}} \cdot z_{\text{candidate}}) \)。  
  - **成对 RPA 损失**：对每个偏好对，最大化“偏优项相似度 > 偏劣项相似度”的对数几率，并用 MLLM 打分差作为权重。  
  - **列表 RPA 损失**：遍历排序列表的每个后缀，鼓励模型将对应位置上的项排在所有后缀项的最前面，并用平均偏好边际加权。  
- **正则组合**：最终损失为 \( L = \lambda L_{\text{RPA}} + (1-\lambda) L_{\text{contrast}} \)，其中 \( L_{\text{contrast}} \) 是锚点对的标准对比损失，防止嵌入坍塌。  

### 3. 实验设计
- **任务与数据集**  
  - **通用检索**：COCO、Flickr30K（R@1 指标）。  
  - **细粒度检索**：Winoground、NaturalBench、MMVP、BiVLC（文本/图像得分，基于成对匹配判断）。  
- **Baselines 对比**  
  - CLIP 系列：CLIP ViT‑L、OpenCLIP ViT‑G、SigLIP、SigLIPv2‑2B、EVA‑CLIP 8B/18B。  
  - MLLM 检索器：E5‑V (LLaVA‑Next‑8B)、VladVA (Qwen2‑VL‑2B, LLaVA‑1.5‑7B)。  
- **MAPLE 变体**：分别以 Qwen2‑VL‑2B 和 7B 作为策略模型（主干 + LoRA 微调），以 Qwen2‑VL‑7B 作为奖励模型。  

### 4. 资源与算力
- **硬件**：32 块 NVIDIA A100 80GB GPU。  
- **训练时长**：约 32 小时（8 个 epoch）。  
- **优化策略**：LoRA（秩 32）仅作用于 LLM 层的注意力与投影层，视觉编码器和连接器冻结；flash attention、梯度检查点、bfloat16 混合精度；最大图像分辨率 384×384。  
- **批量大小**：每 GPU 96（2B 模型）或 48（7B 模型）。  

### 5. 实验数量与充分性
论文设计了 **约 8 张表 + 多幅图**，涵盖：  
- 主实验对比 12+ 个 baseline 在 6 个基准上的表现（表 1）。  
- 损失组件消融（表 2），对比纯对比、对比+偏好、纯 RPA 等 6 种组合。  
- 扩展负样本池的消融（表 3）。  
- 奖励模型规模与架构鲁棒性（表 4、5），测试 Qwen2‑VL‑2B/7B、InternVL3‑1B/2B/8B、SAIL‑VL、InternVL2.5 等 8 种奖励模型，并做跨架构策略‑奖励配对。  
- 模态鸿沟度量对比（表 6）。  
- 超参数 λ 敏感性分析（图 5）、模态鸿沟演变（图 6）、MMVP 和 BiVLC 数据集的分类别性能分解（图 7、8）。  
- 文本采样策略对比（表 8），检索结果可视化（图 9）。  

实验覆盖了**通用检索与细粒度检索的多个维度**，消融充分，比较对象包括不同架构、规模的 CLIP 和 MLLM 模型，评估指标与数据集选择具有代表性。奖励模型消融采用统一策略模型和轮次，确保了对比的公平性。整体实验设计**客观且较为完整**。

### 6. 论文的主要结论与发现
- 现成的 MLLM 拥有强大的**内在模态对齐能力**，可通过将这种先验转化为偏好信号，显著提升检索模型的细粒度分辨力。  
- MAPLE 框架在多个基准上大幅超越基线，尤其在 Winoground、NaturalBench 等需要组合推理的任务上提升显著（如 Winoground 文本得分从 42.5 → 56.0，图像得分从 20.5 → 32.7）。  
- RPA 损失中的**列表形式优于成对形式**；将 RPA 与对比正则项结合可同时保持通用检索性能。  
- MAPLE 对奖励模型的**规模和架构均具有鲁棒性**，即使使用 1 B 级别的奖励模型也能带来稳定增益。  
- 扩展负样本池是提升对比学习有效性的低成本策略。  

### 7. 优点
- **创新性**：首次将 DPO 偏好优化适配到跨模态嵌入学习，提出 RPA 损失，无需人工标注即可自动从 MLLM 提取排序信号。  
- **对齐先验的挖掘**：揭示了 MLLM 的隐式对齐能力，并用统一的 Wasserstein 距离量化模态鸿沟，提供了新的分析视角。  
- **方法灵活性**：偏好构建支持成对/列表多种形式，可搭配不同 MLLM 奖励模型，且对奖励模型的选择不敏感。  
- **工程友好**：LoRA 微调、利用困难负样本扩展有效批次、较低分辨率训练等设计使大模型训练更经济。  
- **实验扎实**：消融详尽，从损失函数、奖励模型、数据采样等多个维度验证了各组件的贡献和鲁棒性。  

### 8. 不足与局限
- **偏差风险**：模型习得的表示可能继承奖励 MLLM 的固有偏见（例如社会偏见或某些类型数据的不均衡），论文未对此做深入分析。  
- **任务局限**：仅在单轮图文检索上验证，尚未扩展到组合检索（composed retrieval）、视频‑文本等多模态对齐任务，适用性有待进一步探索。  
- **数据依赖**：训练数据来自 OpenImage 的精选子集（约 70 万样本），可能限制了在其他领域或更大规模场景下的泛化能力。  
- **计算开销**：在线构建偏好数据需调用 MLLM 进行打分，虽然论文指出可用小规模模型，但训练时频繁推理仍会带来额外耗时。  
- **超参数敏感性**：RPA 与对比损失的平衡权重 λ 对性能影响较大，需要针对任务调整，自动化选取机制尚未提供。  

（完）
