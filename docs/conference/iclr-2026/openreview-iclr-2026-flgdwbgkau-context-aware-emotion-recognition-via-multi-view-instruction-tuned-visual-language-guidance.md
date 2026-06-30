---
title: Context-Aware Emotion Recognition via Multi-View  Instruction-Tuned Visual Language Guidance
title_zh: 基于多视图指令调优视觉语言引导的上下文感知情绪识别
authors: "Jia-Kai Hu, Yi Hsien Lu, Ta-Wei Yang, Cheng-Fu Chou"
date: 2025-09-20
pdf: "https://openreview.net/pdf?id=flgDWBGkAU"
tags: ["query:affective-ai"]
score: 10.0
evidence: 基于VLM的多视图情绪识别
tldr: 本文面向上下文感知情绪识别，通过指令调优视觉语言模型，构建多视图情绪编码器，以参数高效且可解释的方式融合场景、身体和面部线索，提升识别性能。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 上下文情绪识别仍依赖手工特征，VLM方法探索不足。
method: 构建LLM辅助问答数据集，将VLM适配为多视图情绪编码器，使用参数高效组件。
result: 从场景、身体、面部提取细粒度特征，提升情绪识别性能。
conclusion: 多视图VLM为上下文情绪识别提供了可解释方案。
---

## Abstract
Context-aware emotion recognition often relies on heterogeneous cues, but many state-of-the-art systems still hinge on engineered signals (e.g., pose landmarks or temporal cues), limiting applicability. Meanwhile, VLM based emotion recognition remains relatively under-explored in current re search. Our work targets this gap with a parameter-efficient, interpretable design. To mitigate class imbalance and make view–emotion relations explicit, we first curate an LLM-assisted QA dataset. In Stage 1, the VLM is adapted into a multi-view emotion encoder that extracts fine-grained features from scene, body, and face using shared, parameter-efficient com ponents with view-specific pathways, enabling interpretable evidence dis entanglement from a single image. In Stage 2, the VLM remains frozen and its scene/body/face descriptors are fused by a lightweight head. This preserves VLM knowledge (avoiding overfitting and label coupling) while yielding independent, well-calibrated scores that support flexible thresh olds, plug-and-play label sets, and strong sample efficiency. Using only single-image inputs, our pipeline attains 37.88 mAP on EMOTIC, 88.82% top-1 accuracy on CAER-S, and higher recall/F1 on HECO than prior VLM-based baselines, while offering clear per-view interpretability. Code, prompts, and data splits will be released.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：上下文感知情绪识别（Context-Aware Emotion Recognition）通常依赖多源异构线索（如场景、身体姿态、面部表情），但现有先进系统仍大量使用手工设计的特征（如姿态关键点或时序信号），限制了方法的通用性和应用范围。同时，基于视觉语言模型（VLM）的情绪识别方法在当前研究中探索不足。
- **整体含义**：本文旨在填补这一空白，提出一种参数高效、可解释的多视图情绪识别框架。通过指令微调视觉语言模型，从单张图像中显式地解耦场景、身体和面部线索，并实现灵活的阈值、可插拔的标签集和强样本效率，从而提升上下文情绪识别的性能和可解释性。

## 2. 论文提出的方法论

- **核心思想**：将视觉语言模型适配为多视图情绪编码器，利用大语言模型辅助构建问答数据集，分两阶段训练，实现细粒度、可解释的多线索特征提取与融合。
- **关键技术细节**：
  - **LLM辅助问答数据集构建**：为缓解类别不平衡并显式建模视图–情绪关系，首先利用大语言模型（LLM）策划问答形式的数据集。
  - **第一阶段：多视图情绪编码器适配**
    - VLM被改造为多视图情绪编码器，通过**共享、参数高效的组件**以及**视图特定的通路**，从单张图像中同时提取场景、身体和面部三个视图的细粒度特征。
    - 这种设计使得不同视图的证据可以被独立解耦，增强了可解释性。
  - **第二阶段：轻量级融合头**
    - 冻结VLM部分，仅训练一个轻量级融合头，将三个视图的描述子进行融合。
    - 保留VLM的先验知识，避免过拟合和标签耦合，同时输出独立且良好校准的分数，支持灵活阈值、即插即用的标签集和优秀的样本效率。
  - **输入**：仅使用单张图像。
- **算法流程（文字描述）**：
  1. 用LLM生成视图–情绪关系的问答数据。
  2. 用该数据微调VLM（如使用LoRA等参数高效方法），使其成为多视图编码器，分别输出场景、身体、面部特征。
  3. 固定编码器，接入一个可训练的轻量级融合头，将三个视图特征融合，预测最终的情绪类别。

## 3. 实验设计

- **数据集与场景**：
  - **EMOTIC**：衡量上下文情绪识别，报告mAP（37.88）。
  - **CAER-S**：上下文感知情绪识别，报告top-1准确率（88.82%）。
  - **HECO**：对比先前基于VLM的方法，在召回率和F1分数上取得更高结果。
- **基准方法**：与“先前基于VLM的基线”对比（摘要中未列出具体方法名称，但明确提到优于prior VLM-based baselines）。
- **任务场景**：基于单张图像的上下文情绪识别，涵盖多模态线索的整合与解解释。

## 4. 资源与算力

- 摘要中**未明确提及**使用的GPU型号、数量或具体训练时长。仅说明采用参数高效的设计（parameter-efficient），暗示可能使用较少的算力，但无具体数值。

## 5. 实验数量与充分性

- 摘要提及在**三个数据集**（EMOTIC、CAER-S、HECO）上进行评估，并与先前VLM基线对比。
- 消融实验方面，虽未详细列出组件，但提到了“清晰的每视图可解释性”、“独立校准的分数”，并且设计强调了解耦和融合的作用，暗示至少包含了视图分解、融合头等模块的验证。整体实验设计从多数据集、多指标（mAP、准确率、召回率、F1）角度进行了评估，具有一定充分性。
- 由于仅提供摘要，无法确认具体实验组数及是否包含干扰因素控制，但从研究范式看，比较和消融应当客观公平。

## 6. 论文的主要结论与发现

- 提出的多视图指令微调VLM方法在多个上下文情绪识别基准上取得了优于先前VLM基线的性能。
- 通过显式的场景/身体/面部分解，模型能提供清晰的逐视图可解释性。
- 该方法仅需单张图像输入，即可实现强样本效率和灵活的标签集扩展能力。
- 多视图编码器结合轻量融合头可以有效平衡VLM先验知识的保留与任务适配，避免过拟合。

## 7. 优点

- **可解释性强**：显式解耦三个视图的证据，方便分析每个视图对情绪的贡献。
- **参数高效**：使用共享的轻量级适配器和冻结VLM的策略，降低微调成本。
- **灵活性与通用性**：支持灵活阈值和即插即用标签集，避免模型重新训练，便于实际部署。
- **仅需单帧图像**：不依赖视频序列或复杂手工特征，简化了推理流程。
- **数据集贡献**：LLM辅助的QA数据集有助于缓解类别不平衡，潜在可复用于其他类似任务。

## 8. 不足与局限

- **算力信息缺失**：未说明实际训练资源需求，难以评估复现成本。
- **实验覆盖**：仅从摘要看，缺少与最新非VLM的强基线（如基于Transformer的多模态融合模型）的全面对比。
- **数据集偏差风险**：所提LLM辅助数据集可能引入语言模型本身的先验偏差，影响真实场景的泛化性。
- **输入模态的局限**：依赖单张图像捕获非时间性的上下文，对于需要动态时序线索的情绪识别（如视频中的情感变化）可能不适用。
- **可扩展性**：参数高效组件虽节省算力，但在更大规模或更细粒度的情绪类别上的效果有待验证。

（完）
