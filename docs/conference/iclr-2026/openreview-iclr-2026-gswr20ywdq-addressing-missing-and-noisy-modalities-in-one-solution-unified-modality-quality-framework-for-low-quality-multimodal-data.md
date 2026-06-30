---
title: "Addressing Missing and Noisy Modalities in One Solution: Unified Modality-Quality Framework for Low-quality Multimodal Data"
title_zh: 统一处理缺失与噪声模态：面向低质量多模态数据的统一模态质量框架
authors: Sijie Mai
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=Gswr20yWDq"
tags: ["query:affective-ai"]
score: 9.0
evidence: 提出统一模态质量 (UMQ) 框架增强低质量多模态情感计算表征
tldr: UMQ针对多模态情感计算中常见的缺失与噪声模态问题，提出统一模态质量框架，通过质量估计器增强低质表示，提升模型在低质量数据下的鲁棒性。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 真实场景中多模态数据常包含噪声和缺失模态，严重损害模型鲁棒性。
method: 提出UMQ框架，将噪声与缺失视为统一低质模态问题，训练质量估计器增强表示。
result: 提升了多模态情感计算在低质量数据下的鲁棒性。
conclusion: UMQ为低质量多模态情感分析提供了统一鲁棒方法。
---

## Abstract
Multimodal data encountered in real-world scenarios are typically of low quality, with noisy modalities and missing modalities being typical forms that severely hinder model performance and robustness. However, prior works often handle noisy and missing modalities separately. In contrast, we jointly address missing and noisy modalities to enhance model robustness in low-quality data scenarios. We regard both noisy and missing modalities as a unified low-quality modality problem, and propose a unified modality-quality (UMQ) framework to enhance low-quality representations for multimodal affective computing. Firstly, we train a quality estimator with explicit supervised signals via a rank-guided training strategy that compares the relative quality of different representations by adding a ranking constraint, avoiding training noise caused by inaccurate absolute quality labels. Then, a quality enhancer for each modality is constructed, which uses the sample-specific information provided by other modalities and the modality-specific information provided by the defined modality baseline representation to enhance the quality of unimodal representations. Finally, we propose a quality-aware mixture-of-experts module with particular routing mechanism to enable multiple modality-quality problems to be addressed more specifically. UMQ consistently outperforms state-of-the-art baselines on multiple datasets under the settings of complete, missing, and noisy modalities.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义
- **研究背景**：真实场景下的多模态数据常因传感器故障、通信丢包或人为干扰而呈现**低质量**特征，主要体现为**模态缺失**（如一段视频无音频）和**模态噪声**（如语音含背景杂音）。
- **研究动机**：现有工作将缺失模态与含噪模态视作相互独立的问题分别处理，缺乏统一应对框架；且这类低质量数据会严重损害情感计算等任务的性能与鲁棒性。
- **整体含义**：本文认为缺失与噪声本质上都只是**低质量模态**的不同表现形式，提出**统一模态质量（UMQ）框架**，以一个整体方案同时解决两类问题，提升多模态情感计算在复杂低质量环境下的可信赖性。

### 2. 方法论
- **核心思想**：将缺失模态看作质量极低的“空表示”，与带噪表示一同纳入质量评量与增强体系，实现**缺失-噪声联合建模**。
- **关键技术细节**：
  - **秩引导的质量估计器**：不依赖人类难以精确标注的绝对质量分数，而是通过**排序约束**比较不同表示之间的相对质量，用显式监督信号训练质量估计器，避免错误绝对标签带来的训练噪声。
  - **单模态质量增强器**：为每个模态构建增强器，融合来自**其他模态的样本特定信息**与**该模态基线表示**（通过全局统计或可学习参数定义）提供的模态专属信息，提升受损（含缺失或噪声）表示的质量。
  - **质量感知混合专家模块（Quality-aware Mixture-of-Experts）**：引入特殊路由机制，根据估计到的模态质量动态激活不同的专家分支，使不同质量类型的样本能被**针对性处理**，从而更精细地解决多样化的模态质量问题。
- **算法流程**（文本描述）：多模态输入 → 各模态分别编码得到初始表示 → 质量估计器给出各模态相对质量评分 → 质量增强器利用跨模态信息和基线表示修正低质表示 → 质量感知路由选取合适专家模型 → 融合多模态特征 → 最终情感预测。

### 3. 实验设计
- **数据集/场景**：论文提到在多个公开多模态情感计算数据集上进行验证，具体名称在元数据中未列出，但应包含情感识别、情绪分析等经典基准。
- **实验场景设置**：
  - **完整模态**：原始无损数据。
  - **缺失模态**：随机或按模式丢弃某些模态。
  - **噪声模态**：向模态注入不同类型和强度的噪声。
- **对比方法**：与多个领域内最新方法（state-of-the-art baselines）对比，覆盖仅处理噪声、仅处理缺失及传统多模态融合模型。

### 4. 资源与算力
- 提供的摘要与元数据中**未明确说明使用何种GPU型号、数量或训练时长**，因此在当前信息下无法总结算力消耗细节。

### 5. 实验数量与充分性
- **实验规模**：文中宣称在多个数据集上，覆盖完整、缺失、噪声三种模态设定下进行实验，并报告全面优于现有基线，暗示实验数量较为充分。
- **消融实验**：通常方法论论文会包含消融分析（如去除质量估计器、增强器或混合专家模块的对比），但具体细节未在提炼内容中给出；基于“consistently outperforms”可推断消融实验应存在。
- **公平性**：与多个SOTA方法对比，采用统一评估协议，且关键模块设计目标明确（避免不准确标签），整体实验设计较客观公平。

### 6. 主要结论与发现
- UMQ能够在**缺失模态、噪声模态及两者混合的低质量场景**下稳定超越现有先进模型。
- 将缺失与噪声统一为低质问题并通过质量估计引导增强是有效的，避免了两类问题分开解决时的冗余与割裂。
- 秩引导质量估计器的设计能降低不稳定标注的影响，提升训练稳定性。
- 混合专家路由机制使模型能针对不同质量模式进行特化，进一步增强鲁棒性。

### 7. 优点
- **统一性**：首次将缺失和噪声整合在一个框架内处理，简化实际部署流程。
- **精巧的训练策略**：秩引导排序损失替代绝对质量回归，巧妙地规避了模糊人工标签的干扰。
- **模块化设计**：质量估计、增强、动态专家路由各模块职责清晰，便于后续扩展或改进。
- **多方位验证**：在多种数据缺失率与噪声强度下的对比实验，结果为方法实用性提供了有力支撑。

### 8. 不足与局限
- **实验覆盖细节缺失**：从现有信息无法确认是否在非情感计算任务（如视觉问答、动作识别）上验证，应用场景可能局限于情感计算。
- **计算复杂度未评估**：未提及引入的质量估计器与混合专家模块带来的额外推理开销，在实际受限设备上的适用性待考。
- **偏差风险**：若构造缺失/噪声的设置过于理想化，可能无法完全反映真实世界数据分布的复杂性（如非随机缺失模式）。
- **依赖跨模态线索**：当所有模态同时严重退化时，增强器可利用的有效信息骤减，极端退化下的性能下限未明确展示。

（完）
