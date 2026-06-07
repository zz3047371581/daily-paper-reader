---
title: Amplifying Prominent Representations in Multimodal Learning  via Variational Dirichlet Process
title_zh: 通过变分狄利克雷过程增强多模态学习中的显著表征
authors: "Tsai Hor Chan, Feng Wu, Yihang Chen, Guosheng Yin, Lequan Yu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dC5TWysDsZ"
tags: ["query:affective-ai"]
score: 8.0
evidence: 贝叶斯非参融合放大显著特征并保持跨模态交互
tldr: 现有对齐式多模态融合可能过度正则化而压制模态内部表达力。本文受狄利克雷过程富者愈富特性启发，提出变分DP融合方法，自适应放大显著特征，同时保留丰富的跨模态交互。在医疗、金融等实验中，该方法比传统对齐方法更具鲁棒性和表达力。它为多模态学习提供了一种保留模态专有信息的新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 695, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 801, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 706, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 709, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 698, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 707, \"height\": 411, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 706, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 940, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 868, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1443, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1447, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1444, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 796, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1012, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1008, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1294, \"height\": 372, \"label\": \"Table\"}]"
motivation: 现有对齐方法过度强调模态边缘分布对齐，损害了单模态内部的表达力。
method: 提出基于变分狄利克雷过程的多模态融合方法，利用富者愈富特性放大显著特征。
result: 在医疗和金融场景下，方法有效提升了多模态融合的鲁棒性和性能。
conclusion: 狄利克雷过程先验能有效促进多模态学习中的关键特征提取。
---

## Abstract
Developing effective multimodal fusion approaches has become increasingly essential in many real-world scenarios, such as health care and finance. 
The key challenge is how to preserve the feature expressiveness in each modality while learning cross-modal interactions.
Previous approaches primarily focus on the cross-modal alignment,
while over-emphasis on the alignment of marginal distributions of modalities may impose excess regularization and obstruct meaningful representations within each modality.
The Dirichlet process (DP) mixture model is a powerful Bayesian non-parametric method that can amplify the most prominent features by its richer-gets-richer property, which allocates increasing weights to them.
Inspired by this unique characteristic of DP, we propose a new DP-driven multimodal learning framework that automatically achieves an optimal balance between prominent intra-modal representation learning and cross-modal alignment. 
Specifically, we assume that each modality follows a mixture of multivariate Gaussian distributions and further adopt DP to calculate the mixture weights for all the components. This paradigm allows DP to dynamically allocate the contributions of features and select the most prominent ones, leveraging its richer-gets-richer property, thus facilitating multimodal feature fusion.
Extensive experiments on several multimodal datasets demonstrate the superior performance of our model over other competitors.
Ablation analysis further validates the effectiveness of DP in aligning modality distributions and its robustness to changes in key hyperparameters.
Code is anonymously available at https://github.com/HKU-MedAI/DPMM.git

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **核心问题**：现有多模态融合方法（如对比学习、对抗对齐等）过度强调跨模态对齐，在拉近不同模态分布的同时往往会**抑制或削弱各个模态内部原有的重要特征表现力**，导致融合后的表示丢失模态专有信息，损害下游任务性能，尤其在模态缺失情况下问题更严重。
*   **整体含义**：论文受**狄利克雷过程（Dirichlet Process, DP）的“富者愈富”特性**启发，提出一种由DP驱动的多模态学习框架 **DPMM**。该方法将每个模态的特征分布视为一个**高斯混合模型**，并由DP动态分配各模态内混合成分的权重，从而自动放大对任务最重要的显著特征，同时隐式地实现跨模态对齐，在**保留模态内突出表示和捕捉跨模态结构**之间取得最优平衡。

### 2. 方法论：核心思想与技术细节
*   **核心思想**：利用DP的非参数先验对多模态联合特征空间进行建模。DP的“富者愈富”性质会自动将更大权重分配给被数据反复激活的突出特征混合成分，让关键信号在后续融合中占主导，避免传统对齐方法导致的特征坍缩。
*   **关键技术细节**：
    *   **混合权重生成（断棍过程）**：用**逐模态、逐成分的断棍过程**定义混合权重 $\pi_{mk}$ 的先验，通过 $\beta_{mk} \sim \text{Beta}(1, \eta)$ 的乘积形式生成权重，使得DP能够跨模态自动选择突出特征。
    *   **边际分布与联合分布**：假设第 $m$ 个模态的特征分布为 $K$ 元高斯混合 $f_m(\mathbf{z})=\sum_{k=1}^K \pi_{mk} \mathcal{N}(\mathbf{z}|\boldsymbol{\mu}_{mk},\boldsymbol{\Sigma}_{mk})$，所有模态的联合分布则为各模态混合分布的加权组合。均值 $\boldsymbol{\mu}$ 和协方差 $\boldsymbol{\Sigma}$ 为可学习参数。
    *   **变分推断**：为扩展到大规模数据，采用**随机变分推断**优化ELBO，ELBO包含Beta变分后验与先验的KL散度，以及任务相关的预测损失（即观测标签与预测标签的KL散度）。变分后验参数通过闭式更新公式（4）和（5）迭代计算。
    *   **缺失模态填补**：利用学习到的各模态边际高斯混合分布对缺失模态进行采样（梯度保留采样），使填补出的表示同时包含跨模态信息和突出的模态内特征。
*   **算法流程**（文字描述）：对每个训练批次，先通过断棍采样得到混合权重 $\pi_{mk}$，再由编码器得到各模态潜在嵌入，计算基于高斯混合的对数似然，结合任务损失得到ELBO，反向传播更新编码器参数及高斯混合参数 $\boldsymbol{\mu},\boldsymbol{\Sigma}$。

### 3. 实验设计
*   **数据集与场景**：
    *   **临床数据集**：MIMIC‑III（EHR + 临床笔记）、MIMIC‑IV（EHR + 胸片 CXR + 放射学报告），覆盖完全匹配、部分匹配（存在缺失模态）以及三模态设置。
    *   **通用多模态数据集**：CMU‑MOSI（视频+音频+文本，情感分析）、POM（电影特质预测）。
*   **任务与指标**：院内死亡预测（IHM）、30天内再入院预测（READM）、情感分析、电影特质预测；主要采用AUROC、AUPR、F1等。
*   **对比方法**：
    *   临床基线：MMTM、DAFT、Unified、MedFuse、DrFuse。
    *   通用多模态基线：LMF（低秩融合）、TFN（张量融合网络）。
    *   对比实验还涉及不同缺失比率（10%、40%、70%）、不同对齐损失（余弦、KL）、不同超参数组合等。

### 4. 资源与算力
*   所有实验均在**单块RTX‑3090 GPU**上运行。
*   模型训练**100个epoch**，批大小（batch size）为16或32，使用Adam优化器，并采用早停策略。
*   补充材料中给出了各方法的每epoch训练时长（例如DPMM在完全匹配/部分匹配下约26.6s/70.8s），参数量约93.68MB，与其他基线处于同一量级，开销合理。

### 5. 实验数量与充分性
*   实验覆盖**4类数据集（含两个大型临床库和两个通用多模态库）**、**完全匹配与部分匹配两种场景**，并额外测试了**不同缺失比率**下的鲁棒性。
*   进行了**详尽的消融实验**：
    *   DP的浓度参数 $\eta$ 和最大混合成分数 $K$ 的灵敏度分析。
    *   模块有效性：移除融合模块、梯度保留采样、DP对齐的对比。
    *   对齐损失对比：DP对齐 vs. 余弦相似度对齐 vs. KL散度对齐。
    *   DP权重与纯可学习权重的对比。
    *   与多种缺失值填补方法（PSA、LSMT）及对比学习模型（CLIP、ALIGN、CoMM）的对比。
*   所有结果均给出**95%置信区间**，实验设置透明，各基线基本遵循原论文默认配置。总体实验设计较充分，对比客观。

### 6. 主要结论与发现
*   提出的**DPMM在全部数据集和评价指标上均显著优于现有主流多模态融合方法**，尤其在模态缺失场景下优势更明显。
*   **DP能够有效放大各模态中的显著特征**（通过可视化对数密度直方图证实），同时隐式完成跨模态对齐，达到了“突出单模态重要特征”与“学习跨模态交互”之间的自动平衡。
*   模型性能对超参数 $\eta$ 和 $K$ 的变化具有较强的**鲁棒性**，DP的截断近似仍可保持丰富的表示能力。

### 7. 优点
*   **创新视角**：首次将DP的“富者愈富”特性系统性地引入多模态对齐，提供了一种保留模态专有信息的全新范式。
*   **灵活的生成式框架**：基于高斯混合与变分推断，天然支持缺失模态的生成式填补，且填补特征具备模态内典型性。
*   **可扩展与高效**：采用随机变分推断，克服了传统DP需MCMC的扩展性瓶颈，可在现代GPU上高效训练。
*   **实验扎实**：覆盖临床与通用领域，包含完整匹配与高缺失率场景，消融充分，置信区间报告规范。

### 8. 不足与局限
*   **模型假设限制**：假设特征服从各向同性高斯分布（协方差矩阵为对角阵），这可能限制了捕获更复杂特征相关性的能力。
*   **计算开销略有增加**：断棍过程和变分推断带来一定的额外计算，每epoch训练时间略高于部分基线。
*   **应用场景局限**：虽在通用数据集上有效，但主要优势验证集中于医疗数据，在其他高度异质性多模态任务中的泛化性尚需更多检验。
*   **对齐方式隐式**：DP驱动的对齐是通过共享混合权重实现的隐式结构对齐，没有显式的模态间相似性约束，在需要强对齐的任务中可能表现不够直接。

（完）
