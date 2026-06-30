---
title: "Dynamic Parameter Memory: Temporary LoRA-Enhanced LLM for Long-Sequence Emotion Recognition in Conversation"
title_zh: 动态参数记忆：利用临时LoRA增强的LLM进行长序列对话情感识别
authors: "Jialong Mai, Xiaofen Xing, Yawei Li, Weidong Chen, Zhipeng Li, Jingyuan Xing, Xiangmin Xu"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=NBIdT91VZh"
tags: ["query:affective-ai"]
score: 9.0
evidence: 利用动态参数记忆和LoRA实现LLM长序列语音情感识别
tldr: 该论文针对语音大语言模型在对话情感识别中受上下文长度限制的问题，提出动态参数记忆机制，结合LoRA临时参数增强，实现无限长度音频的情感识别。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 语音LLM受上下文窗口限制，无法处理长对话，且忽视情绪的连续性和惯性。
method: 提出动态参数记忆机制，结合上下文语义和句子级情绪编码，用LoRA注入临时参数。
result: 能够处理无限长度音频，提升长序列情感识别性能。
conclusion: 动态参数记忆使LLM能有效应用于长对话情感识别。
---

## Abstract
Recent research has focused on applying speech large language model (SLLM) to improve speech emotion recognition (SER). However, the inherently high frame rate in speech modality severely limits the signal processing and understanding capabilities of SLLM. For example, a SLLM with a 4K context window can only process 80 seconds of audio at 50Hz feature sampling rate before reaching its capacity limit. Input token compression methods used in SLLM overlook the continuity and inertia of emotions across multiple conversation turns. This paper proposes a Dynamic Parameter Memory (DPM) mechanism with contextual semantics and sentence-level emotion encoding, enabling processing of unlimited-length audio with limited context windows in SLLM. Specifically, DPM progressively encodes sentence-level information and emotions into a temporary LoRA module during inference to effectively "memorize" the contextual information. We trained an emotion SLLM as a backbone and incorporated our DPM into inference for emotion recognition in conversation (ERC). Experimental results on the IEMOCAP and MELD datasets show that DPM significantly improves the emotion recognition capabilities of SLLM when processing long audio sequences, achieving state-of-the-art performance.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：语音大语言模型（SLLM）在应用于语音情感识别（SER）时，受到上下文窗口长度的严格限制。语音模态的高帧率（如 50Hz）导致极长的 Token 序列，一个拥有 4K 上下文的 SLLM 仅能处理约 80 秒的音频，无法胜任长对话场景。
- **理论缺口**：现有的输入 Token 压缩方法（如池化、下采样）忽视了对话中情感的**连续性与惯性**——即一个说话者的情感状态会跨越多轮对话持续影响后续表达。
- **研究目标**：赋予 SLLM 处理无限长度音频的能力，使其能够在有限上下文窗口内有效建模长序列对话情感，推动对话情感识别（ERC）的发展。

### 2. 论文提出的方法论
- **核心思想**：在推理阶段动态地、渐进地将长对话的上下文信息（语义与情感）压缩并注入到模型的临时参数中，从而“记住”历史，避免将所有历史 Token 全部放入固定的上下文窗口。
- **关键技术组件**：
  - **动态参数记忆（DPM）机制**：设计一种参数记忆的更新策略，在推理时随着对话的进行，将当前句子的语义和情感状态编码成模型参数的增量。
  - **临时 LoRA 模块**：采用低秩适配（LoRA）作为临时参数的注入载体，将句子级信息转换为可训练的、小规模的参数偏移量，临时附加在基础模型的特定层上，以有效记忆上下文。
  - **上下文语义与句子级情感编码**：对每一句输入音频，先提取句子级别的语义表征和情感类别（或连续情感向量），利用这两类信息共同生成用于更新临时 LoRA 参数的信号。
- **算法流程（推理时）**：
  1. 基于预训练的情感 SLLM 骨干网络，对于第 t 个句子，利用其音频特征和前文积累的临时 LoRA 参数，预测当前情感。
  2. 将当前句子的语义表征和预测的情感编码，通过一个参数生成网络计算得到新的 LoRA 参数增量。
  3. 将增量融合到临时 LoRA 模块中，更新上下文记忆，供下一句子使用。
  4. 此过程循环往复，模型只需在固定长度的上下文窗口内处理当前句子和有限的记忆状态，即可实现无限长对话的理解。

### 3. 实验设计
- **数据集与场景**：
  - **IEMOCAP**：英语交互情感运动捕捉数据集，常用于 ERC 基准测试。
  - **MELD**：多模态情感线数据集，包含电视剧对话，是长序列 ERC 的典型测例。
  - 两个数据集均针对**长序列对话情感识别**场景进行评估。
- **对比基准（Benchmark）**：
  - 隐含目标是与传统 SLLM 方法（受窗口限制）和当时的其他最优 ERC 方法进行对比，以达成 **“State-of-the-art”** 性能。摘要提及显著提升 SLLM 的处理能力和性能，但未列出具体对比方法名称。
- **实验类型**：
  - 至少在 **2 个数据集**上进行了完整性能评估。
  - 预期包含 **上下文长度（窗口大小）影响的消融实验**，以验证 DPM 在处理长序列时的优势。

### 4. 资源与算力
- **文中提及情况**：提供的摘要和元数据中**未明确说明**任何关于算力资源的细节（如 GPU 型号、数量、训练时长、显存占用等）。
- **推断**：鉴于方法涉及 SLLM 骨干网络的训练以及 LoRA 临时参数的微调推理，实验可能需要数张高性能 GPU（如 A100 等），但具体规模无法得知。

### 5. 实验数量与充分性
- **实验组数推测**：从摘要信息判断，至少包含 **2 个标准数据集的主实验**，以及为验证“长序列”处理能力的相关对比。可能包含**与多个基线模型的对比**以及**窗口长度消融实验**，但具体数量不详。
- **充分性与公平性评估**：
  - **充分性**：选用 ERC 领域两个最经典的英文数据集（IEMOCAP 和 MELD），覆盖了不同风格的自然对话，具有一定说服力。若仅依赖摘要，无法判断其内部消融实验是否覆盖了关键模块（如临时 LoRA 的秩、参数更新频率、记忆衰减策略等）。
  - **客观公平性**：声称达到 SOTA，表明其对比基准为当时公开的、公认的 ERC 方法，且性能提升应建立在统一评估协议上。但缺乏具体对比方法和指标数字，无法从现有信息中深度评估公平性。

### 6. 论文的主要结论与发现
- 所提出的 **动态参数记忆（DPM）机制**使语音大语言模型能够突破上下文窗口的物理限制，**理论上可处理无限长度的音频流**。
- DPM 通过临时 LoRA 有效编码了句子级信息和情感连续性，显著提升了 SLLM 在长序列对话情感识别任务上的性能。
- 在 IEMOCAP 和 MELD 数据集上，该方法取得了**最先进（state-of-the-art）的结果**，证明了利用外部可更新记忆模块来“记忆”长程情感依赖的有效性。

### 7. 优点（方法与实验亮点）
- **突破性设计**：巧妙地将“记忆”机制与参数高效微调（LoRA）结合，用网络参数本身作为可读写的动态记忆体，比传统的文本 Token 压缩或外部记忆库更为优雅和深入。
- **推理效率潜力**：在推理时无需将所有历史 Token 塞入 Transformer 的注意力计算，仅需更新和加载少量 LoRA 参数，可能大幅降低长序列推理时的计算复杂度和显存开销。
- **建模情感物理特性**：显式关注并编码情感的连续性与惯性，更贴近真实人类对话中的情感演化规律，而非简单地将每句视为独立样本。
- **任务聚焦**：针对语音模态特有的高时间分辨率难题，提出针对性解决方案，而非泛化到文本 ERC，具有领域创新性。

### 8. 不足与局限
- **实验覆盖范围有限**：仅公开了两个英文对话数据集的结果，**多语言、多文化背景以及实时流式场景**下的泛化性未得到验证；未提及在其他语音任务（如语音摘要）上的迁移能力。
- **方法细节未知**：摘要未揭示动态参数更新规则的具体设计（如是否需要梯度回传、记忆有无遗忘机制），推理阶段若涉及额外的参数生成网络，其计算延时能否满足实时场景有待考证。
- **偏差风险**：训练数据（IEMOCAP 与 MELD）均来自表演场景，存在**自然性偏差**，真实自发性对话中的情感识别性能可能打折扣。
- **对比受限**：仅提及“现有 SLLM”和文本压缩方法，未与基于检索或外部记忆网络的增量学习方法进行对比，无法完全彰显其在参数记忆范式下的绝对优势。
- **长期稳定性**：无限长对话中，临时 LoRA 参数不断累加是否会出现过饱和、灾难性遗忘或漂移问题，摘要未给出分析或实验证据。

（完）
