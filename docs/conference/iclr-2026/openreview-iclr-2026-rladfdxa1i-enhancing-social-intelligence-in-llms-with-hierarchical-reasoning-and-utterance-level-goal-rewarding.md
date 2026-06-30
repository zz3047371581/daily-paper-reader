---
title: Enhancing Social Intelligence in LLMs with Hierarchical Reasoning and Utterance-Level Goal Rewarding
title_zh: 通过层次推理和话语级目标奖励增强LLM的社交智能
authors: "Xiaofeng Wang, Kakam Chong, Shuai Xiao, DeXin Kong, Qingyuan Tian, Chen Ju, Xu Yan, Shuai Zhao, Fei Huang, Rui Wang, Shuguang Han, jufeng chen"
date: 2025-09-16
pdf: "https://openreview.net/pdf?id=rlADfdxA1I"
tags: ["query:affective-ai"]
score: 4.0
evidence: 面向LLM社交对话的层次推理，与情感智能间接相关
tldr: 该论文提出TSR框架和LHRL-VGR方法，通过层次规划和话语级奖励增强LLM社交交互，在社交对话任务上取得提升，但并未直接处理情感或情感计算。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: LLM在动态社交交互中缺乏长期目标协调和快速适应能力。
method: 提出Think-Strategy-Response框架，将对话分解为高层策略规划和低层语言执行，并用线性化层次强化学习优化。
result: 在社交对话基准上表现出更好的目标完成效果。
conclusion: 层次规划和精细化奖励能改善LLM社交对话，但与情感直接关联较弱。
---

## Abstract
Large language models (LLMs) excel in structured tasks but struggle with dynamic social interactions, where success requires long‐term goal coordination and rapid adaptation. Current methods often apply uniform goal‐based rewards to every utterance, overlooking the specificity of objectives at each dialogue turn and failing to account for the rationale of potential strategies. Inspired by the Theory of Planned Behavior, we propose the Think‐Strategy‐Response (TSR) framework, which decomposes social dialogue into two hierarchical stages: high‐level strategic planning and low‐level linguistic execution. To optimize TSR, we introduce Linearized Hierarchical Reinforcement Learning with Variance‐Gated Rewards (LHRL‐VGR), a novel algorithm that dynamically routes rewards—balancing goal completion and strategy adherence—based on the variance of goal achievement scores. Experiments on the SOTOPIA benchmark show that our approach fine‐tunes a Qwen2.5-7B agent to surpass the GPT‐4o baseline by 7.32% in goal completion success, demonstrating state‐of‐the‐art performance in multi‐agent social negotiation tasks.

---

## 论文详细总结（自动生成）

# 论文总结：通过层次推理和话语级目标奖励增强LLM的社交智能

## 1. 论文的核心问题与整体含义
- **问题**：大语言模型在结构化的任务中表现出色，但在动态的社交交互中存在明显短板。此类交互的成功不仅依赖于单轮回复的流畅性，更要求智能体具备**长期目标协调能力**和**快速适应能力**。
- **动机**：现有方法往往对每一句对话施加统一的目标奖励，**忽略了不同对话轮次目标的特殊性**，也未能显式建模潜在策略的合理性。这种粗粒度奖励使得模型难以学会在复杂社交场景中平衡即时回应与长远目标。
- **整体含义**：受社会心理学中的“计划行为理论”启发，论文提出一种分层推理框架，将社交对话拆解为高层策略规划和低层语言执行，并设计专门的强化学习算法来优化这一过程，旨在从机制上提升LLM的社交智能。

## 2. 论文提出的方法论
- **核心思想**：Think‑Strategy‑Response (TSR) 框架
  - **高层策略规划**：模型先“思考”当前局面，生成一个抽象的策略或意图（Think → Strategy）。
  - **低层语言执行**：在此基础上生成具体的自然语言回应（Response），从而将对话中的长期目标和即时语言行为解耦。
- **关键技术细节**：
  - **线性化层次强化学习（LHRL）**：将高层策略选择和低层语言生成视为一个层次化的决策过程，并通过强化学习进行联合优化。其中，高层策略的“动作”是选择某一类对话计划，低层则输出具体的词元序列。
  - **方差门控奖励机制（VGR）**：为解决高层策略和低层生成之间的奖励分配问题，该算法根据**目标达成分数的方差**来动态“路由”奖励。当目标达成的不确定性较高时，更多奖励流向策略选择层，鼓励探索更好的计划；当目标趋于稳定时，奖励则更多分配给语言执行层，以精炼表达。
  - **算法目标**：通过这种动态平衡，模型能够同时优化**目标完成度**和**策略遵循度**。

## 3. 实验设计
- **数据集/场景**：采用 **SOTOPIA基准**，这是一个面向多智能体社交谈判与交互任务的标准化测试平台。
- **对比方法**：主要与 **GPT‑4o** 作为基线模型进行比较。摘要未列出的方法可能包括其他未优化的开源LLM或传统强化学习变体，但核心对比是微调后的 Qwen2.5‑7B agent 与 GPT‑4o。
- **评估指标**：以**目标完成成功率**（goal completion success）作为核心评价指标。
- **实验结果**：微调后的 Qwen2.5‑7B 智能体在目标完成成功率上**超越GPT‑4o达7.32%**，在该多智能体社交谈判任务上取得最优表现。

## 4. 资源与算力
- 论文摘要及提供的元数据中**未明确说明训练所使用的GPU型号、数量或训练时长**。仅能推断出该方法基于 Qwen2.5‑7B 模型进行微调，所需的算力资源可能介于常规7B模型全参数或高效微调之间，但具体配置需查阅正文方可获知。

## 5. 实验数量与充分性
- **实验组数**：从摘要可确认的只有 SOTOPIA 基准上的一个主要实验。正文中可能包含消融实验或更多对比，但摘要未予提供。
- **充分性与公平性**：
  - 仅凭摘要信息，实验的覆盖面显得**较为单薄**，仅在一个基准上与单一基线对比。
  - 若论文未补充在不同社交场景、不同基座模型、或者不同难度等级下的实验，则实验充分性存疑。
  - 对比对象选定 GPT‑4o 是一个强基线，且对比时双方处于“多智能体谈判”的同一任务设定下，基础比较较为公平。

## 6. 论文的主要结论与发现
- **分层规划有效**：将社交对话明确划分为策略规划和语言生成两个阶段，能帮助LLM更好地应对多轮、动态的长期目标。
- **话语级精细奖励关键**：方差门控的层次强化学习算法能够根据目标达成的不确定性动态调整奖励流向，相较于统一全局奖励，**更有利于平衡全局目标与局部表达**。
- **性能突破**：在 SOTOPIA 社交谈判任务上，经过TSR框架和LHRL‑VGR微调的7B模型，**成功率达到超越GPT‑4o的新高度**，证明了小模型可以通过结构化推理和精细奖励在大社交场景中击败通用大模型。

## 7. 优点
- **理论驱动的框架创新**：借鉴心理学的“计划行为理论”，将社交对话建模为“思考‑策略‑回应”的认知过程，为LLM的社交推理提供了清晰的结构化蓝图。
- **精细化的奖励设计**：方差门控奖励机制是一种新颖的路由策略，有针对性地解决了层次强化学习中信用分配问题，具有通用性潜力。
- **效率与性能兼具**：仅微调7B模型即超越规模更大的GPT‑4o，在推理开销和部署成本上具有显著优势。
- **任务针对性**：聚焦于多智能体社交谈判这一现实挑战，研究问题明确且有应用价值。

## 8. 不足与局限
- **与情感的直接关联较弱**：论文虽涉及社交智能，但并未直接处理情感识别、共情或情感计算，其贡献更多在于目标导向的策略规划。
- **实验多样性不足**：基于摘要仅见 SOTOPIA 一个任务，对于其他类型的社交对话（如开放式闲聊、支持性对话）的泛化能力未得到验证。
- **对比方法可能有限**：摘要仅提及GPT‑4o，缺少与更多强化学习对话策略、或者同类层次式方法的直接比较。
- **奖励函数依赖性**：方差门控奖励的设计依赖于一个可靠的目标完成度评分器，若该评分信号本身有偏或噪声较大，方法效果可能受限。
- **未说明算力与复现细节**：欠缺训练资源描述，给复现和成本评估带来困难。
- **应用限制**：当前的社交谈判设定相对封闭，真实世界的社交还涉及人格、长期关系维护、文化背景等复杂因素，论文方法尚未涉及这些维度。

（完）
