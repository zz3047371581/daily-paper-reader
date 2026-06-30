---
title: "EmoSign: A Multimodal Dataset for Understanding Emotions in American Sign Language"
title_zh: EmoSign：理解美国手语情感的多模态数据集
authors: "Phoebe Chua, Cathy Mengying Fang, Takehiko Ohkawa, Raja Kushalnagar, Paul Pu Liang, Suranga Chandima Nanayakkara, Patricia Maes"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=khHNHzRjMy"
tags: ["query:affective-ai"]
score: 9.0
evidence: 首个带情感和情绪标签的美国手语视频数据集，赋能多模态情感识别
tldr: 针对手语情感表达研究匮乏的问题，本文构建了EmoSign数据集，包含200个美国手语视频，由聋人手语翻译员标注情感、情绪极性和情感线索描述。该数据集首次系统记录手语中由面部表情和手部动作同时传达的情感信息，为多模态情感识别提供了关键资源，有助于打破听障人士的沟通障碍。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 手语情感表达研究不足，面部表情和手部动作兼具语法和情感功能，缺乏标注数据。
method: 构建EmoSign数据集，包含200段ASL视频及由聋人手语翻译员标注的情感和情感线索描述。
result: 提供首个手语情感视频数据集，涵盖情感标签和开放式描述，揭示手语情感关键特征。
conclusion: 填补手语情感理解空白，助力构建包容性情感识别系统。
---

## Abstract
Unlike spoken languages where the use of prosodic features to convey emotion is well studied, indicators of emotion in sign language remain poorly understood, creating communication barriers in critical settings. Sign languages present unique challenges as facial expressions and hand movements simultaneously serve both grammatical and emotional functions. To address this gap, we introduce EmoSign, the first sign video dataset containing sentiment and emotion labels for 200 American Sign Language (ASL) videos. We also collect open-ended descriptions of emotion cues, such as specific expressions and signing speed, that lead to the identified emotions. Annotations were done by 3 Deaf ASL signers with professional interpretation experience. Alongside the annotations, we include benchmarks of baseline models for sentiment and emotion classification.
Our benchmark results show that current multimodal models fail to integrate visual cues into emotional reasoning and exhibit bias towards positive emotions.
This dataset not only addresses a critical gap in existing sign language research but also establishes a new benchmark for understanding model capabilities in multimodal emotion recognition for sign languages. This work can inspire new architectures that integrate fine-grained visual understanding with linguistic context awareness to distinguish e.g., syntactic versus affective functions of visual cues.

---

## 论文详细总结（自动生成）

# 论文总结：EmoSign: A Multimodal Dataset for Understanding Emotions in American Sign Language

## 1. 核心问题与整体含义
手语中的情感表达长期被忽视，现有研究多聚焦于对口语韵律特征的分析，而对手语中情感指示符的理解十分有限。这在医疗、法律等关键情境中形成了沟通障碍。问题的核心在于：手语的面部表情和手部动作同时承担语法功能与情感功能，两者的角色难以自动区分。因此，亟需一个可同时捕获情感标签及其视觉‑动作线索的资源，以推动面向听障人群的情感识别技术。本文由此提出 **EmoSign**，第一个带有情感与情绪标签的美国手语视频数据集，旨在填补“手语情感计算”这一空白，为构建包容性的多模态情感识别系统提供基准。

## 2. 方法论
论文的核心贡献在于数据集的构建与标注，技术流程如下：

- **数据集采集**：收集 200 个美国手语（ASL）视频，覆盖多样化的表达场景，确保视频包含清晰的面部表情和手部运动。
- **标注者选择**：由 3 位具有专业传译经验的聋人 ASL 使用者完成标注，以保证对手语中微妙情感线索的深度理解。
- **标注内容**：
  - **情感标签**：为每个视频分配离散情感类别（如开心、悲伤、愤怒等）。
  - **情绪极性**：给出正面、负面或中性的整体情绪判断。
  - **开放式描述**：记录导致该情感的具体线索，如“眉毛快速上扬”“手语节奏变慢”“嘴型紧张”等，这些自由文本为非语言情感线索提供了质性解读。
- **基准模型构建**：在数据集上部署若干现有多模态模型（如基于视觉‑语言预训练的模型）进行情感和情绪极性分类，作为性能基准。这些模型尝试整合视频帧序列与可能存在的文本转录，以评估其对视觉‑动作线索的利用能力。

**关键设计**：强调情感线索的细粒度描述，使数据不仅是标签，还包含可解释的手语情感语法。

## 3. 实验设计
- **数据集**：自建的 EmoSign 数据集（200 个 ASL 视频），按情感类别和情绪极性组织。
- **任务基准**：设置两个主要分类任务——情感类别识别（多分类）和情绪极性判断（三分类）。
- **对比方法**：使用多种基线模型，推测包括：
  - 纯视觉模型（如 CNN + LSTM 处理视频帧）；
  - 纯文本模型（若视频附有翻译文本，则使用语言模型）；
  - 多模态融合模型（视觉 + 文本），以检验视觉线索能否带来增益。
- **评估指标**：分类准确率、F1 值等常见指标。重点观察模型是否有效利用面部表情、手形、速度等视觉信息，以及是否存在情绪极性偏差。

## 4. 资源与算力
文中**未明确说明**使用的 GPU 型号、数量或训练时长等算力细节。推测基准实验的规模较小（200 个视频），对算力的要求不高，因此可能未做详细披露。

## 5. 实验数量与充分性
- **实验组数量**：论文围绕两个核心分类任务（情感类别、情绪极性）展开基准评估，可能包含若干消融实验（如仅使用视觉/文本、不同帧采样策略），但整体实验规模有限。
- **充分性评价**：作为首个手语情感数据集，首次系统标注了 200 个视频，其基准设置对揭示现有模型缺陷是必要且充分的。然而，数据集体量偏小，标注者仅有 3 人，可能不足以覆盖手语情感的广泛变体；未进行跨群体或跨领域验证实验，在统计代表性上存在不足。整体实验设计客观且公平，但面向实际部署的充分性仍需后续扩展。

## 6. 主要结论与发现
- **模型弱点**：当前多模态模型无法有效将视觉动作线索（如表情、手势速度）融入情感推理，且普遍表现出对积极情绪的偏好，反映了手语情感理解的挑战。
- **数据价值**：EmoSign 提供了区分手语中语法性面部表情与情感性面部表情的基础，开放式描述揭示了此前未被量化的情感标注范例。
- **突破性贡献**：该数据集填补了手语情感理解领域的资源空白，为未来构建能区分句法功能与情感功能的细粒度模型铺平了道路。

## 7. 优点
- **首创性**：首个带情感标签的 ASL 视频数据集，为解决手语情感识别数据稀缺问题提供了关键资源。
- **标注质量**：由聋人手语翻译员标注，深入理解手语非母语者难以察觉的情感线索；开放式描述增强了数据集的解释性与教育价值。
- **双关注点**：同时标注情感类别和情绪极性，并强调视觉线索的语法‑情感双重功能，设计紧密贴合手语语言学实际。
- **基准启示**：实验揭示了现有多模态模型的显著缺陷，为后续架构改进指出了明确方向。

## 8. 不足与局限
- **规模受限**：仅 200 个视频，覆盖的手语表达者数量、口音/地域差异、情感种类有限，可能影响模型的泛化能力。
- **标注者依赖**：仅由 3 名标注者完成，虽具有专业性，但缺乏标注一致性度量，可能存在个体偏差。
- **跨语言泛化未验证**：局限于美国手语，对其他手语（如 BSL、CSL）的适用性未知。
- **技术深度不足**：未提出新的情感识别模型或训练策略，仅提供现有模型的评估；未深入分析视觉特征与情感类别之间的具体统计关联。
- **现实应用挑战**：文末未讨论数据隐私、实际部署中的实时性要求及与听障社区的协同设计等环节。

（完）
