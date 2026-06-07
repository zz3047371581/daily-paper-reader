---
title: Multi-modal contrastive learning adapts to intrinsic dimensions of shared latent variables
title_zh: 多模态对比学习适应共享潜在变量的内在维度
authors: "Yu Gui, Cong Ma, Zongming Ma"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sCgYsBVIVG"
tags: ["query:affective-ai"]
score: 5.0
evidence: 多模态对比学习理论分析揭示其对数据内在维度的适应性
tldr: 针对多模态对比学习的表示性质，从理论上分析了温控优化如何使其适应数据内在维度，从而最大化互信息并提高表示效率。合成与真实数据实验验证了理论。该发现为指导高效多模态表示学习提供了理论基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1158, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1388, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1392, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1373, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1158, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1421, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1421, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1417, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1407, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1419, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-scgysbvivg/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1159, \"height\": 403, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-scgysbvivg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1685, \"height\": 1050, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-scgysbvivg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1417, \"height\": 259, \"label\": \"Table\"}]"
motivation: 多模态对比学习的内在表示机制尚不清晰。
method: 通过理论分析揭示温控优化下的维度适应性。
result: 学习到的表示能适应远低于设定维度的内在维度。
conclusion: 为多模态对比学习的有效训练提供了理论解释。
---

## Abstract
Multi-modal contrastive learning as a self-supervised representation learning technique has achieved great success in foundation model training, such as CLIP~\citep{radford2021learning}. 
In this paper, we study the theoretical properties of the learned representations from multi-modal contrastive learning beyond linear representations and specific data distributions. 
Our analysis reveals that, enabled by temperature optimization, multi-modal contrastive learning not only maximizes mutual information between modalities but also adapts to intrinsic dimensions of data, which can be much lower than user-specified dimensions for representation vectors. 
Experiments on both synthetic and real-world datasets demonstrate the ability of contrastive learning to learn low-dimensional and informative representations, bridging theoretical insights and practical performance.

---

## 论文详细总结（自动生成）

# 多模态对比学习适应共享潜在变量的内在维度——论文总结

## 1. 核心问题与整体含义
- **研究动机**：多模态对比学习（如CLIP）在基础模型训练中取得巨大成功，但现有理论分析多局限于线性表示或特定数据分布，无法解释实践中观察到的现象，例如：学习到的表示维度远低于用户设定的输出维度，温度参数τ在训练中收敛至零等。
- **核心问题**：本文旨在从理论上揭示，在温度参数优化的条件下，多模态对比学习如何自动适应数据的**内在维度**（intrinsic dimension），而不仅仅是最大化互信息或均匀对齐。
- **整体含义**：通过理论证明和实验验证，说明对比学习能够在无需事先知道真实内在维度的情况下，学习到低维且信息充分的共享表示，从而弥合理论认知与实践表现之间的差距。

## 2. 方法论
- **核心思想**：将InfoNCE损失分解为负互信息与两个KL散度项之和：
  \[
  L(f,g,\tau) = -2I(f(X);g(Y)) + D_{KL}(P||Q_{f,g,\tau}) + D_{KL}(P||\tilde{Q}_{f,g,\tau})
  \]
  其中\(Q_{f,g,\tau}, \tilde{Q}_{f,g,\tau}\)为平滑后的联合分布。最小化损失等价于同时最大化互信息和最小化KL散度（促使联合分布在支持集上分散）。
- **关键技术细节**：
  - **对齐与相似度最大化**：定义集合\(\mathcal{A}(\mathcal{H})\)，要求归一化后表示几乎处处相等，且正样本对相似度达到本质最大值\(m_\sigma\)。
  - **最大互信息**：为解决连续表示导致互信息无限的问题，引入离散化序列\(M\to\infty\)，定义集合\(\mathcal{W}(\mathcal{H})\)为渐近达到各离散化水平下最大互信息的表示对。
  - **理想表示集**：\(\mathcal{V}(\mathcal{H}) = \mathcal{A}(\mathcal{H}) \cap \mathcal{W}(\mathcal{H})\)，并证明当\(\mathcal{V}(\mathcal{H})\neq\emptyset\)时，所有理想表示具有相同的内在维度\(k^*\)。
  - **内在维度（ID）**：定义为存在可测函数\(h\)使\(f = \phi \circ h\)且\(\dim(\mathcal{R}(h)) = k\)的最小整数\(k\)。
  - **温度优化下的近似最小化元**：引入温度阈值\(\varepsilon(\eta)\)，定义集合\(\mathcal{O}_{L,\eta}(\mathcal{H})\)仅包含满足温度不小于\(\varepsilon(\eta)\)且离散化损失与\(-2I_M^*(\mathcal{H})\)差距不超过\(2\eta\)的表示。所有\(\eta>0\)的交集为真正的极小化元集。
- **主要定理（Theorem 2）**：若\(\mathcal{V}(\mathcal{H})\neq\emptyset\)，则交集非空；且其中任意\((f,g)\)满足：
  1. 相似度最大化：\(\sigma(f(X),g(Y)) = m_\sigma(f,g)\)几乎处处成立；
  2. 内在维度自适应：\(\text{ID}(f) = \text{ID}(g) = k^*\)；
  3. 损失随温度单调递增；
  4. 互信息最大化：\((f,g)\in\mathcal{W}(\mathcal{H})\)。

## 3. 实验设计
- **数据集**：
  - **合成数据**：线性设定（共享前\(k^*\)维标准正态）与非线性设定（包含多项式、三角函数等非线性变换），\(k^*=5, d_1=d_2=20\)。
  - **真实数据**：
    - **CITE‑seq骨髓细胞数据**：24维蛋白质 + 200维RNA，下游任务为两种粒度细胞类型的分类准确率和top‑α%匹配准确率。
    - **ImageNetV2**：图像+文本标签，使用预训练ViT‑L14和Transformer提取特征后再训练CLIP，下游任务为图像分类和top‑α%匹配。
    - **YFCC子集**：图像+文字描述，9级类别标签，下游任务类似。
- **模型与基准**：
  - 编码器统一使用5层ReLU神经网络，中间层宽度50，输出维度\(d\)变化。
  - 相似度度量采用经总体范数期望归一化的内积（实验中证明与余弦相似度效果相当）。
  - 对比方法：无明确对比其他方法，主要验证自身在不同输出维度下的饱和行为。
- **评估指标**：
  - 内在维度估计：使用MLE方法（skdim.id包）。
  - 下游准确率：top‑α%匹配准确率及分类准确率。
  - 温度收敛性及相似度分布直方图。

## 4. 资源与算力
- 论文未明确说明使用的GPU型号、数量或训练总时长。
- 仅提及“small‑scale experiments that can be operated on local laptops”（NeurIPS Checklist第8条），因此实验规模较小，运算资源需求低。
- 合成数据训练集大小12000（或10000），真实数据训练集8000~10000不等，epoch数为800，学习率\(10^{-4}\)，权重衰减\(10^{-4}\)，温度学习率略高（合成\(10^{-3}\)，真实\(2\times10^{-4}\)）。

## 5. 实验数量与充分性
- **实验组数**：
  - 合成数据：线性设定与非线性设定各1组，每组输出维度从1到30左右变化，重复50次取平均。
  - CITE‑seq：输出维度从1到29，50次重复。
  - ImageNetV2和YFCC：类似设置，输出维度变化，50次重复。
  - 消融实验：
    - 相似度度量对比（内积vs余弦相似度）。
    - \(V(\mathcal{H})=\emptyset\)情况实验（2层ReLU，无法对齐）。
    - Transformer编码器替代5层ReLU的消融（CITE‑seq上小规模验证）。
    - 收敛性验证：温度、相似度、范数分布的直方图及散点图。
- **充分性与公平性**：
  - 实验覆盖合成、单细胞组学、图像‑文本等多种数据类型，比较全面。
  - 每个条件下多次重复并报告平均值（图中体现为标准差/误差棒），保证了统计可靠性。
  - 实验设置客观，未发现明确的对比不公平之处；主要结论与理论预测高度一致。

## 6. 主要结论与发现
- 多模态对比学习通过温度优化，能够自动适应数据的**内在维度**\(k^*\)：无论输出维度\(d\)如何设置（只要\(d \geq k^*\)），学习到的表示的内在维度趋近于\(k^*\)，且下游任务准确率饱和。
- 理想表示集\(\mathcal{V}(\mathcal{H})\)非空时，全局极小化解必然满足相似度最大化、互信息最大化、内在维度恰好为\(k^*\)，且温度趋于零。
- 当表示维度正确设定为\(d^* = \mathcal{D}(k^*,\mathcal{H})\)时，极小化解恰为对齐且均匀分布的超球面表示。
- 实验现象验证：正样本相似度集中在常数，负样本相似度被该常数限制；温度训练中收敛至零；估计的内在维度不随输出维度增加而无限增长。

## 7. 优点
- **理论突破**：首次在一般函数类和任意数据分布下，揭示温度优化使对比学习适应内在维度的机制，并严格证明了极小化元的理想性质。
- **概念细化**：通过离散化定义了可比较的互信息概念，解决了连续表示下互信息无限的问题；引入温度阈值集\(\mathcal{O}_{L,\eta}\)避免平庸的\(\tau=0\)解。
- **解释力强**：成功解释实践中观察到的维度选择、温度收敛、相似度常量等现象，并提供了与充分维度归约（SDR）的联系。
- **实验验证充分**：覆盖多种数据类型和任务，重复次数多，并进行了多个消融对比，支撑理论可信度。

## 8. 不足与局限
- **假设前提敏感**：所有主要结论依赖于\(\mathcal{V}(\mathcal{H}) \neq \emptyset\)，但未提供在何种条件下该假设成立的理论判据；实验部分通过训练来间接验证，但缺乏先验保证。
- **温度阈值的构造性不足**：\(\varepsilon(\eta)\)的定义基于存在性（集合\(\mathcal{C}^*\)），未给出具体计算方式，在实际算法中难以直接设置。
- **模型容量与函数类未讨论**：理论分析假定函数类包含所有可测函数，而实验中使用的5层ReLU网络容量有限，未分析逼近误差对内在维度适应性的影响。
- **实验规模较小**：仅在较小数据集和浅层网络上验证，未在大规模预训练（如原始CLIP规模）下测试，结论泛化性存疑。
- **下游任务评估有限**：仅使用top‑α%匹配和简单分类，未评估更复杂的迁移学习或零样本任务性能。
- **资源与算力信息缺失**：未说明具体硬件和耗时，影响复现评估。

（完）
