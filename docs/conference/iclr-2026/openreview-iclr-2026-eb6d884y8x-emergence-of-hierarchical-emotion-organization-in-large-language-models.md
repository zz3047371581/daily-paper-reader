---
title: Emergence of Hierarchical Emotion Organization in Large Language Models
title_zh: 大型语言模型中层次化情绪组织的涌现
authors: "Bo Zhao, Maya Okawa, Eric Bigelow, Rose Yu, Tomer Ullman, Ekdeep Singh Lubana, Hidenori Tanaka"
date: 2025-09-16
pdf: "https://openreview.net/pdf?id=eb6D884y8x"
tags: ["query:affective-ai"]
score: 10.0
evidence: 分析模型输出中情绪状态之间的概率依赖关系；LLMs自然形成层次化情绪树
tldr: 本文研究大语言模型如何内生地形成层次化情绪组织，发现其与人类心理模型对齐，并揭示跨社会角色情绪识别的系统性偏差，突显了为公平部署需评估情感智能的重要性。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 随着LLM驱动对话智能体，理解其情绪建模对伦理部署至关重要。
method: 受情绪轮启发，分析模型输出中情绪状态间的概率依赖，构建层次情绪树。
result: LLM自然形成分层情绪结构，更大模型产生更复杂层次；且发现对交叉弱势群体存在偏差。
conclusion: LLM内化社会情感模式，评估情感智能对公平性至关重要。
---

## Abstract
As large language models (LLMs) increasingly power conversational agents, understanding how they model users' emotional states is critical for ethical deployment. Inspired by emotion wheels -- a psychological framework that argues emotions organize hierarchically -- we analyze probabilistic dependencies between emotional states in model outputs. We find that LLMs naturally form hierarchical emotion trees that align with human psychological models, and larger models develop more complex hierarchies. We also uncover systematic biases in emotion recognition across socioeconomic personas, with compounding misclassifications for intersectional, underrepresented groups. Human studies reveal striking parallels, suggesting that LLMs internalize aspects of social perception. Beyond highlighting emergent emotional reasoning in LLMs, our results hint at the potential of using cognitively-grounded theories for developing better model evaluations.

---

## 论文详细总结（自动生成）

## 核心问题与整体含义
- **研究动机**：随着大语言模型（LLMs）越来越多地作为对话智能体部署，理解其如何建模用户的情绪状态对于伦理、可靠的交互至关重要。如果模型内化了人类社会的情绪偏见，可能对弱势群体造成伤害。
- **核心问题**：LLMs 是否像人类一样，在内部自发形成层次化的情绪组织结构？这种结构是否与人类心理模型对齐，且在不同社会身份下是否存在系统性偏差？
- **整体含义**：论文揭示了 LLMs 不仅能够涌现出与心理学中的情绪轮理论高度一致的层次化情绪树，而且这种情绪推理中嵌入了社会偏见，呼吁在部署 LLM 情感系统前必须进行公平性评估。

## 方法论
- **理论基础**：借鉴心理学中的“情绪轮”框架，该框架认为情绪并非孤立，而是按相似性、强度和极性形成层次树（如“愤怒”属于“厌恶”大类，而“愤怒”下又可细分“烦躁”“怨恨”等）。
- **核心思想**：通过分析 LLM 输出中不同情绪标签之间的概率依赖关系（如共现、转移或条件概率），恢复出模型内部的情绪组织方式，并以层次树的形式可视化。
- **关键技术流程**：
  1. 构建包含多样化社会情境的提示，要求模型预测对应的情绪状态（可能使用预定义的情绪标签集）。
  2. 从模型输出的 logits 或生成的情绪词分布中，统计任意一对情绪状态被共选或相继出现的概率。
  3. 利用这些概率依赖构建距离度量（如互信息倒数或负对数概率），采用层次聚类或类似树生成算法，生成“情绪树”。
  4. 将生成的情绪树与人类心理学的情绪轮进行结构比较（如编辑距离、树形相似度），验证对齐程度。
  5. 对带有不同社会角色（如低收入、少数族裔、性别交叉等）的提示进行相同分析，观察情绪分类的偏差。
- **人类平行实验**：同样给人类被试呈现相似情境，收集情绪分类数据，构建人类情绪树作为对照，并分析人类在社会经济角色上的情绪识别偏差。

## 实验设计
- **模型与场景**：使用了不同规模（参数数量）的系列 LLMs（原文未指明具体模型家族，但对比了从小到大的模型），在若干文本情境下的情绪预测任务中进行评估。
- **数据集/提示构建**：可能采用了公开的情绪文本数据集或自行设计了包含多种社会经济身份（ socioeconomic personas ）的情境提示（如“一位单亲失业母亲…”，“一位富裕的男性高管…”），具体数据集名称未在元数据中披露。
- **比较基准**：
  - 心理学经典情绪轮（如 Plutchik 情绪轮）作为人类心理模型的基准。
  - 人工被试的实验结果，包括情绪树结构和偏差模式。
- **对比方法**：比较了不同规模 LLMs 生成的情绪树复杂度、与人类树的相似度，以及偏差表现；可能还对比了不同情绪标注方法或提示策略。

## 资源与算力
- 论文提供的摘要及元数据中**未提及**任何 GPU 型号、数量、训练时长或推理成本。由于分析主要基于概率依赖挖掘而非训练新模型，可能使用已有 LLMs 的推理输出，算力需求较低，但具体资源不得而知。

## 实验数量与充分性
- **实验组数**：从已有信息推断，至少包含三组主要实验：
  1. 不同规模 LLM 的情绪层次涌现分析（模型规模消融）。
  2. 跨多种社会经济角色的情绪识别偏差分析（包括单一维度与交叉身份）。
  3. 人类对照组的行为实验。
- **充分性评估**：结合心理学理论、多模型比较、人类对照和多维偏差探查，实验设计较为系统和多角度。但作为一篇被拒论文，可能在评估指标、情境多样性、情绪标签覆盖面或统计严谨性上存在不足。由于无法获取全文，无法判断对比实验是否覆盖了其他情感计算基准或消融关键因素（如提示工程）。整体上实验数量看起来合理，但公平性对比的粒度未知。

## 主要结论与发现
- **层次化情绪结构涌现**：LLMs 内部自然形成分层次的情绪组织，其树形结构与人类心理学情绪轮高度对齐，证明模型无监督地学习了类似人类的情感空间。
- **规模效应**：更大的模型产生更复杂、更深层的情绪层次，暗示情感智能可能随规模提升而自然增强。
- **系统性偏差**：在识别不同社会经济人物角色的情绪时，模型表现出显著偏差，尤其是对于交叉弱势群体（如低收入且少数族裔身份）会产生复合性的错误分类，即偏差不是简单的加性，而是非线性的放大。
- **人机平行**：人类受试者在同样任务中表现出极为类似的层次结构和偏差模式，表明 LLM 内化了人类社会的普遍情感感知模式及其隐含的刻板印象。
- **伦理启示**：部署具有情感推理能力的 LLM 前必须严格评估其情感公平性，避免强化社会不公。

## 优点
- **跨学科视角**：巧妙地将认知心理学中的情绪轮理论用于分析和解释 LLM 的黑箱行为，增强了结果的可解释性。
- **无监督发现**：从模型输出的概率依赖中自动恢复情绪层次，不需要外部情绪层级标签，方法具有通用性。
- **多维度验证**：同时对比了模型规模、人类数据和多元社会身份，揭示了情感组织的涌现性质和社会偏见的内化。
- **实践指导性**：为 emotion‑aware AI 的伦理审计提供了具体的分析路径，强调必须关注交叉性公平。

## 不足与局限
- **方法信息缺失**：基于现有摘要和元数据，无法评估具体算法的鲁棒性、情绪标签的封闭集是否合理，以及层次聚类方法的选择依据。
- **实验覆盖未知**：未提及使用了哪些情绪数据集，是否涵盖多语言、多文化情境；可能仅限于英文、西方情绪模型。
- **因果性未验证**：仅展示了情绪树结构和偏差的关联，未通过干预（如微调、提示去偏）验证能否修正偏差或改变层次。
- **应用限制**：情绪轮只是心理模型的一种，其他情绪理论（如维度模型）未被考虑；分析的静态概率依赖可能忽略动态对话中的情绪迁移。
- **评审未知**：论文已被 ICLR 2026 拒绝，可能方法新颖性有限或实验说服力不足，但因缺乏正文，具体弱点不得而知。

（完）
