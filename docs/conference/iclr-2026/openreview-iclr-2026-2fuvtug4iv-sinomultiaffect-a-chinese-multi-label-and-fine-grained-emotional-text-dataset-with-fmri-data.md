---
title: "SinoMultiAffect: A Chinese Multi-Label and Fine-Grained Emotional Text Dataset with fMRI Data"
title_zh: SinoMultiAffect：一个带有fMRI数据的中文多标签细粒度情感文本数据集
authors: "Tingjuntao Ni, Yicheng Huang, Chunfeng Song, Lihui Wang"
date: 2025-09-05
pdf: "https://openreview.net/pdf?id=2fuvTuG4IV"
tags: ["query:affective-ai"]
score: 10.0
evidence: 一个包含fMRI脑数据的中文细粒度情感文本数据集，支持情绪神经关联研究。
tldr: 针对中文情感数据缺乏语言与神经模态整合的问题，构建包含4500句中文社交媒体文本的SinoMultiAffect数据集，提供35类细粒度情感标签、VAD维度标注以及fMRI脑成像数据，支持跨模态情感分析。该数据集为探索情感处理的神经机制和AI情感能力提升提供了独特资源。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 现有中文情感数据集缺乏细粒度标注和脑神经数据，难以支持人机交互情感深层研究。
method: 收集社交媒体文本，进行多标签细粒度情感和VAD维度标注，并采集fMRI数据形成多模态数据集。
result: 数据集包含4058条标注句子及fMRI，覆盖35种情感类别，为多模态情感研究提供新基准。
conclusion: 该数据集将语言与神经信号深度结合，推动AI情感理解与脑启发式模型的发展。
---

## Abstract
Emotion plays an indispensable role in advancing human-AI interaction, yet the field still lacks high-quality, fine-grained Chinese datasets that integrate both language and neural modalities. We present **SinoMultiAffect** (SMA), a multi-modal emotion dataset designed to advance research on emotion, language and the emotion-related capabilities of artificial intelligence. The dataset consists of 4,500 Chinese sentences in total collected from social media platforms in China, with 4,058 of them labeled with a fine-grained taxonomy of 35 emotion categories (including Neutral) with their intensity, as well as continuous annotations along the valence-arousal-dominance (VAD) dimensions. Our dataset also includes functional magnetic resonance imaging (fMRI) recordings of the brain while human participants were reading the sampled sentences. The utility of the dataset was demonstrated by the predictive performance of large language models (LLMs) on multi-label emotion recognition. We also built a VAD-guided human-LLM alignment framework, which revealed that incorporating emotional information enhances the alignment between text and brain embeddings and improves the downstream task performance of bidirectional retrieval. By integrating text, categorical, dimensional, and neuroimaging information, SMA provides a unique resource for studies on emotion and language, offering new opportunities for interdisciplinary research in natural language processing, affective computing, and cognitive neuroscience.

---

## 论文详细总结（自动生成）

### 1. 研究动机与背景
- **核心问题**：现有中文情感数据集缺乏细粒度多标签标注，且未融合语言与神经模态（如 fMRI 脑成像），难以支撑情感在人机交互、认知神经科学中的深层研究。
- **整体含义**：SinoMultiAffect 通过整合中文社交媒体文本、35 类细粒度情感标签、VAD（效价-唤醒-优势度）维度标注以及 fMRI 脑数据，为探索情感处理的神经机制、提升 AI 情感理解能力提供独特的多模态资源。

### 2. 方法论
- **核心思想**：构建一个跨文本、分类、维度、神经影像的多模态数据集，并利用大语言模型和人类脑信号的对齐来验证数据集价值。
- **关键技术与流程**：
  - **文本收集**：从中国社交媒体平台采集 4500 个中文句子。
  - **标注体系**：
    - 35 类细粒度情感（含中性），附带情感强度。
    - 沿效价-唤醒-优势度（VAD）三维的连续值标注。
  - **fMRI 采集**：记录人类参与者阅读句子时的全脑血氧水平依赖信号。
  - **模型对齐框架**：提出 VAD 引导的人-LLM 对齐框架，将情感维度信息引入文本与脑嵌入的对齐过程。

### 3. 实验设计
- **数据集与场景**：基于自主构建的 SinoMultiAffect，4058 条标注句子及其 fMRI 数据。
- **Benchmark 与对比**：
  - 使用大语言模型（LLMs）进行多标签情感识别性能评估。
  - 构建双向检索（brain-to-text, text-to-brain）作为下游任务，对比有无情感信息融入的对齐效果。
- **对比方法**：文中未详细列出对比模型，但提及了 VAD 引导对齐与传统对齐的差异，推测与仅用文本嵌入的基线对齐方法比较。

### 4. 资源与算力
- **文中未明确说明**使用的 GPU 型号、数量、训练时长或算力消耗，仅在摘要中提到使用大语言模型进行预测，未给出具体资源配置。

### 5. 实验数量与充分性
- **实验规模**：论文至少涉及两组主要实验：
  - LLM 在多标签情感识别上的性能测试。
  - VAD 引导的人-LLM 对齐实验，含双向检索下游任务。
- **充分性与公平性**：受限于文本提取信息不全，能看到的实验设计比较直接，未提及消融实验或不同模型的横向对比，但数据集本身具备多维度验证（标签、维度、神经信号），能够支撑后续更复杂的基准测试。

### 6. 主要结论与发现
- **SinoMultiAffect 数据集**成功整合多模态信息，成为中文情感与语言研究的新基准。
- **情感信息增强对齐**：VAD 引导的文本-脑嵌入对齐能够提升双向检索性能，提示情感维度在神经-语言映射中具有重要价值。
- **资源价值**：该数据集可推动 NLP、情感计算与认知神经科学的交叉研究，助力脑启发式 AI 模型发展。

### 7. 优点
- **模态融合**：首次在中文细粒度情感数据集中同步提供分类标签、维度标注和 fMRI 神经信号，实现语言与神经模态的深度结合。
- **细粒度与多标签**：35 类情感标签超越传统正负二元或少量类别，更贴近真实情绪表达。
- **应用导向**：所提出的 VAD 对齐框架验证了数据集在跨模态检索中的实用潜力，为 AI 情感能力增强提供方法支撑。

### 8. 不足与局限
- **数据集规模较小**：仅 4058 条句子，可能限制复杂模型训练和泛化能力。
- **模态相关性验证不足**：摘要中未提及跨被试信度、逐试次 fMRI 信号质量等细节，神经信号的有效性需进一步审查。
- **场景局限**：文本来源仅限于中国社交媒体，文化与语言多样性有限，迁移至其他语言或领域需额外验证。
- **未报告算力与实现细节**：使得可复现性受到影响，且无法评估模型训练成本。

（完）
