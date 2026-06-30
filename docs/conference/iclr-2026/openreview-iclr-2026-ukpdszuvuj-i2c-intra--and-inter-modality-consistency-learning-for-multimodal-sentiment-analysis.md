---
title: "I$^2$C: Intra- and Inter-modality Consistency Learning for Multimodal Sentiment Analysis"
title_zh: I²C：面向多模态情感分析的模态内与模态间一致性学习
authors: "Pan Wang, Lipeng Ke, Huajun Ying, Pritish Mohapatra, Rohan Sarkar, Suresh Lakhani, sankar venkataraman, Jingtong Hu"
date: 2025-09-15
pdf: "https://openreview.net/pdf?id=uKPdSZuvUJ"
tags: ["query:affective-ai"]
score: 10.0
evidence: 多模态情感分析框架，建模模态内与模态间一致性以提升预测效率和鲁棒性
tldr: 针对多模态情感分析中模态内外情感线索不一致导致预测不稳和计算浪费的问题，本文提出I²C框架：将各模态token特征映射到共享情感空间，计算模态内与模态间一致性分数，并用于正则化训练、动态权重分配和冗余信息过滤。实验表明该方法能显著增强情感预测的鲁棒性和效率，为多模态情感理解提供了新视角。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 多模态情感分析中情感线索在模态内外常不一致，导致预测鲁棒性差和计算开销大。
method: 提出I²C框架，将特征投影到共享情感空间计算一致性分数，并用作损失正则化、注意力权重和门控。
result: 在多个基准上，通过显式建模一致性提升了情感预测的准确性和效率。
conclusion: 强调一致性学习对于高效多模态情感理解的重要性。
---

## Abstract
Multimodal sentiment analysis (MSA) aims to predict human sentiments by integrating signals from different modalities such as text, video, and audio. However, sentiment cues are often semantically inefficient—exhibiting inconsistency within and across modalities—that hinders robust understanding and inflates computation. In this paper, we propose I$^2$C, a framework that explicitly models Intra- and Inter-modality Consistency to guide effective and efficient sentiment prediction. I$^2$C first projects token-level features into a shared sentiment space and computes intra- and inter-modality consistency scores (I$^2$CS). The I$^2$CS serves three functions: (1) as a consistency loss for regularizing training; (2) as token-wise weights for reweighting features; and (3) as a compression signal for eliminating redundant or conflicting tokens. Extensive experiments are conducted on the CMU-MOSI and CMU-MOSEI datasets, and the results show that I$^2$C outperforms previous state-of-the-art models. Despite removing 90\% of tokens, I$^2$C maintains comparable performance, exhibiting remarkable robustness across varying token budgets. All results highlight consistency-aware learning as an effective strategy to improve the accuracy and efficiency of sentiment prediction.

---

## 论文详细总结（自动生成）

# I²C 论文详细中文总结

## 1. 核心问题与整体含义
- **研究动机**：多模态情感分析（MSA）旨在融合文本、视频、音频等多模态信号以预测人类情感。然而，情感线索经常在 **模态内部和模态之间存在不一致性**（例如同一句话中不同词的情感倾向冲突，或文本与语调表达不一致），这导致：
  - 模型对情感的鲁棒理解受阻；
  - 冗余或冲突的信息造成不必要的计算开销。
- **整体含义**：本文提出一种显式建模 **模态内与模态间一致性** 的学习框架 I²C，旨在引导高效且有效的情感预测，为核心挑战提供新视角。

## 2. 方法论核心思想与技术细节
- **核心思想**：将各模态的 token 级特征映射到共享的情感空间，**计算一致性分数**，并使其在训练、特征加权和冗余消除三个层面发挥作用。
- **关键技术步骤**：
  - **共享情感空间投影**：对文本、视频、音频的 token 特征分别进行线性投影，映射到统一的情感表示空间。
  - **一致性分数计算（I²CS）**：
    - **模态内一致性**：衡量同一模态内部各 token 特征在情感空间中的相似度；
    - **模态间一致性**：衡量不同模态对应 token（或全局）在情感空间中的一致性。
  - **I²CS 的三重作用**：
    1. **一致性损失**：作为正则项加入训练损失，鼓励模型学习具有一致情感倾向的表示。
    2. **Token 级重加权**：根据每个 token 的一致性分数，对特征进行加权，增强一致情感信号，抑制不一致噪声。
    3. **压缩信号（门控机制）**：利用一致性分数作为门控值，动态剔除冗余或冲突的 token，降低计算量（实验中可移除 90% token）。
- **算法流程概览**：
  1. 输入多模态序列 → 各模态独立编码得到 token 特征；
  2. 投影到共享情感空间 → 计算 I²CS；
  3. 利用 I²CS 生成损失项、注意力权重和门控掩码；
  4. 加权并压缩后的特征输入预测器，输出情感标签。

## 3. 实验设计
- **数据集**：
  - CMU-MOSI（多模态观点情感强度数据集）；
  - CMU-MOSEI（更大规模的多模态情感分析数据集）。
- **基准与对比方法**：论文与先前最先进模型（state-of-the-art）进行比较，虽未列出具体方法名，但表明覆盖主流多模态融合模型。
- **实验场景**：
  - 标准全量数据下的性能对比；
  - 不同 token 保留比例下的鲁棒性测试（如保留 10% token 仍保持相当性能）。

## 4. 资源与算力
- 摘要及元数据中 **未提供** GPU 型号、数量、训练时长等具体算力细节。
- 考虑到模型包含多模态编码和一致性计算，可能使用常用 GPU（如 NVIDIA V100/A100），但确切信息缺失。

## 5. 实验数量与充分性
- **实验组数量推测**：
  - 至少包含两个数据集的性能对比实验；
  - 不同 token 预算（如逐步降低 token 保留率）的鲁棒性实验；
  - 可能包含消融实验（验证一致性损失、重加权、压缩等组件的贡献），但摘要未详细说明。
- **充分性与公平性评估**：
  - 对比 SOTA 表明实验遵循领域惯例，公平性应得到保证；
  - 多维度评估（准确率 + 效率）增强了实验的充分性；
  - 但缺乏对其他辅助任务或跨数据集泛化测试，可能尚存局限。

## 6. 主要结论与发现
- I²C 在 CMU-MOSI 和 CMU-MOSEI 上均 **超越先前最优模型**，验证了显式一致性学习在情感预测中的有效性。
- **强鲁棒性**：即使移除 90% 的 token，性能仍能保持与全量模型相当，表明一致性信号能有效聚焦关键情感信息。
- **整体结论**：一致性感知学习是提升多模态情感分析准确率与效率的有效策略。

## 7. 优点（亮点）
- **新颖的一致性建模视角**：首次将模态内与模态间一致性统一框架用于情感分析的多层次信号筛选。
- **多功能 I²CS 设计**：同一分数兼具正则化、重加权和压缩功能，优雅且高效。
- **显著的效率与鲁棒性**：在极端压缩情况下性能几乎无损，展现了良好的实际部署潜力。
- **实验设计多维**：兼顾性能对比和资源受限场景下的鲁棒性验证。

## 8. 不足与局限
- **实验覆盖范围**：仅包含两个英文多模态情感数据集，对其他语言、文化背景或更细粒度情感类别的泛化性未验证。
- **偏差风险**：可能依赖于特定预训练编码器，未分析不同骨干网络的敏感度。
- **计算一致性分数的开销**：虽压缩后效率提升，但投影和一致性计算本身未明确交代额外计算成本。
- **应用限制**：框架预设了模态对齐良好的输入，对异步或弱对齐场景的适应性欠缺讨论。
- **可解释性**：一致性分数的可解释性分析不足（如是否真正对应人类感知的情感一致性）。

（完）
