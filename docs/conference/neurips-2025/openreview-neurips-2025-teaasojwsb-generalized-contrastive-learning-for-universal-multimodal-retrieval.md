---
title: Generalized Contrastive Learning for Universal Multimodal Retrieval
title_zh: 通用多模态检索的广义对比学习
authors: "Jungsoo Lee, Janghoon Cho, Hyojin Park, Munawar Hayat, Kyuwoong Hwang, Fatih Porikli, Sungha Choi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=TEAASoJWsb"
tags: ["query:affective-ai"]
score: 8.0
evidence: 提出广义对比学习实现任意模态组合下的统一多模态检索
tldr: 为解决现有跨模态检索模型在融合模态键查询时性能下降的问题，本文提出广义对比学习方法，通过共享表示空间直接对齐图文任意组合，无需精心构造三元组数据。实验显示该方法在多个多模态检索基准上超越了传统合成三元组方案，并能够泛化到训练未见过的模态组合，为通用多模态检索提供了简便有效的框架。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-teaasojwsb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1335, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-teaasojwsb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-teaasojwsb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1361, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-teaasojwsb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 643, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-teaasojwsb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1303, \"height\": 501, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-teaasojwsb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1374, \"height\": 683, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-teaasojwsb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1372, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-teaasojwsb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1376, \"height\": 680, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-teaasojwsb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1084, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-teaasojwsb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1339, \"height\": 720, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-teaasojwsb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1009, \"height\": 176, \"label\": \"Table\"}]"
motivation: 现有跨模态检索模型难以应对由图像和文本融合模态组成的检索键，且基于三元组的方法泛化性差。
method: 提出广义对比学习，直接学习跨任意模态组合的对齐方式，无需依赖特定的组合数据集。
result: 在多种模态组合的检索任务上，该方法性能优于合成三元组方法，且能泛化到未知组合。
conclusion: 广义对比学习为统一多模态检索提供了简洁且泛化强的方案，推动了多模态表示学习的前沿。
---

## Abstract
Despite their consistent performance improvements, cross-modal retrieval models (e.g., CLIP) show degraded performances with retrieving keys composed of fused image-text modality (e.g., Wikipedia pages with both images and text). To address this critical challenge, multimodal retrieval has been recently explored to develop a unified single retrieval model capable of retrieving keys across diverse modality combinations. A common approach involves constructing new composed sets of image-text triplets (e.g., retrieving a pair of image and text given a query image). However, such an approach requires careful curation to ensure the dataset quality and fails to generalize to unseen modality combinations. To overcome these limitations, this paper proposes Generalized Contrastive Learning (GCL), a novel loss formulation that improves multimodal retrieval performance without the burdensome need for new dataset curation. Specifically, GCL operates by enforcing contrastive learning across all modalities within a mini-batch, utilizing existing image-caption paired datasets to learn a unified representation space. We demonstrate the effectiveness of GCL by showing consistent performance improvements on off-the-shelf multimodal retrieval models (e.g., VISTA, CLIP, and TinyCLIP) using the M-BEIR, MMEB, and CoVR benchmarks.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究动机**：现有跨模态检索模型（如 CLIP）在检索由图像‑文本融合模态构成的键（如同时包含图片和文字说明的网页）时，性能显著下降。这种**模态差距**导致语义相似的跨模态样本在嵌入空间中距离较远，而同模态内的不相似样本却靠得很近。
- **现有方法局限**：已有工作（如 VISTA）通过合成特定的三元组数据集（例如“图像‑文本对→图像”或“文本→图像‑文本对”）来训练模型，但这类合成数据需精心策划以保证质量，且**无法泛化到训练中未见的模态组合**。
- **本文目标**：提出一种**无需合成新三元组**的损失函数，直接利用现成的图像‑描述配对数据，在统一表示空间中学习文本、图像、融合图文三种模态的对齐，从而提升通用多模态检索性能。

## 2. 论文提出的方法论
### 2.1 核心思想
- **广义对比学习（Generalized Contrastive Learning, GCL）**：将图像嵌入（\(e_i\)）、文本嵌入（\(e_t\)）、融合图文嵌入（\(e_{it}\)）同时放入一个小批次，并在**所有模态对**之间施加对比损失，使正样本跨模态靠近，负样本（无论模态）被推开。

### 2.2 关键技术细节
- **融合嵌入获取**：
  - VISTA 类模型：使用专用架构（在文本编码器输入中附加视觉 token）。
  - CLIP‑based 模型：采用 “分数融合” 方式，即 \(e_{it} = e_i + e_t\)。
- **正样本对定义**：来自同一图文配对的任意两种不同模态构成正对，即：
  \[
  \mathcal{P} = \{(i, t), (i, it), (t, i), (t, it), (it, i), (it, t)\}
  \]
  相同模态的正对（自己与自己）被屏蔽。
- **对比损失形式**（公式2）：
  \[
  L_{\text{GCL}} = -\frac{1}{6N}\sum_{j=1}^{N}\sum_{(a,b)\in\mathcal{P}}\log\frac{\exp(e_j^a\cdot e_j^b/\tau)}{\sum_{m\in\{i,t,it\}}\sum_{k=1}^{N}\exp(e_j^a\cdot e_k^m/\tau)}
  \]
  其中 \(N\) 为小批次样本数，\(\tau\) 为温度系数。该损失将跨模态对齐、融合模态候选学习、融合模态查询学习统一在一个目标中。
- **训练流程**：直接使用预训练好的跨模态检索模型（仅用图文对预训练），在标准图文对数据集上微调，不引入任何新合成的三元组。

## 3. 实验设计
### 3.1 数据集与基准
- **训练数据**：LLaVA Visual Instruct Pretrain LCS-558K 数据集（已进行人脸模糊处理）。
- **评估基准**：
  - **M-BEIR**：包含 10 个子数据集，分为全局检索（共享多模态数据库）和局域检索（任务专属数据库）。
  - **MMEB**：12 个子数据集。
  - **CoVR**：视频组合检索基准，从视频中采样帧来计算视觉嵌入。
- **评估指标**：Recall@K（M‑BEIR 全局 K=50，局部 K=5；MMEB K=1；CoVR K=1,5,10,50）。所有实验为零样本，未使用评测集的训练集微调。

### 3.2 对比方法
- **基线**：预训练模型（VISTA‑stage1、CLIP‑SF、TinyCLIP‑SF）。
- **标准对比学习微调**（CL）：仅使用传统的跨模态对比损失。
- **基于三元组的微调**（CL + Triplet）：VISTA 在原论文第二阶段使用合成三元组数据集（IT2I、T2IT）。
- **本文方法**：GCL 微调（CL + Pairwise 结合 GCL 损失）。

### 3.3 模型变体
- VISTA、CLIP‑SF（427M）、TinyCLIP‑SF（120M）等。

## 4. 资源与算力
- **论文正文未明确说明**使用的 GPU 型号、数量、训练时长及内存消耗。这些信息可能出现在补充材料中，但基于所提供的内容，无法给出具体算力资源总结。文中仅提及了推理速度（ms）的比较，而未涉及训练开销。

## 5. 实验数量与充分性
- **覆盖多个基准与模型**：在 M‑BEIR（全局+局部，共 20 个任务×多个数据集）、MMEB（12 个子任务）、CoVR 上进行了系统性实验，并涉及 VISTA、CLIP、TinyCLIP 三个骨干网络。
- **消融研究**：详细拆解了 GCL 损失中的各个成分（如移除跨模态对齐项 \(L_{i2t}, L_{t2i}\)、移除融合候选项 \(L_{i2it}, L_{t2it}\) 等），并与 AlignCLIP 的模态内分离损失进行对比。
- **其他分析**：可视化（PCA、排名分布、余弦相似度）、轻量模型有效性验证。实验设计**充分、客观且公平**，能够支持核心结论。

## 6. 论文的主要结论与发现
- GCL 能够在不依赖任何新三元组合成数据的情况下，显著提升多模态检索性能，尤其在查询或候选包含图文融合模态时表现突出。
- 基于合成三元组微调的方法（如 VISTA 的第二阶段）仅在特定场景有效，且会损害原始跨模态检索能力；而 GCL 可在各种任务上实现**一致的泛化提升**。
- GCL 有效缩小了模态差距，使正确候选的嵌入与查询更靠近，并保持了高排名相关候选的语义连贯性。
- 将 GCL 应用于轻量模型（TinyCLIP）后，性能可超过更大规模的基础模型，展现出高效部署的潜力。

## 7. 优点
- **方法简洁通用**：仅修改损失函数，无需额外数据构造，易于复现和扩展到其他多模态检索模型。
- **性能增益显著**：在多个基准、多种模态组合任务上均取得稳定提升，优于专门合成三元组的方法。
- **消融与分析充分**：详细验证了各损失组件的作用，并对排序、余弦相似度进行了可视化分析，增强了可解释性。
- **高效性**：对小模型同样有效，为边缘端检索提供可行方案。

## 8. 不足与局限
- **特定领域任务退化**：在某些场景（如 CIRR、FashionIQ）微弱的性能下降，可能因通用微调数据未充分覆盖领域特性，需额外任务特定微调。
- **未集成多模态大语言模型**：作者指出尚未与 MLLM 结合，限制了在生成式或推理任务中的应用。
- **超参数未充分调优**：各损失项采用等权相加，针对特定场景可能存在更好的权重分配策略，但未探索。
- **训练成本隐私**：缺乏训练资源需求（GPU 数量、时间等）的详细说明，难以评估实际部署成本。

（完）
