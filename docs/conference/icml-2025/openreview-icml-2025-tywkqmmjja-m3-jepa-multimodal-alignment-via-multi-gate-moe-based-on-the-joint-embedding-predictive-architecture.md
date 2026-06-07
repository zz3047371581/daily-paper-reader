---
title: "M3-JEPA: Multimodal Alignment via Multi-gate MoE based on the Joint-Embedding Predictive Architecture"
title_zh: M3-JEPA：基于联合嵌入预测架构的多门控混合专家多模态对齐
authors: "Hongyang Lei, Xiaolong Cheng, Qi Qin, Dan Wang, Huazhen Huang, Qingqing Gu, Yetao Wu, Luo Ji"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tYwKQMMjJA"
tags: ["query:affective-ai"]
score: 8.0
evidence: 利用JEPA与多门控混合专家在潜在空间进行跨模态对齐
tldr: 当前多模态学习主要在原始token空间优化，易导致模态坍缩。M3-JEPA引入联合嵌入预测架构（JEPA），将输入嵌入通过多门控混合专家（MMoE）预测器转换到输出嵌入空间，在潜在空间进行跨模态对齐。该方法能解耦模态特定与共享信息，实现信息论最优。实验证明该框架在多个下游任务上取得优越性能，为多模态表示对齐提供了新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tywkqmmjja/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 820, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tywkqmmjja/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 848, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tywkqmmjja/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 835, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tywkqmmjja/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 763, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tywkqmmjja/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 693, \"height\": 467, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1692, \"height\": 827, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1591, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 877, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 808, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 810, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 795, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 477, \"height\": 131, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 856, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tywkqmmjja/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1053, \"height\": 525, \"label\": \"Table\"}]"
motivation: 现有token空间优化容易导致模态坍缩，需要更有效的跨模态对齐方法。
method: 采用JEPA架构，使用MMoE作为预测器，将输入嵌入映射到输出嵌入空间，在潜在空间对齐模态。
result: 在跨模态检索、视觉问答等任务上，对齐效果与性能均取得显著提升。
conclusion: 潜在空间对齐方法有效缓解模态坍缩，为多模态表示学习提供信息论保障。
---

## Abstract
Current multimodal learning strategies primarily optimize in the original token space. Such a framework is easy to incorporate with the backbone of pretrained language model, but might result in modality collapse. To alleviate such issues, we leverage the Joint-Embedding Predictive Architecture (JEPA) on the multimodal tasks, which converts the input embedding into the output embedding space by a predictor and then conducts the cross-modal alignment on the latent space. We implement this predictor by a Multi-Gate Mixture of Experts (MMoE) and name the framework as M3-JEPA, accordingly. The gating function disentangles the modality-specific and shared information and derives information-theoretic optimality. The framework is implemented with both contrastive and regularization loss, and solved by alternative gradient descent (AGD) between different multimodal tasks. By thoroughly designed experiments, we show that M3-JEPA can obtain state-of-the-art performance on different modalities and tasks, generalize to unseen datasets and domains, and is computationally efficient in both training and inference. Our observation suggests that M3-JEPA might become a new basis to self-supervised learning in the open world.

---

## 论文详细总结（自动生成）

好的，以下是根据提供的论文内容生成的结构化中文总结。

## 1. 研究核心与背景
- **核心问题**：当前主流多模态学习策略（如基于大语言模型的方法）主要在原始 token 空间优化跨模态对齐，虽易于整合预训练模型，但容易导致**模态坍缩**（modality collapse），即由于梯度冲突、信息冗余或语义歧义导致模型无法有效捕捉跨模态的核心关联。
- **研究动机**：受人类多感官感知的启发，作者提出在**潜在空间（latent space）** 而非 token 空间进行跨模态对齐，以过滤不相关或误导性的输入特征，从而缓解模态坍缩问题，提升多模态学习的泛化性与效率。

## 2. 方法论核心
- **整体思想**：基于联合嵌入预测架构（JEPA），构建一个**任意模态到任意模态（any-to-any）** 的对齐框架 `M3-JEPA`。将输入信号通过预测器映射到输出信号的嵌入空间，并在该潜在空间进行对齐。
- **关键技术细节**：
  - **预测器设计**：采用**多门控混合专家（Multi-Gate MoE, MMoE）** 结构作为跨模态连接器。该预测器将输入嵌入（如文本、图像）转换为输出嵌入空间的表示。
  - **信息解耦**：门控函数通过 `softmax(g · [e_x ⊕ e_m])` 的机制，自动分离**模态特定信息**（由专家和各模态专属嵌入 `e_m` 处理）和**模态共享信息**（由共享投影矩阵 `g` 在公共子空间提取）。
  - **双门控输出**：MMoE 并行生成两个输出，分别用于计算**对比损失**（最大化互信息，分离负样本）和**正则化损失**（L2 距离，最小化条件熵），两者线性组合作为总能量函数：`L = α L_reg + (1-α) L_cl`。
  - **优化策略**：采用**交替梯度下降（AGD）**，在不同方向的多模态任务间轮流执行前向和反向传播，以解耦梯度更新，缓解跨任务梯度冲突。
- **理论支撑**：从信息论角度证明，该框架实质上是**最大化输入输出间的互信息 `I(x;y)` 并最小化条件熵 `H(y|x)+H(x|y)`**，并推导出当损失权重 `α=0.5` 时，系统达到信息耦合最优（等价于自由能最小化）。

## 3. 实验设计
- **数据集与场景覆盖**：
  - **图像-文本检索**：COCO、Flickr30K。
  - **音频-文本检索**：在 WavText5K、Freesound 等数据集上训练，在 Clotho、Audiocaps 上实施零样本评估。
  - **图像分类**：ImageNet-1K（将分类标签视为一种模态）。
  - **多模态理解**：视觉问答任务，使用 VQAv2 和 NLVR-2，此时输入为图文拼接。
- **对比基准**：涵盖了多数同类主流方法，包括：
  - 轻量化模型：TinyCLIP、MobileCLIP。
  - 双编码器模型：CLIP、ALIGN、Florence、BEiT-3。
  - 融合编码器模型：UNITER、OSCAR、VinVL。
  - 混合架构：ALBEF、BLIP、BLIP-2。
  - 音频任务：对比 AVFIC、ImageBind、VALOR、LanguageBind。
  - 分类/VQA 任务：对比 CLIP-ViT、DinoV2、SimVLM、Flamingo 等。

## 4. 资源与算力
- 论文**未明确提及**具体的 GPU 型号、数量或训练总时长。
- 文中强调了模型的计算效率：仅需训练**1.4亿参数**（总参数量约 85 亿，但大部分预训练编码器冻结），因此训练成本较低。推理时支持模态预计算与在线缓存，平均检索时间仅为 0.02 秒（CLIP 为 0.16 秒），表现出显著的轻量化部署优势。

## 5. 实验充分性与客观性评估
- **实验数量充裕**：论文至少进行了 **4 大类主任务**（视觉检索、音频检索、视觉分类、视觉问答）的评估，并在每个任务上对比了多个强基线。此外，还包含了**丰富的分析与消融实验**：
  - 组件消融：移除 MoE（改用 MLP）、移除 AGD（采用联合优化）、冻结/部分微调/全微调编码器对比。
  - 敏感性分析：探讨损失权重 α 的影响（验证了 α=0.5 最优）。
  - 结构参数分析：考察 MoE 专家数量（n）和 Top-K 值的影响。
  - 效率分析：对比训练参数量和推理时间。
  - 定性分析：提供了相似度矩阵可视化与 VQA 任务的典型失败案例。
- **公平性**：对比基线均为当前主流或 SOTA 方法，论文在相同设定下重跑了部分基线结果（如 LanguageBind）以确保公平。整体实验设计系统、客观，但视觉问答任务未超越使用大规模预训练语料的 BEiT-3，作者也对此做了诚实的归因分析。

## 6. 主要结论与发现
- M3-JEPA 在多类跨模态任务上**均取得 SOTA 或极具竞争力的性能**，尤其是图像-文本检索任务在多个指标上达到 100% 召回，同时训练参数量仅为 1.4 亿，远少于同类模型。
- 框架具备**强大的泛化能力**，无需改动架构即可从语言-视觉任务无缝迁移至音频-语言及视觉分类任务。
- 信息论分析与实证相互印证，证明通过 MMoE 架构和 AGD 优化，分离模态特定/共享信息并平衡对比与正则化损失，是实现高效跨模态对齐的有效路径。

## 7. 论文优点
- **架构创新**：首次将 JEPA 泛化到任意到任意的多模态场景，并创新性地使用 MMoE 解耦模态信息，为多模态自监督学习提供了新范式。
- **理论与实践结合**：从信息论和能量模型角度提供了严谨的数学推导，并给出了最优损失权重的理论证明，且与实验结果吻合。
- **高效设计**：通过冻结大部分编码器、轻量化 MoE 连接器和潜在空间预计算，实现了极低的训练和推理开销，实用性强。

## 8. 不足与局限
- **缺乏生成能力**：JEPA 架构本质上抛弃了自回归生成范式，目前无法直接应用于文本生成等任务，应用范围受限。
- **模态扩展非自动化**：尽管声称支持任意模态，但引入新模态仍需手动选择编码器、添加对应专家并调整训练流程，并非完全的模态无关架构。
- **复杂融合能力待提升**：在多模态输入（如 VQA）时仅使用简单拼接，导致模型可能忽略细粒度对象，限制了在复杂推理任务上的性能上限。
- **优化策略未穷举**：仅探讨了 AGD 与联合优化的区别，对于其他潜在的联合优化变体或更高效的调度策略缺乏探索。

（完）
