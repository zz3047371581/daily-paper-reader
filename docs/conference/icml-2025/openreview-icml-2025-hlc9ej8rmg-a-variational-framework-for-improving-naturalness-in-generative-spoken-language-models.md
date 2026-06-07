---
title: A Variational Framework for Improving Naturalness in Generative Spoken Language Models
title_zh: 提升生成式口语模型自然度的变分框架
authors: "Li-Wei Chen, Takuya Higuchi, Zakaria Aldeneh, Ahmed Hussen Abdelaziz, Alexander Rudnicky"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=HLC9eJ8RMg"
tags: ["query:affective-ai"]
score: 8.0
evidence: 变分框架建模韵律和副语言特征以生成自然语音
tldr: 现有口语模型仅关注语义，忽视韵律和副语言信息，导致语音自然度差。本文提出端到端变分框架，自动学习并注入丰富的副语言特征（如情感语调、重音等），克服手动设计特征的局限。实验生成更自然的语音，有效提升了口语语言模型的表达力，对情感语音合成等任务具有直接价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1761, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1713, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1714, \"height\": 65, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 618, \"height\": 61, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1706, \"height\": 68, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 821, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1435, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1475, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1542, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 805, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1134, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1107, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1147, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1007, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1017, \"height\": 279, \"label\": \"Table\"}]"
motivation: 口语模型因忽略韵律信息而生成不自然的语音。
method: 提出端到端变分框架，自动建模并融合韵律与副语言属性。
result: 生成的语音在自然度和表现力上显著优于仅使用音高特征的方法。
conclusion: 为情感语音合成和自然口语生成提供了有效方案。
---

## Abstract
The success of large language models in text processing has inspired their adaptation to speech modeling.
However, since speech is continuous and complex, it is often discretized for autoregressive modeling.
Speech tokens derived from self-supervised models (known as semantic tokens) typically focus on the linguistic aspects of speech but neglect prosodic information.
As a result, models trained on these tokens can generate speech with reduced naturalness.
Existing approaches try to fix this by adding pitch features to the semantic tokens.
However, pitch alone cannot fully represent the range of paralinguistic attributes, and selecting the right features requires careful hand-engineering.
To overcome this, we propose an end-to-end variational approach that automatically learns to encode these continuous speech attributes to enhance the semantic tokens.
Our approach eliminates the need for manual extraction and selection of paralinguistic features.
Moreover, it produces preferred speech continuations according to human raters.
Code, samples and models are available at https://github.com/b04901014/vae-gslm.

---

## 论文详细总结（自动生成）

好的，我将基于提供的论文内容，以结构化的方式对其进行深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：当前的生成式口语语言模型（GSLM）通常将连续的语音信号离散化为“语义令牌”（Semantic Tokens）进行自回归建模。这些令牌主要捕捉语音中的语言内容（如音素），但普遍**忽略了韵律、能量、频谱等副语言信息**，导致生成的语音**自然度不足**。
*   **研究动机**：现有补救方案，如人工提取并添加音高（F0）特征，存在根本性缺陷：(1) 音高无法全面表征副语言信息；(2) 人工选择和设计特征需要大量专家经验且不一定最优。
*   **整体含义**：本文旨在提出一个端到端的变分框架，**自动学习**连续的、能补充语义令牌的副语言特征（称为“变分特征”），从而在无需手动设计特征的情况下，显著提升生成语音的自然度。

### 2. 论文提出的方法论

论文的核心思想是**将变分自编码器（VAE）与带自回归先验的语义令牌模型相融合**。

*   **核心思想与框架**：
    *   **框架构成**：框架（图1）包含三条主线：
        1.  **语义令牌流**：预训练的语音分词器将语音转为离散语义令牌 \( Z^d \)。
        2.  **变分特征流**：一个编码器 \( \phi \) 从语音中学习连续的变分特征 \( Z^c \)。
        3.  **联合自回归建模**：一个自回归模型 \( \psi \) 同时以上下文序列 \( Z_{1:t-1} \)（包含变分特征和语义令牌）为条件，预测下一个变分特征 \( z^c_t \) 和下一个语义令牌 \( z^d_t \)。
        4.  **语音重建**：一个解码器 \( \theta \)（默认为扩散模型）则根据完整的序列 \( Z^c \) 和 \( Z^d \) 重建原始语音。

*   **关键技术细节**：
    *   **VAE与自回归先验的结合**：变分特征 \( Z^c \) 的后验分布 \( q_\phi(Z^c|X) \) 被建模为对角高斯分布，而其先验分布 \( p_\psi(Z^c) \) 不再是固定的标准高斯，而是一个**可训练的自回归模型**，从而可以捕捉时序依赖。
    *   **与语义令牌的整合**：通过假设 \( Z^c \) 和 \( Z^d \) 在给定过去生成内容 \( Z_{1:t-1} \) 时条件独立，将整体损失函数（`ELBO`）分解为三个主要部分（公式4和5）：
        *   \( \mathcal{L}_{rec} \)（重建损失）：鼓励变分特征 \( Z^c \) 包含有助于与 \( Z^d \) 共同重建语音 \( X \) 的信息。
        *   \( \mathcal{L}^c_{kl} \)（变分特征预测损失）：训练自回归模型预测下一个 \( z^c_t \)，同时正则化 \( Z^c \) 使其易于被自回归模型建模。
        *   \( \mathcal{L}^d_{kl} \)（语义令牌预测损失）：训练自回归模型预测下一个语义令牌 \( z^d_t \)。
    *   **损失平衡**：引入两个超参数 \( \beta \) 和 \( \gamma \) 来平衡上述三个损失项（`ELBO` = \( \mathcal{L}_{rec} - \beta(\mathcal{L}^c_{kl} + \gamma \cdot \mathcal{L}^d_{kl}) \)）。\( \beta \) 控制 \( Z^c \) 的信息量，\( \gamma \) 控制自回归模型对语言内容和副语言特征的关注权重。对 \( \beta \) 采用从零开始的线性预热策略以防止后验坍塌。
    *   **逐时间归一化流**：为了增强自回归先验 \( p_\psi(z^c_t|Z_{1:t-1}) \) 的表达能力，在自回归模型输出后接了一个轻量级的逐时间共享的可逆归一化流网络（仿射耦合层）。
    *   **其他组件**：使用扩散模型作为解码器以提升生成质量；引入一个发声编码器（Utterance Encoder）从语音片段中提取全局静态信息（如说话人身份），以使 \( Z^c \) 更专注于动态的韵律特征。

### 3. 实验设计

*   **数据集**：
    *   **LibriSpeech**（960小时）：用于大部分消融研究和分析。
    *   **Libri-light**（60,000小时）：用于主实验的模型训练，以展示在大数据下的性能。
    *   语义令牌来自在相应数据集上预训练的HuBERT模型，通过K-means聚类（K=200）得到。
*   **对比方法**：
    1.  **Token-LM**：仅使用语义令牌的自回归模型，作为基线。
    2.  **Token-LM + Pitch**：在语义令牌基础上，额外输入通过CREPE提取的音高特征，并增加音高回归任务。
    3.  **Token-LM + Acoustic**：在语义令牌基础上，额外输入多层残差矢量量化得到的声学令牌。
    4.  **Proposed**：本文提出的变分词建模方法。
*   **评估指标**：
    *   **客观指标**：
        *   **重建质量**：F0-RMSE（基频均方根误差）、MCD（梅尔倒谱失真）、CER（字符错误率，基于Whisper ASR）。
        *   **语言能力**：ZeroSpeech挑战中的sWUGGY（非词辨别）和sBLIMP（语法辨别）。
    *   **主观指标**：
        *   **N-MOS**（自然度平均意见分）：评估合成语音有多像人类。
        *   **M-MOS**（意义性平均意见分）：评估合成语音的语法和内容质量。

### 4. 资源与算力

*   **GPU与训练时长**：
    *   **Libri-light模型**：使用**2块L40S GPU**，配合梯度累积（步长2），有效批大小为192。训练了**600,000步**，耗时约**14天**。
    *   **LibriSpeech模型**：同样使用**2块L40S GPU**，有效批大小与Libri-light相同但不使用梯度累积。不同方法训练步数在100k到500k步之间，耗时**少于1天或2天**。
*   **优化与精度**：采用AdamW优化器配合余弦学习率衰减，使用**混合精度**训练。
*   **推理开销**：论文明确指出，提出的方法引入的额外参数量很小（总参数221M vs 基线的219M，**开销<1%**）。

### 5. 实验数量与充分性

*   **实验数量**：论文设计了多组充分的实验，包括：
    *   **主实验**：在Libri-light大规模数据上，对比4种方法，并评估客观重建指标、客观语言能力指标和两种主观MOS指标。
    *   **关键超参数消融**：在LibriSpeech上研究不同\( \beta \)值的影响；在Libri-light上研究不同\( \gamma \)值的影响，并验证其对主客观指标的作用。
    *   **部件有效性实验**：移除语义令牌（仅剩VAE+自回归先验）以检验其作用。
    *   **泛化性实验**：将语义令牌提取方法替换为SpeechTokenizer，验证框架的通用性。
*   **充分性与公平性**：
    *   **公平性**：相当公平。所有对比方法的自回归Transformer主体架构、扩散解码器、发声编码器和声码器（HiFi-GAN）均保持一致，**仅改变自回归模型的输入和输出层**，确保了对比的严谨性。
    *   **客观性**：结合了客观评测（重建误差、语言建模能力）和主观评测（听觉感知），评估维度全面。
    *   **偏差风险**：主观评测通过众包进行，每份样本由7名评估者打分，并报告了95%置信区间，统计上较为可靠。但结果可能受限于英语数据集和LibriSpeech/Libri-light的朗读风格。

### 6. 论文的主要结论与发现

1.  **自然度显著提升**：所提方法生成的语音在主观自然度（N-MOS）上**显著优于**所有基线，证明自动学习的变分特征能有效补充语义令牌，改善合成质量。
2.  **重建质量优异**：变分特征极大提升了基频和频谱重建的准确性（F0-RMSE和MCD远低于Token-LM和+Pitch），表明其编码了丰富的副语言信息。
3.  **语言能力得以保持**：虽然sWUGGY/sBLIMP得分略低于纯语义模型（因模型需分配部分容量建模声学信息），但主观意义性得分（M-MOS）**达到或优于基线**。作者分析认为，自然的韵律显著提高了语音的可懂度，使得人类做语义判断时无需反复聆听。
4.  **超参数\( \beta \)和\( \gamma \)的作用**：\( \beta \)越小，重建质量越好但自回归建模越难；\( \gamma \)控制着变分特征中编码的信息类型（更大的\( \gamma \)促使特征包含更多语音信息，反之则包含更多音高信息）。
5.  **框架的灵活性**：该框架不仅限于HuBERT令牌，对SpeechTokenizer令牌同样有效，也不依赖于特定的解码器。

### 7. 优点

*   **方法创新性强**：巧妙地将VAE、自回归先验和归一化流结合，用于自动学习口语中的连续副语言特征，摆脱了对手动设计特征的依赖。
*   **性能提升显著**：在保持语言内容质量的同时，极大地提升了生成语音的自然度，N-MOS提升幅度可观。
*   **理论实践结合紧密**：通过引入\( \beta \)和\( \gamma \)两个超参数并对其作用进行深入分析，为理解模型的行为提供了明确的“控制旋钮”。
*   **对比实验严谨且公平**：固定大部分模型组件，仅改变核心建模对象，使得性能对比极具说服力。
*   **模型轻量高效**：引入的额外参数量极小（<1%），具有很高的实用价值。

### 8. 不足与局限

*   **超参数敏感性**：作者明确指出，模型性能对 \( \beta \) 和 \( \gamma \) 这两个超参数的选择**较为敏感**，目前需要手动调整，未来可探索自动化调参方法。
*   **语言单一性**：实验仅基于**英语**数据集（朗读语音），模型能否推广到其他具有不同韵律模式的语言尚待验证。
*   **数据与规模限制**：尽管使用了Libri-light，但与当前最前沿的超大模型和海量数据相比，论文使用的模型（2亿参数）和数据规模（6万小时）相对较小，**结论在大规模下的可扩展性有待考证**。
*   **生成语音类型有限**：训练数据为朗读语音，模型对更自然的、带有更高情感表达和复杂语境变化的场景交流语音的建模能力未做探索。

（完）
