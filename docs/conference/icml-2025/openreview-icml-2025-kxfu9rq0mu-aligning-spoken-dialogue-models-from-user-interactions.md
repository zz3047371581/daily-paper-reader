---
title: Aligning Spoken Dialogue Models from User Interactions
title_zh: 从用户交互中对齐口语对话模型
authors: "Anne Wu, Laurent Mazaré, Neil Zeghidour, Alexandre Défossez"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=kxFu9rQ0Mu"
tags: ["query:affective-ai"]
score: 6.0
evidence: 利用语音交互中的偏好对对齐口语对话模型，可用于语音情感识别
tldr: 针对文本偏好对齐方法不适用于实时语音交互的问题，提出一种面向口语对话模型的偏好对齐框架。构建了超15万对从多轮语音对话中标注的偏好数据，覆盖语言内容和时序变化，并用其微调全双工自回归语音到语音模型。实验显示对齐后的模型在语音自然度和用户满意度上显著提升，为构建情感感知对话系统提供了技术基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1729, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 841, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1595, \"height\": 1027, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1400, \"height\": 802, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1225, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1747, \"height\": 651, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1595, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1681, \"height\": 585, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1466, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1264, \"height\": 1445, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 653, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1394, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1382, \"height\": 764, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1660, \"height\": 680, \"label\": \"Table\"}]"
motivation: 现有偏好学习主要针对文本模型，无法处理实时语音对话的丰富动态特性。
method: 构建大规模语音对话偏好对数据集，采用离线对齐方法微调全双工语音到语音模型。
result: 对齐后模型在语音内容和时序偏好上均优于基线，用户交互质量提升。
conclusion: 证明了语音偏好对齐有助于开发更自然的情感对话智能体。
---

## Abstract
We propose a novel preference alignment framework for improving spoken dialogue models on real-time conversations from user interactions. Current preference learning methods primarily focus on text-based language models, and are not directly suited to the complexities of real-time speech interactions, with richer dynamics (e.g. interruption, interjection) and no explicit segmentation between speaker turns.We create a large-scale dataset of more than 150,000 preference pairs from raw multi-turn speech conversations, annotated with AI feedback, to cover preferences over both linguistic content and temporal context variations. We leverage offline alignment methods to finetune a full-duplex autoregressive speech-to-speech model. Extensive experiments demonstrate that feedback on generic conversations can be consistently effective in improving spoken dialogue models to produce more factual, safer and more contextually aligned interactions. We deploy the finetuned model and conduct holistic human evaluations to assess the impact beyond single-turn conversations. Our findings shed light on the importance of a well-calibrated balance among various dynamics, crucial for natural real-time speech dialogue systems.

---

## 论文详细总结（自动生成）

好的，以下是根据你提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **研究背景**：当前，基于人类反馈的强化学习等对齐技术已广泛应用于文本大语言模型，使其能生成更有用、更符合语境的回复。然而，语音交互正成为主流，其由自动语音识别、自然语言理解和语音合成串联而成的传统级联系统存在延迟高、丢失非语言信息、难以处理打断和交叠等局限性，催生了端到端的全双工语音对话模型。
*   **核心问题**：现有的偏好对齐方法主要针对文本模型，无法直接适用于具有丰富动态特性（如打断、插话、沉默）且无明显话轮边界的实时语音对话。如何为这种全双工口语对话系统设计有效的对齐框架，是论文要解决的核心问题。
*   **整体含义**：本文旨在弥合文本对齐方法与语音对话系统间的鸿沟，提出一个能从真实用户交互中学习偏好，从而提升口语对话模型在内容、安全性和交互自然度上的综合框架。

### 2. 论文提出的方法论

*   **核心思想**：从大规模的真实人机口语对话中，利用AI评判来识别问题回复，并生成内容或时序上更优的回复，构建偏好对数据集，再用离线偏好优化算法直接微调全双工语音对话模型。
*   **关键技术细节与流程**：
    1.  **数据采集与标注**：部署预训练的Moshi模型，收集其与用户进行的无约束、多轮、实时口语对话。
    2.  **偏好对构建**：
        *   **转录与分割**：使用Whisper对用户和模型的音频进行带时间戳的转录。
        *   **问题识别**：利用一个基于大语言模型的评判器，从有用性、安全性、事实准确性、指令遵循度、语调、打断行为、无响应性七个维度评估模型回复，并标记出存在问题的“失败”回复。
        *   **偏好纠正**：将问题分为**内容相关**（如信息不准确）和**时序相关**（如不合时宜的打断或沉默）。随后，引导LLM评判器为这些问题回复生成一个经过修正的、内容更优或时序更恰当的“获胜”回复，从而形成（上下文，获胜回复，失败回复）偏好三元组。
    3.  **隐私保护的用户音频合成**：为保护用户隐私，不直接存储用户原始音频。在构建模型输入上下文时，根据用户文本的时间戳，使用一个文本到语音模型重新合成用户语音，保留其时序结构。
    4.  **全双工多模态离线对齐**：
        *   针对Moshi这类多流（文本、模型音频、用户音频）模型，作者对直接偏好优化等离线对齐方法进行了适配。经过实验，最终选择**仅在模型的文本流上计算概率**，而非联合音频和文本，因为后者训练不稳定。
        *   采用长度归一化的直接偏好优化作为主要训练目标，并与SimPO， APO-Zero等其他离线对齐算法进行了比较。

### 3. 实验设计

*   **基础模型**：基于两个不同声音版本的Moshi模型进行实验。
*   **数据集与场景**：
    *   **偏好训练集**：从用户交互中构建了一个包含超过15万对（唯一上下文）至28万对（重叠上下文）的偏好数据集，并混合了不同比例的内容问题、打断问题、沉默问题数据以进行消融研究。
    *   **客观评测集**：
        *   **口语问答**：使用Llama Questions， 以及合成音频版本的TriviaQA和Web Questions三个基准，评估模型提供事实信息的准确性。
        *   **安全性**：使用ALERT和合成音频版本的XSTest基准，评估模型回复的毒性以及拒答不安全请求的能力。
*   **对比方法**：
    *   **基线模型**：对比了其他语音对话模型，包括SpeechGPT (7B)、Spectron (1B)以及一个9B的语音-文本模型。
    *   **消融实验**：对比了不同的模态优化策略（仅文本流 vs. 联合文本/音频流）、不同的偏好数据类型组合（纯内容、纯时序、混合）、不同的离线对齐算法（DPO， DPO-LN， SimPO， APO-Zero）。
*   **人工评估**：设计了一个两阶段评估流程。第一阶段，让真人用户与“Moshi-Instruct”和“Moshi-Aligned”进行多轮语音对话；第二阶段，由另一组标注员回看对话转录，从“连贯性与流畅度”、“参与度”、“相关性与有用性”三个维度进行评分。

### 4. 资源与算力
论文在正文的“5.3 Training”部分和附录“A. Implementation & Hyperparameter Details”中均未明确提及训练所使用的GPU型号、数量或具体训练时长。仅提到了训练框架、学习率、批次大小等超参数以及学习率衰减策略。

### 5. 实验数量与充分性

*   **实验组数量**：实验设计较为充分，包含了多组实验：
    1.  **模态流消融**实验（1组对比）。
    2.  **数据类型混合**消融实验（至少6种不同数据组合的比较）。
    3.  **对齐算法**对比实验（4种算法的比较）。
    4.  **声音迁移**实验（在另一个声音的模型上验证框架泛化性）。
    5.  **人工评估**实验（收集了共8小时的对话数据进行主观评分）。
*   **充分性与公平性**：实验覆盖了多维度的客观评测和主观评价，对比基线和方法消融较为全面，分析细致，结论具有说服力。特别是对不同类型偏好数据影响的探究，以及对声音迁移效果的分析，加深了对方法机制的理解。

### 6. 论文的主要结论与发现

1.  **框架有效性**：所提出的对齐框架能够持续有效地提升全双工口语对话模型的性能。对齐后的模型在口语问答准确性（平均+3.1%）和安全性（平均+6.9%）上均取得显著提升。
2.  **数据类型影响**：偏好数据的具体类型至关重要。仅使用内容偏好数据提升有限，而加入关于打断、沉默等时序偏好的数据，能带来更显著的性能增益，并且能更好地控制模型的语速和响应性。
3.  **算法选择**：长度归一化的DPO在整体表现上优于普通DPO、SimPO等算法，能更好地平衡回答质量、安全性和回复长度。
4.  **泛化与人评**：对齐数据可以对声音相近的模型提供增益。在真人短对话测试中，对齐后的模型在连贯性、参与度和相关性上均优于未对齐模型，尤其在短对话中表现突出。

### 7. 优点

*   **问题新颖且实际**：首次系统性解决了全双工、实时口语对话模型的偏好对齐问题，这是当前语音AI发展的一个关键方向。
*   **数据集构建方法完善**：提出了一套完整的、从真实交互中自动构建包含时序和内容偏好的数据集流程，并巧妙地通过语音合成解决了用户隐私问题。
*   **实验全面深入**：不仅通过消融实验详细分析了模态、数据类型和对齐算法的影响，还设计了专门的两阶段人工评估来验证多轮对话的实际体验，论证非常扎实。
*   **模型无关性**：虽然实验基于Moshi，但提出的数据集构建和离线对齐流程是模型无关的，具有良好的可迁移性。

### 8. 不足与局限

*   **对话长度局限**：偏好数据主要集中在对第一个问题回复的优化上。人工评估也显示，对齐在短对话中效果显著，但在更长的对话中，性能会有所退化。
*   **声音迁移限制**：实验表明，将偏好数据用于对齐声音差异较大的模型时，效果会明显变差，说明该方法的跨声音泛化能力有限。
*   **合成语音偏差**：为保护隐私而采用合成用户语音，会丢失说话人身份、情感韵律等副语言信息，这可能影响对齐模型在真实语音环境下的表现。
*   **评估维度缺失**：人工评估更侧重于语义和语用层面，对生成语音的声学质量（如自然度、音质）评估不足。
*   **未在线学习**：目前的框架是离线训练，无法实时地从连续的用户在线反馈中学习并迭代改进。

（完）
