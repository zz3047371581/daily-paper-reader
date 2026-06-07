---
title: Aggregation of Dependent Expert Distributions in Multimodal Variational Autoencoders
title_zh: 多模态变分自编码器中依赖专家分布的聚合
authors: "Rogelio A. Mancisidor, Robert Jenssen, Shujian Yu, Michael Kampffmeyer"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=jYmGi1175R"
tags: ["query:affective-ai"]
score: 6.0
evidence: 聚合依赖的模态分布用于多模态VAE，推进融合技术
tldr: 现有多模态VAE常用乘积或混合专家聚合法假设模态独立，过于乐观。本文提出CoDE方法，基于依赖专家共识聚合模态分布，推导出新的ELBO以近似联合似然。CoDE-VAE在生成质量和跨模态一致性上优于传统方法，为多模态概率融合提供更精确的建模方式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 823, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 609, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 607, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 644, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1729, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 640, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1586, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1749, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 586, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 866, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1612, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 836, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1656, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1659, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1468, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 527, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 527, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 528, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 527, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 827, \"height\": 1085, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 724, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 824, \"height\": 912, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1638, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1555, \"height\": 850, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1526, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jymgi1175r/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 653, \"height\": 495, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1638, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1550, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1048, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1412, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1411, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1401, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1390, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1415, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1457, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1457, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 909, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 560, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1433, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1608, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jymgi1175r/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1302, \"height\": 378, \"label\": \"Table\"}]"
motivation: 现有聚合方法假设各模态独立，忽略模态间依赖性，导致多模态联合分布建模不准确。
method: 引入依赖专家共识（CoDE）原则，通过学习各模态子集的贡献，构建新的ELBO以逼近真实联合分布。
result: CoDE-VAE在图像文本等多模态任务上展现了更好的生成保真度和跨模态一致性。
conclusion: 考虑模态依赖的融合策略提升了多模态生成模型的性能与合理性。
---

## Abstract
Multimodal learning with variational autoencoders (VAEs) requires estimating joint distributions to evaluate the evidence lower bound (ELBO). Current methods, the product and mixture of experts, aggregate single-modality distributions assuming independence for simplicity, which is an overoptimistic assumption. This research introduces a novel methodology for aggregating single-modality distributions by exploiting the principle of *consensus of dependent experts* (CoDE), which circumvents the aforementioned assumption. Utilizing the CoDE method, we propose a novel ELBO that approximates the joint likelihood of the multimodal data by learning the contribution of each subset of modalities. The resulting CoDE-VAE model demonstrates better performance in terms of balancing the trade-off between generative coherence and generative quality, as well as generating more precise log-likelihood estimations. CoDE-VAE further minimizes the generative quality gap as the number of modalities increases. In certain cases, it reaches a generative quality similar to that of unimodal VAEs, which is a desirable property that is lacking in most current methods. Finally, the classification accuracy achieved by CoDE-VAE is comparable to that of state-of-the-art multimodal VAE models.

---

## 论文详细总结（自动生成）

好的，我将根据提供的论文内容，生成一份结构化的中文总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：
    *   多模态变分自编码器（VAEs）在学习联合表示时，需要将从各单模态数据推断出的分布（称为“专家”）聚合成一个联合后验分布。
    *   当前主流的聚合方法，如专家乘积（PoE）和专家混合（MoE），为简化问题均假设各模态/专家之间相互独立。
    *   作者认为，由于不同模态描述的通常是同一个底层对象，它们提供的信息存在固有联系，因此独立性假设是过于乐观且不切实际的，这会导致联合分布估计出现偏差（如PoE低估方差、MoE无法产生比单一专家更尖锐的分布），从而损害模型在生成质量和似然估计等方面的表现。

*   **整体含义**：
    *   本研究旨在解决多模态VAE中因忽略模态间依赖性而导致性能受限的问题。通过提出一种名为“依赖专家共识”（CoDE）的新方法，显式建模专家分布间的相关性，从而更准确地估计联合后验分布，最终提升多模态生成模型的综合性能。

### 2. 论文提出的方法论

*   **核心思想：依赖专家共识（CoDE）**
    *   摒弃专家独立的假设，通过专家对潜变量估计的“误差”之间的相关性来建模它们之间的依赖关系。
    *   利用贝叶斯推断，将各专家给出的点估计和不确定性视为对真实潜变量的似然，从而推导出更合理的后验分布。

*   **关键技术细节与公式流程**：
    *   **误差建模**：将第 `j` 个专家对潜变量 `z` 第 `d` 维的估计误差定义为 `e_{dj} = μ_{dj} - θ_{dk}`。所有专家在第 `d` 维的误差向量 `e_d` 被假定服从多元高斯分布 `N(0, Σ_d)`，其中协方差矩阵 `Σ_d` 的非对角线元素 `σ_{j,i} = ρσ_j σ_i` 用于捕捉专家误差间的相关性（`ρ` 为相关系数）。整体误差向量 `e_k` 服从 `N(0, Σ_k)`，`Σ_k` 为各维度协方差矩阵分块对角排列。
    *   **共识分布推导**：基于误差分布，将专家估计 `μ_k` 视为关于真实潜变量 `θ_k` 的似然函数 `N(uθ_k, Σ_k)`。在扁平先验假设下，通过贝叶斯法则推导出后验分布（即共识分布）`h(θ_k|μ_k) ~ N(A_k^{-1}B_k, A_k^{-1})`，其中 `A_k = u^T Σ_k^{-1} u`，`B_k = u^T Σ_k^{-1} μ_k`。
    *   **与PoE关系**：当设定相关性 `ρ = 0`（即 `Σ_d` 为对角阵）时，CoDE推导出的分布形式退化为PoE，表明PoE是CoDE在独立性假设下的特例。
    *   **新型ELBO设计**：提出了一种新的证据下界（ELBO），为数据幂集 `P(X)` 中的每个模态子集 `X_k` 分配一个可学习的权重 `π_k`，该权重服从分类分布。最终的ELBO是所有权重 `π_k`、对应子集的生成项与KL散度项、以及权重分布的熵组成的加权和。这使得模型能自动学习不同模态组合在优化中的重要性。

### 3. 实验设计

*   **数据集与场景**：
    *   **MNIST-SVHN-Text** (M=3)：包含手写数字、街景门牌号图像和描述文本，模态异质性大。
    *   **PolyMNIST** (M=5)：由5个不同背景和书写风格的手写数字图像组成，用于分析生成质量差距随模态数量增加的变化。
    *   **Caltech Birds (CUB)** (M=2)：包含鸟类图像和对应文本描述，是更具挑战性的真实世界数据集。

*   **基准方法与对比模型**：
    *   与当前最优的多模态VAE模型进行全面对比，包括：**MVAE** (Wu & Goodman)、**MMVAE** (Shi et al.)、**mmJSD** (Sutter et al.)、**MoPoE-VAE** (Sutter et al.)、**MVTCAE** (Hwang et al.) 和 **MMVAE+** (Palumbo et al.)。

*   **评估指标**：
    *   生成一致性：条件生成和条件生成下，生成样本的分类准确率。
    *   生成质量：使用FID分数评估生成图像的真实性。
    *   似然估计：通过ELBO的对数似然估计下限来评估对联合分布近似的紧密程度。
    *   分类精度：使用线性分类器评估联合潜表示的可判别性。

### 4. 资源与算力

*   文中明确提到，模型训练使用**单块NVIDIA A100 GPU**，搭配AMD EPYC Milan处理器。
*   计算开销：CoDE-VAE的计算复杂度为 `O(2^M - 1)`，但在实践中仍然可行，例如对5模态的PolyMNIST数据集也可在单GPU上训练。与标准PoE相比，CoDE方法在MNIST-SVHN-Text上的每批次处理时间从36毫秒增加到46毫秒，在PolyMNIST上从790毫秒增加到1050毫秒，增加的开销不大。

### 5. 实验数量与充分性

*   **海量实验**：论文进行了极其广泛的实证研究。例如，为分析生成质量差距，作者针对PolyMNIST数据集，将模态数从2扩展到5，为每种配置训练了4个模型版本，并结合β、ρ、π的不同取值，共运行了**超过480组实验**（每组重复3次）。
*   **多维度评估**：实验覆盖了多个不同复杂度的数据集和多达7种基准模型的对比。
*   **消融与分析实验**：专门设计了消融实验来验证`π`（权重学习）和 `ρ`（相关性建模）各自的效果，同时分析了权重系数 `π_k` 与分布不确定性（迹）的关系，充分证明了方法的有效性。
*   **客观公平性**：所有实验均遵循领域内标准设置，关键超参数（如β、ρ）均通过交叉验证确定，并在最优超参数下进行公平比较。

### 6. 论文的主要结论与发现

*   CoDE-VAE在生成一致性和生成质量之间实现了**更好的平衡**，并在多个数据集上提供了更精确的对数似然估计。
*   由于不依赖于有害的子采样技术，CoDE-VAE随着模态数量的增加，能够**最小化甚至消除生成质量差距**，在PolyMNIST的4和5模态训练中达到了与单模态VAE相当的无条件生成质量。
*   CoDE-VAE的线性分类精度与当前最先进模型有**可比之处**。
*   消融实验证实，显式**建模专家依赖关系（通过`ρ`）和学习各ELBO项对优化的贡献（通过`π`）** 均对模型性能有显著积极影响。

### 7. 优点

*   **理论创新**：首次将依赖专家共识原则系统引入多模态VAE领域，用贝叶斯方法优雅地解决了模态依赖性问题，为聚合方法提供了新视角。
*   **方法简洁有效**：CoDE仅通过在误差协方差矩阵中引入单个参数`ρ`来建模依赖，易于实现且计算开销不大，并可无缝替换现有的PoE。
*   **实验全面扎实**：在多个标准数据集上，从生成一致性、生成质量、似然估计、分类精度和模态数扩展性等多个维度，与当前最先进模型进行了详尽的对比和消融分析，论证充分，结果有说服力。

### 8. 不足与局限

*   **超参数敏感性**：模型关键超参数`ρ`需要通过交叉验证来确定，对于大规模复杂数据，这可能会带来较高的计算成本。
*   **结构固化**：论文假设了多元高斯误差分布和固定的正相关结构（`σ_{j,i} = ρσ_j σ_i`）。虽然文中指出可以指定任意形式的可逆`Σ_d`，但单一参数化的灵活性有限，可能无法完美捕捉所有复杂的依赖模式。
*   **计算复杂度**：虽然可接受，但模型复杂度随模态数指数增长（`O(2^M-1)`），对于模态数非常多的场景可能仍然构成挑战。

（完）
