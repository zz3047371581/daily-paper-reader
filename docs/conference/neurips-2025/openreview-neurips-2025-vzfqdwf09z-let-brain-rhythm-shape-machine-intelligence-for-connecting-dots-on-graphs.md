---
title: Let Brain Rhythm Shape Machine Intelligence for Connecting Dots on Graphs
title_zh: 让脑节律塑造机器智能：连接图上的点
authors: "Jiaqi Ding, Tingting Dan, Zhixuan Zhou, Guorong Wu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vZfqDwF09z"
tags: ["query:affective-ai"]
score: 4.0
evidence: 利用脑节律原理和神经耦合设计图学习算法
tldr: 神经科学中的节律协调机制为高效鲁棒的机器学习提供了设计灵感。本文提出物理信息驱动的深度学习框架，通过Kuramoto模型识别脑节律，并将神经耦合原理迁移到图学习任务中。实验表明，该脑启发方法在图数据上有效提升了模型的效率和鲁棒性。该工作为桥梁大脑机制与人工智能提供了新设计原则。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vzfqdwf09z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 986, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vzfqdwf09z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vzfqdwf09z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1428, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vzfqdwf09z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vzfqdwf09z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vzfqdwf09z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 714, \"height\": 381, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vzfqdwf09z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1128, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vzfqdwf09z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1413, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vzfqdwf09z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1400, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vzfqdwf09z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1382, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vzfqdwf09z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 499, \"height\": 188, \"label\": \"Table\"}]"
motivation: 将神经振荡的节律协调机制转化为设计下一代高效鲁棒机器学习模型的原则。
method: 提出物理信息驱动的深度学习框架，利用Kuramoto模型识别脑节律。
result: 在图任务上验证，方法提升了模型效率和鲁棒性。
conclusion: 脑节律建模为脑启发式机器学习提供了新颖且有效的设计准则。
---

## Abstract
In both neuroscience and artificial intelligence (AI), it is well-established that neural “coupling” gives rise to dynamically distributed systems. These systems exhibit self-organized spatiotemporal patterns of synchronized neural oscillations, enabling the representation of abstract concepts. By capitalizing on the unprecedented amount of human neuroimaging data, we propose that advancing the theoretical understanding of rhythmic coordination in neural circuits can offer powerful design principles for the next generation of machine learning models with improved efficiency and robustness. To this end, we introduce a physics-informed deep learning framework for \underline{B}rain \underline{R}hythm \underline{I}dentification by \underline{K}uramoto and \underline{C}ontrol (coined \textit{BRICK}) to characterize the synchronization of neural oscillations that shapes the dynamics of evolving cognitive states.  Recognizing that brain networks are structurally connected yet behaviorally dynamic, we further conceptualize rhythmic neural activity as an artificial dynamical system of coupled oscillators, offering a shared mechanistic bridge to brain-inspired machine intelligence. By treating each node as an oscillator interacting with its neighbors, this approach moves beyond the conventional paradigm of graph heat diffusion and establishes a new regime of representation compression through oscillatory synchronization. Empirical evaluations demonstrate that this synchronization-driven mechanism not only mitigates over-smoothing in deep GNNs but also enhances the model’s capacity for reasoning and solving complex graph-based problems.

---

## 论文详细总结（自动生成）

## 一、论文的核心问题与整体含义

- **研究背景与动机**  
  神经科学和人工智能均表明神经“耦合”可产生动态分布式系统，这些系统通过自组织的神经振荡节律实现抽象概念表征。然而，现有图神经网络（GNN，如 GCN、Graph Transformer）在信息传播时多采用图热扩散机制，容易造成节点表示同质化（过度平滑）和信息稀释，限制了深层网络的表达能力和推理能力。

- **核心问题**  
  论文旨在将生物脑的节律协调机制（振荡同步）转化为新一代图机器学习的设计原则，从而在增强模型效率与鲁棒性的同时，缓解深层 GNN 的过度平滑问题，并提高图推理能力。为此，论文提出了两个紧密关联的模型：**BRICK**（面向脑节律识别的物理信息深度学习框架）和 **BIG-NOS**（面向一般图学习的脑启发式图神经振荡同步框架）。

## 二、方法论

- **整体思想**  
  将人脑网络和图结构化数据均视为 Kuramoto 振子耦合的动态系统。节点（脑区或图节点）作为振子，通过正弦耦合项实现相位同步，从而产生稳定的聚类表示，替代传统的图热扩散机制。这种振荡同步在保持信息差异性的同时实现了压缩和结构化表示。

- **BRICK 的关键技术**  
  - **向量化神经振荡器**：使用几何散射变换（GST）从 BOLD 信号中提取多频率成分，将每个脑区的标量信号升维为多尺度向量，构成振荡器状态 \(\hat{x}_i\in\mathbb{R}^H\)。  
  - **带记忆注意的控制项**：引入全局最优反馈控制信号 \(y_i\)，通过可学习的网络 \(\Gamma_\mu\) 生成，模拟认知控制中“记忆引导的注意力”机制，使得振荡器能够根据任务需求动态调整同步。  
  - **物理约束与稳定性**：演化方程 \[ \frac{d\hat{x}_i}{dt}= \omega_i + \tau\cdot\phi_{\hat{x}_i}\Big(y_i+\sum_j w_{ij}\hat{x}_j\Big) \] 可解释为能量泛函的梯度流，保证了系统的 Lyapunov 稳定性，防止发散。  
  - **数值求解器**：采用前向欧拉步骤循环进行耦合聚合、切空间投影、相位更新和流形重归一化（Algorithm 1），最终输出振荡器状态和控制器。

- **BIG-NOS 的图学习迁移**  
  - 将 BRICK 的物理架构无缝迁移到一般图：图节点作为振子，邻接矩阵视作耦合强度矩阵。  
  - 用 Kuramoto 振荡同步替代图热扩散方程 \(\frac{\partial X}{\partial t}=\nabla\cdot(\nabla X)\)，避免全局平均导致的过度平滑。  
  - 同样引入任务相关的反馈控制信号 \(Y\)，作为可学习的图注意力/控制场，动态调节耦合强度，以提升对同质和异质图的适应能力。  
  - 网络结构：初始节点嵌入通过 GCN 等编码器得到初始控制项，后续通过 Algorithm 1 迭代更新节点振荡状态。

## 三、实验设计

- **脑数据实验（BRICK）**  
  - **数据集**：  
    - HCP‑Aging (HCP‑A): 717 名被试，4 种认知任务，300 时间点 fMRI，116 脑区 (AAL 图谱)。  
    - HCP‑Young Adults (HCP‑YA): 7 种任务（运动、关系、社会等），175 时间点，116 脑区。  
    - HCP‑Working Memory (HCP‑WM): 8 类条件（2‑back/0‑back × 4 刺激类型），405 时间点；扩展至 246 脑区 (Brainnetome 图谱)。  
  - **任务与基线**：4/7/8 类认知状态分类。对比方法包括 GCN、GAT、GIN、GCNII、GraphSAGE、SAN、GRAND、GTN、GraphCON、KuramotoGNN。  
  - **其他测试**：无监督脑功能分区（对比谱聚类）、推断时间消融、GST 超参数分析。

- **图数据实验（BIG-NOS）**  
  - **节点分类**：  
    - 异质图：Texas, Wisconsin, Actor, Squirrel, Chameleon, Cornell (同质率 \(h\) 0.11‑0.3)  
    - 同质图：Citeseer, Pubmed, Cora (\(h\) 0.57‑0.81)  
    - 大规模图：ogbn‑arxiv (169,343 节点，40 类)  
  - **图分类**：ENZYMES、PROTEINS (TUDataset)  
  - **基线**：GCN, GIN, GAT, GCNII, GraphSAGE, SAN, GRAND, GTN, GraphCON, KuramotoGNN，以及 OGB 榜单前两名 BiGTex、SimTeG+TAPE+RevGAT。  
  - **评价指标**：准确率、加权精确率、F1 分数；采用标准的半监督划分或 10 折交叉验证，报告均值和标准差。

- **抗过平滑验证**  
  在 Cora 和 Citeseer 上增加层数（4 至 128 层），观察性能稳定性，验证 BIG-NOS 不过早出现平滑退化。

## 四、资源与算力

- **文中未明确说明**  
  论文仅给出了部分超参数（如隐藏维度 256、BRICK 深度 16、批大小 256），以及推断时间（每被试毫秒级），但**没有提供**训练所使用的 GPU 型号、数量、显存大小或总训练时长等计算资源细节。因此无法评估该方法在硬件上的绝对开销。

## 五、实验数量与充分性

- **实验覆盖范围**  
  论文进行了三类主要实验：
  1. **脑状态识别**：3 个人类脑数据集 × 7 种以上对比方法，共数十组对比；  
  2. **图节点分类**：9 个标准数据集 × 11 种模型，各多次重复；  
  3. **图分类**：2 个数据集 × 多模型对比；  
  4. **深度抗平滑实验**：2 个数据集，层数从 4 到 128；  
  5. **无监督分区、消融研究（GST 阶数/层数）与推断效率对比**。  
  总计约超过 50 组独立实验配置。

- **客观性与公平性**  
  - 所有对比均采用公开基准和标准评估协议（如固定数据划分、交叉验证）。  
  - 在同质和异质图上分别测试，排除了对某种图结构的偏向。  
  - 统计检验采用配对 \(t\) 检验并标注显著性 (\(p<0.001\))。  
  - 超参数细节在附录中提供，增强可复现性。  
  整体来看，实验设计较为全面、客观且公平，能有效支撑论文主张。

## 六、主要结论与发现

- **脑节奏识别方面**：BRICK 在所有 HCP 数据集上均显著优于传统 GNN 模型，能捕捉到任务特异性的脑区相位同步模式，且其振荡器状态在深层中展现出与认知功能网络高度一致的空间聚类，证明模型具有生物可解释性。  
- **图学习方面**：BIG-NOS 在异质图上取得最优或次优性能（平均准确率 69.2%），在同质图上与先进方法持平；在大规模 ogbn‑arxiv 上准确率达到 86%，仅次于榜首模型；在图分类任务中也展现竞争性。  
- **抗过平滑**：在深度增加到 128 层时，BIG-NOS 依然保持高分类性能，验证了振荡同步机制能够从根本上抵抗传统 GNN 的过度平滑问题。  
- **机制解读**：耦合振荡器的相位同步对节点特征进行结构性“聚类压缩”，而非单纯平均，这一过程自然地保留了类别差异信息，并从控制论角度引入任务适应的调控场。

## 七、优点

- **生物与物理机制深度融合**：首次将脑节律的 Kuramoto 模型与记忆注意控制有机融入深度图学习，提供了清晰的理论桥接。  
- **双重框架统一**：BRICK 为神经影像分析提供物理信息指导，而 BIG-NOS 将同一原理泛化为通用图学习组件，跨域复用性强。  
- **有效对抗过度平滑**：在极深网络（128 层）上表现稳定，突破了传统 GNN 的深度限制。  
- **异质图性能突出**：依靠振荡同步而非单纯的特征相似性，在邻居特征不一致的图上表现出色，显示了机制的通用性。  
- **可解释性**：通过可视化振荡器相位聚类，能在无监督条件下反映脑功能网络结构，为认知状态提供直观的生物学解读。  
- **实验全面性**：涵盖脑状态解码、节点分类、图分类、效率、消融等，充分验证了有效性。

## 八、不足与局限

- **计算效率瓶颈**：BIG-NOS 依赖迭代的几何投影和振子更新，每 batch 计算开销显著大于前馈 GNN，在 TUDataset 等图分类数据上规模化受限。  
- **硬件资源未披露**：训练算力及时间成本模糊，不利于读者评估实际部署的可行性。  
- **超参数敏感性未深入讨论**：虽然进行了 GST 消融，但对控制项权重 \(\tau\)、耦合可重加权矩阵 \(S\) 的初始化等对性能的影响未作详细分析。  
- **应用场景偏向**：主要实验集中于静态节点/图分类和认知状态识别，尚未在动态图、时序预测或更复杂生成任务上验证。  
- **对比方法局限**：虽然对比了多种 GNN，但未包括最新的基于 Transformer 的 Graphormer、GPS 等强基线（ogbn-arxiv 仅比较了两个旧榜单模型）。  
- **理论分析欠缺**：文中指明了 Lyapunov 稳定性，但对同步收敛速度、信息瓶颈等理论性质未做深入推导。

---

（完）
