---
title: "Emotion-o1: Adaptive Long Reasoning for Emotion Understanding in LLMs"
title_zh: Emotion-o1：面向LLM情感理解的自适应长链推理
authors: "Changhao Song, Yazhou Zhang, Hui Gao, Kaiyun Huang, Peng Zhang"
date: 2025-09-17
pdf: "https://openreview.net/pdf?id=1cypyDBSAl"
tags: ["query:affective-ai"]
score: 9.0
evidence: 面向LLM情感理解的自适应思维链，平衡推理深度与效率
tldr: 该论文针对固定长度思维链在情感理解中无法平衡深度与效率的问题，提出Emotion-o1框架，从大型推理模型蒸馏自适应思维链模式，并通过监督微调和强化学习进行训练。在五个情感理解基准上，动态调整推理长度显著提升了性能。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 现有固定长度思维链方法对简单任务过度推理，对复杂任务推理不足。
method: 从大型推理模型蒸馏自适应思维链模式，用四部分奖励（准确、简洁、结构、冗余）进行强化学习微调。
result: 在多个情感理解任务上取得更好表现。
conclusion: 自适应思维链能有效提升LLM的情感理解效率与深度。
---

## Abstract
Long chain-of-thought (CoT) reasoning has shown great promise in enhancing the emotion understanding performance of large language models (LLMs). However, current fixed-length CoT methods struggle to balance reasoning depth and efficiency. Simple tasks (e.g., sentiment classification) are over-reasoned, while complex tasks (e.g., sarcasm understanding) lack depth. To fill this gap, we present Emotion-o1, an adaptive CoT framework that dynamically adjusts reasoning length based on task complexity. Emotion-o1 is trained by distilling adaptive CoT patterns from a large reasoning model (LRM), followed by supervised fine-tuning and reinforcement learning with a four-part reward targeting accuracy, brevity, structure, and redundancy. Experimental results on four emotion tasks highlight: (1) Emotion-o1 demonstrates significant improvements over its backbone, with F1 score increases of 11\%↑(Sentiment), 14\%↑(Emotion), 18\%↑(Humor), and 27\%↑(Sarcasm). (2) In sentiment and emotion tasks, our 8B model demonstrates superior performance against SoTA LLMs, outperforming Grok‑3 by 2.1\% in sentiment and within 1\% of OpenAI‑o1 in emotion. (3) The framework maintains accuracy while reducing reasoning length by 83\% compared to OpenAI-o1, demonstrating effective precision-efficiency optimization. From a lower-cost perspective, the framework also empowers SLMs to achieve reasoning capabilities comparable to larger ones.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义
- **研究动机**：当前大型语言模型（LLMs）在情感理解中普遍采用固定长度的思维链（Chain-of-Thought, CoT）推理。这种方式无法根据任务复杂度动态调整推理深度，导致简单任务（如情感分类）被过度推理，浪费计算资源，而复杂任务（如讽刺识别）则推理不足，限制精度。
- **整体含义**：该工作旨在解决情感理解中推理深度与效率的平衡问题，提出一个自适应框架，使LLM能依据任务难度自动调节推理长度，从而在提升性能的同时显著降低冗余。

### 2. 方法论
- **核心思想**：从大型推理模型（Large Reasoning Model, LRM）中蒸馏出自适应CoT模式，再通过两阶段训练注入小模型，包括监督微调（SFT）与强化学习（RL）。
- **关键技术细节**：
    - **知识蒸馏**：利用LRM生成适应不同任务复杂度的多长度CoT轨迹，作为训练数据。
    - **强化学习奖励设计**：定义四部分奖励函数，分别针对推理的准确性（accuracy）、简洁性（brevity）、结构合理性（structure）和冗余度惩罚（redundancy），驱动模型学习何时以及如何进行短链或长链推理。
    - **算法流程**：蒸馏模式 → SFT初步拟合 → RL精细优化，使模型最终能依据输入任务动态输出对应深度的推理过程。

### 3. 实验设计
- **任务与数据集**：在四项情感理解任务上验证，具体为情感倾向分类（Sentiment）、细粒度情绪识别（Emotion）、幽默理解（Humor）和讽刺识别（Sarcasm）。
- **评估指标**：以F1分数为核心评价指标，同时对比推理长度压缩率。
- **对比基准**：
    - **骨干模型**：未指定的基础LLM（文中提到“its backbone”）。
    - **顶尖LLMs**：Grok‑3 和 OpenAI‑o1，对比其在情感分类与情绪任务上的绝对性能以及推理效率。

### 4. 资源与算力
- 文中提供的摘要未明确说明训练所使用的GPU型号、数量、训练时长或总计算量等具体算力信息。

### 5. 实验数量与充分性
- **实验组数**：至少涵盖4个不同任务的数据集评估、与多个基线模型的对比，以及推理长度变化分析。
- **充分性与客观性**：
    - 任务覆盖了从简单到复杂的情感理解层次，具有一定代表性。
    - 与SoTA模型进行了直接对比，且不仅关注效果，还考察了推理效率（长度减少83%），评估维度较为全面。
    - 但摘要未提及消融实验（如无四部分奖励的影响）、不同模型规模的泛化测试或统计显著性检验，实验充分性尚无法完全判定。

### 6. 主要结论与发现
- **性能提升显著**：相比骨干模型，在四项任务上F1分别提升11%（情感倾向）、14%（情绪）、18%（幽默）和27%（讽刺），复杂任务增益最突出。
- **与顶尖模型匹敌**：8B参数的Emotion‑o1在情感分类上超Grok‑3 2.1%，在情绪任务上与OpenAI‑o1差距在1%以内。
- **效率优化**：在保持高准确率的同时，推理长度比OpenAI‑o1缩减83%，验证了精度‑效率的平衡。
- **低成本赋能**：该框架同样能使较小模型（SLMs）获得媲美更大模型的推理能力。

### 7. 优点
- **动态推理机制**：突破固定长度CoT的局限，使模型能按需分配推理资源，兼顾复杂与简单场景。
- **精细化的RL奖励**：四部分奖励直接优化推理的准确、简洁与结构，设计目标与任务需求高度对齐。
- **高性价比**：在多个情感理解任务上以远低地推理成本取得接近或超越大模型的性能，实用性强。

### 8. 不足与局限
- **算力细节缺失**：未提供训练所需资源数据，其他研究者难以复现或评估成本。
- **可能存在的偏差**：情感理解数据常带有文化与标注主观性，框架对非英语或跨文化场景的鲁棒性未提及。
- **实验覆盖限制**：仅摘要信息不足以确认是否有充分的消融实验、跨领域测试或误差分析，结论的稳健性待进一步验证。
- **应用局限**：蒸馏依赖LRM的质量，且自适应性可能对某些需要固定格式输出的下游应用引入不确定性。

（完）
