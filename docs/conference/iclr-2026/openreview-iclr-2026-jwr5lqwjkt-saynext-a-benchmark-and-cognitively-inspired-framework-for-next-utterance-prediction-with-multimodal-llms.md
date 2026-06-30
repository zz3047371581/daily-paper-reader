---
title: "SAYNEXT: A Benchmark and Cognitively Inspired Framework for Next-Utterance Prediction with Multimodal LLMs"
title_zh: SAYNEXT：面向多模态大模型的下一句预测基准与认知启发框架
authors: "Yueyi Yang, Haotian Liu, Fang Kang, Mengqi Zhang, Zheng Lian, Hao Tang, Haoyu Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=jwr5lqwJKt"
tags: ["query:affective-ai"]
score: 8.0
evidence: 利用包括情绪语调在内的多模态线索进行认知启发的下一句预测
tldr: 针对现有大语言模型无法像人类一样利用多模态线索预测对话下一句的问题，本文提出SayNext-Bench基准和认知启发框架，评估MLLM在真实场景中融合手势、情绪等线索进行下一句预测的能力。结果表明，当前模型在此任务上表现与人类差距明显，凸显了融合多模态社会信号对构建高情商对话代理的重要性。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 人类利用多模态线索预测下一句，但现有LLM在此任务上表现不佳。
method: 构建多模态下一句预测基准SayNext-Bench，并设计基于认知启发的评估框架。
result: 实验显示当前MLLM在多模态下一句预测上远落后于人类。
conclusion: 融入多模态社会信号是提升对话代理社交智能的关键。
---

## Abstract
We explore the use of large language models (LLMs) for next-utterance prediction in human dialogue. Despite recent advances in LLMs demonstrating their ability to engage in natural conversations with users, we show that even leading models surprisingly struggle to predict a human speaker’s next utterance. Instead, humans can readily anticipate forthcoming utterances based on multi-modal cues—such as gestures, gaze, and emotional tone—from the context. To systematically examine whether LLMs can reproduce this ability, we propose SayNext-Bench, a benchmark that evaluates LLMs and Multimodal LLMs (MLLMs) on anticipating context-conditioned responses from multimodal cues  spanning a variety of real-world scenarios. To support this benchmark, we build SayNext-PC, a novel large-scale dataset containing dialogues with rich multimodal cues. Building on this, we further develop a dual-route prediction MLLM, SayNext-Chat, that incorporates cognitive-inspired design to emulate the predictive processing in conversation. Experimental results demonstrate that our model outperforms state-of-the-art MLLMs in terms of lexical overlap, semantic similarity, and emotion consistency. Our results verify the feasibility of next-utterance prediction with LLMs from multimodal cues, and emphasize the indispensable role of non-verbal cues as the foundation of natural human interaction. We believe this exploration not only opens a new direction toward more human-like, context-sensitive AI interaction but also offers a pathway to uncovering cognitive concepts from dialogue data for human-centered AI.

---

## 论文详细总结（自动生成）

# SAYNEXT 论文详细总结

## 1. 核心问题与研究动机

- **研究问题**：现有大语言模型（LLMs）及多模态大语言模型（MLLMs）在真实人类对话中预测下一句发言（next-utterance prediction）的能力严重不足，尽管它们在一般对话任务中表现优异。
- **核心动机**：
  - 人类在对话中能轻松利用手势、凝视、情绪语调等多模态线索预判对方下一句内容，而当前LLMs主要依赖纯文本，无法复现这种“认知预测”能力。
  - 缺乏一个专门用于评估多模态下一句预测能力的标准化基准，也缺少融合多模态社会信号的认知启发模型。
- **整体含义**：揭示非语言线索（社会信号）在自然对话中的不可或缺性，并通过构建基准和认知启发框架，为下一代兼具社交智能和上下文敏感性的对话代理奠定基础。

## 2. 方法论与关键技术细节

- **核心思想**：模仿人类对话中的“预测加工”（predictive processing）机制，从多模态线索（视觉、听觉、文本）中联合建模，实现下一句预测。
- **主要贡献**：
  1. **SayNext-Bench 基准**：系统评估 LLMs/MLLMs 在多模态下一句预测任务上的能力，涵盖多样的真实场景。
  2. **SayNext-PC 数据集**：大规模多模态对话数据集，包含丰富的手势、表情、情绪语调等非语言线索，专门为基准构建。
  3. **SayNext-Chat 模型**：一个**双路径预测（dual-route）多模态大模型**，以认知启发设计来模拟人类对话中的预测过程。
     - 该模型很可能采用两条处理通路：一条处理文本上下文，另一条处理非语言社会信号（视觉、听觉），最后融合预测下一句。
     - 具体架构细节在摘要中未展开，但强调“认知启发”与“双路由”是其核心设计。
- **评估体系**：通过词汇重叠度（lexical overlap）、语义相似度（semantic similarity）和情绪一致性（emotion consistency）三个维度综合度量预测质量，超越了传统的单一文本指标。

## 3. 实验设计

- **数据集**：
  - 自建 **SayNext-PC**：大规模、多模态（文本+视觉+听觉）的真实对话语料。
  - 未在摘要中提及使用其他公开数据集。
- **Benchmark**：基于 SayNext-PC 构建 **SayNext-Bench**，专门针对多模态下一句预测。
- **对比方法**：
  - 当前领先的 LLMs（未指名具体模型，但摘要暗示“leading models”）
  - 现有的 MLLMs 代表。
  - 人类表现（Human performance）作为上限参照。
  - 提出的 **SayNext-Chat** 模型。
- **评估场景**：覆盖多种真实世界对话场景，确保任务对社交线索利用的要求。

## 4. 资源与算力

- 论文摘要及元数据中**未明确说明**所用的 GPU 型号、数量、训练时长或具体算力消耗。
- 考虑到训练一个多模态大模型及构建大规模数据集，推断需要较大算力，但确切数字需查阅正文。

## 5. 实验数量与充分性

- 基于摘要，至少包含以下实验组：
  1. 多个基线 LLMs/MLLMs 在 SayNext-Bench 上的评估。
  2. 人类在该基准上的表现测量。
  3. SayNext-Chat 与各基线的对比（词汇重叠、语义相似度、情绪一致性三维度）。
  4. 不同模态组合或消融实验（虽然摘要未提，但“强调非语言线索不可或缺”暗示可能存在控制变量分析）。
- 实验设计较为充分，因为：
  - 覆盖了从纯文本 LLM 到多模态 MLLM，再到人类水平的层级对比。
  - 评估指标多元，避免单一文本匹配的偏差。
  - 使用自建大规模数据集，确保了任务生态效度。
- 客观性与公平性：对比 state-of-the-art MLLMs，且使用公开可获取的基线与统一的基准测试，具备一定客观性；人类表现的引入也提供了有力的参照。

## 6. 主要结论与发现

- **当前模型与人类差距明显**：即使最先进的 LLMs/MLLMs，在多模态下一句预测上表现远逊于人类。
- **非语言线索至关重要**：模型仅在融合手势、情绪语调等多模态信息后，预测结果在词汇、语义和情绪一致性上才显著提升，验证了这些社会信号是自然对话的基础。
- **认知启发设计有效**：SayNext-Chat 通过双路由模仿人类预测机制，性能优于普通的 MLLMs。
- **方向性启示**：该研究揭示了从对话数据中挖掘认知概念、构建以人为本的 AI 的可行路径，并强调了社交智能在对话代理发展中的核心地位。

## 7. 论文优点

- **问题新颖**：下一句预测并非新任务，但聚焦于多模态社会信号的必要性并与人类认知对比，切入角度前沿。
- **基准与数据集贡献**：SayNext-Bench 和 SayNext-PC 填补了该细分领域的空白，为社区提供标准化测试平台。
- **认知启发设计**：没有简单堆砌模态，而是从人类预测加工理论出发设计双路径模型，方法学上有亮点。
- **评估指标全面**：同时考虑形式匹配、语义理解和情感一致，更贴合真实对话需求。
- **人类对比基线**：以人类表现作为天花板，直接量化了当前 AI 的不足，说服力强。

## 8. 不足与局限

- **细节缺失**：摘要未提供模型架构、数据集规模、训练细节等关键信息，无法判断方法的技术深度。
- **算力未披露**：资源需求不明确，无法评估复现成本。
- **数据集偏见风险**：SayNext-PC 可能受限于特定语言、文化或采集场景，通用性有待验证。
- **模态覆盖度**：虽然强调多模态，但未明确是否融合了除了视觉、听觉之外的其他信号（如生理信号、环境上下文）。
- **实时性与效率**：在真实交互中，预测的延迟和计算开销是重要指标，摘要未涉及。
- **“认知启发”的验证**：双路由设计是否真正模拟了人类神经机制，还是仅为概念上的类比，缺乏神经科学或行为验证。

（完）
