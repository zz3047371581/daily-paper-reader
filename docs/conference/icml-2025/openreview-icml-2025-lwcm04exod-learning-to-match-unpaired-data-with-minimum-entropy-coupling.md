---
title: Learning to Match Unpaired Data with Minimum Entropy Coupling
title_zh: 学习以最小熵耦合匹配未配对数据
authors: "Mustapha BOUNOUA, Giulio Franzese, Pietro Michiardi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=lWcM04ExOD"
tags: ["query:affective-ai"]
score: 6.0
evidence: 基于扩散模型的最小熵耦合对齐未配对多模态数据
tldr: 本文针对多模态数据常缺失配对的问题，提出一种基于扩散模型的最小熵耦合方法，实现连续数据的跨模态对齐。该方法通过合作学习近似并最小化联合熵，在保持边缘分布约束的同时，能够处理图像、文本等连续模态，为多模态翻译与融合提供了基础工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lwcm04exod/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 873, \"height\": 1054, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwcm04exod/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 856, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwcm04exod/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 1249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwcm04exod/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1583, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwcm04exod/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1409, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwcm04exod/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1308, \"height\": 2253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwcm04exod/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1319, \"height\": 2260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwcm04exod/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1005, \"height\": 755, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwcm04exod/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1334, \"height\": 1411, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lwcm04exod/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 765, \"height\": 551, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwcm04exod/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 922, \"height\": 1813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwcm04exod/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 958, \"height\": 967, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwcm04exod/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 516, \"height\": 384, \"label\": \"Table\"}]"
motivation: 多模态数据常不成对出现，阻碍联合分布学习。
method: 提出一种基于扩散模型的连续最小熵耦合方法，通过合作学习最小化联合熵实现跨模态对齐。
result: 实验证明该方法能有效匹配连续数据的跨模态分布。
conclusion: 为无配对多模态对齐提供了新的生成式解决方案。
---

## Abstract
Multimodal data is a precious asset enabling a variety of downstream tasks in machine learning. However, real-world data collected across different modalities is often not paired, which is a significant challenge to learn a joint distribution. A prominent approach to address the modality coupling problem is Minimum Entropy Coupling (MEC), which seeks to minimize the joint Entropy, while satisfying constraints on the marginals. Existing approaches to the MEC problem focus on finite, discrete distributions, limiting their application for cases involving continuous data. In this work, we propose a novel method to solve the continuous MEC problem, using well-known generative diffusion models that learn to approximate and minimize the joint Entropy through a cooperative scheme, while satisfying a relaxed version of the marginal constraints.
We empirically demonstrate that our method, DDMEC, is general and can be easily used to address challenging tasks, including unsupervised single-cell multi-omics data alignment and unpaired image translation, outperforming specialized methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **问题背景**：现实中多模态数据（如图像、基因表达、蛋白质）常以**未配对**形式出现，无法直接获得联合分布 \(p(x,y)\)，这严重阻碍了基于配对数据的下游任务（如跨模态生成、对齐）。
- **整体含义**：本文从**信息论的耦合问题**出发，提出**连续域下的最小熵耦合（Minimum Entropy Coupling, MEC）**方法，旨在找到一个联合分布，使其具有最小联合熵，同时近似满足给定的边缘分布约束。与现有仅适用于离散分布的工作不同，本文首次将 MEC 拓展到**连续、任意分布**的场景，不依赖几何可比性或人为定义的距离度量，并通过**扩散生成模型**协作实现。

### 2. 论文提出的方法论
- **核心思想**：将联合分布 \(p_{\theta}(x,y)\) 参数化为一个**条件生成模型** \(p_{\theta}(x|y)p_Y(y)\)。最小化联合熵等价于**最小化条件熵** \(H(X|Y)\)，这又对应于**最大化条件对数似然**。同时，通过 KL 散度施加**松弛的边缘约束**，保证生成样本的边缘分布与原数据分布对齐。
- **对称协作框架**：为解决方向不对称性和稳定性问题，引入两个对称的条件模型：
  \[
  \begin{aligned}
  \min_\theta \mathbb{E}_{p_\theta} [-\log p_\phi(y|x)] + \lambda \text{KL}(p_\theta^X \| p_X) , \\
  \min_\phi \mathbb{E}_{p_\phi} [-\log p_\theta(x|y)] + \lambda \text{KL}(p_\phi^Y \| p_Y) .
  \end{aligned}
  \]
  两个模型**互为奖励信号**，交替优化，同时约束 \(p_{\theta}(x,y) \approx p_{\phi}(x,y)\)。
- **技术实现**：
  - 使用**去噪扩散概率模型（DDPM）**作为条件生成器的骨干。
  - 先**预训练无条件扩散模型** \(p_{\theta^*}^X\) 和 \(p_{\phi^*}^Y\) 捕获边缘分布。
  - 将边缘约束转化为对预训练权重的 KL 正则化（避免偏离太远）。
  - 采用**强化学习微调**（类似 DPoK，使用 PPO 风格更新）计算奖励梯度，并利用蒙特卡洛估计扩散模型的负对数似然。
  - 训练时用交替算法：固定一个模型，用另一个模型的 log-likelihood 作奖励更新当前模型，再通过生成样本拉近两模型的距离。

### 3. 实验设计
- **任务一：单细胞多组学对齐**
  - **数据集**：PBMC (RNA+ATAC)、BM (RNA+ADT)、SNARE-seq（基因表达+染色质可及性）。
  - **Benchmark 指标**：交叉模态邻域一致性（Celltype Acc, Subcelltype Acc）；SNARE-seq 还使用 FOSCTTM 和标签迁移准确率。
  - **对比方法**：SCOT、MMD-MA、UnionCom、scTopoGAN、InfoOT（部分仅在附录）。
- **任务二：无配对图像翻译**
  - **数据集**：AFHQ（CAT↔DOG, WILD↔DOG）和 CelebA‑HQ（MALE↔FEMALE）。
  - **指标**：FID（图像质量）、SSIM（结构保真度）。
  - **对比方法**：CycleGAN、MUNIT、DRIT、CUT、StarGAN v2、SDEdit、ILVR、EGSDE、SDDM 等。
- **实现细节**：扩散模型采用 1000 步，训练时 DDIM 采样（50 或 100 步），使用无分类器引导，奖励估计使用 3 步蒙特卡洛。不同数据集有专属超参数（学习率、KL 权重等）。

### 4. 资源与算力
- **文中未明确说明** GPU 型号、数量及训练时长。仅提供了学习率（\(2\times10^{-5}\)）、批量大小（16）、训练步数（2000）、梯度累积（12）等超参数。因此**无法评估具体算力消耗**，但可以判断其对显存需求较高（扩散模型微调 + 条件编码器复制 + 强化学习轨迹生成）。

### 5. 实验数量与充分性
- **实验组数**：在**两个完全不同模态**的领域上进行评估，包含 **4 个数据集**（PBMC、BM、AFHQ、CelebA‑HQ），并在 AFHQ 上执行了两个方向（CAT→DOG, WILD→DOG），CelebA‑HQ 上双向（MALE↔FEMALE）。附录中还有 SNARE-seq 和更多定性结果。
- **消融实验**：研究了**引导尺度**（guidance scale）对 FID 和 SSIM 的权衡（本文图 8a），验证了 MEC 框架中的信息最大化和模态保真度平衡。
- **公平性与客观性**：对比方法均选用该领域公认的基线，指标通用，部分基线结果直接引用自原论文。DDMEC 结果报告均值和标准差（5 种子），训练和测试分离，具有一定客观性。但需注意，部分对比方法可能是几年前的成果，未包含 2024 年后的最新模型。

### 6. 论文的主要结论与发现
- DDMEC 成功将**最小熵耦合从离散拓展至连续分布**，无需几何可比性，且在两种截然不同的任务上（单细胞组学、图像翻译）取得**优于或可比**于专用方法的表现。
- 在**多组学对齐**中，DDMEC 在 PBMC 上显著超越基线，在 BM 上子类对齐最优，显示对复杂生物学数据的鲁棒性。
- 在**图像翻译**中，DDMEC 在多个方向（AFHQ, CelebA‑HQ）上取得了**最佳 FID 与高 SSIM 的平衡**，体现了生成质量与结构保真度之间的良好折中。
- 方法天然支持**双向生成**，应用灵活。

### 7. 优点
- **普适性**：无需定义域间相似性度量或几何空间，适用于图像、基因等多种模态。
- **信息论根基**：以联合熵最小化为目标，理论上收敛到互信息最大化，符合耦合直觉。
- **协作式训练**：两个对称模型互为奖励信号，训练稳定且缓解了非对称性问题。
- **利用预训练扩散模型**：可复用现有高质量无条件模型，降低训练成本并提升质量。
- **生成式框架**：输出的是分布而非确定性映射，能捕捉一对多关系。

### 8. 不足与局限
- **计算开销大**：微调扩散模型需要生成完整轨迹并多步梯度累积，训练成本显著高于某些对抗生成方法（如图像翻译中的 CycleGAN 等）。
- **依赖预训练质量**：若无条件模型未学好边缘分布，后续耦合效果受限，且预训练本身可能需要在各域单独收集足够数据。
- **理论近似性**：松弛边缘约束和联合分布一致性通过 KL 正则化近似，可能引入偏差；公式中“角色互换”是基于相等联合分布假设，仅在训练后期近似成立。
- **实验覆盖不足**：对比基线未涵盖所有最新方法（如 2024 年扩散图像翻译模型），实验仅在两任务上验证，其他连续耦合问题（如文本-图像、时间序列对齐）尚未探索。
- **超参数敏感**：引导系数、KL 权重、MC 步数等需要根据数据集调整，缺乏自适应机制。
- **潜在风险**：生成模型可能被滥用于 deepfake 等。

（完）
