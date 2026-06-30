---
title: "UDDETTS: Unifying Discrete and Dimensional Emotions for Controllable Emotional Text-to-Speech"
title_zh: UDDETTS：统一离散与维度情绪的可控情感文本到语音合成
authors: "Jiaxuan Liu, Yang Xiang, Han zhao, Xiangang Li, Yingying Gao, Shilei Zhang, Zhen-Hua Ling"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=DuPYSaCiep"
tags: ["query:affective-ai"]
score: 10.0
evidence: 基于大语言模型的情感语音合成框架，统一离散和维度情感以实现可控生成。
tldr: 针对现有情感语音合成无法细粒度捕捉情绪复杂性和连续性的问题，提出UDDETTS，一个统一离散和维度情绪的大语言模型框架，通过平衡数据生成和可解释的情绪控制，实现可控的情感语音生成。实验表明该框架能有效合成具有细腻情绪变化的语音，推动了情感AI在交互应用中的发展。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 传统TTS依赖离散情感标签，无法表达情绪的连续性和复杂性，且缺乏大规模均衡数据集，模型易过拟合。
method: 提出UDDETTS框架，在大语言模型中统一离散和维度情感表示，实现可解释的细粒度情绪控制。
result: 实验表明该框架能合成丰富情感表达的语音，比传统方法更准确和自然。
conclusion: 该工作为情感语音合成提供了一种新范式，促进了多模态人机交互中的情感表达。
---

## Abstract
Recent large language models (LLMs) have made great progress in the field of text-to-speech (TTS), but they still face major challenges in synthesizing fine-grained emotional speech in an interpretable manner. Traditional methods rely on discrete emotion labels to control emotion categories and intensities, which cannot capture the complexity and continuity of human emotional perception and expression. The lack of large-scale emotional speech datasets with balanced emotion distributions and fine-grained emotional annotations often causes overfitting in synthesis models and impedes effective emotion control. To address these issues, we propose UDDETTS, a universal LLM framework unifying discrete and dimensional emotions for controllable emotional TTS. This model introduces the interpretable Arousal-Dominance-Valence (ADV) space for dimensional emotion description and supports emotion control driven by either discrete emotion labels or nonlinearly quantified ADV values. Furthermore, a semi-supervised training strategy is designed to comprehensively utilize diverse speech datasets with different types of emotional annotations to train the UDDETTS. Experiments show that UDDETTS achieves linear emotion control along three interpretable dimensions, and exhibits superior end-to-end emotional speech synthesis capabilities. Code and demos are available at: https://anonymous.4open.science/w/UDDETTS.

---

## 论文详细总结（自动生成）

```markdown
# UDDETTS: Unifying Discrete and Dimensional Emotions for Controllable Emotional Text-to-Speech 论文总结

## 1. 研究动机与核心问题
- **核心问题**：现有情感文本到语音合成（Emotional TTS）难以在**细粒度**和**可解释性**层面上合成情感语音。
- **主要痛点**：
  - 传统方法依赖**离散情感标签**（如“开心”、“悲伤”）控制情绪类别和强度，无法捕捉人类情感感知与表达的**复杂性**与**连续性**。
  - 大规模情感语音数据集普遍存在**类别分布不均**、缺乏**细粒度情感标注**的问题，导致模型容易过拟合，难以实现有效的情感控制。
- **研究目标**：提出一个统一离散（类别）与维度（可量化连续空间）情绪表征的大语言模型（LLM）框架，实现**可控**且**可解释**的细粒度情感语音合成。

## 2. 方法论
- **核心框架：UDDETTS**（Unifying Discrete and Dimensional Emotional TTS）。
- **关键技术细节**：
  - **维度情绪空间**：引入可解释的 **Arousal-Dominance-Valence (ADV)** 三维连续空间来描述情绪，Arousal 表示激活度，Dominance 表示支配感，Valence 表示效价（愉悦度），三者共同量化情绪的细微变化。
  - **统一控制机制**：模型支持两种驱动方式——既可通过传统的**离散情感标签**控制，也可通过**非线性量化的 ADV 值**进行细粒度的连续调节。
  - **半监督训练策略**：为解决不同数据集标注类型（仅有离散标签 / 仅有维度标注 / 两者兼有）不统一的问题，设计了一种**半监督学习方案**，能够综合、高效地利用多种异构情感语音数据进行联合训练。
  - 方法本质上是**端到端**的大语言模型架构，将离散与维度情绪统一到同一表征空间中，实现从语言特征到语音波形的直接映射与情感控制。

## 3. 实验设计
- **数据集**：论文摘要中未列出具体公开数据集名称，但可明确其使用了**多种具有不同情感标注类型**的数据集（含离散标签和维度标注）用于半监督训练（具体数据集名称需查阅全文）。
- **基准与对比方法**：摘要提及与“传统方法”进行对比，传统方法主要指仅依赖离散情感标签进行控制的 TTS 模型；UDDETTS 展示了相较于传统方法更优越的合成能力。具体对比对象及评价指标需见原文实验部分。
- **实验任务**：验证 UDDETTS 在**线性情绪控制**（沿三个可解释维度）及**端到端情感语音合成**上的能力。

## 4. 资源与算力
- 摘要未提供任何关于硬件资源（GPU 型号、数量）、训练时长、参数量等算力信息。这部分细节需查阅论文正文或附录。

## 5. 实验数量与充分性（基于现有信息推断）
- **实验组别**：至少包含与“传统方法”的对比实验、展示三维线性情绪控制效果的定性/定量实验，以及可能验证半监督训练策略有效性的消融实验。
- **充分性评估**：从摘要描述看，实验聚焦在框架的整体合成能力与可控性上，但未给出多维度客观评测指标（如 MOS 分、情感识别准确率等）的细节。实验是否充分需结合全文的客观评测、主观测听及消融研究来综合判断。
- **公平性**：若对比传统方法时保持了数据、模型规模等条件的一致性，则具有公平性，摘要尚未提供相关信息。

## 6. 主要结论与发现
- **线性可控**：UDDETTS 能够沿 ADV 三个可解释维度实现**线性的情感控制**，生成具有细微情感变化的语音。
- **合成性能优越**：在端到端情感语音合成任务上表现出**优于传统方法**的能力，可生成情感表达更丰富、更自然的语音。
- **新范式**：这项工作将离散和维度情绪统一于大语言模型框架下，为情感语音合成提供了**一种新范式**，有助于促进多模态人机交互中的情感表达。

## 7. 优点与亮点
- **统一建模**：首次在 LLM-based TTS 中统一离散情感类别与连续 ADV 维度空间，解决了情感表达的复杂性与连续性问题。
- **可解释性**：ADV 空间本身具有心理学可解释性，实现的控制维度直观易懂。
- **数据高效利用**：提出的**半监督训练策略**能融合不同标注类型的数据集，缓解了单一类型标注数据稀缺和不平衡的问题。
- **灵活驱动**：同时支持离散标签与连续值两种控制方式，应用场景更广泛。

## 8. 不足与局限
- **实验信息缺失**：摘要未提供具体数据集、对比模型、评测指标（如情感控制精度、自然度 MOS）和消融实验细节，难以评估实验的完备性与结论的稳健性。
- **维度表征的局限性**：ADV 模型虽然经典，但并非人类情绪的唯一维度解释（如可能忽略“新奇度”等维度），其非线性量化方法的效果和普适性尚需验证。
- **应用风险**：基于 ADV 的连续控制可能引入**非自然或极端情感组合**（如高 Arousal、高 Valence 但低 Dominance），生成的情感语音可能存在扭曲或不真实的风险，需谨慎约束生成空间。
- **偏差风险**：半监督训练若数据集偏差较大，可能导致模型偏向于数据量大的情感类型或特定标注风格，需额外关注公平性与泛化能力。

（完）
```
