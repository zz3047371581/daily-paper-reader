---
title: Disentangled Cross-Modal Representation Learning with Enhanced Mutual Supervision
title_zh: 增强互监督的解耦跨模态表示学习
authors: "Lu Gao, Wenlan Chen, Daoyuan Wang, Fei Guo, Cheng Liang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sFyTsO2qO3"
tags: ["query:affective-ai"]
score: 8.0
evidence: 通过互监讲解耦跨模态共享与特有表示以改善对齐
tldr: 跨模态表示学习旨在从图像、文本等异构模态中提取语义对齐的表示，但现有变分自编码器方法常难以有效分离模态共享与特有因子。本文提出 DCMEM 框架，通过增强互监督机制，使模型能从每个模态中解耦出共有和独特信息，并相互约束共享表示。结合信息瓶颈，进一步滤除噪声。实验证明，该方法在跨模态检索和分类等任务上取得优异效果，为解耦表义学习提供了新路径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
motivation: 多模态 VAE 模型难以对齐异构模态，且缺乏清晰分离共有和特有信息的机制。
method: 提出 DCMEM，在 VAE 中引入共有-特有解耦，并通过跨模态互监督正则化共享表示。
result: 在图像-文本跨模态任务上，DCMEM 提升了对齐质量和下游任务性能。
conclusion: 显式解耦跨模态信息并互监督是有效的表示学习策略，可应用于多模态理解任务。
---

## Abstract
Cross-modal representation learning aims to extract semantically aligned representations from heterogeneous modalities such as images and text. Existing multimodal VAE-based models often suffer from limited capability to align heterogeneous modalities or lack sufficient structural constraints to clearly separate the modality-specific and shared factors. In this work, we propose a novel framework, termed **D**isentangled **C**ross-**M**odal Representation Learning with **E**nhanced **M**utual Supervision (DCMEM). Specifically, our model disentangles the common and distinct information across modalities and regularizes the shared representation learned from each modality in a mutually supervised manner. Moreover, we incorporate the information bottleneck principle into our model to ensure that the shared and modality-specific factors encode exclusive yet complementary information. Notably, our model is designed to be trainable on both complete and partial multimodal datasets with a valid Evidence Lower Bound. Extensive experimental results demonstrate significant improvements of our model over existing methods on various tasks including cross-modal generation, clustering, and classification.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究背景**：跨模态表示学习旨在从图像、文本等异构数据中提取语义对齐的共享表示。多模态变分自编码器（VAEs）是主流方法，但存在两个主要痛点：
  - 对异构模态的对齐能力有限；
  - 缺乏足够结构约束来清晰分离模态共享与模态特有信息。
- **核心问题**：如何在变分框架下同时实现 **共享‑特有因素的有效解耦** 和 **跨模态语义高度对齐**，并能在部分缺失模态的场景下稳健训练。
- **整体含义**：提出 **DCMEM**（增强互监督的解耦跨模态表示学习），通过互监督与信息瓶颈原则，显式解耦跨模态的共有与独有信息，并利用互信息最大化促进共享空间对齐，最终提升生成、聚类、分类等下游任务表现。

## 2. 方法论
- **核心思想**
  - 为每个模态引入 **共享隐变量**（`zs`, `zt`）和 **模态特有隐变量**（`ws`, `wt`），分别捕捉跨模态一致性信息和各模态私有特征。
  - 通过 **双向互监督**（`s → zs → t` 和 `t → zt → s`）实现语义对齐，同时用信息瓶颈原则强制共享与特有变量间信息互补、无冗余。
- **关键技术细节**
  - **变分下界（ELBO）推导**：基于生成过程 `p(t,s,zs,ws)` 和因式化后验 `q(zs,ws|s,t)`，得到包含重要性权重 `qφ(t|zs)/qϕz,φ(t|s)` 的 ELBO（公式 2）。重要性权重调节采样分布与真实条件分布的偏差，并采用 stop‑gradient 稳定训练。
  - **结构化表示学习**：引入互信息项 `max I(zs;t;s) - I(zs;ws)`，经分解变成 `I(s;zs,ws) - I(s;ws) - I(zs;s|t)`（公式 3）。第一项用重构下界近似，第二项天然包含于 ELBO，第三项用共享隐空间的 KL 散度近似 `-Ep[DKL(qϕz(zs|s)||qψz(zt|t))]`（公式 5）。
  - **互监督双向训练**：交替构造 `L{Φ,Ψ}(s,t)` 和 `L{Ψ,Φ}(s,t)`（交换编解码参数的角色），形成双向目标 `LBi(s,t)`。
  - **共享表示对齐**：额外加入 **共享隐变量互信息最大化** 项 `α I(zs;zt)`，并用对比学习（batch 内余弦相似度 + 交叉熵）近似优化。
  - **部分缺失模态处理**：利用 VampPrior 思想，从未缺失模态构建混合先验（如 `pus(zs) = 1/B ∑ pψz(zs|uti)`），使得仅有一模态时仍能通过先验对齐到另一模态，推导出单模态 ELBO（公式 11、12）。
  - **总体目标**：三种数据（完全配对、仅 s、仅 t）的下界之和（公式 13），训练流程详见算法 1。
- **公式/算法文字描述**
  - **ELBO**：最大化 `log p(t,s)` 的下界，包含重构项、KL 正则、重要性权重与条件 log 项。
  - **互信息分解**：通过链式法则将 `I(zs;t;s) - I(zs;ws)` 转化为可计算的重构损失和跨模态 KL 散度。
  - **互监督**：双向路径约束，使每个模态的共享隐变量既要能重建另一模态，又要被对方共享隐变量正则。
  - **缺失模态**：用一批锚点构造缺失模态的近似先验，实现单模态情况下的有意义的隐空间正则。

## 3. 实验设计
- **数据集与场景**
  - **MNIST‑SVHN**：10 类数字，MNIST（手写）与 SVHN（街景）配对，评估生成与对齐。
  - **CUBICC**：8 类鸟类图像与文本描述，更复杂的跨模态场景。
  - **Human Breast Cancer 空间转录组**：20 类空间标签，包含基因表达、空间坐标、组织形态多模态数据，用于域识别聚类。
  - 所有数据集均支持 **部分缺失模态** 实验（缺失比例 η = 0.25, 0.5, 0.75）。
- **对比方法（Benchmark）**
  - 八大多模态 VAE：MVAE、MMVAE、MoPoE、MEME、MMVAE+、CMVAE、MMVM、MVP。
  - 针对空间数据还对比了 Scanpy、STAGATE、GraphST、SiGra、xSiGra 等专用聚类方法。
- **评估指标**
  - **生成**：生成质量（FID）、连贯性（预训练分类器准确率）。
  - **聚类**：ACC、NMI、ARI，基于共享或联合隐表示。
  - **分类**：线性分类器准确率（尤其在不同缺失率下）。

## 4. 资源与算力
- 使用 **单个 NVIDIA GeForce RTX 2080 Ti** GPU，64 GB RAM。
- **训练时长**：
  - MNIST‑SVHN：约 8 小时/run，9 方法 × 3 种子 ≈ 216 GPU 小时。
  - CUBICC：约 16 小时/run，9 方法 × 3 种子 ≈ 432 GPU 小时。
  - 乳腺癌：约 2 小时/run，14 方法 × 3 种子 ≈ 84 GPU 小时。
- 总计核心实验约 **732 GPU 小时**，另有调参额外时间。

## 5. 实验数量与充分性
- **实验丰富度**：
  - 三个不同性质的数据集，覆盖图像‑图像、图像‑文本、空间多模态。
  - 生成、聚类、分类三大类下游任务，并考察缺失模态鲁棒性（3 种缺失率 × 2 种缺失模态方向）。
  - 消融实验（移除结构化学习、移除共享对齐），参数量分析（α 从 0.01 到 100）。
  - 语义相关性与类条件距离分析（2‑Wasserstein 直方图、热图），定性生成样本展示，变模态特有变量可视化。
- **公平性**：所有方法使用原作者架构与默认参数，多次运行（3 次随机种子），报告标准差。
- **完整性**：对比了 VAE 基线 9 种（含最新 2024‑2025 方法），空间数据还额外对比 5 种专用聚类方法，消融覆盖关键组件。实验设计充分、客观。

## 6. 主要结论与发现
- DCMEM 在所有任务（生成连贯性与质量、聚类、分类）上 **一致超越** 对比方法。
- 在缺失模态场景下表现 **更稳健**，即使仅保留 25% 配对数据，仍能维持高聚类和分类准确率，基线方法则普遍大幅下降。
- 消融表明，结构化表示学习（信息瓶颈推动解耦）和共享对齐（互信息最大化）都是性能关键组件。
- 学到的共享隐空间具有良好的 **语义对齐** 与 **类内紧凑性**，类间分离度优于其他方法。

## 7. 优点
- **方法论创新**：将互监督、信息瓶颈与显式解耦结合，推导出完整的变分目标，兼具理论与实用性。
- **缺失模态原生支持**：无需特殊处理即可在部分配对数据上训练，扩展性强。
- **多任务统一框架**：同时支撑高质量生成、聚簇与分类，且通过参数 α 平衡。
- **实验扎实**：大量定量结果、可视化分析、鲁棒性测试，对比方法多且公平。
- **广阔应用前景**：在生物医学空间组学数据上验证，体现跨领域潜力。

## 8. 不足与局限
- **仅限双模态**：方法设计针对两个模态，扩展到三个及以上模态需要非平凡改进。
- **生成与聚类权衡**：模型需在保留细节（生成）和抽取类级特征（聚类）间平衡，单项极致并非最优。
- **数据集规模与场景**：主要在标准中小数据集上测试，未见更大规模或更复杂真实场景（如视频‑文本、多模态对话）的验证。
- **计算开销**：双向训练、对比损失等增加额外计算，时间成本高于简单联合 VAE。
- **缺失模态先验依赖**：VampPrior 效果受限于锚点选择与批次内多样性，极端缺失时可能退化。
- **可解释性**：解耦程度未直接量化，缺乏独立指标证明共享与特有信息完全分离。

（完）
