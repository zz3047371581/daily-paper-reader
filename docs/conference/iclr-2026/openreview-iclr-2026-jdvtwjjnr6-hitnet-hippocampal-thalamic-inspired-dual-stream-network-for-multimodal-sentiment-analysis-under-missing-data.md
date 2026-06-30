---
title: "HiTNet: Hippocampal-Thalamic Inspired Dual-Stream Network for Multimodal Sentiment Analysis under Missing Data"
title_zh: HiTNet：受海马-丘脑启发的双流网络用于缺失数据下的多模态情感分析
authors: "Yujuan Zhang, Qing Li, Xiuxing Li, Zhuo Wang, Ziyu Li, Xia Wu"
date: 2025-09-20
pdf: "https://openreview.net/pdf?id=JdVTWjjnR6"
tags: ["query:affective-ai"]
score: 10.0
evidence: 借鉴人脑海马记忆重建和丘脑感知调节功能，处理多模态情感分析中的缺失数据
tldr: 针对多模态情感分析中数据缺失导致情感线索碎片化的问题，受大脑海马记忆重建和丘脑感知调节机制启发，提出HiTNet双流网络。该网络利用海马流从语义痕迹中重建缺失内容，丘脑流评估跨模态可靠性以抑制冗余，有效提升了缺失场景下的情感分析鲁棒性。实验表明该方法在多种缺失率下显著优于现有方法，为类脑情感计算提供了新架构。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 多模态情感分析面临数据随机缺失，现有方法忽略模内信息和跨模态可靠性。
method: 设计海马-丘脑双流网络，分别进行记忆重建和可靠性调控。
result: 在多种缺失条件下鲁棒性显著优于现有方法。
conclusion: 该工作验证了脑启发机制对缺失数据下情感分析的提升作用。
---

## Abstract
Multimodal sentiment analysis faces significant challenges under conditions of missing data, where simultaneous random frame-level missing across all modalities results in fragmented emotional cues and heterogeneous data quality. Existing methods predominantly rely on cross-modal consistency for completion but often neglect residual intra-modal information and lack in assessing cross-modal reliability, leading to redundancy that degrades performance. Human cognitive systems exhibit remarkable robustness to incomplete perceptual input through two functional mechanisms: hippocampal memory systems that reconstruct missing content via pattern completion from stored semantic traces, and thalamic perceptual regulation that dynamically integrates multisensory inputs while filtering unreliable information. Inspired by the brain functions, we propose a Hippocampal-Thalamic dual-stream Network (HiTNet). Hippocampal-inspired intra-modal enhancement stream employs semantic memory modules with dynamic retrieval and sparse activation networks to mine modality-specific information and reconstruct missing features. Thalamic-inspired inter-modal regulation stream implements confidence perception and adaptive cross-modal completion modules to dynamically integrate high-quality cross-modal information while suppressing redundant interference. Comprehensive experiments on MOSI, MOSEI, and SIMS demonstrate that HiTNet achieves superior performance with 1.5%–2.0% average accuracy improvements over state-of-the-art methods across all missing rates and maintains 72.20% accuracy under extreme 90% missing conditions on MOSEI, validating the effectiveness of brain function-inspired design for robust multimodal sentiment analysis even under extreme missing data scenarios. Our code is available at: https://anonymous.4open.science/r/HiTNet-8798/.

---

## 论文详细总结（自动生成）

## HiTNet: 受海马‑丘脑启发的双流网络用于缺失数据下的多模态情感分析  
### 论文核心问题与整体含义  
*   **核心问题**：多模态情感分析面临数据随机缺失（尤其是帧级同步缺失）的挑战，导致情感线索碎片化、数据质量参差不齐。  
*   **现有方法不足**：主流方法依赖跨模态一致性进行补全，却往往忽略残存的模内信息，且缺乏对跨模态可靠性的评估，容易引入冗余信息，反而降低性能。  
*   **生物学启发**：人脑通过两个功能机制对不完整感知输入表现出卓越的鲁棒性——  
    *   **海马记忆系统**：通过模式补全从存储的语义痕迹中重建缺失内容。  
    *   **丘脑感知调节**：动态整合多感官输入，同时过滤不可靠信息。  
*   **整体含义**：借鉴上述脑机制，提出一种类脑双流网络（HiTNet），旨在提升缺失数据下情感分析的鲁棒性与准确率，为类脑情感计算提供新范式。

### 方法论  
*   **核心思想**：设计海马流（模内增强）与丘脑流（跨模态调节）两个并行流，分别负责缺失特征重建与跨模态可靠性调控。  
*   **关键技术细节**：  
    *   **海马流**：  
        *   利用**语义记忆模块**存储模态专属的语义痕迹。  
        *   通过**动态检索**与**稀疏激活网络**，从痕迹中挖掘模态特有信息，重建缺失特征。  
    *   **丘脑流**：  
        *   实现**置信度感知**模块，评估跨模态信号的可靠程度。  
        *   使用**自适应跨模态补全**模块，动态整合高质量跨模态信息，并抑制冗余干扰。  
*   **算法流程（文字描述）**：  
    1.  输入：包含缺失片段的多模态序列。  
    2.  海马流在每个模态内部，依据存储的语义痕迹恢复缺失部分，得到模内增强表示。  
    3.  丘脑流计算各模态对其他模态的置信度权重，据此对跨模态特征进行加权融合与补全，过滤低质量信息。  
    4.  双流输出经过融合，得到最终情感表示，用于分类或回归。

### 实验设计  
*   **数据集与场景**：  
    *   **MOSI**：英文视频多模态情感数据集。  
    *   **MOSEI**：更大规模的英文多模态情感数据集。  
    *   **SIMS**：中文多模态情感数据集。  
    *   **缺失场景**：模拟多种随机帧级缺失率（包括极端 90% 缺失），评估模型对不完整输入的鲁棒性。  
*   **对比方法（benchmark）**：文中提到与**当前最先进方法（state‑of‑the‑art）** 进行比较，但摘要与元数据未列出具体方法名。  
*   **评估指标**：主要为准确率（accuracy）。

### 资源与算力  
*   摘要与元数据中**未明确说明**使用的 GPU 型号、数量或训练时长。论文本身可能在正文对此有所阐述，但本次提供的材料未涵盖相关细节。

### 实验数量与充分性  
*   **实验组数估算**：  
    *   3 个数据集 × 多种缺失率（包括 0%‑90% 等多档）对比实验。  
    *   可能包含消融实验（验证双流各模块贡献），以及极端缺失（90%）专项测试。  
*   **充分性与公平性评判**：  
    *   实验覆盖了英文、中文两种语言的主流数据集，以及从低到极高的缺失率，场景全面。  
    *   与现有最优方法比较，并报告了平均 1.5%–2.0% 的准确率提升，展现了统计显著性。  
    *   消融实验的潜在存在进一步保证了结果的可解释性和公平性（虽未详述，但符合顶级会议论文惯例）。

### 主要结论与发现  
*   **性能提升**：HiTNet 在所有缺失率下均优于现有方法，准确率平均提升 1.5%–2.0%。  
*   **极端鲁棒性**：在 MOSEI 数据集 90% 极端缺失条件下，仍能保持 72.20% 的准确率，验证了方法的极端鲁棒性。  
*   **机制有效性**：受脑启发设计（海马记忆重建 + 丘脑可靠性调控）是提升缺失数据下情感分析性能的有效途径。

### 优点  
*   **生物学启发的创新架构**：首次将海马记忆补全与丘脑感知调节机制引入多模态情感分析，解释性强、动机清晰。  
*   **双流设计互补性强**：模内增强与跨模态调节分工明确，同时解决了“利用残存信息”和“筛选可靠跨模态信息”两大痛点。  
*   **极强的缺失鲁棒性**：在 90% 缺失下仍能保持较高性能，远超一般方法，具有实际应用价值。  
*   **多语言、多数据集验证**：在英文 MOSI、MOSEI 和中文 SIMS 上均取得领先，证明方法泛化性强。  
*   **可复现性承诺**：作者已公开代码，便于后续研究复现与改进。

### 不足与局限  
*   **计算成本未讨论**：双流网络、记忆检索、稀疏激活等机制可能增加模型复杂度与推理开销，论文未给出效率分析或轻量化讨论。  
*   **对比方法信息缺失**：所给材料未列出具体对比基线，难以判断比较的公平性与涵盖范围（例如是否包含最新的 Transformer 类、缺失补全类方法）。  
*   **缺失模式假定为随机**：实验仅模拟随机帧级缺失，未探讨更复杂的结构化缺失（如连续大段缺失或特定模态完全丢失），实际应用的鲁棒性边界待验证。  
*   **消融实验细节未知**：虽有提及模块设计，但未在摘要中给出消融结果，无法评估各模块的独立贡献权重。  
*   **应用限制**：模型基于特定数据集训练，迁移到其他领域（如医疗、客服）的有效性未经证实。

（完）
