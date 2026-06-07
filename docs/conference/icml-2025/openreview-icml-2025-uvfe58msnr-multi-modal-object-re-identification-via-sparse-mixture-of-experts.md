---
title: Multi-Modal Object Re-identification via Sparse Mixture-of-Experts
title_zh: 基于稀疏混合专家的多模态目标重识别
authors: "Yingying Feng, Jie Li, Chi Xie, Lei Tan, Jiayi Ji"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=uvFE58mSnR"
tags: ["query:affective-ai"]
score: 4.0
evidence: 跨模态特征融合用于目标重识别，与跨模态对齐技术相关
tldr: 针对多模态目标重识别中跨模态像素级特征交互不足和模态共享/特有特征难平衡的问题，提出MFRNet，包含特征融合模块（FFM）实现细粒度跨模态交互，以及特征表示模块（FRM）利用稀疏混合专家网络提取和组合模态共享与特有特征。在多个基准上取得领先性能，提供了一种可迁移的跨模态对齐思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uvfe58msnr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 852, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvfe58msnr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1748, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uvfe58msnr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 827, \"height\": 900, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 757, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 851, \"height\": 1085, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1767, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 778, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 836, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 771, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 774, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 777, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 776, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uvfe58msnr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 773, \"height\": 282, \"label\": \"Table\"}]"
motivation: 现有方法在像素级跨模态特征交互和模态特征平衡上存在局限。
method: 设计特征融合模块实现细粒度跨模态交互，特征表示模块用稀疏混合专家网络平衡模态特征。
result: MFRNet在多模态重识别数据集上显著超越现有方法，准确率提高。
conclusion: 验证了稀疏混合专家用于跨模态特征对齐的有效性，可借鉴至其他跨模态任务。
---

## Abstract
We present MFRNet, a novel network for multi-modal object re-identification that integrates multi-modal data features to effectively retrieve specific objects across different modalities. Current methods suffer from two principal limitations: (1) insufficient interaction between pixel-level semantic features across modalities, and (2) difficulty in balancing modality-shared and modality-specific features within a unified architecture. To address these challenges, our network introduces two core components. First, the Feature Fusion Module (FFM) enables fine-grained pixel-level feature generation and flexible cross-modal interaction. Second, the Feature Representation Module (FRM) efficiently extracts and combines modality-specific and modality-shared features, achieving strong discriminative ability with minimal parameter overhead. Extensive experiments on three challenging public datasets (RGBNT201, RGBNT100, and MSVR310) demonstrate the superiority of our approach in terms of both accuracy and efficiency, with 8.4% mAP and 6.9% accuracy improved in RGBNT201 with negligible additional parameters.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **任务背景**：多模态目标重识别（ReID）旨在利用可见光（RGB）、近红外（NIR）、热红外（TIR）等多模态图像，在跨摄像头场景下鲁棒地检索同一目标。
- **现存痛点**：
  - **跨模态交互不足**：现有方法多聚焦高层语义特征的融合，忽视了多模态图像天然的像素级对齐特性，导致细粒度交互缺失。
  - **特征表示失衡**：在统一架构中难以兼顾模态共享特征和模态特有特征——完全共享参数会丢失模态判别性，为不同模态分别维护网络又带来参数冗余和计算开销。
- **论文目标**：提出 MFRNet（Modality Fusion and Representation Network），通过混合专家（Mixture-of-Experts）的思想，同时实现像素级细粒度融合与高效的模态共享/特有特征表示。

## 2. 方法论：核心思想与关键技术细节
### 2.1 总体架构
- 以 CLIP 预训练的 ViT-Base 为主干，在其前插入**特征融合模块（FFM）**，在 ViT 的若干层后插入**特征表示模块（FRM）**。
- FFM 完成不同模态间像素级特征的重建与交互，FRM 则在特征提取阶段自适应地分离模态共享与特有信息。

### 2.2 特征融合模块（FFM）
- **动机**：跨谱变换可看作局部线性变换，其变换因子随表面材质变化，因此采用多个简单生成器（专家）的混合，以适应不同位置、模态和属性的 token。
- **重建策略**（以 RGB 为例）：
  \[
  I^R_{\text{gen}} = \lambda I^R + w_{NR}(I^N) \cdot g_{NR}(I^N) + w_{TR}(I^T) \cdot g_{TR}(I^T)
  \]
  - \(g_{NR}\)、\(g_{TR}\) 分别是从 NIR、TIR 生成 RGB 特征的专家网络。
  - \(w(\cdot)\) 通过学习得到可学习的融合权重，引入全局平均池化和线性投影，并对权重做 Softmax。
- **专家设计**：生成器专家极简，仅由两个 1×1 卷积构成（conv1→drop→conv2）。利用余弦路由（cosine router）和 Top‑1 选择机制，每个 token 动态激活最相关的专家。
- **模态缺失处理**：若某模态缺失，其自留项 \(\lambda I^M\) 直接置零，仅由其余可用模态生成，从而天然兼容不完整输入。

### 2.3 特征表示模块（FRM）
- **动机**：在共享 ViT 的基础上，用 MoE 增强 RepAdapter，既能保留模态特有信息，又保持参数高效。
- **实现细节**：
  - 在 ViT 的残差注意力层后插入 RepAdapter（即 \(Y_{\text{lnorm}} + \text{conv}_B(\text{drop}(\text{conv}_A(Y_{\text{lnorm}})))\) 结构）。
  - 将该 RepAdapter 提升为 MoE 层：定义多个 adapter 专家，通过余弦路由为每个 token 选择 Top‑1 专家，公式：
  \[
  Z = Y + \text{MoE‑RAda}(Y_{\text{lnorm}})
  \]
  - 专家数 ≥ 3（模态数）。
- **辅助损失**：针对 MoE，添加重要性损失 \(L_{\text{imp}}\) 和负载损失 \(L_{\text{load}}\)，以平衡专家使用频率和分配均匀性。

### 2.4 总体损失函数
\[
L = L^{\text{ViT}}_{ce} + L^{\text{ViT}}_{tri} + \frac{L_{\text{moe1}}^{\text{aux}} + L_{\text{moe2}}^{\text{aux}}}{2} + L_{\text{Ada}}^{\text{aux}}
\]
其中 \(L^{\text{ViT}}_{ce}\) 为标签平滑交叉熵，\(L^{\text{ViT}}_{tri}\) 为三元组损失，其余为 MoE 辅助损失。

## 3. 实验设计
- **数据集**：
  - **RGBNT201**：行人重识别，201 人，4787 组对齐的 RGB‑NIR‑TIR 图像。
  - **RGBNT100**：大规模车辆重识别，17250 组三模态图像。
  - **MSVR310**：小规模车辆重识别，2087 组三模态图像。
- **评测指标**：mAP 和 CMC @ Rank‑1、5、10。
- **对比方法**：
  - 单模态方法：MUDeep, HACNN, MLFN, PCB, OSNet, CAL, TransReID 等。
  - 多模态方法：HAMNet, PFNet, IEEE, DENet, UniCat, HTT, EDITOR, RSCNet, TOP‑ReID 等。
- **特殊场景**：设置不同模态缺失（如缺 RGB、缺 NIR、双模态缺失等）评估鲁棒性。

## 4. 资源与算力
- **硬件**：NVIDIA V100 GPU（未明确提及数量）。
- **框架**：PyTorch。
- **超参数**：图像尺寸 256×128（行人）或 128×256（车辆）；批量大小 64 或 128；Adam 优化器，初始学习率 \(3.5\times10^{-4}\)（ViT 编码器部分 \(5\times10^{-6}\)）；训练轮数 45 或 50 epoch。
- 论文未给出具体训练总时长或 GPU 小时数，无法复现精确算力估计。

## 5. 实验数量与充分性
- **主实验**：在三个数据集上与近 20 种方法进行全面对比（表 1、表 2），覆盖行人、车辆任务，单模态与多模态方法，充分体现优越性。
- **模态缺失实验**：在 RGBNT201 上对 6 种缺失组合进行评测（表 3），验证了模型对不完整多模态输入的适应能力。
- **计算成本对比**：与 HTT、EDITOR、TOP‑ReID 对比参数量和 FLOPs（表 4），突出轻量高效。
- **消融研究**：
  - 逐个加入 FFM、FRM 的效果（表 5）。
  - FRM 专家数量（3/6/9）（表 6）、FRM 插入层位置（表 7）的影响。
  - FFM 专家数量（1‑12）（表 8）、融合权重 λ（0‑1）（表 9）、FFM 插入深度（表 10）的灵敏度分析。
- **可视化**：对 FRM 专家分配进行可视化（图 3），展示了模态共享与特有特征的专家选择模式。
- **评价**：实验设计系统性强，消融维度丰富，对比基线合理，数据透明，无明显挑选性偏差。

## 6. 主要结论与发现
- MFRNet 在 RGBNT201 上获得 **80.7% mAP、83.5% Rank‑1**，超出此前最优 TOP‑ReID **8.4% mAP、6.9% Rank‑1**；在车辆数据集上也普遍大幅领先。
- 在参数仅 57.1M、计算量 22.1 GFLOPs 的情况下，达到性能与效率的双赢。
- 无需专门训练，FFM 即可通过模态互补机制应对模态缺失场景，即使双模态缺失仍保持可用性能。
- FFM 和 FRM 分别负责细粒度交互和高效特征解耦，二者协同显著提升了多模态 ReID 的精度与鲁棒性。

## 7. 优点
- **问题导向清晰**：直击多模态 ReID 两大核心痛点。
- **创新性强**：将稀疏 MoE 引入跨模态融合与表示学习，设计了轻量的生成器专家与 adapter 专家路由机制。
- **模块化与即插即用**：FFM 前置、FRM 后插，可轻松集成到现有 ViT 架构。
- **参数效率高**：利用 RepAdapter 和简单卷积专家，仅少量额外参数即获大幅性能提升。
- **缺失模态鲁棒**：天然具备模态补全能力，无需重训练。
- **实验扎实**：多个数据集、多种指标、丰富消融，提供了充分证据。

## 8. 不足与局限
- **数据集规模与多样性有限**：仅在三个数据集上验证，且均为相对受控的 ReID 场景；对其他大规模、开放环境的泛化性有待检验。
- **模态类型固定**：针对 RGB‑NIR‑TIR 三模态设计，若模态数量或类型变化（如深度图、事件相机），可能需要重新设计专家数量或路由策略。
- **专家数量的选择依赖经验**：实验表明不同模块的最佳专家数不同（FFM 3 个、FRM 6 个），尚无自适应选择机制。
- **模型完全基于 ViT**：未探讨 CNN 骨干上的适用性，可能限制在边缘设备上的部署。
- **缺少实时性分析**：虽给出 FLOPs，但未报告实际推理延迟或吞吐量。
- **训练数据依赖**：MoE 负载均衡可能对 batch 大小和训练策略敏感，复现时需注意调参。

（完）
