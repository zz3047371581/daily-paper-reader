---
title: "MME-Emotion: A Holistic Evaluation Benchmark for Emotional Intelligence in Multimodal Large Language Models"
title_zh: MME-Emotion：面向多模态大语言模型情感智能的全面评估基准
authors: "Fan Zhang, Zebang Cheng, Chong Deng, Haoxuan Li, Zheng Lian, Qian Chen, Huadai Liu, Wen Wang, YiFan Zhang, Renrui Zhang, Ziyu Guo, Zhihong Zhu, Hao Wu, Haixin Wang, Yefeng Zheng, Xiaojiang Peng, Xian Wu, Kun Wang, Xiangang Li, Jieping Ye, Pheng-Ann Heng"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=oSX9aenbea"
tags: ["query:affective-ai"]
score: 10.0
evidence: 评估多模态大语言模型情感理解与推理的基准，提供可扩展任务和多样化场景。
tldr: 现有评测体系难以全面衡量多模态大语言模型的情感智能，MME-Emotion构建了系统性基准，包含情感理解和因果推理两类任务，覆盖多种场景和统一协议。通过对主流多模态模型的评测，揭示了它们在情感推理上的不足，为发展具备深层情感认知的AI提供了关键洞察。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 当前情绪评测无法评估多模态模型的情感情境泛化能力和情绪触发因素推理。
method: 构建大规模多模态情感基准，设计情感理解和推理任务，统一评估协议。
result: 评测发现现有模型的情绪推理能力有限，与通用视觉语言能力存在差距。
conclusion: 该基准为多模态情感AI的发展确立了新的评测标准，促进情感推理研究。
---

## Abstract
Recent advances in multimodal large language models (MLLMs) have catalyzed transformative progress in affective computing, enabling models to exhibit emergent emotional intelligence. Despite substantial methodological progress, current emotional benchmarks remain limited, as it is still unknown: (a) the generalization abilities of MLLMs across distinct scenarios, and (b) their reasoning capabilities to identify the triggering factors behind emotional states. To bridge these gaps, we present MME-Emotion, a systematic benchmark that assesses both emotional understanding and reasoning capabilities of MLLMs, enjoying scalable capacity, diverse settings, and unified protocols. As the largest emotional intelligence benchmark for MLLMs, MME-Emotion contains over 6,000 curated video clips with task-specific questioning-answering (QA) pairs, spanning broad scenarios to formulate eight emotional tasks. It further incorporates a holistic evaluation suite with hybrid metrics for emotion recognition and reasoning, analyzed through a multi-agent system framework.
Through a rigorous evaluation of 20 advanced MLLMs, we uncover both their strengths and limitations, yielding several key insights: (1) Current MLLMs exhibit unsatisfactory emotional intelligence, with the best-performing model achieving only $39.3\%$ recognition score and $56.0\%$ Chain-of-Thought (CoT) score on our benchmark. (2) Generalist models (\emph{e.g.}, Gemini-2.5-Pro) derive emotional intelligence from generalized multimodal understanding capabilities, while specialist models (\emph{e.g.}, R1-Omni) can achieve comparable performance through domain-specific post-training adaptation. By introducing MME-Emotion, we hope that it can serve as a foundation for advancing MLLMs' emotional intelligence in the future.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **研究动机**：多模态大语言模型（MLLMs）在情感计算领域取得显著进展，展现出“涌现式情感智能”。然而，现有情感评测基准存在两大盲区：
  - (a) 模型在不同场景下的泛化能力尚未被系统检验；
  - (b) 模型对情绪触发因素的因果推理能力缺乏有效评估。
- **整体含义**：论文提出 **MME-Emotion**，首个系统化、大规模的多模态情感智能基准，旨在全面衡量 MLLMs 在情感理解与推理上的真实水平，填补当前评测体系的空白，并为情感 AI 的下一步发展提供标尺和方向。

## 2. 方法论

- **核心思想**：构建一个多任务、多场景的评测框架，同时覆盖“情绪理解”和“情绪因果推理”两个维度，避免单一维度评测带来的片面性。
- **关键技术细节**：
  - **数据集构建**：从广泛场景中收集超过 **6,000 个精心挑选的视频片段**，并为每个片段设计任务特定的问答对（QA），形成 **8 类情感任务**。
  - **评测协议**：采用统一、可扩展的协议，融合**混合指标**，同时评估情绪识别准确率和推理质量（例如 Chain-of-Thought 评分）。
  - **分析框架**：通过**多智能体系统（multi-agent system）框架**对模型输出进行整体性分析，提升评估的细粒度与客观性。
- **公式或算法流程**（文字描述）：
  - 给定视频输入，模型需完成两类任务：
    - **情绪理解**：识别视频中人物的情感状态。
    - **情绪推理**：解释引发该情绪的原因，通常以思维链（CoT）形式生成推理过程。
  - 评价指标分为“识别分数”和“CoT 分数”，分别量化模型对情绪标签的准确性及推理过程的质量。

## 3. 实验设计

- **数据集/场景**：
  - 使用自建 **MME-Emotion 基准**，包含 6,000+ 视频片段，覆盖多类真实场景以形成多样化情绪触发情境。
  - 任务类型包括 8 种情感子任务，系统考察情绪识别与因果推理。
- **对比方法**：
  - 在 20 个先进 MLLMs 上进行严格评测，涵盖：
    - **通用模型**（如 Gemini-2.5-Pro）
    - **领域特化模型**（如 R1-Omni）
  - 通过横向对比，揭示不同训练范式（通用预训练 vs. 领域后训练）下模型的情感智能差异。

## 4. 资源与算力

- 文中未明确提供关于 GPU 型号、数量、训练时长等算力消耗的详细说明。由于本工作主要聚焦于**评测基准的构建与模型评估**，而非训练新模型，因此算力描述可能并非核心内容，但在现有信息中确实缺失。

## 5. 实验数量与充分性

- **实验规模**：至少进行了覆盖 **20 个模型的全面评测**，每个模型在 6000+ 视频的 8 种任务下接受测试，实验体量较大。
- **充分性**：
  - 模型种类覆盖通用与专精两类代表，对比具有客观性。
  - 评测指标从识别和推理双维度设计，避免了单一准确率的陷阱。
  - 可能缺乏系统的消融实验（如不同模态组合、提示策略的敏感度分析），但作为评测基准论文，重点在于提供标准化测试床，而非方法本身的消融。
- **公平性**：统一协议和混合指标保证了不同模型间比较的公平性。

## 6. 主要结论与发现

- **整体表现不佳**：当前 MLLMs 的情感智能远未令人满意，表现最好的模型在 MME-Emotion 上仅获得 **39.3% 的情绪识别分数** 和 **56.0% 的 CoT 推理分数**。
- **能力来源分化**：
  - **通用模型**（如 Gemini-2.5-Pro）的情感智能源于其泛化的多模态理解能力。
  - **专用模型**（如 R1-Omni）通过领域特化后训练能够达到与通用模型相当的性能。
- **核心差距**：模型在因果推理环节的普遍薄弱，表明现有 MLLMs 尚未真正理解情绪的发生机制，与通用视觉语言能力之间存在明显鸿沟。

## 7. 优点

- **系统性**：首次将情绪理解和推理整合进统一基准，解决了过去评测维度的分裂与缺失。
- **规模与多样性**：6000+ 视频、多场景、8 类任务，提供了目前最大规模的多模态情感评测数据集。
- **评测创新性**：引入 CoT 评估与多智能体分析框架，对推理过程的评价更为深入和可靠。
- **实用洞察**：通过对比通用与专用模型，为未来情感 MLLMs 的研发路径提供了明确指引。

## 8. 不足与局限

- **评估本身的风险**：CoT 评分依赖自动化指标与多智能体框架，其与人类判断的一致性未经过充分验证，可能存在评估偏差。
- **数据覆盖的局限**：尽管场景广泛，但视频片段主要来自特定来源，文化、语言、情绪表达方式的多样性可能受限，影响基准的外部效度。
- **仅做评测，未给出改进方案**：论文揭示了问题，但未针对情感推理的薄弱环节提出具体的模型改进方法或训练策略。
- **动态交互缺失**：基准为离线视频问答，与现实世界中连续、互动的情绪交流场景仍有距离，无法评估模型在对话情境中的动态情商。

（完）
