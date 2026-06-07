---
title: Learning a Cross-Modal Schrödinger Bridge for Visual Domain Generalization
title_zh: 学习跨模态薛定谔桥实现视觉域泛化
authors: "Hao Zheng, Jingjun Yi, Qi Bi, Huimin Huang, Haolan Zhan, Yawen Huang, Yuexiang Li, Xian Wu, Yefeng Zheng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=13BJ5FYG8E"
tags: ["query:affective-ai"]
score: 7.0
evidence: 通过薛定谔桥进行跨模态对齐，用于视觉-语言域泛化
tldr: 针对视觉域泛化中静态文本对齐不足以应对域差异的问题，提出SBGen方法，利用薛定谔桥模拟跨模态语义随机演化，增强模型对未见域的泛化能力。实验表明该方法在多个域泛化任务中取得了先进性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-13bj5fyg8e/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1152, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13bj5fyg8e/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13bj5fyg8e/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13bj5fyg8e/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 803, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13bj5fyg8e/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1234, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-13bj5fyg8e/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 1361, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 810, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 679, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 924, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 556, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 492, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 869, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 553, \"height\": 110, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 669, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-13bj5fyg8e/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 529, \"height\": 253, \"label\": \"Table\"}]"
motivation: 视觉域泛化中静态文本锚点对齐难以应对域间巨大分布差异。
method: 提出SBGen，通过薛定谔桥显式建模随机语义演化，实现跨域对齐。
result: SBGen在多个域泛化基准上显著提升鲁棒性。
conclusion: 该方法为跨模态对齐提供新的概率模型视角，有效应对域迁移。
---

## Abstract
Domain generalization aims to train models that perform robustly on unseen target domains without access to target data. 
The realm of vision-language foundation model has opened a new venue owing to its inherent out-of-distribution generalization capability.
However, the static alignment to class-level textual anchors remains insufficient to handle the dramatic distribution discrepancy from diverse domain-specific visual features.
In this work, we propose a novel cross-domain Schrödinger Bridge (SB) method, namely SBGen, to handle this challenge, which explicitly formulates the stochastic semantic evolution, to gain better generalization to unseen domains.
Technically, the proposed \texttt{SBGen} consists of three key components: (1) \emph{text-guided domain-aware feature selection} to isolate semantically aligned image tokens; (2) \emph{stochastic cross-domain evolution} to simulate the SB dynamics via a learnable time-conditioned drift; and (3) \emph{stochastic domain-agnostic interpolation} to construct semantically grounded feature trajectories. 
Empirically, \texttt{SBGen} achieves state-of-the-art performance on domain generalization in both classification and segmentation. This work highlights the importance of modeling domain shifts as structured stochastic processes grounded in semantic alignment.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：视觉域泛化（Domain Generalization，DG）旨在从多个源域训练出对未见目标域鲁棒的模型。现有基于视觉-语言基础模型（VLM）的方法通常使用**静态对齐**策略，即强制图像特征与类别级文本锚点进行直接相似性匹配。
- **整体含义**：论文指出，这种静态对齐不足以应对域间剧烈的分布差异和虚假关联，因此提出将跨模态对齐建模为**随机语义演化过程**，通过**跨模态薛定谔桥（Schrödinger Bridge，SB）** 模拟从域特异视觉特征到域无关文本语义的随机动态，从而获得更好的泛化能力。

## 2. 论文提出的方法论
- **核心思想**：将视觉-语言对齐构造成一个受控的随机过程，在最小化与先验偏差的约束下，让域特异视觉特征“演化”到域无关的文本语义锚点。
- **关键技术细节**：
  1. **文本引导的域感知特征选择**（Text-guided Domain-aware Feature Selection）  
     - 利用图像编码器提取视觉特征 $F$，文本编码器提取类别查询 $q_c$。  
     - 计算每个空间位置特征与类别嵌入的余弦相似度，选取 **Top‑k** 语义对齐的最优图像令牌作为初始状态 $z_0$，过滤域噪声。
  2. **随机跨域演化**（Stochastic Cross-Domain Evolution）  
     - 定义时间连续随机过程 $z_t$，满足随机微分方程（SDE）:  
       $dz_t = f_\theta(z_t, t) dt + \sqrt{2\varepsilon} dW_t$，其中 $f_\theta$ 是可学习漂移函数，$\varepsilon$ 为扩散系数，$W_t$ 为标准布朗运动。  
     - 漂移由 MLP 参数化，并加入**时间嵌入** $\gamma(t)$ 和**类别嵌入** $q_c$，实现语义和时间控制。
  3. **随机域无关插值**（Stochastic Domain-Agnostic Interpolation）  
     - 使用欧拉‑丸山离散化数值模拟 SDE，生成从 $z_0$ 到 $z_T$ 的演化轨迹。  
     - 将终态 $z_T$ 写回原始视觉特征图，对齐后的特征与类别查询一起送入解码器完成预测。
  4. **优化目标**：  
     $\min_\theta \mathbb{E}[\mathcal{L}_{\text{sup}} + \lambda \cdot \text{KL}(Q_\theta \| P)]$，其中 $\mathcal{L}_{\text{sup}}$ 为任务监督损失，KL 散度近似为漂移项正则化与终点对齐损失之和。
- **算法流程**：论文提供了伪代码（Algorithm 1），包括特征选择、SDE 模拟、损失计算与参数更新。

## 3. 实验设计
- **数据集与场景**：
  - **分类任务**：PACS, VLCS, OfficeHome, TerraIncognita, DomainNet。
  - **语义分割任务**：GTA5→{Cityscapes, BDD‑100K, Mapillary} 以及 Cityscapes→{BDD‑100K, Mapillary}，共 19 个共享类别。
- **基准设置**：采用留一域交叉验证（leave-one-domain-out），以**分类准确率**和 **mIoU** 为评价指标。
- **对比方法**：
  - 分类：SWAD, CLIP, SMA, DUPRG, CoOp, MIRO, SEDGE, DPL, CLIPOOD, Promptstyler, KAdaptation, GESTUR, DPR, CLIPCEIL++ 等最新 VLM 域泛化方法，以及若干 ImageNet 预训练方法（DANN, Fish 等）。
  - 分割：基于 ResNet 的方法（ISW, GTR, SHADE, WildNet 等）、基于 Mask2Former 的方法（HGFormer, CMFormer）和基于 VFM/VLM 的方法（REIN, SET, FADA, tqdm, MGRNet 等）。

## 4. 资源与算力
- 论文在**计算成本分析**（Table 8）中明确指出，与 baseline 相比，SBGen 的训练时间为 **79.2 GPU 小时**（使用 **单个 A100 GPU**），参数量 **790.17M**，模型大小 **5.61GB**。  
- 文中未提及多 GPU 并行训练或 GPU 显存等更细粒度信息。

## 5. 实验数量与充分性
- **实验覆盖面广**：包含 5 个分类数据集和 2 个分割源域‑目标域设置的全面对比，表格多达数十张。
- **消融研究充分**：
  - 各组件消融（DFS, SCE, SDI）。
  - 时间步 $T$、特征选择比率 $K$、超参数 $\lambda$ 的敏感度分析。
  - 不同最优传输求解方法（CFM, Sinkhorn）比较。
  - 不同 VLM 骨干网络（DINOv2, CLIP, EVA02）的泛化测试。
  - 静态对齐 vs 随机演化对比。
  - 还提供了 t‑SNE 可视化、分割结果定性图以及理论泛化误差分析。
- 实验设计遵循领域标准协议，对比的 baseline 方法均为当时最优，**客观且公平**。

## 6. 论文的主要结论与发现
- SBGen 在几乎所有数据集和设定下均取得 **state‑of‑the‑art** 性能，在 5 个分类数据集的平均准确率上比第二名高 **1.3%**，在分割任务上 mIoU 也有显著提升。
- 将域迁移建模为**结构化随机过程**比静态对齐更能捕捉语义演化，有效缓解域间差异。
- 理论分析证明，基于 SB 的对齐在泛化误差上界上**比确定性基线更紧**，支撑了方法的优越性。

## 7. 优点
- **原创性**：首次将薛定谔桥引入视觉‑语言域泛化，把对齐过程建模为随机动态，视角新颖。
- **理论支撑**：给出了完整的泛化误差界推导，说明方法与理论的一致性。
- **方法优雅**：三阶段流水线（选择‑演化‑插值）可微分、端到端训练，且与现有 VLM 即插即用。
- **实验充分**：涵盖分类和分割两大任务、多种骨干网络、详尽的消融和敏感度分析，结果可靠。
- **可视化分析**：通过 t‑SNE 和分割结果图直观展示域泛化能力的提升。

## 8. 不足与局限
- **计算开销略增**：虽然额外耗时可控，但需要对每批样本进行多步 SDE 模拟，时间复杂度高于直接余弦匹配。
- **实验数据集受限**：仅在标准的自然图像域泛化基准上验证，未涉及医疗影像、遥感等更具挑战的领域，潜在的数据偏差风险未知。
- **超参数依赖**：时间步 $T$、特征选择比率 $K$ 等对性能有一定敏感，最佳设置可能随任务变化，需要额外调参。
- **未讨论负社会影响**：论文虽声称无负面社会影响，但对域泛化在安全关键应用中可能的失效模式缺乏深入讨论。
- **生成随机性依赖**：SDE 采样引入随机性，推理阶段的稳定性与确定性需求之间的矛盾未深入探讨。

（完）
