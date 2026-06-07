---
title: "InfMasking: Unleashing Synergistic Information  by Contrastive Multimodal Interactions"
title_zh: InfMasking：通过对比多模态交互释放协同信息
authors: "Liangjian Wen, Qun Dai, Jianzhuang Liu, Jiangtao Zheng, Yong Dai, Dongkai Wang, zhao kang, Jun Wang, Zenglin Xu, Jiang Duan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=6AbM9UG4aD"
tags: ["query:affective-ai"]
score: 8.0
evidence: 对比多模态协同信息提取用于表示学习
tldr: 针对现有多模态方法难以充分捕捉模态间协同信息的问题，提出InfMasking，一种对比式协同信息提取方法。通过无限掩码策略增强模态交互，提升多模态表示学习在需要强协同的下游任务中的表现。实验证明该方法有效捕获了模态间独有的互补信息，推动了跨模态表示学习的前沿。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-6abm9ug4ad/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 855, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6abm9ug4ad/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6abm9ug4ad/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 598, \"height\": 724, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-6abm9ug4ad/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6abm9ug4ad/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 970, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6abm9ug4ad/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 825, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6abm9ug4ad/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1010, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6abm9ug4ad/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1163, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6abm9ug4ad/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1323, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6abm9ug4ad/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 977, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6abm9ug4ad/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1470, \"height\": 324, \"label\": \"Table\"}]"
motivation: 现有多模态方法难以充分提取模态间的协同信息，限制了任务性能。
method: 提出InfMasking，一种对比协同信息提取方法，通过无限掩码策略增强模态交互。
result: 在关键任务中，InfMasking有效捕获了互补和协同信息，实现性能提升。
conclusion: 该方法为多模态学习提供了更强大的协同信息建模能力，具有广泛适用性。
---

## Abstract
In multimodal representation learning, synergistic interactions between modalities not only provide complementary information but also create unique outcomes through specific interaction patterns that no single modality could achieve alone. Existing methods may struggle to effectively capture the full spectrum of synergistic information, leading to suboptimal performance in tasks where such interactions are critical. This is particularly problematic because synergistic information constitutes the fundamental value proposition of multimodal representation. To address this challenge, we introduce InfMasking, a contrastive synergistic information extraction method designed to enhance synergistic information through an Infinite Masking strategy. InfMasking stochastically occludes most features from each modality during fusion, preserving only partial information to create representations with varied synergistic patterns. Unmasked fused representations are then aligned with masked ones through mutual information maximization to encode comprehensive synergistic information. This infinite masking strategy enables capturing richer interactions by exposing the model to diverse partial modality combinations during training. As computing mutual information estimates with infinite masking is computationally prohibitive, we derive an InfMasking loss to approximate this calculation. Through controlled experiments, we demonstrate that InfMasking effectively enhances synergistic information between modalities. In evaluations on large-scale real-world datasets, InfMasking achieves state-of-the-art performance across seven benchmarks. Code is released at https://github.com/brightest66/InfMasking.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **核心问题**：现有多模态表示学习方法往往依赖于“多视图冗余假设”，即假设各模态共享足够多的任务相关信息。然而，许多现实任务（如仇恨迷因检测、需要结合图像与文本的隐含语义）的关键在于**模态间的协同信息（synergy）**——即只有组合多个模态才能产生的互补性信息，单个模态无法单独获得。
- **研究差距**：当前方法（如FactorCL、CoMM）虽尝试捕获冗余、独特和协同三种交互，但在充分提取协同信息方面仍然有限，导致在强协同需求的任务上性能欠佳。
- **整体含义**：论文提出 **InfMasking**，旨在通过一种 **无限掩码（Infinite Masking）** 策略，系统性地增强多模态融合过程中协同信息的提取，从而提升多模态表示的质量和下游任务表现。

## 2. 方法论

### 核心思想
- 在模态特征融合前，**随机掩码（随机置零）每个模态的大部分特征**，仅保留部分信息，生成具有不同协同模式的融合表示（掩码视图）。
- 通过最大化掩码视图与未掩码完整融合表示之间的互信息，迫使模型编码全面、多样化的协同交互模式。
- 采用**无限多次随机掩码**的方式，使模型在训练中接触到几乎所有可能的局部模态组合，从而捕获更丰富的协同关系。

### 关键技术细节
- **总体损失函数**：
  \[
  \mathcal{L}_{\text{Total}} = -\hat{I}_{\text{NCE}}(Z', Z'') \;(\approx R+S+\sum U_i) \;-\; \sum_{i=1}^n \frac{1}{2}[\hat{I}_{\text{NCE}}(Z_i, Z') + \hat{I}_{\text{NCE}}(Z_i, Z'')] \;(\approx R+U_i) \;-\; \mathbb{E}_{\text{mask}}[\hat{I}_{\text{NCE}}(Z'_{\text{mask}}, Z') + \hat{I}_{\text{NCE}}(Z''_{\text{mask}}, Z'')] \;(\text{InfMasking loss})
  \]
  其中第一项对齐未掩码的增强视图，捕获所有交互类型；第二项对齐单模态与多模态表示，加强冗余与独特信息；第三项为本文提出的 **InfMasking 损失**，专门增强协同信息。

- **计算可行的InfMasking损失**：直接对无穷多种掩码采样的互信息求期望在计算上不可行。因此推导了一个**下界**：
  - 假设掩码后融合表示 \(z'_{\text{mask}}\) 服从高斯分布 \(\mathcal{N}(\mu_{z'_{\text{mask}}}, \Sigma_{z'_{\text{mask}}})\)。
  - 利用Jensen不等式和高斯矩生成函数，将掩码期望的InfoNCE转化为关于均值 \(\mu\) 和协方差 \(\Sigma\) 的解析表达式：
    \[
    \mathbb{E}_{\text{mask}}[\hat{I}_{\text{NCE}}(Z'_{\text{mask}}, Z')] \ge \mathbb{E}_{z'\sim p(Z')}\left[z'^T\mu / \tau - \log\left(e^{z'^T\mu/\tau + \frac{z'^T\Sigma z'}{2\tau^2}} + \sum_{z'_{\text{neg}}} e^{z'^T z'_{\text{neg}}/\tau}\right)\right]
    \]
  - 该下界允许仅通过估计均值与协方差来近似无穷掩码的互信息，无需实际枚举所有掩码。

### 算法流程
1. 对输入的多模态数据 \(X = (X_1, \dots, X_n)\) 分别做两次增强，得到 \(X'\) 和 \(X''\)。
2. 通过模态专属编码器提取各模态的潜在特征。
3. **三条并行路径**：
   - 所有模态特征拼接后经Transformer块得到**融合表示** \(Z', Z''\)。
   - 每个模态特征单独经Transformer得到**单模态表示** \(Z_1, \dots, Z_n\)。
   - 对每个模态特征随机掩码，拼接后经Transformer得到**掩码融合表示**，重复 \(k\) 次（实际实现中近似无穷大）得到 \(Z'^1_{\text{mask}}, \dots, Z'^k_{\text{mask}}\) 及对应 \(Z''\)。
4. 按总损失函数进行优化。

## 3. 实验设计

### 数据集与场景
- **合成数据集**：Trifeature，人工定义形状（冗余）、纹理（独特性）及纹理-颜色映射（协同），用于可控评估三类交互的捕获能力。
- **真实多模态数据集**（来自MultiBench）：
  - 双模态：
    - MIMIC（表格+时间序列，疾病分类）
    - MOSI（文本+视频，情感分析）
    - UR-FUNNY（文本+视频，幽默检测）
    - MUSTARD（文本+视频，讽刺检测）
    - Vision&Touch（视觉+本体感受，接触预测与末端位置回归）
  - 三模态：Vision&Touch（视觉+力+本体感受）、UR-FUNNY（视觉+文本+音频）。
- **多标签电影分类**：MM-IMDb（图像海报+文本剧情，23类）。

### 对比方法
- 双模态：Cross（仅跨模态InfoNCE）、Cross+Self、FactorCL、MAE、CoMM。
- 三模态：CMC、CoMM。
- MM-IMDb：SimCLR（单视觉）、CLIP（单/多模态）、SLIP、CoMM。

### 评估指标
- 线性探测（冻结预训练主干，训练线性分类器/回归器），使用准确率、MSE、加权/宏观F1分数。

## 4. 资源与算力

- 所有实验均在一块 **NVIDIA 4090 GPU（24 GB显存）** 上运行。
- 训练轮次因数据集而异（例如Trifeature 100个epoch，MM-IMDb 70个epoch），但论文未明确给出每个实验的具体训练时长（墙钟时间），因此无法精确估计总计算开销。
- 单个模型训练的内存消耗因掩码视图数 \(M'\) 和Transformer层数不同而变化，文中未提供精确的显存占用量。

## 5. 实验数量与充分性

- **实验组数概览**：
  - 合成实验：1个数据集 × 多个交互维度（冗余、独特、协同） × 多组对照方法。
  - 真实双模态：~5个任务（分类/回归）。
  - 真实三模态：2个任务。
  - MM-IMDb：1个大规模多标签任务。
  - 消融实验：损失函数组合（4种配置）、掩码视图数（2–10）、掩码比例（0.1–0.9）。
  - 额外消融：数据增强的影响、与MAE重建损失的对比。
- **充分性评价**：实验覆盖了合成与真实、双模态与三模态、分类与回归、平衡与不平衡标签等多种场景，并系统探讨了关键超参数。所有结果均提供5次随机运行的平均值和标准差，确保了统计可靠性。对比方法选取了当前主流基线，且部分已复现或引用自原论文，整体评估较为**客观、公平**。

## 6. 主要结论与发现

- InfMasking在捕获**协同信息**上显著优于现有方法（如CoMM）。在Trifeature合成数据中，协同准确率从71.4%提升至77.0%，冗余信息与独特性也保持领先。
- 在多个真实多模态基准上，InfMasking**均取得最优结果**，尤其在需要深度融合的任务（如MOSI、MUSTARD）上提升明显。
- 三模态场景下，InfMasking性能进一步提升，说明方法可有效扩展至更多模态。
- 消融实验证明：
  - 全部三项损失项共同作用才能达到最佳协同效果。
  - 掩码视图数在6–10之间性能稳健；过高的掩码比例（≥70%）更有利于学习互补信息。
  - 数据增强（尤其是裁剪）对学习独特性与协同性至关重要。

## 7. 优点

- **新颖的理念**：将掩码策略从重建/增强范式引入对比学习，针对性增强协同交互，弥补了现有方法的不足。
- **理论推导严谨**：基于信息分解框架，并推导了可高效计算的InfMasking损失下界，使得无穷掩码在数学上有据可循。
- **实验全面扎实**：覆盖合成到真实、双模态到三模态，且包含系统性的消融和对比，结果可靠，具有统计显著性。
- **代码开源**：易于复现和社区验证。

## 8. 不足与局限

- **计算开销较大**：掩码视图数增大会线性增加GPU内存占用与计算量，虽通过下界近似无需实际采样无穷多次，但实际训练中仍需 \(M'\) 次前向传播，可能限制在大规模预训练或设备受限场景下的使用。
- **理论深度有限**：论文承认“缺乏严格的理论框架来系统分析协同交互的机制”，目前对为什么无限掩码能捕获协同信息缺乏更深层的理论支撑。
- **掩码策略的适应性**：掩码比例和视图数均为固定超参数，未根据任务或模态动态调整，可能在某些场景下存在次优配置。
- **实验覆盖面**：虽然包含多个真实数据集，但仅限于论文选定的基准，并未在更广泛的领域（如医疗影像、自动驾驶）中进行验证；此外，未与最新的大规模多模态模型（如CLIP后续变体）的直接比较，可能影响成果的普适性宣称。
- **社会影响与偏差**：方法依赖于训练数据，如果数据本身存在偏见，模型可能放大这些偏见；论文在附录中对隐私和公平性进行了简要讨论，但未进行专门的偏差评估实验。

（完）
