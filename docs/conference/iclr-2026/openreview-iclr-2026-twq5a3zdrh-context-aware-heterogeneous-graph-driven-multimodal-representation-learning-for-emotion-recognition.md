---
title: Context-aware Heterogeneous Graph-driven Multimodal Representation Learning for Emotion Recognition
title_zh: 上下文感知的异构图驱动多模态表征学习用于情感识别
authors: "Mohammed Rahman Sherif Khan Mohammad, Swagat Kumar, Yonghuai Liu, Ran Song, Ardhendu Behera"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=twq5A3zdrH"
tags: ["query:affective-ai"]
score: 10.0
evidence: 提出异构图学习的多模态情感识别方法，编码模态特有的动态和依赖关系。
tldr: 针对多模态情感识别中忽略模态特异性时序和非对称依赖的问题，提出上下文感知异构图表征学习方法，先利用Transformer为各模态编码上下文特征，再构建异构图并引入关系感知图Transformer进行信息融合。实验表明该方法能更好捕捉模态间的复杂交互，提升情感识别精度。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 现有方法常将多模态统一处理，忽略模态特有的时序动态和不对称依赖关系。
method: 设计异构图表征学习，用Transformer编码单模态特征，构建异构图并采用关系感知图Transformer融合。
result: 在公开数据集上获得领先的情感识别准确率，验证了异构建模的有效性。
conclusion: 该方法提升了多模态情感理解的鲁棒性，为人机交互提供更精确的情绪感知。
---

## Abstract
Multimodal emotion recognition (MER) aims to infer human affect from verbal, vocal, and visual signals, a core challenge in representation learning for human–AI interaction. State-of-the-art approaches, including standard Transformers and graph-based models, often collapse modalities into uniform structures, ignoring modality-specific temporal dynamics and asymmetric dependencies. We propose a novel context-aware heterogeneous graph-driven representation learning that explicitly encodes both structural and semantic heterogeneity. Each modality is first contextualized with dedicated Transformer encoders, enriching unimodal features before graph construction. We then introduce a relation-aware graph transformer that performs type-conditioned message passing, enabling specialized transformations across sequential, cross-modal, and speaker-conditioned edges. The topology is adapted to the target regime: in multi-party dialogue (IEMOCAP, MELD), we distinguish within-speaker and cross-speaker temporal flows, while in single-speaker videos (CMU-MOSEI), we extend k-step temporal links to capture offset dynamics. In both settings, co-temporal edges synchronize audio, visual, and textual cues. Experiments demonstrate consistent gains over prior state-of-the-art, showing that structural and semantic heterogeneity are indispensable for robust multimodal representation learning. Our results establish that explicitly modeling interaction structure, rather than relying on generic sequence attention, is critical for advancing multimodal learning. To support reproducibility and further research, we will release our source code.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：多模态情感识别（MER）需要从语言、语音和视觉信号中推断人类情绪，但现有主流方法（如标准Transformer、同质图模型）往往将不同模态压入统一结构，**忽视了模态特有的时序动态**以及**模态间非对称的依赖关系**。
- **研究动机**：同质化处理会丢失重要的结构异质性和语义异质性，限制了模型对复杂交互的捕捉能力。因此，论文提出要显式地建模模态间和模态内的交互结构，从而推动多模态表征学习在情感理解任务上的鲁棒性提升。
- **整体含义**：通过上下文感知的异构图表示学习，构建更精细的模态关系拓扑，使模型能够捕获真实对话或独白视频中多层次、不均衡的信息流，为人机交互提供更精确的情绪感知能力。

### 2. 论文提出的方法论
- **核心思想**：设计一个**上下文感知的异构图驱动的表示学习框架**，分两阶段实现多模态融合。
  - 第一阶段：**模态特定的上下文编码**——使用**专属的Transformer编码器**为每个模态（文本、语音、视觉）分别建模其时序上下文，生成富含模态内信息的单模态特征。
  - 第二阶段：**异构图构建与关系感知融合**——基于单模态特征构建异构图，并引入**关系感知图Transformer**（relation-aware graph transformer）执行**类型条件化的消息传递**，使不同边类型（如时序边、跨模态边、说话人条件边）经历专门化的变换，从而有效捕捉非对称依赖。
- **关键技术细节与拓扑适应性**：
  - **异构图中的边类型**：同时包含语义异构边（如跨模态同步边）和结构异构边（如时序链接、说话人关系链接）。
  - **多说话人对话场景**（IEMOCAP、MELD）：区分**说话人内部时序流**和**说话人之间交叉时序流**，分别建模个体情感演化和互动影响。
  - **单说话人视频场景**（CMU-MOSEI）：扩展**k步时序边**，捕捉更远时间偏移的动态关联；同时保留**共时边**（co-temporal edges）同步音视频与文本线索。
  - **算法流程（摘要描述）**：单模态特征提取 → 各自Transformer上下文增强 → 构建异构图（节点为时间步-模态片段，边类型按场景定制）→ 关系感知图Transformer进行消息传递与特征更新 → 下游情感分类。

### 3. 实验设计
- **数据集/场景**：
  - 多说话人对话：**IEMOCAP**、**MELD**。
  - 单说话人视频：**CMU-MOSEI**。
- **Benchmark与对比方法**：摘要称“实验显示相比此前最先进方法有一致性提升”（consistent gains over prior state-of-the-art），但未列出具体对比模型名称。依据元数据，对比对象可能包括标准Transformer、同质图模型等代表方法。
- **评价指标**：未在摘要中明确给出，通常为加权/未加权准确率、F1值等情感识别常用指标。

### 4. 资源与算力
- **文中说明情况**：摘要和元数据均**未提及GPU型号、数量、训练时长或训练数据量**等算力细节。将在完整论文中期待相关说明。

### 5. 实验数量与充分性
- **可识别的实验组**：
  - 三个公开数据集上的主实验（多说话人 × 2，单说话人 × 1）。
  - 摘要暗示有消融或对比实验（如验证结构异质性与语义异质性的必要性），但**未展开说明具体消融维度、变体数目**。
- **充分性与公平性评估**：
  - **充分性暂无法判断**：摘要缺少消融实验类别、统计显著性检验、多次运行误差范围等细节。
  - **客观公平性**：所有对比均在同一任务和数据集框架下，且声称将开源代码，有利于复现验证。

### 6. 论文的主要结论与发现
- **核心发现**：**结构异质性和语义异质性的显式建模**对鲁棒多模态表征学习不可或缺。单纯依赖通用序列注意力机制，不如结合任务场景构建专门化交互拓扑。
- **性能结论**：所提方法在IEMOCAP、MELD、CMU-MOSEI上均取得领先结果，验证了异构图和关系感知消息传递的有效性。
- **方法论启示**：推进多模态学习的关键不在于堆叠更强的通用注意力，而在于**显式设计并利用模态间的交互结构**。

### 7. 优点：方法或实验设计上的亮点
- **精细的模态异质性建模**：突破传统多模态融合“一视同仁”的假设，用不同Transformer编码器和类型条件化图传递，切合情感表达的非对称特性。
- **场景自适应的拓扑设计**：针对多说话人和单说话人不同需求，灵活设计时序与说话人关系边，体现面向任务的图结构定制能力。
- **两步富表示学习**：先利用Transformer增强单模态上下文，再基于增强特征构图，有助于图模型接收更高质量的输入。
- **可复现性承诺**：承诺发布源代码，透明度高。

### 8. 不足与局限
- **实验细节缺失**：摘要未提供消融实验的广度、统计检验方式及对比方法的完整清单，难以评估结论的稳健性。
- **算力与资源成本未知**：未报告模型参数量、GPU消耗与训练时长，对实际部署的可用性判断缺少依据。
- **数据集覆盖局限**：虽涵盖英文多模态情感识别三个主流数据集，但未涉及低资源语言、野外环境或文化差异场景，泛化边界不清。
- **实时性与效率考量未提**：异构构图和关系感知图Transformer的计算复杂度是否适应实时人机交互系统，有待进一步分析。

（完）
