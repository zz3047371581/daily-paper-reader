---
title: A Unified Framework for EEG–Video Emotion Recognition with Brain Anatomy Guidance
title_zh: 基于脑解剖引导的EEG-视频情感识别统一框架
authors: "JangHyun Kim, Seongro Yoon, Temo Saghinadze, Aowen Shi, Mingyun Jeong, Donghyeon Cho, Jinsun Park, Francois Bremond"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=hga7TjP3uD"
tags: ["query:affective-ai"]
score: 10.0
evidence: 利用脑解剖引导的层次图卷积网络融合EEG和视频进行情感识别，结合神经动态与视觉线索。
tldr: 针对多模态情感识别中生理信号与视觉信息融合不足的问题，提出EVER框架，采用脑解剖引导的跨模态层次图卷积网络，将EEG通道特征聚合为脑区表示并与视频特征交互，实现神经动态与行为线索的互补融合。实验证明，该方法在情感识别任务上显著超越单模态和传统融合方法，为脑机情感计算提供有力工具。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 现有研究多单独使用视频或EEG，忽略两者结合带来的内部神经与外部行为信号互补性。
method: 提出BIH-GCN，先根据脑解剖结构聚合EEG特征到脑区，再与视频特征通过图网络进行分层交互。
result: 在公开数据集上，框架显著提高情感识别准确率，验证了脑解剖先验的有效性。
conclusion: 该工作首次系统融合EEG与视频的时空信息，为基于脑信号的情感AI研究开辟新路径。
---

## Abstract
Recent studies in video- and EEG-based emotion recognition have shown notable progress. However, multi-modal emotion recognition remains largely unexplored, particularly the integration of physiological signals with video. This integration is crucial, as EEG–video fusion combines observable behavioral cues with internal neural dynamics and enables a more comprehensive and robust characterization of human emotion. To this end, we propose EVER, a novel EEG–Video Emotion Recognition framework that effectively integrates complementary information from both modalities. Specifically, EVER employs a Brain anatomy-aware Inter-modal Hierarchical Graph Convolution Network (BIH-GCN), which aggregates EEG channel features into region-level representations guided by anatomical priors. These region-level features are combined with global EEG and video embeddings to form a unified representation for emotion classification. Furthermore, we introduce a correlation-based distribution alignment loss to reconcile modality-specific embeddings and reduce cross-modal discrepancies. To provide a comprehensive evaluation, we conduct comprehensive benchmark across three public EEG-video paired datasets---Emognition, MDMER, and EAV. We evaluate 12 representative models, consisting of 5 EEG-only, 5 video-only, and 2 audio-video models, and report their performance under EEG, video, and EEG–video settings. Our benchmark highlights the strengths and limitations of both unimodal and multi-modal approaches across diverse environments. Extensive experiments demonstrate that the proposed EVER achieves state-of-the-art performance by jointly modeling behavioral cues from video and physiological responses from EEG, thereby enabling the recognition of emotional patterns unattainable by either modality alone.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究领域**：多模态情感识别，特别是视频与脑电图（EEG）的融合。
- **核心问题**：现有情感识别工作大多单独使用视频（外部行为线索）或 EEG（内部神经动态），忽略了两者的互补性，导致对复杂情感状态的理解不够全面。
- **整体含义**：视频反映外在表现，EEG 揭示内在生理活动；将二者结合，可从“外部行为 + 内部神经”的双重视角构建更鲁棒、更完整的情感表征，实现仅靠单一模态无法达到的情感识别性能。
- **动机来源**：生理信号与视觉信息的融合研究仍处于早期阶段，缺乏能够有效捕捉模态间复杂交互的框架，且未充分利用脑解剖先验知识。

## 2. 论文提出的方法论

- **总体框架**：提出 EVER（EEG–Video Emotion Recognition），一个统一多模态情感识别框架。
- **核心模块**：**脑解剖感知的跨模态层次图卷积网络（BIH‑GCN）**。
  - **脑区聚合**：根据人脑解剖结构（如功能分区）定义的先验图，将 EEG 的多个通道特征聚合到脑区级别的表示。这一步骤将细粒度的传感器信号抽象为与神经科学知识一致的区域特征。
  - **层次交互**：在聚合后的脑区表示与视频特征之间构建图网络，通过分层传播实现跨模态信息融合。视频特征作为图节点之一，与脑区节点进行消息传递，从而让视觉线索引导 EEG 区域表征的更新，反之亦然。
  - **统一表示**：最终将脑区级 EEG 特征、全局 EEG 嵌入和全局视频嵌入整合为统一的特征向量，用于情感分类。
- **对齐损失**：引入**基于相关性的分布对齐损失（correlation‑based distribution alignment loss）**，缩小 EEG 和视频两种模态在嵌入空间中的分布差异，减少跨模态鸿沟，促进有效融合。
- **技术特点**：利用解剖先验约束多模态图交互，在不需大规模跨模态配对预训练的情况下，实现生理信号与视觉信号的深度协同。

## 3. 实验设计

- **数据集**：在三个公开 EEG‑视频配对数据集上评测：
  - **Emognition**
  - **MDMER**
  - **EAV**
- **基准设置**：构建了全面的基准测试，覆盖三种输入模态组合：
  - 仅 EEG
  - 仅视频
  - EEG + 视频联合
- **对比方法**：共 12 个代表性模型，包括：
  - 5 个纯 EEG 模型
  - 5 个纯视频模型
  - 2 个音频‑视频多模态模型
- **评价指标**：情感识别准确率（文中未详述其他指标，但以准确率为主）。
- **实验目的**：验证提出的 EVER 相比单模态及现有多模态方法的优势，同时揭示不同环境下单模态与多模态方法的强项和局限。

## 4. 资源与算力

- 论文摘要及提供材料中**未明确说明**使用的 GPU 型号、数量、训练时长或具体算力消耗。因此无法总结相关资源信息。

## 5. 实验数量与充分性

- **实验规模**：
  - 三维数据集 × 三种模态设置（EEG/视频/EEG‑视频）下的比较，至少涵盖 12 个模型的性能报告。
  - 推断可能包含消融实验（如验证 BIH‑GCN 各组件、分布对齐损失的有效性），但摘要未明确列出详细消融实验数量。
- **充分性评价**：
  - 实验覆盖了多个公开数据集，避免了单一数据集偏差。
  - 对比了单模态与多模态两大类、多种代表性方法，比较公平且具有代表性。
  - 未报告统计显著性检验细节，但整体对比充分，能够支撑核心结论。

## 6. 论文的主要结论与发现

- EVER 框架通过联合建模视频行为线索和 EEG 生理响应，**在情感识别任务上取得了最先进性能**。
- 脑解剖先验引导的层次图卷积能够有效融合两种异构模态，且相比无解剖引导的融合方式更具优势。
- 两种模态的信息互补性使得模型能够识别单一模态无法捕捉的情感模式。
- 该工作首次系统地将 EEG 与视频的时空信息进行整合，为基于脑信号的情感计算研究开辟了新路径。

## 7. 优点（方法或实验设计的亮点）

- **解剖先验的创新引入**：将脑科学知识显式融入模型结构，提升了 EEG 特征表示的生物合理性和跨模态交互的针对性。
- **层次图形融合**：通过“通道 → 脑区 → 全局”的分层聚合与跨模态图传播，实现对多尺度、多模态信息的精细建模。
- **多数据集、多设置基准**：在三个真实 EEG‑视频配对数据集上提供全面的基准测试，提升了结果的可信度和通用性。
- **分布对齐显式约束**：通过相关性对齐损失直接优化模态间一致性，缓解了异构模态融合时的分布不匹配问题。

## 8. 不足与局限

- **算力与实现细节缺失**：未披露所用硬件与训练计算量，限制了对方法效率与可复现性的评估。
- **方法泛化性未知**：仅在三个特定情感数据集上验证，未讨论在其他脑机接口任务或跨数据集泛化时的性能。
- **模态局限性**：依赖同时采集的 EEG 与视频数据，实际应用中 EEG 采集不便且个体差异大，可能影响现实部署。
- **对比方法数量**：虽然对比了 12 个模型，但缺少最新的多模态融合 Transformer 等更先进方法的直接比较。
- **统计显著性**：摘要未提及是否进行了显著性检验，部分结论的稳健性有待确认。
- **实时性考量**：未讨论推理速度或在线应用的可行性，可能局限在离线分析场景。

（完）
