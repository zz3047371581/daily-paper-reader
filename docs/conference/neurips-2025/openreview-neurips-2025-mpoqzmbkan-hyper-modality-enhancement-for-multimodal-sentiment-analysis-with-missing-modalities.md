---
title: Hyper-Modality Enhancement for Multimodal Sentiment Analysis with Missing Modalities
title_zh: 面向模态缺失的多模态情感分析超模态增强方法
authors: "Yan Zhuang, Minhao LIU, Wei Bai, Yanru Zhang, Wei Li, Jiawen Deng, Fuji Ren"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=mPOQZMBKaN"
tags: ["query:affective-ai"]
score: 10.0
evidence: 面向模态缺失的多模态情感分析与情绪识别
tldr: 针对真实场景中多模态情感分析常面临模态缺失问题，提出超模态增强框架HME，通过跨样本检索语义相关线索丰富已有模态，避免显式重建。结合不确定性感知融合，在多个基准数据集上显著提升了缺失模态下的情感识别性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mpoqzmbkan/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1396, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mpoqzmbkan/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1408, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mpoqzmbkan/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1388, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mpoqzmbkan/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1331, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mpoqzmbkan/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1330, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mpoqzmbkan/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1329, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mpoqzmbkan/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1441, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mpoqzmbkan/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1250, \"height\": 460, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1422, \"height\": 1440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1386, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1413, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1359, \"height\": 1064, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1358, \"height\": 1063, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1379, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1299, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1074, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1075, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1087, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1078, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1262, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 549, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 536, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 714, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mpoqzmbkan/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 997, \"height\": 301, \"label\": \"Table\"}]"
motivation: 模态缺失（如隐私、传感器故障）严重降低多模态情感分析性能。
method: 提出HME框架，通过跨样本检索增强观察到的模态，不依赖重构。
result: HME在多个情感分析数据集上，缺失模态条件下获得SOTA。
conclusion: HME为不完备多模态情感分析提供了鲁棒且高效的解决方案。
---

## Abstract
Multimodal Sentiment Analysis (MSA) aims to infer human emotions by integrating complementary signals from diverse modalities. However, in real-world scenarios, missing modalities are common due to data corruption, sensor failure, or privacy concerns, which can significantly degrade model performance. To tackle this challenge, we propose Hyper-Modality Enhancement (HME), a novel framework that avoids explicit modality reconstruction by enriching each observed modality with semantically relevant cues retrieved from other samples. This cross-sample enhancement reduces reliance on fully observed data during training, making the method better suited to scenarios with inherently incomplete inputs. In addition, we introduce an uncertainty-aware fusion mechanism that adaptively balances original and enriched representations to improve robustness. Extensive experiments on three public benchmarks show that HME consistently outperforms state-of-the-art methods under various missing modality conditions, demonstrating its practicality in real-world MSA applications.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：多模态情感分析（MSA）在真实场景中常因数据损坏、传感器故障或隐私受限出现模态缺失，现有方法大多依赖“伪缺失”训练（在完整数据上掩码模拟，并利用被掩盖的真实表征进行监督），或采用教师–学生框架，这些做法假设训练时有完全观测的数据，限制了实际适用性。此外，已有工作通常只利用当前样本的可用模态，忽略了跨样本的语境信息。
- **整体含义**：本文旨在直接面向不完整输入，不进行显式模态重建，通过从其他样本中检索语义相关线索来增强观测到的模态，并利用不确定性感知融合提升鲁棒性，从而在真实缺失模式下实现更稳定、更高效的情感预测。

### 2. 方法论
#### 2.1 总体框架
- 框架名称：Hyper‑Modality Enhancement (HME)
- 三大模块：预处理、超模态表示生成、多模态超模态融合。

#### 2.2 预处理模块
- 对语言、音频、视频模态提取初始特征 \(X_m\)，模拟缺失时补零得到 \(X'_m\)。
- 用一维时序卷积（核大小3×3）统一到相同维度 \(d\) 和序列长度 \(T\)，加入位置编码。
- 经Transformer编码器与全局平均池化，得到紧凑的模态表示 \(H_m \in \mathbb{R}^d\)。

#### 2.3 超模态表示生成模块
- **模态增强（Modality Enhancement）**：
  - 对同一批次内各模态计算余弦相似度，设置阈值 \(t_s\)：高于阈值的样本取平均，若不存在或模态缺失则取该模态所有非缺失样本的平均，形成 \(H'_m\)。
  - 采用 Perceiver 架构：引入可学习提示 \(E'_m\) 作为查询，\(H'_m\) 作为键和值，通过交叉注意力和多个 Transformer 层得到增强表示 \(E_m\)。
  - 额外引入共享可学习提示 \(E'_S\)，聚合所有可用模态，得到样本级表示 \(E_S\)。
- **超模态生成（Hyper‑Modality Generation）**：
  - 用 \(E_L\) 查询 \(E_V, E_A\)，生成跨模态表示 \(E_{L,V}, E_{L,A}\)；再用 \(E_S\) 查询它们的拼接，得到该样本的语言超模态表示 \(R_L\)。对视频、音频重复相同操作，得到 \(R_m\)。
- **变分信息瓶颈（Variational Information Bottleneck, VIB）**：
  - 对 \(R_m\) 施加 VIB，优化 \(I(Z,Y) - \beta I(Z,X)\)，在保留任务相关信息的同时压缩噪声。
  - 用两个 MLP 分别预测均值 \(\mu_i\) 和标准差 \(\sigma_i\)，通过重参数化得到压缩表示 \(F_m\)，同时获得其不确定性 \(\sigma_m\)。
  - 损失项 \(L_{\text{VIB}}\) 由任务损失与 KL 散度组成。

#### 2.4 多模态超模态融合模块
- 定义不确定性权重：\(\zeta_m = 1/(\sigma_m + \epsilon)\)，并钳位到 \([t_l, t_u]\)。
- 双分支融合：
  - 对每个模态，将原始表示 \(H_m\) 与增强表示 \(F_m\) 拼接，乘以注意力权重后，再用 \(U2_m = [1.0, \zeta_m]\) 进行 Softmax 加权，得到融合表示 \(S_m\)。
  - 对三种超模态表示 \(F_m\)，通过 \(U3_m = e^{\zeta_m}/\sum e^{\zeta_m}\) 和注意力机制融合，得到 \(S_H\)。
- 拼接 \(S_L, S_V, S_A, S_H\)，经过一个 Transformer 编码器和两层 MLP 输出最终预测 \(\hat{y}\)。

#### 2.5 整体损失
\[
L_{all} = L_{TASK}(\hat{y}, y) + \alpha \overline{L_{VIB}}
\]
其中 \(L_{TASK}\) 为分类交叉熵或回归绝对误差，\(L_{VIB}\) 对三个模态平均。

### 3. 实验设计
- **数据集**：CMU‑MOSI、CMU‑MOSEI、IEMOCAP，以及额外的 UR‑FUNNY、MUStARD。
- **评价指标**：对于 MOSI/MOSEI 使用二分类准确率和 F1（将回归标签映射为正/负），IEMOCAP 使用四分类平均准确率和 F1。
- **缺失协议**：
  - 固定缺失：仅在验证与测试时移除特定模态，训练时保留全部模态。
  - 随机缺失：对整个数据集按缺失率（MR ∈ [0.0, 0.1, …, 0.7]）随机丢弃模态，训练、验证、测试阶段均不可见被丢弃的模态。
- **对比方法**：GCNet、MPLMM、DiCMoR、IMDer、LNLN 等专门针对模态缺失设计的 SOTA 模型。部分工作因设定不同由作者重新实现并标注 †。

### 4. 资源与算力
- 所有实验均在 **NVIDIA GTX 3090 GPU**（单卡）上完成。
- 训练配置：每个模型训练 100 个 epoch，使用早停（patience=10），结果取 5 次独立运行的平均值。
- 以 MOSI 为例，HME 训练耗时仅约 **684 秒**，远低于 DiCMoR（12,792 秒）和 IMDer（175,138 秒），参数量约 118M。
- 批大小对效率的影响：固定 256 时取得最佳性能，峰值 GPU 显存约 13.2 GB，训练时间 290 秒（50 epoch），作者也分析了不同批大小下的计算开销与性能权衡。

### 5. 实验数量与充分性
- 主实验覆盖 **3 个主流数据集**，两种缺失协议共 **14 种不同缺失条件**（固定 7 种，随机 8 种 MR 值）。
- 对比多达 **5 个 SOTA 基线**，部分基线缺失结果由作者统一复现，确保公平。
- 详尽的消融实验：逐模块移除（EL, EV, EA, ES, Um, HMG, VIB），展示了每个组件的贡献。
- 附加分析：模型稳定性（95% 置信区间，不同随机种子和批大小）、错误分析（高相似样本的对齐情况）、泛化性与即插即用（将 HMG 模块嵌入 MPLMM、跨数据集迁移）、变分信息瓶颈权重分析、增强表示的距离分析、超参数敏感性（相似阈值、不确定性上界、提示长度）、可视化（训练损失收敛、t‑SNE 表示、案例样本）。
- 实验设计系统、对比公平，多角度验证了方法的有效性和鲁棒性，实验量充分。

### 6. 主要结论与发现
- HME 在所有缺失协议和几乎所有缺失率下均取得了最优或极具竞争力的性能，固定缺失下 MOSI 平均 ACC/F1 提升约 0.9，IEMOCAP 提升 2.0/2.8；随机缺失下 MOSI 平均提升 2.0/2.3。
- 跨样本超模态增强能有效利用批次内语义相关样本，无需模态重建即可丰富表示。
- 不确定性感知融合能够自适应地降低低质量增强表示的影响，显著提升鲁棒性。
- VIB 模块有助于过滤跨样本增强引入的噪声，但单独移除会导致性能下降。

### 7. 优点
- **无需完整数据训练**：直接在不完整输入上工作，更贴近真实应用场景。
- **避免显式重建**：通过检索式增强，避免了复杂的生成模型和对完整数据的依赖。
- **跨样本信息利用**：突破单样本限制，从相关样本中提取情感线索，是新颖且有效的思路。
- **不确定性引导融合**：显式建模增强表示的不确定性，动态调节融合权重，提升了模型的可靠性和灵活性。
- **高效性**：相较于依赖扩散模型或教师–学生框架的方法，HME 训练速度更快，参数量适中。
- **插件式设计**：HMG 模块可轻松嵌入其他模型，具有良好的即插即用能力。

### 8. 不足与局限
- **表示重叠**：即便使用 VIB，不同模态生成的压缩表示仍可能包含冗余信息。
- **原始模态内噪声未处理**：方法专注于抑制来自其他样本的噪声，未考虑原始特征本身可能存在的噪声或错误。
- **相似样本的误导风险**：当相似样本标签不一致时，增强可能引入冲突信号（论文中已通过 VIB 和不确定融合部分缓解，但未能完全消除）。
- **跨数据集泛化有限**：从 MUStARD 转移到 UR‑FUNNY 时性能下降明显（受数据集规模和分布差异影响），实际部署时可能需要微调。
- **对批大小的依赖**：模态增强基于批次内样本选择，批大小过小会减少可供检索的样本池，可能影响增强效果（尽管论文在较小批大小下仍表现良好）。
- **社会影响**：基于不完整信号的推理可能导致偏差或不准确预测，存在隐私与不当监控的风险。

（完）
