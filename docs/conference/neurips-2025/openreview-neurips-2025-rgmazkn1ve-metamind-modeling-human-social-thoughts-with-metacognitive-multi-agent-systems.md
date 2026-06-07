---
title: "MetaMind: Modeling Human Social Thoughts with Metacognitive Multi-Agent Systems"
title_zh: MetaMind：基于元认知多智能体系统的人类社会思维建模
authors: "Xuanming Zhang, Yuxuan Chen, Samuel Yeh, Sharon Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=rGMaZkn1ve"
tags: ["query:affective-ai"]
score: 9.0
evidence: MetaMind通过元认知多智能体系统建模人类社会思维，包括情感推理。
tldr: 大语言模型在社交互动中难以推断情感和心理状态。MetaMind提出元认知多智能体框架，包含心理推理、道德评估和信念追踪智能体，模拟人类社会推理过程，实现情感识别和社会思考建模。实验表明其社会理解能力优越。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgmazkn1ve/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgmazkn1ve/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgmazkn1ve/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1633, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rgmazkn1ve/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1280, \"height\": 407, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1435, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 676, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 610, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 1634, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1451, \"height\": 1754, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 590, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rgmazkn1ve/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1443, \"height\": 210, \"label\": \"Table\"}]"
motivation: LLMs在社交推理中难以推断情感和意图。
method: 提出元认知多智能体框架MetaMind。
result: 实现包含情感识别的社会思维建模。
conclusion: MetaMind通过元认知协作提升LLMs社交智能。
---

## Abstract
Human social interactions depend on the ability to infer others' unspoken intentions, emotions, and beliefs—a cognitive skill grounded in the psychological concept of Theory of Mind (ToM). While large language models (LLMs) excel in semantic understanding tasks, they struggle with the ambiguity and contextual nuance inherent in human communication. To bridge this gap, we introduce **MetaMind**, a multi-agent framework inspired by psychological theories of metacognition, designed to emulate human-like social reasoning. MetaMind decomposes social understanding into three collaborative stages: (1) a *Theory-of-Mind Agent* generates hypotheses about user mental states (e.g., intent, emotion), (2) a *Moral Agent* refines these hypotheses using cultural norms and ethical constraints, and (3) a *Response Agent* generates contextually appropriate responses while validating alignment with inferred intent.
Our framework achieves state-of-the-art performance across three challenging benchmarks, with 35.7% improvement in real-world social scenarios and 6.2% gain in ToM reasoning. Notably, it enables LLMs to match human-level performance on key ToM tasks for the first time. Ablation studies confirm the necessity of all components, which showcase the framework’s ability to balance contextual plausibility, social appropriateness, and user adaptation. This work advances AI systems toward human-like social intelligence, with applications in empathetic dialogue and culturally sensitive interactions. Code is available at https://github.com/XMZhangAI/MetaMind.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以 Markdown 形式，对提供的《MetaMind: Modeling Human Social Thoughts with Metacognitive Multi-Agent Systems》论文进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义
*   **研究动机**：人类社交互动依赖于“心理理论”（Theory of Mind, ToM），即推断他人未言明的意图、情绪和信念的能力。现有的大语言模型（LLMs）在语义理解上表现优异，但在处理人类交流中固有的模糊性、间接性和情境细微差别时存在显著困难，难以进行深层次的社交推理。
*   **核心问题**：如何弥合LLMs在表层语言理解与深层社交认知之间的差距，使其能够像人类一样，通过结构化的认知过程来推断和回应社交情境中的潜在意图与情感。
*   **整体含义**：论文提出了一个名为 **MetaMind** 的认知启发式框架，旨在通过模拟人类的“元认知”过程，系统性地提升LLMs的社交智能，使其在同理心对话、文化敏感交互等应用中更加有效和自然。

### 2. 论文提出的方法论
MetaMind的核心思想是将人类的社会推理过程分解为一个三阶段的、协作式的多智能体系统。

*   **核心思想**：借鉴心理学的元认知理论，将社交理解建模为“假设生成 → 规范约束下的优化 → 验证性回应”的循环过程，而非单步预测。
*   **关键技术细节与流程**：
    *   **阶段 1: Theory-of-Mind Agent (心理理论智能体)**
        *   **功能**：作为推理的起点，负责推断用户的心理状态。
        *   **流程**：根据用户输入、对话上下文和“社交记忆”，生成一组关于用户潜在心理状态的候选假设。这些假设按类型分类，包括`Belief（信念）`, `Desire（渴望）`, `Intention（意图）`, `Emotion（情绪）`, `Thought（想法）`。此过程通过一个名为“心理状态推理”的结构化提示来实现。
    *   **阶段 2: Moral Agent (道德智能体)**
        *   **功能**：对第一阶段生成的假设进行社会规范和道德层面的过滤与优化。
        *   **流程**：接收第一阶段的候选假设，并依据一套预设的约束规则（如文化规范、伦理准则、角色期待）对这些假设进行修订。例如，若在职场对话中推断出“浪漫意图”，该智能体会将其修正为更符合情境的解释（如同事间的赞赏）。然后，通过一个综合了“上下文合理性”和“信息增益”的评分函数，选择出最优的优化后假设。
    *   **阶段 3: Response Agent (回应智能体)**
        *   **功能**：基于优化后的心理状态推断，生成最终回复，并进行自我验证，形成一个元认知闭环。
        *   **流程**：依据选定的最优假设和用户的社交记忆，生成自然语言回复。接着，通过一个效用函数对回复进行自我反思和评估，该函数综合考量了“共情性”（情感对齐度）和“连贯性”（上下文一致性）。如果效用分数过低，系统会触发重新生成机制。
    *   **关键组件：社交记忆**：一个动态数据库，用于存储和更新长期用户偏好、情感模式等，使系统能适应特定用户。

### 3. 实验设计
*   **数据集与基准测试**：论文在三个挑战性基准上进行了全面评估，分别对应MetaMind框架的不同阶段。
    *   **ToMBench**：用于评估心理理论推理能力，与**阶段1 （心理理论智能体）** 的功能对齐。这是一个多选题基准，覆盖了情绪、渴望、意图等六个类别。
    *   **社交认知任务套件**：包含如“失言识别”、“模糊故事任务”等8个任务，旨在测试在文化、社会规范下的精细推理能力，与**阶段2 （道德智能体）** 的功能对齐。
    *   **STSS （Social Tasks in Sandbox Simulation）**：一个沙盒模拟基准，用于评估在开放式的目标导向型社交互动（如约会、寻求帮助）中的表现，与**阶段3 （回应智能体）** 的功能对齐。
*   **对比方法**：论文将MetaMind与多种基线方法进行了比较，包括：
    *   **基础LLM** （如GPT-4、DeepSeek-R1）。
    *   **提示工程方法**：如思维链（CoT）、Hypothetical Minds、SymbolicToM。
    *   **多智能体/角色扮演方法**：如Generative Agents、ToM2C。

### 4. 资源与算力
*   文中明确说明，超参数优化（网格搜索）过程使用了**单个NVIDIA A100 80GB GPU**，总搜索耗时**166.8小时**，用于搜索最佳的超参数组合。对于其他主实验的推理成本，论文未详细说明总消耗，但指出为减少推理开销，选择了较小的超参数配置。

### 5. 实验数量与充分性
*   **实验数量庞大且全面**：
    *   **跨模型泛化性实验**：在超过16种不同的LLM上进行了测试，涵盖了开源与闭源模型、不同参数量级的模型，以证明框架的模型无关性和普适性。
    *   **多维度基准测试**：分别在ToM推理、社会认知、社会模拟三大类任务上进行了评估，覆盖了从选择题到开放式生成的不同任务形式。
    *   **消融实验**：系统地移除了每个智能体（阶段1、2、3）和社交记忆模块，以验证各组件的必要性。
    *   **对比实验**：与多个强基线方法进行了公平对比。
    *   **扩展性与人类对齐实验**：测试了与顶级推理模型（如OpenAI o3）的兼容性，并进行了人类表现对比和人工评估研究。
*   **充分性与客观性**：实验设计非常充分，通过多维度、多模型、多任务的评估，以及对各组件的严格消融，强有力地支持了论文的主张。对比的基线方法选取合理，具有代表性，保证了实验的客观与公平。

### 6. 论文的主要结论与发现
*   **显著的性能提升**：MetaMind在多个社交智能基准上取得了最先进的性能，例如在STSS上平均得分相对基础GPT-4提升35.7%，在社交认知任务上提升9.0%。
*   **首次达到人类水平**：该框架使LLM首次在关键的ToM测试维度上与人类平均水平持平，极大地缩小了人工与人类社交认知的差距。
*   **框架普适性与可扩展性**：MetaMind在不同规模和类型的LLM上均能带来一致且显著的提升，甚至能进一步增强顶尖推理模型（如OpenAI o3）的性能。
*   **组件必要性验证**：消融研究证实，心理理论推理、规范约束优化和回应验证三个阶段都是框架成功的关键，缺一不可。

### 7. 优点
*   **理论与工程创新结合**：巧妙地将心理学的“元认知”和“心理理论”概念转化为一个清晰、可操作的三阶段多智能体计算框架。
*   **结构化与可解释性**：通过分解推理过程，使得模型的社交思考过程（假设、规范优化、验证）更加透明和可追踪。
*   **模型无关的即插即用式增强**：作为一个外挂框架，能无缝集成到各种LLM上，而无需对基座模型进行微调，实用性强。
*   **全面的评估体系**：构建了一个与框架设计原理高度对齐的评估矩阵，通过不同性质的基准测试来分别验证各阶段组件的功能，实验论证逻辑严密。

### 8. 不足与局限
*   **对领域知识和内存质量的依赖**：性能受限于预定义的约束规则质量和社交记忆的准确性与覆盖率，广泛部署至不同文化背景时需要领域适配。
*   **基础模型性能瓶颈**：尽管能普遍提升性能，但搭载小型LLM的MetaMind与搭载大型LLM的版本之间仍存在绝对性能差距，框架无法从根本上弥补基座模型的能力短板。
*   **缺乏对多模态和复杂动态的建模**：当前基准测试聚焦于文本场景，未能处理真实社交互动中的多模态线索（如语调、表情）、复杂的群体动态及长期人际关系的建立。
*   **幻觉与社会记忆污染风险**：定性案例研究表明，早期阶段的错误或幻觉数据可能被存入“社交记忆”，并在后续交互轮次中被循环强化和引用，导致对话偏离正轨。
*   **计算成本**：多智能体多阶段的推理流程，特别是自我验证和重新生成机制，会带来显著高于单次模型调用的推理延迟和计算开销。

（完）
