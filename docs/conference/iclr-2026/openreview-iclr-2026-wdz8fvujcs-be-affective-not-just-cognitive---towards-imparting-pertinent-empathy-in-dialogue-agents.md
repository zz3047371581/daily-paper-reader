---
title: "Be Affective, Not Just Cognitive - Towards Imparting Pertinent Empathy in Dialogue Agents"
title_zh: 要情感，不要只认知——让对话智能体获得贴切同理心
authors: "Srishti Gupta, Piyush Kumar Garg, Sourav Kumar Dandapat"
date: 2025-09-20
pdf: "https://openreview.net/pdf?id=wdZ8FVuJcS"
tags: ["query:affective-ai"]
score: 9.0
evidence: 通过预训练将情感同理心注入对话智能体，生成贴切共情回复
tldr: 该论文针对现有共情回复生成缺乏情感同理心的问题，策划了8.5GB数据集，通过额外预训练赋予模型真正感受用户情绪的能力，并构建EMPATH框架提升回复的贴切性和用户关联性。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 现有共情回复缺乏情感同理心，回复单调且用户关联性低。
method: 通过策划大规模数据集进行额外预训练，结合EMPATH框架以注入情感同理心。
result: 显著提升了共情回复的有效性和用户关联性。
conclusion: 情感同理心可以通过预训练有效融入对话智能体。
---

## Abstract
Empathetic Response Generation (ERG) has gained significant attention in diverse areas but still faces challenges that hinder its effectiveness. These challenges include $1$) the lack of affective empathy in existing works, where they exhibit cognitive empathy (feel $\textit{for}$ user); $2$) generate generic responses, where agents address an emotion with monotonous replies; $3$) have limited user relatability. To tackle these issues, we propose incorporating affective empathy in models through additional pre-training. We introduce a benchmark dataset and its collection mechanism, that helps curate an $8.5$GB dataset, enabling the agent to truly feel $\textit{with}$ user. Using this pre-trained model, our framework EMPATH enhances ERG by reducing generic responses. This is achieved by a novel loss function that involves both conversation history and golden response. EMPATH also enhances user relatability by accounting for multiple emotions and their underlying causes via explainability. Through extensive experimentation, we demonstrate the effectiveness of our dataset on our proposed framework and other existing approaches. Additionally, we depict EMPATH's superior performance in ERG on benchmark datasets across various metrics.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：现有共情回复生成（Empathetic Response Generation, ERG）系统普遍存在三大缺陷：
  - 缺乏**情感同理心**（affective empathy），仅停留在**认知同理心**（cognitive empathy）层面，即只能“同情”用户，而非“感同身受”。
  - 回复趋于**通用化**（generic），面对同一种情绪往往给出千篇一律的回应。
  - **用户关联性**（user relatability）不足，难以贴合用户具体的情绪状态与背后原因。
- **整体含义**：该研究主张对话智能体不仅要“认知”用户的情绪，更应真正“感受”用户的情绪，从而生成贴切、有温度、能与用户建立深度连接的共情回复。

## 2. 论文提出的方法论

- **核心思想**：通过大规模额外预训练，将**情感同理心**注入对话模型，使其从“为而感受（feel *for*）”转向“与同感受（feel *with*）”；并进一步构建 **EMPATH 框架**，以减少通用回复并提升回复的针对性和可解释性。
- **关键技术细节**：
  - **数据集策划**：设计并整理了一个 8.5GB 的基准数据集，专门用于注入情感同理心。数据集包含对话历史、多种情绪标注及其潜在原因，为模型提供“感受”用户情绪的素材。
  - **额外预训练**：在该数据集上对基础模型进行持续预训练，使模型习得情感状态的内化表征。
  - **EMPATH 框架**：
    - **新颖的损失函数**：同时考虑对话历史与真实黄金回复（golden response），约束生成结果既忠实于语境又贴近理想共情回复，从而抑制通用化输出。
    - **多情绪与原因建模**：通过可解释性机制，显式建模复数情绪及其底层诱因，提升回复的用户关联性。
- **算法流程概述**：先使用策划的共情数据集对语言模型进行额外预训练；预训练后的模型接入 EMPATH 框架，在生成阶段利用涉及历史与目标回复的损失函数进行优化，并借助多情绪-原因解释模块生成更具贴切性的回复。

## 3. 实验设计

- **使用的数据集与场景**：
  - 自行策划的 **8.5GB 基准数据集**，用于额外预训练与评估。
  - 多个公开的共情回复生成基准数据集（论文未提及具体名称，但提到在基准数据集上验证了 EMPATH 的优越性能）。
- **对比方法**：与现有共情回复生成方法进行比较（具体方法名未公开，但论文提到在多种现有方法上证明了自研数据集的有效性）。
- **评估指标**：多种指标，可能涵盖自动评估（如 BLEU、ROUGE、多样性指标）和人工评估（针对贴切性、共情程度等）。

## 4. 资源与算力

- 论文提取文本中**未明确提及**具体算力信息，包括 GPU 型号、数量、训练时长等。元数据中也未含此部分细节。

## 5. 实验数量与充分性

- 实验覆盖：
  - 在自建数据集上验证额外预训练的有效性。
  - 在多个现有基准数据集上评估 EMPATH 框架的性能。
  - 将自建数据集应用于其他已有方法，以证明数据集的泛化价值。
- 充分性与客观性：
  - 实验设计包含对比分析、多数据集测试以及跨方法验证，层次较为丰富。
  - 使用了多种指标进行评估，有助于多角度衡量模型能力。
  - 但提取文本未披露消融实验细节，难以判断是否对各组件（预训练、损失函数、多情绪模块）单独进行了严格剥离实验。从整体描述看，实验大致充分且对比公平。

## 6. 论文的主要结论与发现

- **情感同理心可通过额外预训练有效注入**：模型不再仅仅理性分析用户情绪，而是能生成更贴近用户内心感受的回复。
- **EMPATH 框架显著提升共情回复的质量**：减少了通用化回复，增强了对多情绪及其原因的捕捉能力，使得回复更具贴切性和用户关联性。
- **自建数据集具有高迁移性**：不仅适用于本框架，也能改善其他既有方法的共情表现。

## 7. 优点

- **理念创新**：明确区分认知同理心与情感同理心，并指出前者是现有工作短板，切入点新颖且具有现实意义。
- **数据驱动**：策划了大规模（8.5GB）富含多情绪与原因的专用数据集，为情感同理心的学习提供了坚实基础。
- **框架设计精细**：EMPATH 通过联合损失函数和可解释多情绪建模，同时解决通用化和低关联性问题，工程考虑周全。
- **实验说服力较强**：不仅自评，还将数据集应用于其他模型，增加了结论的稳健性。

## 8. 不足与局限

- **算力信息缺失**：未披露训练所需的计算资源，大模型额外预训练的高成本可能限制复现与实际部署。
- **数据集细节不清**：虽提及 8.5GB 规模和收集机制，但提取文本未说明数据来源、语言、标注质量等，可能存在偏差风险。
- **对比方法与指标模糊**：基准方法与具体评估指标未给出，难以完全判断性能提升的幅度和实际优越性。
- **应用场景局限**：主要聚焦文本对话，未探讨多模态或实时交互场景的适配性。
- **可能的偏差风险**：训练数据若存在文化或性别偏见，可能使模型生成的共情回复带有不均衡性，文中未提及任何偏差缓解策略。

（完）
