---
title: "AffectGPT: A New Dataset, Model, and Benchmark for Emotion Understanding with Multimodal Large Language Models"
title_zh: AffectGPT：面向多模态大语言模型情感理解的新数据集、模型与基准
authors: "Zheng Lian, Haoyu Chen, Lan Chen, Haiyang Sun, Licai Sun, Yong Ren, Zebang Cheng, Bin Liu, Rui Liu, Xiaojiang Peng, Jiangyan Yi, Jianhua Tao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=xmbdACI0xu"
tags: ["query:affective-ai"]
score: 10.0
evidence: 多模态大语言模型用于情感理解，提供数据集、模型和基准，直接针对多模态情感识别
tldr: 针对多模态大语言模型(MLLM)在情感理解中缺乏大规模描述性标注数据集和专用框架的问题，提出AffectGPT：构建了基于模型众包策略的MER-Caption数据集，包含密集情感描述标注；并设计用于MLLM的情感理解模型，实现从简单判别到复杂情感描述与视频理解的跃升。实验表明该模型在多项情感理解基准上达到最优，确立了MLLM情感理解新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1639, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1350, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1758, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 812, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1733, \"height\": 179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1750, \"height\": 180, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1694, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 623, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1460, \"height\": 1071, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xmbdaci0xu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1308, \"height\": 542, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1598, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 799, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 797, \"height\": 546, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 888, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 845, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 800, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 530, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 687, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1610, \"height\": 578, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1207, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1771, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1734, \"height\": 1344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xmbdaci0xu/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1722, \"height\": 581, \"label\": \"Table\"}]"
motivation: MLLM将多模态情感识别提升至情感理解层次，但缺乏大规模描述性情感数据集和专用模型框架。
method: 采用模型众包策略构建MER-Caption情感描述数据集，并设计适配MLLM的情感理解模型。
result: AffectGPT模型在多个情感理解指标上领先，验证了数据集和模型的有效性。
conclusion: 为MLLM时代的情感理解研究提供了基准数据集和强基线模型。
---

## Abstract
The emergence of multimodal large language models (MLLMs) advances multimodal emotion recognition (MER) to the next level—from naive discriminative tasks to complex emotion understanding with advanced video understanding abilities and natural language description. However, the current community suffers from a lack of large-scale datasets with intensive, descriptive emotion annotations, as well as a multimodal-centric framework to maximize the potential of MLLMs for emotion understanding. To address this, we establish a new benchmark for MLLM-based emotion understanding with a novel dataset (MER-Caption) and a new model (AffectGPT). Utilizing our model-based crowd-sourcing data collection strategy, we construct the largest descriptive emotion dataset to date (by far), featuring over 2K fine-grained emotion categories across 115K samples. We also introduce the AffectGPT model, designed with pre-fusion operations to enhance multimodal integration. Finally, we present MER-UniBench, a unified benchmark with evaluation metrics tailored for typical MER tasks and the free-form, natural language output style of MLLMs. Extensive experimental results show AffectGPT's robust performance across various MER tasks. We have released both the code and the dataset to advance research and development in emotion understanding: https://github.com/zeroQiaoba/AffectGPT.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- 多模态大语言模型（MLLM）将多模态情感识别从简单的判别式分类推向复杂的自然语言描述与理解。传统方法局限于 Ekman 六类基本情绪，无法刻画情绪的多样性、共存性与情境依赖性。
- 当前社区缺乏**大规模、密集描述性情感标注的数据集**，也缺乏**专门为 MLLM 情感理解设计的多模态融合框架**，限制了 MLLM 在情感理解上的潜力。
- 论文旨在从数据集、模型和评估基准三方面系统性地提升 MLLM 的情感理解能力，构建面向生成式情感描述的研究基础。

## 2. 论文提出的方法论

### 2.1 数据集：MER-Caption 与 MER-Caption+
- **标注策略**：采用“模型主导、人工辅助”的模型众包方式，平衡标注质量与数据集规模。
  - 利用**人类先验**进行基座模型筛选：选取 SALMONN 作为音频 LLM，Chat-UniVi 作为视频 LLM，用 GPT-3.5 融合音频、视频和文本线索生成情绪描述。
  - 对 115k 样本生成描述，构建 MER-Caption。
- **多级过滤提升质量**：
  - **低级过滤**：使用 TalkNet 检测并移除音视频说话人不匹配的样本；去除描述长度位于高斯分布两端的异常样本（易含错误）。
  - **高级过滤**：提出“模型众包”技术——训练多个情绪与情感分类器对样本进行预测，并利用多数投票获得伪标签；同时从描述中提取情绪标签，若两者不一致则视为低质量并剔除，最终得到 31k 样本的 **MER-Caption+** 数据集。
- 最终数据集包含超过 **2,932 个细粒度情绪类别**，是目前最大的多模态情绪描述数据集。

### 2.2 模型：AffectGPT
- **主流架构局限**：现有 AV-LLM 将跨模态交互完全留给 LLM，难以充分捕捉多模态情绪特征。
- **预融合操作**：在 LLM 之前引入显式的多模态融合模块，对音频编码特征 \(Z_a\) 和视频编码特征 \(Z_v\) 进行融合：
  - **Q-Former 方式**：通过可学习查询向量与拼接的 \(Z_{av}\) 做交叉注意力，保留时序信息，蒸馏多模态知识。
  - **注意力方式**：先对时序维度平均池化得到压缩特征，再通过注意力权重动态融合两个模态，计算融合特征 \(Z_f\)，计算量远小于 LLM。
- 训练时冻结音频/视频编码器和 LLM 主体，仅微调投影层、预融合分支及 LLM 的 LoRA 模块，实现高效训练。

### 2.3 评估基准：MER-UniBench
面向 MLLM 自由形式、自然语言输出特性设计三类任务及其评价指标：
- **细粒度情绪识别**（OV-MERD+）：采用基于情绪轮的分层同义词映射，评价集合级别的精确率、召回率和 \(F_s\) 宏平均。
- **基本情绪识别**（MER2023/2024, IEMOCAP, MELD）：提出“命中率”（HIT），要求真实基本标签至少出现在预测的任意情绪集合中。
- **情感分析**（CMU-MOSI, CMU-MOSEI, CH-SIMS, CH-SIMS v2）：将连续情感分数映射为正/负极性，以加权平均 F1（WAF）为主要指标，准确率为辅助指标。

## 3. 实验设计

- **训练数据**：使用 MER-Caption+（31K 样本）进行训练，同时对比通用指令数据集（MiniGPT4, VideoChat, LLaVA 等）及已有情绪描述数据集（EmoVIT, MAFW, MERR-Coarse/Fine）。
- **评估基准与数据集**：在 MER-UniBench 涵盖的所有数据集上评估，任务含细粒度、基本情绪、情感分析，模态组合包括 A、V、T、AVT 等。
- **对比方法**：涵盖主流的音频理解 MLLM（SALMONN, Qwen-Audio, SECap 等）、视频理解 MLLM（VideoChat, Chat-UniVi, mPLUG-Owl 等）和多模态 MLLM（PandaGPT, Emotion-LLaMA 等），均使用官方权重，输入对应模态内容后进行推理。
- **额外分析**：消融实验（预融合方式、过滤级别、输入模态、LLM/编码器选择、LoRA 秩、采样帧数）以及用户研究对比描述质量。

## 4. 资源与算力

- 论文明确指出实验使用 **80GB NVIDIA Tesla A100 GPU** 进行训练与推理。
- 训练设置：最大 epoch 数为 60，每个 epoch 含 5,000 次迭代，batch size 为 3，优化器为 AdamW，学习率 \(1\times10^{-5}\)。
- 未提及使用的 GPU 数量（推测为单卡或少量卡），也未提供具体的训练总时长，但作为生成式大模型训练，计算量较为可观。

## 5. 实验数量与充分性

- **实验组数极多**：
  - 主结果表 2：约 15 个对比模型 × 3 种模态组合 × 9 个数据集，给出主/辅指标。
  - 数据集对比（表 3）：8 个通用/情感描述数据集 × 9 个评估集。
  - 消融研究：过滤方式（表 4）、预融合结构（表 5）、输入模态（表 6）、LoRA 秩（表 8）、LLM/音视频编码器（图 4）、采样帧数（图 10）等。
  - 此外还有用户研究（表 7）和 LLM 提示方案的选择实验。
- **实验充分且客观**：固定了比较条件（相同模型结构仅变数据集，使用官方权重和统一提示），多维度消融验证了数据集质量、融合模块和输入模态的贡献，用户研究从人类感知角度验证了描述质量。实验覆盖了不同语言（中英文）、不同标注粒度和任务类型，公平性良好。

## 6. 论文的主要结论与发现

- **AffectGPT 显著优于现有 MLLM**：在全部三大任务上，与最佳对比模型相比平均相对提升超 9%，在多个数据集上达到 SOTA。
- **MER-Caption 是有效的关键因素**：其大规模、高质量、描述性标注弥补了当前情绪理解数据集的不足，即使在自动标注无人工校验下，仍优于人工标注数据集 MAFW。
- **预融合操作有效提升多模态融合**：将跨模态交互前置于 LLM 可增强对多模态情绪特征的捕捉，Q-Former 和注意力方式均带来增益。
- **数据集质量与数量并重**：二级过滤（低级+高级）能进一步提升数据质量，少量高质量样本胜过大而粗糙的数据集。
- 现有通用指令数据集对 MER 任务关注不足，过滤非情绪样本也无明显改善，凸显专用数据集的重要性。

## 7. 优点

- **数据集贡献突出**：提出了迄今最大规模的多模态情绪描述数据集，定义了“模型主导、人工辅助”的可靠标注范式，兼具规模与质量。
- **基准设计合理**：为 MLLM 自由文本输出量身定做了集合级、命中率等评价指标，解决了传统分类指标不适用的问题，并整合多种 MER 任务进行统一评估。
- **模型结构创新且高效**：预融合模块轻量且易于集成，冻结编码器和 LLM 主体仅微调少量参数，训练成本可控，同时有效提升了情感理解性能。
- **实验全面系统**：从模型、数据集、消融、编码器选择、用户感知等多角度深入分析，结论可信度高。代码和数据开源，利于社区发展。

## 8. 不足与局限

- **数据集仍可能存在噪声**：MER-Caption+ 虽经多级过滤，但自动标注无最终人工校验，描述准确性并非完美。未来需进一步探索后处理技术。
- **仅关注单人场景**：当前研究限定为单人视频，回避了多人对话中的情绪传递与影响（如音视频不匹配的样本被直接剔除），降低了任务复杂性，但也限制了实用范围。
- **评价中未惩罚多标错误**：基本情绪识别只要求真实标签命中，预测中额外的细粒度标签不会被判定为错误，可能高估模型区分能力；未来需对多标预测的精确性进行更严格的度量。
- **生成链路依赖闭源模型**：在描述生成阶段采用了 GPT-3.5 进行线索融合，若完全开源替代可能影响性能，数据集的可复现性和迁移性受一定制约。
- **未利用多阶段训练**：实验发现预训练其他指令数据再微调无性能提升，说明当前 MER-Caption 规模已足够，但对域外情绪数据的泛化潜力尚未充分探索。

（完）
