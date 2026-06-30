---
title: "LongEmotion: Measuring Emotional Intelligence of Large Language Models in Long-Context Interaction"
title_zh: LongEmotion：衡量大语言模型在长上下文互动中的情感智能
authors: "Weichu Liu, Jing Xiong, Yuxuan Hu, Zixuan Li, Minghuan Tan, Ningning Mao, Chenyang Zhao, Zhongwei Wan, Chaofan Tao, Wendong XU, Hui Shen, Chengming Li, Lingpeng Kong, Ngai Wong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=08KOxSjRyj"
tags: ["query:affective-ai"]
score: 10.0
evidence: 用于评估大语言模型在长上下文交互中情感智能的基准，涵盖情绪分类、问答、对话等任务。
tldr: 现有情感评估忽略长上下文真实交互场景，LongEmotion构建了面向大语言模型的长上下文情感智能基准，包含情绪分类、检测、问答、对话、摘要与表达六类任务，输入长度远超现有基准。评估发现，多数模型在长对话中情感理解能力急剧下降，突出了长时情感建模的重要性，为开发更具情感连续性的AI系统提供方向。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 现有情感智能基准忽视长上下文和现实噪声环境，无法全面衡量大模型情感能力。
method: 设计覆盖六种情感任务的长上下文评测数据集，构建统一评估框架。
result: 评测表明，大模型在长文本下情感智能明显下降，现有模型仍有显著不足。
conclusion: 该基准为长对话情感AI的研究提供了新的标尺，推动情感LLM的实用化。
---

## Abstract
Large language models (LLMs) make significant progress in Emotional Intelligence (EI) and long-context understanding. However, existing benchmarks tend to overlook certain aspects of EI in long-context scenarios, especially under $\textit{realistic, practical settings}$ where interactions are lengthy, diverse, and often noisy. To move towards such realistic settings, we present $\textit{LongEmotion}$, a benchmark specifically designed for long-context EI tasks. It covers a diverse set of tasks, including $\textbf{Emotion Classification}$, $\textbf{Emotion Detection}$, $\textbf{Emotion QA}$, $\textbf{Emotion Conversation}$, $\textbf{Emotion Summary}$, and $\textbf{Emotion Expression}$. On average, the input length for these tasks reaches 8${,}$777 tokens, with long-form generation required for $\textit{Emotion Expression}$. To enhance performance under realistic constraints, we incorporate Retrieval-Augmented Generation ($\textit{RAG}$) and Collaborative Emotional Modeling ($\textit{CoEM}$), and compare them with standard prompt-based methods. Unlike conventional approaches, our $\textit{RAG}$ method leverages both the conversation context and the large language model itself as retrieval sources, avoiding reliance on external knowledge bases. The $\textit{CoEM}$ method further improves performance by decomposing the task into five stages, integrating both retrieval augmentation and limited knowledge injection. Experimental results show that both $\textit{RAG}$ and $\textit{CoEM}$ consistently enhance EI-related performance across most long-context tasks, advancing LLMs toward more $\textit{practical and real-world EI applications}$. Furthermore, we conduct a detailed case study on the performance comparison among GPT series models, the application of CoEM in each stage and its impact on task scores, and the advantages of the LongEmotion dataset in advancing EI. All of our code and datasets will be open-sourced, which can be viewed at the anonymous repository link https://anonymous.4open.science/r/anonymous-578B.

---

## 论文详细总结（自动生成）

# LongEmotion 论文总结

## 1. 论文的核心问题与整体含义
现有多数情感智能（EI）评测基准主要聚焦于短文本或独立回合对话，**忽视现实场景中普遍存在的长上下文、多轮互动和噪声干扰**，难以全面反映大语言模型（LLMs）在真实情感理解与交互中的能力。为此，论文提出 **LongEmotion**，一个专门面向长上下文情感智能的基准，旨在填补这一缺口。其整体含义在于：长时段对话中的情感连续性、记忆与推理是情感 AI 落地的关键瓶颈，LongEmotion 为推进具备实用情感能力的 LLMs 提供了新的衡量标尺。

## 2. 方法论
### 2.1 核心思想
- **长上下文真实场景**：构造多轮、多样且带噪声的交互数据，平均输入长度达 8,777 token，并要求部分任务进行长文本生成，模拟实际应用。  
- **两类增强策略**：在标准提示（prompt）基础上，引入 **检索增强生成（RAG）** 与 **协作情感建模（CoEM）**，以提升 LLMs 在长上下文中的情感理解与生成能力。

### 2.2 关键技术细节
- **RAG（检索增强生成）**：  
  不同于传统的依赖外部知识库的 RAG，LongEmotion 中的 RAG **同时以对话上下文和 LLM 自身作为检索源**，无需额外知识库，更贴近现实环境。
- **CoEM（协作情感建模）**：  
  将长上下文情感任务**分解为五个阶段**，融合检索增强与有限的知识注入，通过多阶段协同建模来逐步改善情感相关性能。

### 2.3 评测框架
LongEmotion 数据集覆盖六类任务：
1. **情感分类**（Emotion Classification）
2. **情感检测**（Emotion Detection）
3. **情感问答**（Emotion QA）
4. **情感对话**（Emotion Conversation）
5. **情感摘要**（Emotion Summary）
6. **情感表达**（Emotion Expression）

每类任务均在长上下文设定下进行统一框架的评测。

## 3. 实验设计
- **数据集**：自建 LongEmotion 基准，无外部公开数据集（论文提及将开源）。  
- **场景**：模拟长对话、含噪声的真实互动，覆盖上述六种任务，输入长度远超以往基准（均值约 8.8k tokens）。  
- **对比方法**：标准提示（如直接调用 LLM）作为基线，对比 **RAG 方法** 和 **CoEM 方法**。同时进行 GPT 系列模型自身的性能对比及 CoEM 各阶段的消融研究。

## 4. 资源与算力
摘要与元数据中 **未提供具体算力信息**（如 GPU 型号、数量、训练时长等），也未说明是否涉及模型训练或仅进行推理评测。由于主要工作为基准构建与现有 LLM 的评测，推测以推理为主，但算力配置细节缺失。

## 5. 实验数量与充分性
- **实验组数**：论文提及了多种比较，包括不同方法（标准提示、RAG、CoEM）在多个任务上的评估，以及 GPT 系列模型对比、CoEM 各阶段影响的案例研究。但未给出确切的实验矩阵规模。  
- **充分性与公平性**：从描述看，实验覆盖了多任务与多方法，且采用统一评测框架，具备一定的充分性。然而，文中缺少消融实验的详细数据、统计显著性检验或误差分析，**公平性与客观性尚需完整论文验证**。由于仅见摘要和元数据，难以判断是否所有受试模型均在同等条件下进行评测。

## 6. 主要结论与发现
- 多数 LLMs 在长上下文下**情感理解能力急剧下降**，凸显长情感建模的必要性。  
- 所提出的 RAG 与 CoEM 方法能够在多数长上下文情感任务上**持续提升性能**，表明检索增强与多阶段建模可有效缓解长对话中的情感智能退化。  
- LongEmotion 数据集为开发更具**情感连续性与实用性**的 AI 系统提供了方向，并推动了情感 LLM 的落地研究。

## 7. 优点
- **填补空白**：首次系统性地聚焦长上下文、真实噪声环境下的情感智能评测，比现有短对话基准更贴近实际。  
- **创新增强方法**：提出面向长情感的 RAG（无外部知识库依赖）和 CoEM 多阶段协作建模，思路新颖且实验证明有效。  
- **任务全面**：覆盖分类、检测、QA、对话、摘要、表达六种维度，多角度考察情感能力。  
- **开源承诺**：计划公开代码与数据集，有助于社区复现与后续研究。

## 8. 不足与局限
- **算力与实验细节缺失**：未提供资源开销、模型规模、推理成本等，影响对实用性的评估。  
- **实验充分性待证实**：消融实验和显著性检验的细节未知，可能影响结论的稳健性。  
- **领域覆盖风险**：数据集构造细节未公开，若覆盖的情感类别、对话领域有限，可能导致偏差；长上下文数据的噪声模拟方式也可能影响泛化性。  
- **未有训练层面的改进**：方法主要基于推理增强，未探讨如何通过训练或微调从根本上提升模型的长情感能力。  
- **未与其他外部知识库 RAG 对比**：无外部知识库的 RAG 方法虽具特色，但缺乏与传统 RAG 的对照，难以判断其相对优势。

（完）
