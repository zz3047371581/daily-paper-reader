---
title: Emotional Face-to-Speech
title_zh: 情感面部到语音
authors: "Jiaxin Ye, Boyuan Cao, Hongming Shan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=EuDlvBqcSm"
tags: ["query:affective-ai"]
score: 9.0
evidence: 从面部表情生成情感语音，直接的情感计算任务
tldr: 针对现有面部到语音方法缺乏情感表达多样性的问题，提出DEmoFace框架，采用离散扩散Transformer与课程学习，结合多级神经音频编解码器，从表情线索直接合成情感语音。实验表明该方法能生成富有情感表现力的语音，对虚拟角色配音和辅助表达障碍者具有重要意义。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1669, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1674, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1747, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 843, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1655, \"height\": 708, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1714, \"height\": 629, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 826, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1839, \"height\": 899, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1544, \"height\": 1329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1681, \"height\": 676, \"label\": \"Table\"}]"
motivation: 现有面部到语音方法缺乏情感表达多样性，限制虚拟配音等应用。
method: 提出DEmoFace，利用离散扩散Transformer与多级音频编解码器，通过课程学习动态对齐面部特征与语音情感。
result: 生成的语音具有丰富情感，优于现有方法在风格多样性上的表现。
conclusion: 该方法为情感语音合成提供了新范式，拓展了跨模态生成的应用场景。
---

## Abstract
How much can we infer about an emotional voice solely from an expressive face? This intriguing question holds great potential for applications such as virtual character dubbing and aiding individuals with expressive language disorders. Existing face-to-speech methods offer great promise in capturing identity characteristics but struggle to generate diverse vocal styles with emotional expression. In this paper, we explore a new task, termed *emotional face-to-speech*, aiming to synthesize emotional speech directly from expressive facial cues. To that end, we introduce  **DEmoFace**, a novel generative framework that leverages a discrete diffusion transformer (DiT) with curriculum learning, built upon a multi-level neural audio codec. Specifically, we propose multimodal DiT blocks to dynamically align text and speech while tailoring vocal styles based on facial emotion and identity. To enhance training efficiency and generation quality, we further introduce a coarse-to-fine curriculum learning algorithm for multi-level token processing. In addition, we develop an enhanced predictor-free guidance to handle diverse conditioning scenarios, enabling multi-conditional generation and disentangling complex attributes effectively. Extensive experimental results demonstrate that DEmoFace generates more natural and consistent speech compared to baselines, even surpassing speech-driven methods. Demos of DEmoFace are shown at our project https://demoface.github.io.

---

## 论文详细总结（自动生成）

好的，作为资深学术论文分析助手，我将以Markdown形式，对所提供的《Emotional Face-to-Speech》论文进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**:
    *   现有面部到语音（Face-to-Speech, F2S）方法在生成语音时，能够有效捕获说话人的身份特征，但在生成富有情感表达和多样化的语音风格方面存在明显不足。
    *   用户在人类-机器交互中，越来越期待生成语音不仅能复现说话人身份，还能传达丰富的**情感韵律**。
    *   考虑到面部表情是情感最直接的视觉指标，论文旨在探索一个根本问题：**我们能否仅从一张富有表情的面孔中，推断并合成出相应的情感语音？**

*   **核心问题与整体含义**:
    *   论文正式提出了一个新任务——**情感面部到语音（Emotional Face-to-Speech, eF2S）**。
    *   **核心目标**：给定一段文本和一张参考人脸图像，模型需要同时从人脸上解耦出**身份**和**情感**信息，合成出既保持说话人身份，又融入参考人脸情感状态的语音。这是一个不依赖任何语音（声学）线索的全新视觉到语音的生成范式。
    *   **应用价值**：对于虚拟角色配音、辅助表达性语言障碍患者等场景具有巨大潜力。

### 2. 论文提出的方法论

*   **核心思想**:
    *   提出 **DEmoFace** 框架，首次将**离散扩散模型（Discrete Diffusion Model, DDM）** 应用于基于残差矢量量化（RVQ）的语音Token生成，以实现高质量、多样化的情感语音合成。
    *   整个流程无需任何声学提示，仅通过视觉线索（面部图像）和文本驱动。

*   **关键技术细节与流程**：
    *   **1. 语音离散化**：使用基于残差矢量量化（RVQ）的神经音频编解码器（Neural Audio Codec）将连续语音波形压缩为多层级的离散Token序列。这解决了连续语音生成中一对多映射的难题。
    *   **2. 离散扩散过程**：
        *   **前向过程**：将RVQ语音Token逐步替换为`[MASK]` Token，直至完全掩码。
        *   **反向去噪过程**：模型学习预测每一步被掩码Token的“具体分数（Concrete Score）”，从而实现从纯`[MASK]`状态迭代式地细化并生成目标Token序列。
    *   **3. 多模态条件注入（MM-DiT）**:
        *   提出**多模态DiT（MM-DiT）块**，与标准DiT不同，它专门设计用于eF2S任务。
        *   **面部条件器**：分别构建身份编码器（结合ArcFace和FaceNet）和情感编码器（基于Poster2），从人脸图像中解耦出身份嵌入 `cid` 和情感嵌入 `cemo`，并通过自适应层归一化（AdaLN）注入到扩散Transformer中。
        *   **文本条件器**：使用SpeechT5对音素序列进行编码，得到文本嵌入 `ctext`，通过交叉注意力机制注入模型，实现语音内容与文本的动态对齐。
    *   **4. 课程学习策略 (Curriculum Learning)**:
        *   观察到RVQ不同层级的Token承载不同频率信息：低层级包含语义等低频信息，高层级包含声学细节等高频信息。
        *   提出**由粗到细的课程学习**：训练初期仅输入低层级Token，随后逐步引入高层级Token，实现了高效且稳定的训练。
    *   **5. 增强的无预测器引导（EPFG）**:
        *   针对eF2S的多条件（身份、情感、文本）生成挑战，提出**增强的无预测器引导（Enhanced Predictor-Free Guidance, EPFG）**。
        *   从能量模型（EBM）视角出发，将条件得分分解为`组成得分`和`联合得分`的乘积，有效提升了模型对全局条件的响应能力，并促进了对多个局部条件的解耦控制。其引导公式核心为：`引导得分 = 无条件得分 × ∏(各条件组成得分 / 无条件得分) × (联合条件得分 / 无条件得分)`。

### 3. 实验设计

*   **使用的数据集**:
    *   **主数据集**：组合了3个包含面部-语音配对的数据集进行训练和评估：**RAVDESS**、**MEAD**和**MELD-FAIR**，总计约31.33小时、26,767条语音，覆盖7种基本情感和953个说话人。
    *   **辅助预训练数据集**：为弥补主数据集语义信息不足的缺陷，引入**LRS3**数据集的一个10小时子集进行预训练，用于提升模型的可比性。

*   **Benchmark与对比方法**:
    *   论文将对比方法分为两类范式：
        *   **声学引导方法**（依赖语音提示，提供性能上界参考）：EmoSpeech, FastSpeech2, V2C-Net, HPM, StyleDubber，以及DEmoFace的一个用真实语音嵌入指导身份的变体 `DEmoFace*`。
        *   **视觉引导方法**（仅依赖视觉输入，为论文主要对比对象）：**Face-TTS**（最直接的视觉驱动F2S基线）。
    *   **评估指标**：全面覆盖生成语音的质量和风格一致性。
        *   **情感表现力**：情感相似度（EmoSim）、基频误差（RMSE）。
        *   **身份一致性**：说话人相似度（SpkSim）。
        *   **自然度与可懂度**：梅尔倒谱失真（MCD）、词错误率（WER）。
        *   **主观评测**：招募50名参与者进行平均意见分（MOS）打分，包括自然度（MOSₙₐₜ）、身份相似度（MOSᵢd）和情感相似度（MOSₑₘₒ）。

### 4. 资源与算力

*   **说明**：文中明确说明了训练使用的GPU型号和显存。
    *   **GPU型号**：NVIDIA RTX 4090（24GB显存）。
    *   **训练步数与批次**：主要模型（MM-DiT）训练30万步（300k iterations），批次大小（Batch Size）为32。
    *   **辅助模块训练**：身份对齐编码器训练8万步；时长预测器训练至少10万步。
*   文中未明确说明总的训练时长（以小时/天为单位）。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了较为充分的定量、定性和消融实验。
    *   **主要对比实验**：在组合数据集上，与两大类共7种SOTA方法进行了全面的客观指标对比（1组，见表1）。
    *   **主观评测实验**：与2种代表性方法（声学引导和视觉引导各一个）进行了MOS评测（1组，见表2）。
    *   **定性分析**：提供了生成语音的梅尔频谱和F0曲线可视化，与4种基线方法及真实语音进行对比（图3）。还提供了语音特征（情感、身份）的t-SNE分布可视化（图4）。
    *   **消融研究**：设计了5组消融实验，分别验证了身份条件、情感条件、课程学习、身份对齐损失、EPFG的有效性，并单独分析了课程学习的训练动态和EPFG的参数选择、采样步数效率（表3，图5，图6）。这些消融实验设计合理，能够清晰地证实各个模块的贡献。

*   **充分性与公平性评价**：
    *   **充分性**：实验设计全面，从客观指标、主观评价到可视化分析，层层递进，论证链条完整。
    *   **公平性**：公平性较高。对比方法中，开源代码的方法（如EmoSpeech等）均在相同的数据预处理和训练集上复现。对于不开源的方法（如Face-TTS），则使用其官方发布的预训练模型进行评估，这是一种务实的对比方式。值得注意的一点是，Face-TTS虽然数据量远超DEmoFace，但DEmoFace在风格一致性上表现更优。

### 6. 论文的主要结论与发现

*   DEmoFace是首个成功仅从视觉线索合成情感一致且身份保真语音的框架，在视觉引导语音合成任务上取得了显著的性能突破。
*   在客观和主观评测中，提出的**视觉引导DEmoFace在自然度和风格一致性上不仅超越了同类视觉引导方法（Face-TTS），甚至优于部分需要声学引导的方法**，成功弥合了跨模态差距。
*   所提出的**离散扩散模型**、**课程学习策略**和**EPFG**多条件引导技术是有效的，无需依赖任何语音提示即可实现情感丰富、表意清晰的语音生成。
*   消融实验证实，对身份和情感的精细解耦与建模是实现高质量eF2S的关键。

### 7. 优点

*   **新颖的任务定义**：率先提出并定义了“情感面部到语音（eF2S）”这一具有挑战性和应用前景的新任务，拓展了F2S的研究边界。
*   **完整创新的技术框架**：提出的DEmoFace框架首次将离散扩散模型与RVQ编解码器结合用于语音生成，并配套设计了MM-DiT、课程学习、EPFG等一系列原创技术，形成了一套完整的解决方案。
*   **多条件解耦能力**：所设计的EPFG和条件注入模块能有效解耦身份、情感和文本信息，实现了精准的语音属性控制。
*   **生成质量与效率**：在生成高质量语音的同时，模型经优化后具有较低的实时系数（RTF为0.49），展示了实时应用的潜力。强大的泛化能力，使用较少的数据量超越了大数据量训练的基线。

### 8. 不足与局限

*   **“平均音色”问题**：作者坦言，由于数据集（视觉-语音）内部固有的偏差，模型倾向于生成“平均化”的语音，难以精确重建特定个体的真实音色。
*   **发音准确性受限**：受限于当前数据集规模（31.33小时），模型在精确发音方面仍面临挑战，词错误率（WER）相比使用超大规模数据训练的方法仍有差距。
*   **数据集多样性**：实验主要在实验室环境或影视剧（RAVDESS, MEAD, MELD）数据集上进行，其在复杂多变的真实世界环境（In-the-wild）下的鲁棒性和泛化能力有待进一步验证。
*   **伦理与隐私风险**：作为一种可从面部生成特定人物声音的技术，存在被滥用于深度伪造、侵犯个人隐私和声音权的风险，应用时需严格的伦理审查和用户授权。

（完）
