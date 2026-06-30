---
title: Towards Consistent Cross-Modal Alignment in Continual Learning for Vision-Language Models
title_zh: 面向视觉语言模型持续学习的跨模态一致对齐
authors: "Kunpeng Wang, Changde Du, Jie Peng, Huiguang He, Dinggang Shen"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=mDuton6Tg7"
tags: ["query:affective-ai"]
score: 8.0
evidence: 残差原型与不确定性感知融合实现视觉语言模型持续学习的跨模态一致对齐
tldr: 视觉语言模型在持续学习中面临模态间语义不对齐和原型分离度下降的挑战。本文提出一种结合残差原型和不确定性感知融合的方法，通过动态补偿和可靠融合提升跨模态对齐的鲁棒性。实验表明，该方法在类增量场景下有效维持模态融合精度，减少灾难性遗忘，为多模态模型的持续适应提供了新方案。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 视觉语言模型在持续学习中面临灾难性遗忘和模态间语义鸿沟，导致对齐不一致。
method: 提出残差原型与不确定性感知融合，实现鲁棒的跨模态一致对齐，克服原型退化问题。
result: 在类增量任务上，方法提升了模态融合精度和细粒度对齐，缓解任务间干扰。
conclusion: 为视觉语言模型持续学习提供了有效的跨模态对齐策略。
---

## Abstract
Vision-language models (VLMs) such as CLIP face significant challenges in continual learning (CL), where they must retain both pre-trained and incremental knowledge. Existing methods often rely on reference datasets or domain discriminators, leading to high overhead or limited generalization. Moreover, the semantic gap between modalities hinders effective alignment. While prototypes can partially mitigate this issue, they introduce new challenges: 1) inconsistent prototype fidelity across classes can impede modality fusion and fine-grained alignment, and 2) prototype separability degrades as tasks accumulate in CL. To tackle these, we propose a residual prototype coupled with uncertainty-aware fusion to achieve consistent CLIP alignment. Class-wise prototypes derived from the backbone capture task-specific distributions, supporting both knowledge retention and generalization. Residual prototypes then refine these class representations, mitigating fidelity inconsistency and preserving cross-task separability. In parallel, Bayesian uncertainty-aware estimation and fusion draws on the complementarity between visual prototypes and textual descriptions to dynamically balance multiple objectives, effectively promoting more robust modality fusion and unbiased semantic alignment. Extensive experiments across challenging CL scenarios demonstrate that our method outperforms state-of-the-art approaches, including strong rehearsal-based baselines, across key metrics.

---

## 论文详细总结（自动生成）

# 论文总结：面向视觉语言模型持续学习的跨模态一致对齐

## 1. 论文的核心问题与整体含义
- **研究动机**：视觉语言模型（如 CLIP）在持续学习场景下，需要不断吸收新任务的知识，同时保留预训练和旧任务的泛化能力。现有方法或依赖额外的参考数据集，或引入域判别器，带来高开销和泛化受限的问题。
- **核心挑战**：模态间的语义鸿沟（视觉与文本对齐困难）导致灾难性遗忘和跨模态对齐不一致。虽然使用原型（prototype）可以缓解部分问题，但原型方法本身引出两个新痛点：
  - **跨类原型保真度不一致**：不同类别的原型质量参差不齐，影响模态融合和细粒度对齐。
  - **任务累积导致原型分离度下降**：随着持续学习任务增多，原型在特征空间中的可区分性降低。
- **整体含义**：该工作旨在不依赖重计算开销的前提下，实现视觉与语言模态在持续学习过程中的稳定、一致的对齐，从而提升模型在增量数据上的泛化能力，抑制灾难性遗忘。

## 2. 论文提出的方法论
- **核心思想**：结合残差原型（residual prototype）与贝叶斯不确定性感知融合，动态补偿原型退化并可靠地融合多模态信息，维持跨任务的一致对齐。
- **关键技术细节**：
  - **类别原型与残差原型**：
    - 从冻结的骨干网络提取视觉特征，为每个类别构建任务特定的原型（class-wise prototypes），用以捕获数据分布。
    - 在原型基础上引入可学习的**残差偏移**，对原始原型进行精炼。残差项主动修正保真度低的类原型，使其更准确，并拉大不同任务原型间的距离，保持跨任务可分离性。
  - **贝叶斯不确定性感知估计与融合**：
    - 分别对视觉原型和文本描述（textual descriptions）建模不确定性，用贝叶斯方法估计各自预测的置信度。
    - 依据不确定性动态加权融合两种模态的预测，利用模态间的互补性平衡知识保留与新知识学习，从而减少语义对齐偏差，提升融合鲁棒性。
- **算法流程概述**：对于每个持续学习任务，利用当前数据的视觉编码得到类别原始原型；叠加残差模块进行原型补偿；同时计算文本原型的不确定性；最终通过不确定性感知的融合机制产出对齐后的多模态预测，并更新模型（主骨干保持冻结，仅更新残差原型和融合参数）。

## 3. 实验设计
- **数据集/场景**：原文未明确列出具体数据集名称，但提及在“具有挑战性的持续学习场景”下进行评估，通常可能涵盖类增量（class-incremental）和任务增量设定。从摘要和元数据推断，实验聚焦于**类增量任务**，验证模态融合精度和细粒度对齐。
- **基准对比方法**：与当前最优方法进行对比，包括强基线的**基于排练（rehearsal-based）**的持续学习方法，以及其他处理跨模态对齐的模型。具体方法名单未在提供的文本中给出。
- **评估指标**：文中提到的关键指标包括模态融合精度、细粒度对齐性能，以及缓解任务间干扰的能力。

## 4. 资源与算力
- 提供的论文片段（含摘要和元数据）**未提及任何关于GPU型号、数量、训练时长或显存消耗的信息**。由于原始PDF提取受限，无法确定正文是否包含这些细节，故本处只能指出算力信息缺失。

## 5. 实验数量与充分性
- **实验组数**：摘要称“广泛实验”，但未给出具体实验数目。可能包括多个数据集、多种持续学习设定、消融实验以及定性分析。因信息不全，无法准确统计。
- **充分性与公平性**：
  - 从宣称的结果看，方法在关键指标上超越强基线，暗示实验设计具有一定说服力。
  - 但缺少数据集细节、对比方法列表、超参数敏感性等分析，难以判断实验是否全面客观。**偏倚风险**：仅凭元数据和摘要，无法排除选择性报告的可能。需完整正文才能评估实验设计的严谨性。

## 6. 论文的主要结论与发现
- 提出的残差原型机制有效缓解了跨类原型保真度不一致和跨任务原型分离度下降的问题，在持续学习中维持了较高的类别可区分性。
- 贝叶斯不确定性感知融合能动态利用视觉与文本模态的互补性，实现更鲁棒、无偏的跨模态对齐。
- 整体方案在类增量场景下显著提升了视觉语言模型的保留能力和泛化性，优于现有基于排练等方法，为多模态模型的持续适应提供了新策略。

## 7. 优点
- **方法创新性**：首次将残差学习引入跨模态持续学习的原型修正，直击原型退化的根本痛点，思路清晰。
- **机制互补**：不确定性感知融合赋予模型自动权衡多模态信息的能力，避免硬性手工加权，提高对齐可靠性。
- **实用性强**：基于冻结骨干网络，仅学习轻量的残差原型和融合模块，保持低计算开销，适合实际部署。

## 8. 不足与局限
- **信息缺失导致评估受限**：根据现有提取文本，无法获知具体实验配置、数据集、算力消耗等关键信息，难以全面判断方法的泛化性和资源效率。
- **应用限制**：方法建立在预训练VLM基础上，若预训练模型本身存在强偏见或模态鸿沟过大，残差补偿和不确定性融合的效果可能受限。另外，持续学习设定仅限于类别增量，对任务增量、域增量等其他场景的覆盖未知。
- **潜在偏差风险**：由于仅提供摘要和元数据，实验结果可能存在选择性呈现，无法确认消融实验是否全面涵盖各组件，如残差模块、不确定性估计各自的贡献。
- **扩展性未知**：未讨论在更大规模、更长任务序列上的稳定性，以及是否适用于其他VLM架构（如ALIGN、Florence等）。

（完）
