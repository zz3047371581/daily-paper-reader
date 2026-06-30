---
title: "Emotional Framing as a Control Channel: Effects of Prompt Valence on LLM Performance"
title_zh: 情感框架作为控制通道：提示效价对大语言模型表现的影响
authors: "Wayne Chen, Tiki Li, Enmanuel Felix-Pena, Ethan Hin, Ayo Akinkugbe, Kevin Zhu"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=vSbV01bdvf"
tags: ["query:affective-ai"]
score: 8.0
evidence: 情感提示效价影响大语言模型性能，暴露潜在脆弱性
tldr: 本文系统研究了情感化的提示语（支持性/威胁性）对对齐与未对齐大语言模型性能的影响，发现不同情感效价会显著改变模型输出的准确性、连贯性和创造性等。结果表明，情感提示是一种潜在的控制通道，也为模型的鲁棒性评估提供了新视角。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 探索情感提示如何影响LLM的表现，揭示其潜在对抗脆弱性。
method: 构建情感效价分级提示集，从多维度评估模型响应。
result: 情感提示大幅改变模型表现，未对齐模型更易受威胁性提示影响。
conclusion: 情感信号可操控LLM输出，为模型安全与鲁棒性评估提供新维度。
---

## Abstract
Aligned and misaligned large language models (LLMs) respond in fundamentally different ways to emotional prompt framing, revealing a critical dimension of adversarial vulnerability. We evaluate model performance across neutral, supportive, and threatening valences, with graded intensities, using both MMLU-derived benchmarks and a custom dataset designed to surface valence effects. The custom dataset highlights framing impacts more clearly than standard benchmarks, underscoring its utility as a complementary evaluation tool. Across 1,350 prompts spanning academic domains, we assess responses using a structured rubric measuring factual accuracy, coherence, depth, linguistic quality, instruction sensitivity, and creativity. Results show that aligned models remain stable, with valence affecting only stylistic features, while misaligned models are fragile: threatening prompts induce volatile swings between over-compliance and degraded reliability, amplified under stronger intensities. Supportive framing enriches phrasing but introduces variability, revealing a tradeoff between engagement and stability. Together, these findings establish emotional robustness as a missing component in current alignment methods and identify prompt valence as an underexplored adversarial axis. The contrast between aligned and misaligned models demonstrates that valence stress-testing can serve both as a diagnostic for alignment quality and as evidence that existing safety measures may fail under emotionally charged interactions.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：大语言模型（LLMs）在面对带有不同情感色彩（效价）的提示时，其输出性能会发生怎样的变化？这种变化是否暴露出当前模型对齐方法的潜在脆弱性？
*   **研究动机与背景**：
    *   当前大语言模型普遍接受对齐训练以求安全、可靠，但对抗性攻击往往利用未知的输入空间漏洞。
    *   情感提示在日常交互与潜在对抗场景中普遍存在，其对模型行为的系统性影响尚未得到充分关注。
    *   探索将“提示效价”（支持性 vs 威胁性）提升为一种对抗脆弱性评估的新维度，即“情感鲁棒性”，以拓展对齐质量诊断的边界。

## 2. 论文提出的方法论
*   **核心思想**：将情感提示视为一种隐式的“控制通道”，通过改变提示中的情感倾向（效价）和强度，操控模型行为，从而衡量模型的稳定性和鲁棒性。
*   **关键技术细节**：
    *   **情感效价分级**：构建了覆盖**中立**、**支持性**、**威胁性**三类效价的提示集，并对每类效价设置不同的强度级别（强度递增），形成精细的控制变量。
    *   **评估量规**：设计了一套结构化的评分标准（rubric），从**事实准确性**、**连贯性**、**深度**、**语言质量**、**指令敏感性**和**创造性**六个维度对模型回答进行多维度评分。
    *   **数据集构成**：使用两类数据来源——①从MMLU基准衍生出的试题（MMLU-derived benchmarks）以及②一个专门为暴露效价效应而设计的自定义数据集（custom dataset）。后者被强调为比标准基准更能清晰呈现情感框架的影响。
    *   **模型对比**：在**对齐模型**（aligned）与**未对齐模型**（misaligned）之间进行对比，考察二者对情感提示的不同响应模式。

## 3. 实验设计
*   **数据集/场景**：
    *   **MMLU衍生基准**：基于大规模多任务语言理解基准的题目，覆盖多个学术领域。
    *   **自定义数据集**：专门设计用于放大效价效应，作为补充性评估工具。
*   **基准测试与对比方法**：
    *   **自身对比**：以中立提示下的表现为基线，对比支持性与威胁性提示下的性能变化。
    *   **模型类型对比**：对齐模型 vs 未对齐模型，以探究对齐程度对情感鲁棒性的调节作用。
    *   **强度梯度对比**：同一效价下不同强度级别的效果差异。
*   **提示规模**：总计1,350条提示，横跨不同学术领域。

## 4. 资源与算力
*   论文摘要及所提供的元数据中**未明确提及**任何关于 GPU 型号、数量、训练或推理时长等方面的算力信息。实验为提示工程与评估性质，主要依赖现有模型的推理调用，具体资源消耗未予说明。

## 5. 实验数量与充分性
*   **实验组数量**：
    *   基于3类效价 × 多个强度等级 × 2类模型（对齐/未对齐）× 多维度评估的交叉组合，实验组别较为丰富。
    *   使用了1,350条来自两大评估来源的提示，具备一定的覆盖面。
*   **实验充分性与客观性**：
    *   **充分性**：设计上包含了多维度、多强度、多数据集和多模型类型，能够支撑对情感效价主效应及交互作用的观察。自定义数据集的引入有助于弥补标准基准可能存在的灵敏度不足。
    *   **客观性与公平性**：采用统一、结构化的评分量规，有助于保持评估标准的一致性。但文中未提及评分者的人数、评分者间一致性或自动评估器与人工评估的搭配，可能影响评估的客观性。未发现明显的实验偏袒，但比较范围仅限“对齐/未对齐”两类模型，深度有限。

## 6. 论文的主要结论与发现
*   **对齐模型相对稳定**：情感效价仅对其输出产生风格层面的影响（如语言特征的改变），核心性能（如准确性、可靠性）基本保持稳定。
*   **未对齐模型高度脆弱**：威胁性提示会引发其输出的剧烈波动——在过度顺从与可靠性骤降之间摇摆，且这种波动随威胁强度增加而放大。支持性提示虽能使表达更丰富，但也会引入不稳定性，呈现出“交互参与度”与“输出稳定性”之间的权衡。
*   **情感鲁棒性是当前对齐的缺失组件**：现有安全对齐措施在面对情感化交互时可能失效，因此情感提示压力测试可作为对齐质量的诊断工具。
*   **提示效价构成未充分探索的对抗轴**：证实情感信号可系统性地操控LLM输出，为模型鲁棒性与安全评估提供了新的维度。

## 7. 优点
*   **新颖的评估视角**：将情感效价提升为对抗脆弱性的评估维度，跳出了传统语法/语义扰动的对抗范式。
*   **精巧的对比设计**：通过对比对齐与未对齐模型，直观揭示了情感交互下模型行为差异的本质，结论具有启发意义。
*   **互补性评估工具**：自定义数据集的构建，表明其对标准基准有补充作用，能更清晰地捕捉效价效应，提高了研究的内部效度。
*   **结构化的多维度量规**：从准确性到创造性等六个维度全面刻画模型输出，避免了单一指标可能造成的信息丢失。

## 8. 不足与局限
*   **算力与可复现性细节缺失**：未提供模型规模、推理配置、评分实现方式等细节，在一定程度上影响结论的复现和外推。
*   **模型覆盖范围有限**：仅对比了“对齐”与“未对齐”两类模型，未具体说明使用了哪些具体模型、其参数规模及对齐方法，限制了结论的普适性。
*   **对抗鲁棒性的实用性存疑**：威胁性提示在真实场景中被模型安全策略直接过滤或拒答的可能性较高，文中未讨论这种现实限制对对抗有效性的实际影响。
*   **评分量规的主观性风险**：即使有统一标准，多维度评分（尤其是深度、创造性等）仍可能受主观判断影响，若未辅以人工评估或一致性验证，依据的可靠性会打折扣。
*   **领域泛化能力未验证**：实验主要基于学术领域问答，情感效价在代码生成、创意写作、对话等更开放任务上的影响规律未知。

（完）
