---
title: Efficient Quantification of Multimodal Interaction at Sample Level
title_zh: 高效样本级多模态交互量化
authors: "Zequn Yang, Hongfa Wang, Di Hu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Ggt3iu0Zni"
tags: ["query:affective-ai"]
score: 7.0
evidence: 量化样本级多模态交互（冗余、独特、协同），可分析多模态情感动态
tldr: 针对多模态系统中交互（冗余、独特、协同）的样本级量化难题，提出基于点互信息的轻量级估计器LSMI。该方法首先构建冗余分解框架，继而利用高效熵估计实现一般交互量化。实验证明LSMI在多模态情感分析等任务中有效量化了模态交互，为理解多模态信息动态提供了理论支撑和实用工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ggt3iu0zni/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 852, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ggt3iu0zni/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1512, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ggt3iu0zni/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 836, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ggt3iu0zni/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ggt3iu0zni/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 840, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ggt3iu0zni/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 841, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ggt3iu0zni/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1658, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ggt3iu0zni/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1635, \"height\": 551, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1744, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1792, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1702, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 793, \"height\": 658, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1616, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 879, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 768, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 864, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1538, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1016, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ggt3iu0zni/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 944, \"height\": 324, \"label\": \"Table\"}]"
motivation: 多模态交互（冗余、独特、协同）的样本级量化面临理论计算挑战，缺乏精确高效的估计方法。
method: 提出基于点互信息的轻量级样本级多模态交互估计器LSMI，包含冗余分解与高效熵估计。
result: LSMI在多模态数据集上准确量化了交互，优于现有指标，计算效率高。
conclusion: 为多模态表示学习和情感分析提供了可解释的交互分析工具。
---

## Abstract
Interactions between modalities—redundancy, uniqueness, and synergy—collectively determine the composition of multimodal information. Understanding these interactions is crucial for analyzing information dynamics in multimodal systems, yet their accurate sample-level quantification presents significant theoretical and computational challenges. To address this, we introduce the Lightweight Sample-wise Multimodal Interaction (LSMI) estimator, rigorously grounded in pointwise information theory. We first develop a redundancy estimation framework, employing an appropriate pointwise information measure to quantify this most decomposable and measurable interaction.
Building upon this, we propose a general interaction estimation method that employs efficient entropy estimation, specifically tailored for sample-wise estimation in continuous distributions. Extensive experiments on synthetic and real-world datasets validate LSMI's precision and efficiency. Crucially, our sample-wise approach reveals fine-grained sample- and category-level dynamics within multimodal data, enabling practical applications such as redundancy-informed sample partitioning, targeted knowledge distillation, and interaction-aware model ensembling. The code is available at https://github.com/GeWu-Lab/LSMI_Estimator.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义
- **研究动机**：多模态数据中，模态间的交互（冗余、唯一性与协同）共同决定了信息的构成。理解这些交互对分析多模态系统的信息动态至关重要。
- **核心问题**：现有交互量化方法主要针对离散或整个分布层面，难以在连续分布下实现**样本级（sample‑level）的精确量化**，无法捕捉样本间交互模式的细粒度差异。
- **整体含义**：本文首次提出一种可应用于真实世界连续数据的**轻量级样本级多模态交互估计器 (LSMI)**，从点信息理论出发，实现高效、精确的每个样本冗余、唯一性和协同的量化，为多模态数据分析和学习提供新的可解释工具。

## 2. 方法论
LSMI 的核心思想是基于点信息分解与轻量熵估计完成样本级交互量化。

- **冗余分解框架**
  - 将点互信息 $i(x;y)$ 拆分为两个非负成分：
    - $i^+(x;y) = h(x) = -\log p(x)$（自信息）
    - $i^-(x;y) = h(x|y) = -\log p(x|y)$（条件自信息）
  - 这样 $i(x;y) = i^+ - i^-$，且两个成分均满足单调性，可在格结构上定义冗余。
  - 样本级冗余 $r$ 由两部分分别取最小值后相减得到：
    - $r^+ = \min(i^+(x_1;y), i^+(x_2;y))$
    - $r^- = \min(i^-(x_1;y), i^-(x_2;y))$
    - $r = r^+ - r^-$
  - 得到 $r$ 后，利用点互信息分解方程 $i(x_1;y) = r + u_1$、$i(x_2;y) = r + u_2$、$i(x_1,x_2;y) = r + u_1 + u_2 + s$ 解出唯一性与协同 $u_1, u_2, s$。

- **高效熵估计 (KNIFE)**
  - 采用微分熵估计器 $h_\theta$，通过对数似然上界训练：$\mathbb{E}[h_\theta(x)] \ge H(X)$，通过最小化 KL 散度逼近真实熵。
  - 利用判别模型 $p(y|x)$ 估计条件熵：$h_\theta(x|y) = h_\theta(x) - h(y) - \log p(y|x)$。
  - 流程：输入双模态数据与目标，训练两个轻量熵估计器，计算每个样本的 $h(x_1), h(x_2)$ 及条件熵，再按上述框架得到 $r, u_1, u_2, s$。

- **算法特点**：无需建模联合分布或基分布，仅需少量参数，支撑样本级高效估计。

## 3. 实验设计
论文设计了合成实验、真实数据集验证和应用三大实验板块。

- **合成数据实验**（精度验证）
  - **电路逻辑**：基于 XOR, OR, XOR+NOT 等布尔运算加高斯噪声，以解析计算的地面真值 (GT) 为基准，比较 LSMI 与 PID‑CVX 和 PID‑Batch。
  - **高斯混合**：调节模态间的相关系数 $\rho$，考察冗余和协同的变化趋势，与 GT 对比。
  - **预设交互**：手动设计仅含冗余/唯一/协同的样本并混合，检验估计器对不同交互比例的还原能力。

- **真实数据集实验**
  - **数据集**：Food‑101 (图文)、CREMA‑D (音视)、Kinetic‑Sounds (音视)、UCF‑101 (RGB+光流)、CMU‑MOSEI (视/音/文)、UR‑Funny (视/文)。
  - **对比指标**：PID‑Batch 和人类判断，展示 LSMI 给出合理的交互分布，且与人类认知高度相关。
  - **时间效率**：在所有数据集上 LSMI 时间消耗远低于 PID‑Batch，在大类别空间下优势更明显。

- **应用实验**
  - **数据划分**：利用 LSMI 计算冗余高低，分区微调 ImageBind，验证高冗余子集有利于对齐强模态。
  - **知识蒸馏**：基于样本级 $r, u, s$ 加权有选择地蒸馏教师模型信息，比直接蒸馏提升性能。
  - **模型集成**：利用各样本交互得分集成不同模型，性能优于简单加权集成。

## 4. 资源与算力
- 论文**未明确说明**所使用的 GPU 型号、数量和具体训练时长。
- 仅在时间效率对比中给出 LSMI 与 PID‑Batch 的耗时（秒），例如 UCF‑101 为 678.9 s vs. 48576.6 s，Food‑101 为 504.0 s vs. 59679.5 s，但未提及硬件平台。

## 5. 实验数量与充分性
- 实验总量充足，覆盖约 **3 类合成设置、6 个真实多模态数据集、3 种应用场景**，加上消融类实验（如多模态扩展、域偏移影响、融合阶段分析）总计约 **十余组独立实验**。
- 实验设计客观公平：合成实验提供理论地面真值，真实数据集对比现有分布级方法和人类一致性；应用任务选取多种代表性基线，从学习、蒸馏到集成多角度验证。
- 整体实验详尽地验证了方法的**精确性、效率、可解释性与实用价值**，具备充分性。

## 6. 主要结论与发现
- LSMI 能够**首次在连续分布下实现样本级多模态交互的精确高效量化**。
- 合成数据中估计值紧密贴合地面真值，优于已有分布级方法。
- 真实数据集中揭示不同类别交互偏好（如乐器具高冗余，特殊动作高协同），与人类认知一致。
- 样本级交互可用于指导**冗余感知数据分区**、**选择性知识蒸馏**和**交互感知模型集成**，均获得性能提升。
- 交互模式受融合阶段影响：早期融合倾向学习协同，晚期融合更侧重冗余。

## 7. 优点
- **新颖性**：首个针对连续分布现实数据的样本级多模态交互估计器。
- **理论基础扎实**：用点信息分量拆分解决负值不满足单调性难题，严格推导冗余。
- **高效且轻量**：仅需少量熵估计参数，大幅降低计算开销。
- **可解释性强**：直观展示每样本的冗余/唯一/协同，揭示类别和模型交互动态。
- **应用驱动**：直接支持数据策略、蒸馏和集成优化，具有实际工程价值。
- **实验丰富**：合成、真实、应用多维度验证，与多种基线对比，证据充分。

## 8. 不足与局限
- **依赖模型质量**：$p(y|x)$ 判别模型和熵估计器的准确性直接影响交互估计，若无准确预测器结果可能偏差。
- **理论适用范围**：当前分解基于两模态，多模态情况采用成对分析，缺少更高阶交互的固有分解（文中已指出）。
- **真实数据无绝对真值**：与人类判断比较时，人类评分并非直接的信息量度量，相关性的解释需谨慎。
- **熵估计器泛化**：KNIFE 在高维或复杂分布下的估计误差可能引入不确定性，论文未深入讨论高维极限。
- **算力细节缺失**：未说明实验硬件，影响复现性评估。
- **应用场景**：仅展示了分类和简单融合等任务，对生成、检索等其他多模态场景未验证。

（完）
