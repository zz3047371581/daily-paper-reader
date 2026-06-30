---
title: "EmotionTalk: An Interactive Chinese Multimodal Emotion Dataset With Rich Annotations"
title_zh: EmotionTalk：一个具有丰富标注的交互式中文多模态情感数据集
authors: "Haoqin Sun, Xuechen Wang, Jinghua Zhao, Shiwan Zhao, Jiaming Zhou, Hui Wang, Aobo Kong, Xi Yang, Yequan Wang, Yonghua Lin, Yong Qin"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=U7qDPmezw7"
tags: ["query:affective-ai"]
score: 9.0
evidence: 提供来自交互对话的高质量中文多模态情感数据集，涵盖语音、文本和视频
tldr: 针对中文多模态情感对话数据集稀缺的问题，提出EmotionTalk数据集，包含19对演员在二元对话中的语音、视频和文本记录，并提供丰富的情感标签。该数据集捕捉了中文独特的语言文化特征和复杂多模态交互，为推进中文多模态情感识别研究提供了关键资源。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 中文多模态情感数据集稀缺，制约相关研究。
method: 收集19对演员的交互式对话，提供多模态数据和丰富标注。
result: 构建了一个高质量中文多模态情感数据集EmotionTalk。
conclusion: 该数据集填补了中文多模态情感研究的空白，推动跨文化情感计算。
---

## Abstract
In recent years, emotion recognition has played an increasingly crucial role in applications such as human-computer interaction, mental health monitoring, and sentiment analysis. Although a large number of sentiment analysis datasets have emerged for mainstream languages such as English, high-quality and naturally recorded multimodal dialogue datasets remain extremely scarce for Chinese, given its unique linguistic characteristics, rich cultural connotations, and complex multimodal interaction features. In this work, we propose EmotionTalk, an interactive Chinese multimodal emotion dataset with rich annotations. This dataset provides multimodal information from 19 actors participating in dyadic conversational settings, incorporating acoustic, visual, and textual modalities. It includes 23.6 hours of speech (19,250 utterances), annotations for 7 utterance-level emotion categories (happy, surprise, sad, disgust, anger, fear, and neutral), 5-dimensional sentiment labels (negative, weakly negative, neutral, weakly positive, and positive) and 4-dimensional speech captions (speaker, speaking style, emotion and overall). The dataset is well-suited for research on unimodal and multimodal emotion recognition, missing modality challenges, and speech captioning tasks. To our knowledge, it represents the first high-quality and versatile Chinese dialogue multimodal emotion dataset, which is a valuable contribution to research on cross-cultural emotion analysis and recognition. Additionally, we conduct experiments on EmotionTalk to demonstrate the effectiveness and quality of the dataset. The EmotionTalk dataset will be made freely available for all academic purposes.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：当前主流情感分析数据集多针对英语等语言，**中文高质量、自然录制的多模态对话情感数据集极度稀缺**，阻碍了面向中文的情感计算研究。
- **整体含义**：通过构建并发布 **EmotionTalk**——一个具有丰富标注的交互式中文多模态情感数据集，填补该领域空白，为汉语情感识别、跨文化情感分析等提供基准，推动多模态、跨文化的情感计算发展。
- **研究动机**：
  - 情感识别在人机交互、心理健康、情感分析中日益重要。
  - 中文具有独特的语言特征、丰富的文化内涵和复杂的多模态交互特性，现有多数数据集无法有效覆盖这些方面。
  - 缺少针对中文的、自然交互对话下的多模态（语音、视频、文本）高质量情感语料。

### 2. 论文提出的方法论
- **核心思想**：设计并收集一个大规模、高质量、多模态的中文交互对话数据集，提供丰富标注以支持多种情感计算任务。
- **关键技术细节**：
  - **参与者与场景**：19 位演员参与**二元对话**（dyadic conversational settings），营造自然交互。
  - **多模态数据**：同时记录**声学（语音）、视觉（视频）和文本（转录）**三种模态。
  - **数据规模**：总计约 **23.6 小时语音**，包含 **19,250 条话语**（utterances）。
  - **标注体系**（三层标注）：
    - **7 类话语级情感类别**：高兴、惊讶、悲伤、厌恶、愤怒、恐惧、中性。
    - **5 维情感强度/效价标签**：消极、弱消极、中性、弱积极、积极。
    - **4 维语音描述（speech captions）**：说话人、说话风格、情感、整体描述。
- **算法流程**：本文为数据集论文，侧重数据构建流程，不涉及新算法公式。

### 3. 实验设计（数据集使用、基准与对比方法）
- **使用数据集**：本身构建的 **EmotionTalk** 数据集。
- **基准任务**：
  - 单模态情感识别（音频、视频、文本各模态独立）。
  - 多模态情感识别（融合多模态）。
  - 缺失模态挑战下的情感识别。
  - 语音描述生成（speech captioning）。
- **对比方法**：文中未详述具体对比的现有模型，但在数据集上进行实验以验证有效性，证明该数据集的高质量和适用性。（摘要提到“we conduct experiments... to demonstrate the effectiveness and quality of the dataset”，未列出具体方法名称。）

### 4. 资源与算力
- 论文摘要及元数据中**未明确提及**训练模型时的算力配置（如 GPU 型号、数量、训练时长）。因此算力信息缺失，无法评估其计算开销。

### 5. 实验数量与充分性
- **大致实验组数**：未给出具体数字，但根据描述，实验覆盖**单模态、多模态、缺失模态、语音描述**等不同设置，推测包含若干组基准实验。
- **充分性与公平性**：
  - 数据集论文通常需在自建数据上验证其可用性与挑战性，本文声明进行了此类实验，但具体细节（如划分策略、评价指标、对比基线数量与模型）在摘要中未展开，难以判断是否足够充分和客观。
  - 若能提供多种主流情感识别模型的基线结果、跨数据集对比或人类表现基准，则更具说服力；摘要未体现这些内容。

### 6. 论文的主要结论与发现
- 成功构建了**首个高质量、多功能的中文对话多模态情感数据集**，填补了领域空白。
- 该数据集包含多模态数据与丰富标注，适用于情感识别、缺失模态鲁棒性研究、语音描述生成等多个任务。
- 通过在 EmotionTalk 上的实验，初步验证了数据集的**有效性和质量**，可为跨文化情感分析提供宝贵资源。
- 数据集将**免费**向学术界公开。

### 7. 优点
- **填补空白**：首次提供针对中文的、交互式多模态对话情感数据集，具有重要价值。
- **多模态与交互性**：源自自然二元对话，更真实且有利于研究交互动力学。
- **标注丰富**：三层标注（7 类情感、5 级效价、4 维语音描述）提供细粒度信息，可支撑多种任务。
- **大规模**：23.6 小时语音、近 2 万条话语，具备足够数据量。
- **语言文化特色**：突出中文独特的语言文化内涵，有利于跨文化对比研究。
- **开放性**：承诺免费开放用于学术研究，促进社区发展。

### 8. 不足与局限
- **实验细节缺失**：摘要未给出具体的实验模型、基线方法、性能指标与对比分析，难以直接评判数据集的难度和实际提升效果。
- **演员依赖与生态效度**：数据由演员在受控对话中录制，可能缺少完全自发情感的自然性和多样性，存在从实验室到真实应用场景的泛化风险。
- **偏差风险**：仅包含 19 位演员，样本可能无法充分覆盖性别、年龄、方言、情绪强度等人口统计学变量，存在选择偏差。
- **任务覆盖**：虽提及缺失模态等场景，但未说明在连续情感维度（如 Valence-Arousal-Dominance）或对话级情感动态等更复杂任务上的适用性。
- **伦理与隐私**：未提及演员数据使用的知情同意、数据处理与隐私保护措施。

（完）
