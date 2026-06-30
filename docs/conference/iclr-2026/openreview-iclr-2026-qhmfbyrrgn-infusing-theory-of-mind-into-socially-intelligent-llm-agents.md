---
title: Infusing Theory of Mind into Socially Intelligent LLM Agents
title_zh: 将心理理论注入具有社交智能的LLM智能体
authors: "EunJeong Hwang, Yuwei Yin, Giuseppe Carenini, Peter West, Vered Shwartz"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=qHmfByRRGn"
tags: ["query:affective-ai"]
score: 8.0
evidence: 将心理理论融入LLM智能体，通过心理状态建模改善社交对话
tldr: 该论文证明在LLM对话智能体中显式运用心理理论（ToM）能提升对话效果。ToMAgent通过结合ToM与对话前瞻训练，在Sotopia社交互动基准上实现了更高的目标完成率。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 现有聊天机器人和LLM社交智能体通常缺乏对他人心理状态的显式理解。
method: 提出ToMAgent，训练时将心理理论建模与对话前瞻结合，以产生最大化对话目标的心理状态。
result: 在Sotopia评估基准上优于一系列基线方法。
conclusion: 显式整合心理理论能有效提升LLM的社交智能。
---

## Abstract
Theory of Mind (ToM)—an understanding of the mental states of others—is a key aspect of human social intelligence, yet, chatbots and LLM-based social agents do not typically integrate it. In this work, we demonstrate that LLMs that explicitly use ToM get better at dialogue, achieving goals more effectively. After showing that simply prompting models to generate mental states between dialogue turns already provides significant benefit, we further introduce ToMAgent (ToMA), a ToM-focused dialogue agent. ToMA is trained by pairing ToM with dialogue lookahead to produce mental states that are maximally useful for achieving dialogue goals. Experiments on the Sotopia interactive social evaluation benchmark demonstrate the effectiveness of our method over a range of baselines. Comprehensive analysis shows that ToMA exhibits more strategic, goal-oriented reasoning behaviors, which enable long-horizon adaptation, while maintaining better relationships with their partners. Our results suggest a step forward in integrating ToM for building socially intelligent LLM agents.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义

- **研究动机**：心理理论（Theory of Mind, ToM）指理解他人心理状态的能力，是人类社交智能的关键组成部分。然而，现有聊天机器人与基于大语言模型（LLM）的社交智能体通常未显式整合这种能力。
- **核心问题**：能否通过将心理理论显式地融入LLM智能体，来提升其在社交对话中的表现，尤其是更有效地达成对话目标。
- **整体含义**：本文证明了在LLM对话智能体中显式运用心理理论能够改善对话效果，为构建具备社交智能的LLM智能体迈出了有意义的一步。

## 方法论

- **核心思想**：将心理理论建模与对话前瞻训练相结合，让智能体不仅能推断对话伙伴的心理状态，还能生成对达成对话目标最为有用的心理状态。
- **方法框架**：
  - **第一步**：验证了在对话轮次之间简单提示模型生成心理状态即可带来显著收益。
  - **第二步**：提出**ToMAgent (ToMA)**——一个以心理理论为核心的对话智能体。
  - **训练机制**：将ToM与“对话前瞻”（dialogue lookahead）配对训练，即让模型在生成心理状态时，能够预见该状态对后续对话进程及目标达成的影响，从而产生最大化对话目标效用的心理状态。
- **技术流程**（文字说明）：
  1. 智能体在对话中进行心理状态推理，形成对伙伴信念、意图、情绪等的内部表征。
  2. 该内部表征被用于指导后续对话策略的生成。
  3. 通过对话前瞻机制，模型学习优化心理状态的生成，使其能更有效地导向预设的社交或任务目标。

## 实验设计

- **评估基准与场景**：在**Sotopia**交互式社交评估基准上进行实验。Sotopia是一个用于衡量社交智能体在复杂社会互动中表现的平台。
- **对比方法**：与一系列基线方法进行比较，具体包括未经显式ToM训练的LLM智能体以及其他对照方法（文中未在摘要与元数据中列出基线名称）。
- **评估维度**：重点评估目标完成率，同时分析推理行为的策略性、长程适应能力以及伙伴关系维持质量。

## 资源与算力

- 所提供的文本与元数据中**未明确说明**所使用的GPU型号、数量、训练时长或总计算量。无法从当前信息中给出具体算力描述。

## 实验数量与充分性

- **实验数量**：从摘要和描述推断，实验至少覆盖了以下维度——
  - 简单ToM提示的有效性验证。
  - ToMAgent在Sotopia基准上相对于多个基线的性能对比。
  - 对ToMAgent的行为进行全面分析（策略性推理、长程适应、关系维护等）。
- **充分性与公平性**：
  - 使用了公开的社会互动基准 Sotopia，具备标准化评估环境。
  - 对比了多个基线方法，存在对照组。
  - 进行了超越单一指标的深入行为分析，增强了结论的可靠性和解释性。
  - 在给定信息范围内，整体实验架构较为严密，但缺少具体的统计显著性检验、重复次数或消融实验的详细说明。

## 主要结论与发现

- **有效性**：显式整合心理理论能够有效提升LLM的社交智能，ToMAgent在Sotopia基准上实现了更高的目标完成率。
- **行为质量提升**：ToMAgent展现出更具策略性、目标导向的推理行为，能够在长对话中做出适应性调整，同时与对话伙伴保持更好的关系。
- **范式验证**：实验表明心理状态建模能够直接转化为更优的社交互动表现，而不仅仅是对话流畅度等表面指标。

## 优点

- **显式认知建模**：将心理理论这一人类高级认知功能显式注入LLM智能体，区别于传统端到端对话生成范式。
- **训练方法创新**：ToM与对话前瞻的结合设计了目标导向的心理状态生成机制，具有明确的学习信号。
- **评估扎实**：在复杂的社交互动基准上验证，不仅包含任务完成指标，还涵盖推理策略和社交维持等细粒度分析。
- **步骤清晰**：从简单的ToM提示逐步过渡到完整的ToMAgent框架，论证路线明确。

## 不足与局限

- **信息缺失**：基于当前文本，无法判断模型架构细节、训练数据规模、算力消耗以及具体的基线名称，因此难以评估其资源效能和对比公平性的全貌。
- **领域泛化性未知**：实验仅在Sotopia单一社交互动基准上进行，在不同类型对话任务或现实世界应用中的泛化能力未经验证。
- **偏差风险**：若训练数据或评估场景中存在特定的社交规范或文化偏差，ToMAgent可能习得并放大这些偏差，文中未提及相关的偏差检测与缓解。
- **ToM准确性**：论文未说明模型所推断的心理状态是否真正准确，即ToM推理本身可能发生错误并导致系列化的决策失误。
- **计算代价**：对话前瞻机制可能带来显著的推理或训练开销，其实用性在低资源场景中待商榷。

（完）
