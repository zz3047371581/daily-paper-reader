---
title: "VowelPrompt: Hearing Speech Emotions from Text via Vowel-level Prosodic Augmentation"
title_zh: VowelPrompt：通过元音级韵律增强从文本中感知语音情感
authors: "Yancheng Wang, Osama Hanna, Ruiming Xie, Xianfeng Rui, Maohao Shen, Xuedong Zhang, Christian Fuegen, Jilong Wu, Debjyoti Paul, Arthur Guo, Zhihong Lei, Ozlem Kalinli, Qing He, Yingzhen Yang"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=PMbionN5cC"
tags: ["query:affective-ai"]
score: 9.0
evidence: 通过元音级韵律线索增强大语言模型的语音情感识别，将语音学知识融入情感推理
tldr: 针对大语言模型在语音情感识别中忽视细粒度韵律信息的问题，提出VowelPrompt框架，基于元音是情感韵律主要载体的语音学证据，将可解释的元音级韵律特征（如基频、强度、时长）注入文本提示，使LLM能利用韵律知识进行推理。实验表明该方法在准确率和可解释性上均优于纯文本方法，为情感LLM与声学知识的结合提供了新思路。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 现有LLM-based情感识别忽略细粒度韵律信息，缺乏可解释性。
method: 基于语音学事实，在文本提示中注入元音级韵律特征以增强LLM推理。
result: 准确率和可解释性均得到提升。
conclusion: 该工作证明了将声学知识与LLM结合对语音情感识别的有效性。
---

## Abstract
Emotion recognition in speech presents a complex multimodal challenge, requiring comprehension of both linguistic content and vocal expressivity, particularly prosodic features such as fundamental frequency, intensity, and temporal dynamics. Although large language models (LLMs) have shown promise in reasoning over textual transcriptions for emotion recognition, they typically neglect fine-grained prosodic information, limiting their effectiveness and interpretability. In this work, we propose VowelPrompt, a linguistically grounded framework that augments LLM-based emotion recognition with interpretable, fine-grained vowel-level prosodic cues. Drawing on phonetic evidence that vowels serve as primary carriers of affective prosody, VowelPrompt extracts pitch-, energy-, and duration-based descriptors from time-aligned vowel segments, and converts these features into natural language descriptions for better interpretability.
Such a design enables LLMs to jointly reason over lexical semantics and fine-grained prosodic variation. Moreover, we adopt a two-stage adaptation procedure comprising supervised fine-tuning (SFT) followed by Reinforcement Learning with Verifiable Reward (RLVR), implemented via Group Relative Policy Optimization (GRPO), to enhance reasoning capability, enforce structured output adherence, and improve generalization across domains and speaker variations. Extensive evaluations across diverse benchmark datasets demonstrate that VowelPrompt consistently outperforms state-of-the-art emotion recognition methods under zero-shot, fine-tuned, cross-domain, and cross-linguistic conditions, while enabling the generation of interpretable explanations that are jointly grounded in contextual semantics and fine-grained prosodic structure.

---

## 论文详细总结（自动生成）

## 1. 研究动机与核心问题  
- 语音情感识别是一个多模态挑战，需同时理解语言内容和声音表现力（尤其是基频、强度、时长等韵律特征）。  
- 当前基于大语言模型（LLM）的方法主要利用文本转录进行情感推理，普遍忽略了细粒度韵律信息，导致模型效果和可解释性受限。  
- 核心问题在于：如何将可解释的声学韵律线索注入 LLM，在不牺牲推理能力的前提下，提升语音情感识别的准确性与透明度。  

## 2. 方法论  
- **核心思想**：以语音学事实为基础——元音是情感韵律的主要载体，所以聚焦**元音级别的韵律特征**，并将其转化为自然语言描述，作为 LLM 提示的增广信息。  
- **关键技术细节**：  
  - 从时间对齐的元音片段中提取三类可解释特征：基频（pitch）、强度（energy）、时长（duration）。  
  - 将这些声学特征转换为自然语言描述，形成**韵律增强的文本提示**，使 LLM 能够同时推理词汇语义与细粒度韵律变化。  
- **训练策略**：  
  - 采用两阶段适应流程：  
    1. **有监督微调（SFT）**：让模型初步学习融合韵律信息的推理模式。  
    2. **基于可验证奖励的强化学习（RLVR）**：通过组相对策略优化（GRPO）施加结构化输出约束，进一步提升推理能力与跨域、跨说话人的泛化性。  

## 3. 实验设计  
- **数据集**：论文在多个基准数据集上进行了评估，涵盖**零样本、微调、跨域、跨语言**等多种条件（具体数据集名称在提供的摘要中未列出，但提到“diverse benchmark datasets”）。  
- **对比方法**：与 state-of-the-art 语音情感识别方法对比，包括传统的纯文本 LLM 方法。  
- **任务场景**：零样本直接推理、有监督微调后测试、域外泛化（跨数据集）、跨语言迁移等。  
- **评价维度**：准确率与生成解释的可解释性，后者强调上下文语义与细粒度韵律结构的共同支撑。  

## 4. 资源与算力  
- 所提供的摘要与元数据中**未明确提及** GPU 型号、数量、训练时长等算力细节。  
- 典型做法会涉及 LLM 微调（可能使用 8×A100 或类似配置），但具体信息缺失，无法准确总结。  

## 5. 实验数量与充分性  
- 实验中包含了多种设置：零样本、微调、跨域、跨语言，且在与现有方法的对比上展现出总体优势，说明**实验覆盖范围较广**。  
- 由于摘要没有给出具体的消融实验细节，但方法论中的两阶段流程（SFT + RLVR）暗示可能进行了消融分析（如仅 SFT 与 SFT+RLVR 对比）。  
- 整体来看，实验设计**比较多维，客观性较强**，在多个基准上超越 SOTA，表明评估相对公平。  

## 6. 主要结论与发现  
- 通过元音级韵律增强，LLM 的情感识别准确率在多种条件下**均优于纯文本方法**。  
- 生成的解释更具可解释性，因为其仍由上下文语义和细粒度韵律结构双重支撑。  
- 该工作证明了将声学知识与 LLM 相结合的可行性和有效性，为语音情感识别提供了新范式。  

## 7. 优点  
- **语音学驱动**：将元音作为韵律载体的语音学知识有机融入模型，增强了方法的内在合理性。  
- **可解释性**：韵律特征被显式转化为自然语言，使推理过程透明，便于分析模型决策依据。  
- **两阶段训练**：SFT 结合 RLVR 不仅提升性能，还强化了输出格式的规范性和泛化能力。  
- **评估全面**：覆盖零样本、跨域、跨语言等场景，验证了方法的鲁棒性。  

## 8. 不足与局限  
- 从摘要看，**缺少关键实验细节**（如数据集构成、消融实验定量结果、RLVR 的具体奖励设计），影响可复现性评估。  
- 未提及对**噪声、口音、极端情绪强度**等情况下的鲁棒性测试，可能高估实际部署的效果。  
- 依赖时间对齐的元音边界，实际应用中需额外预处理步骤，可能引入级联误差。  
- 对非英语语言或语调丰富语言的多语言泛化能力仍待更深入验证。  

（完）
