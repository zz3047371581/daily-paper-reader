---
title: Learning Shared Representations from Unpaired Data
title_zh: 从非成对数据中学习共享表征
authors: "Amitai Yacobi, Nir Ben-Ari, Ronen Talmon, Uri Shaham"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=idxHcrwBYP"
tags: ["query:affective-ai"]
score: 9.0
evidence: 利用非成对数据学习跨模态共享表征；基于谱嵌入的随机游走矩阵
tldr: 针对多模态表征学习严重依赖成对样本的问题，本文证明可从非成对数据中学习共享表征。方法基于各模态独立构建的随机游走矩阵的谱嵌入，在计算机视觉和自然语言处理领域的检索、生成等任务上展现了非成对数据的有效性，为缓解成对数据稀缺提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1427, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 725, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1428, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1156, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1402, \"height\": 141, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1439, \"height\": 240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1439, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1435, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 721, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 863, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 579, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idxhcrwbyp/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1437, \"height\": 175, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 503, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 714, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1045, \"height\": 503, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1143, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 422, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 988, \"height\": 595, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 789, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 846, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 871, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 669, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1433, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idxhcrwbyp/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1362, \"height\": 247, \"label\": \"Table\"}]"
motivation: 现有跨模态共享表征学习方法高度依赖成对数据，而成对数据获取困难且昂贵。
method: 通过各模态独立的随机游走矩阵谱嵌入，从非成对数据中学习模态间共享表征。
result: 在图像-文本检索和生成任务上，仅用非成对数据取得了与成对数据方法可比的结果。
conclusion: 该研究表明非成对数据在多模态任务中的巨大潜力，拓宽了多模态学习的应用场景。
---

## Abstract
Learning shared representations is a primary area of multimodal representation learning. The current approaches to achieve a shared embedding space rely heavily on paired samples from each modality, which are significantly harder to obtain than unpaired ones. In this work, we demonstrate that shared representations can be learned almost exclusively from unpaired data. Our arguments are grounded in the spectral embeddings of the random walk matrices constructed independently from each unimodal representation. Empirical results in computer vision and natural language processing domains support its potential, revealing the effectiveness of unpaired data in capturing meaningful cross-modal relations, demonstrating high capabilities in retrieval tasks, generation, arithmetics, zero-shot, and cross-domain classification. This work, to the best of our knowledge, is the first to demonstrate these capabilities almost exclusively from unpaired samples, giving rise to a cross-modal embedding that could be viewed as universal, i.e., independent of the specific modalities of the data. Our project page: https://shaham-lab.github.io/SUE_page.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义

- **研究动机**：多模态共享表征学习（如 CLIP）高度依赖大规模成对数据（例如 4 亿图文对），而成对数据获取困难、成本高，尤其在医疗等专业领域。非成对数据远比成对数据容易获得，但传统方法很难利用非成对数据实现逐点匹配。
- **整体含义**：本文证明**共享表征几乎可以完全从非成对数据中学习**，只需极少量的成对样本（弱配对场景）。核心思想是“普适嵌入（universal embedding）”——不同模态的扩散算子特征函数具有相似性（模态不变性），因此可以通过独立构建随机游走矩阵的谱嵌入来挖掘跨模态语义结构。

## 提出的方法论：SUE（Spectral Universal Embedding）

**核心思想**：利用各模态内部的无监督谱嵌入（Spectral Embedding, SE）从非成对数据中提取模态不变的特征，再利用极少量成对数据进行对齐。

### 关键技术细节
- **问题设定**：给定大量非成对预训练单模态嵌入 \(X \subseteq \mathbb{R}^{d_1}, Y \subseteq \mathbb{R}^{d_2}\)，以及极少成对样本 \(X_p, Y_p\)（\(m \ll n_1, n_2\)）。
- **三步流程**：
  1. **谱嵌入（SE）**：对每个模态独立训练 SpectralNet，近似学习该模态扩散算子的前 \(k\) 个非平凡特征向量（即谱嵌入）。训练基于随机游走拉普拉斯矩阵，最小化 Rayleigh 商并施加正交约束，**不依赖配对信息**。
  2. **典型相关分析（CCA）**：利用极少量成对样本（如几百对）对两个模态的谱嵌入做 CCA，获得线性投影 \(Q_X, Q_Y \in \mathbb{R}^{k\times r}\)，解决谱嵌入方向与基的不确定性，实现初始线性对齐。
  3. **分布匹配残差网络（MMD）**：设计一个带残差连接的浅层网络 \(F_\theta: \mathbb{R}^r\to\mathbb{R}^r\)，最小化两个模态对齐后嵌入的经验最大均值差异（MMD），以进行非线性微调对齐。**MMD 损失不依赖配对数据**，可充分利用全部非成对样本。

- **算法总览**（Algorithm 1）：
  - 输入：非成对集 \(X, Y\) 和成对集 \(X_p, Y_p\)
  - 输出：映射函数 \(f_X: \mathbb{R}^{d_1}\to\mathbb{R}^r, f_Y: \mathbb{R}^{d_2}\to\mathbb{R}^r\)
  - 步骤：训练 SE → CCA 计算投影 → 训练 MMD 残差网络 → 组合得到最终映射。

### 理论依据简述
- 假设存在潜在语义流形 \(\mathcal{M}\)，两个模态映射 \(f, g\) 若满足有界畸变与有界 Ricci 曲率，则对应扩散算子的特征函数在 \(L_\infty\) 意义下相近（引用 Béard 等 Thm. 21）。
- 随机游走相似性实验（Fig. 1a）表明：图像和文本独立构建的随机游走矩阵之间的距离远小于随机匹配情况。

## 实验设计

### 数据集与场景
- **视觉-语言**：Flickr30k、MSCOCO、Polyvore（时尚图文）、caption-FFHQ（生成任务）
- **视觉-视觉**：Edges2Shoes（鞋草图与实物图）
- **表格-表格**：Handwritten 数据集（KL 系数与像素均值）
- **跨域分类**：Office31（Amazon 与 DSLR 图像域）
- **零样本**：ImageNet 类别文本与图片

### Benchmark 与对比方法
- **主要 baseline**：对比学习（用同样少量成对样本训练 MLP，类似 CLIP 损失）；CSA（针对小配对数据集的方法）
- **其他对比**：域混淆（只用 MMD，完全无配对）；SAIL（结合成对与非成对数据的代表方法）
- **消融**：逐步增加 SE、CCA、MMD 各环节；替换 SE 为自编码器；探究不同预训练单模态编码器的影响

### 评估指标
- 检索：Recall@k (k=1,5,10)，mAP，Relative CLIP Score (RCS)
- 分类：准确率；零样本：余弦相似度最高标签分类准确率
- 生成：定性展示；算术：图像向量运算定性示例

## 资源与算力

- **GPU**：实验在 Nvidia GeForce GTX 1080 Ti 和 A100 80GB PCIe GPU 上进行。
- **训练细节**：谱嵌入网络为 MLP，隐藏层 [4096, 4096, 1024]，batch size 4096，学习率 1e-4，100 epoch；MMD 残差网络 3 层隐藏层各 128，100 epoch，使用 AdamW。**未明确提及总训练时长**。

## 实验数量与充分性

- **多数据集覆盖**：7 个不同模态数据集，涵盖视觉-语言、视觉-视觉、表格数据。
- **多任务验证**：跨模态检索、跨域分类、零样本分类、文本到图像生成、语义算术。
- **消融研究**：
  - 逐步增加 SE、CCA、MMD（Tab. 2）
  - 替换 SE 为自编码器（Tab. 10）
  - 探究非成对与成对数据量影响（Fig. 5）
  - 不同单模态编码器对比（Tab. 8）
  - 与 CSA、SAIL、域混淆方法的全面对比
- **统计与可视化**：提供 UMAP 可视化、距离直方图、误差棒（标准误差）。
- 总体实验设计系统，从组件有效性、数据规模敏感性到跨任务泛化均被考察，**较为充分且公平**，在弱配对场景下尤其展示 SUE 有效性。

## 主要结论与发现

- 利用 SE 可以从非成对数据中提取模态不变的语义结构；SE 是整个方法的关键组件。
- SUE 仅需要极少量成对样本（如 MSCOCO 100 对、Flickr30k 500 对）即可构建共享表征，**显著优于同等配对数的对比学习方法**（召回率提升超 250%）。
- 非成对数据可大幅提升性能，而成对数据的需求存在饱和点（Fig. 5）。
- 所得共享空间支持多种下游任务：跨模态检索、几乎无文本对应的人脸生成、语义向量算术、零样本分类和跨域分类。
- 共享空间无“模态间隙”（modality gap），两模态嵌入位于同一流形（Fig. 14）。

## 优点

- **方法原创性**：率先证明几乎全用非成对数据学习跨模态共享表征的可能性，提出“普适嵌入”概念。
- **组件合理**：谱嵌入捕捉全局结构 + CCA 旋转对齐 + MMD 分布匹配，各环节理论支撑明确。
- **弱配对设定有效**：在极少配对样本情况下极大超越对比学习，切合真实场景中配对数据稀缺的痛点。
- **实验全面**：多模态、多任务、多 baseline、消融和规模分析，定性与定量结合，增强了结论可靠性。
- **开源承诺**：提供项目页面与代码（评审通过后公开），具可复现性。

## 不足与局限

- **性能上限**：与动辄数亿配对数据训练的大模型（如 CLIP）仍有差距，不追求替代已有大规模配对方法。
- **模态与任务范围有限**：仅在图像、文本、简单视觉和表格数据上测试，未扩展到视频、语音、科学数据等更复杂模态。
- **对预训练单模态模型的依赖**：SE 质量受单模态编码器表征能力影响（Tab. 8），且尚需 CCA 所需的少量成对数据，全无配对的学习仍不成熟。
- **理论部分较 heuristic**：对扩散算子特征函数相似性的定理引用属于存在性结果，实际近似程度缺乏更严格的界。
- **应用风险**：未见显著负面社会影响，但未深入讨论数据偏差、隐私等问题。

（完）
