---
title: Word-Level Emotional Expression Control in Zero-Shot Text-to-Speech Synthesis
title_zh: 零样本文语转换中的词级情感表达控制
authors: "Tianrui Wang, Haoyu Wang, Meng Ge, Cheng Gong, Chunyu Qiang, Ziyang Ma, Zikang Huang, Guanrou Yang, Xiaobao Wang, EngSiong Chng, Xie Chen, Longbiao Wang, Jianwu Dang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SYcggdxX6W"
tags: ["query:affective-ai"]
score: 10.0
evidence: 无需句内情感数据实现零样本文语转换中的词级情感控制
tldr: 针对情感文语转换中缺乏句内情感标注和难以建模多情感过渡的挑战，本文提出WeSCon框架，通过自训练策略首次在预训练零样本TTS模型上实现词级情感和语速控制。该方法引入过渡平滑和动态说话人适应技术，不依赖句内情感数据集。实验表明WeSCon能够精确控制每个词的情感表达，生成自然连贯的多情感语音，为细粒度表现力语音合成开辟了新方向。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 923, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1212, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1407, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1390, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 745, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1090, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 696, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1159, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1393, \"height\": 1045, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1361, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1372, \"height\": 517, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1341, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 600, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 884, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1173, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1208, \"height\": 351, \"label\": \"Table\"}]"
motivation: 现有情感TTS大多局限于话轮级情感表达，无法实现词级精细控制，且句内情感标注数据稀缺。
method: 提出WeSCon自训练框架，结合过渡平滑和动态说话人适应，在预训练零样本TTS上实现词级情感和语速控制。
result: 实验证明WeSCon能生成具有平滑多情感过渡的高质量语音，词级控制精确。
conclusion: WeSCon突破了情感TTS的粒度限制，为情感语音生成提供了新的自训练范式。
---

## Abstract
While emotional text-to-speech (TTS) has made significant progress, most existing research remains limited to utterance-level emotional expression and fails to support word-level control. Achieving word-level expressive control poses fundamental challenges, primarily due to the complexity of modeling multi-emotion transitions and the scarcity of annotated datasets that capture intra-sentence emotional and prosodic variation. In this paper, we propose WeSCon, the first self-training framework that enables word-level control of both emotion and speaking rate in a pretrained zero-shot TTS model, without relying on datasets containing intra-sentence emotion or speed transitions.
Our method introduces a transition-smoothing strategy and a dynamic speed control mechanism to guide the pretrained TTS model in performing word-level expressive synthesis through a multi-round inference process. To further simplify the inference, we incorporate a dynamic emotional attention bias mechanism and fine-tune the model via self-training, thereby activating its ability for word-level expressive control in an end-to-end manner. Experimental results show that WeSCon effectively overcomes data scarcity, achieving state-of-the-art performance in word-level emotional expression control while preserving the strong zero-shot synthesis capabilities of the original TTS model.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **核心问题**：当前的情感文本转语音（TTS）系统大多只能实现**句子级（utterance-level）的情感控制**，无法像人类一样在同一个句子中对不同的词语赋予不同的情感和语速变化（即**词级控制**）。这一能力的缺失，阻碍了 TTS 合成语音达到自然且富有表现力的人类水平。
*   **根本挑战**：
    *   **建模复杂性**：需要处理一句话中多种情感之间的平滑过渡。
    *   **数据稀缺性**：几乎不存在公开的、带有句内情感和韵律变化标注的大规模数据集，这使得传统有监督训练方法不可行。
*   **整体含义**：本文旨在解决上述挑战，提出一种在**不依赖句内情感过渡数据**的情况下，赋予预训练零样本 TTS 模型词级情感和语速控制能力的方法，从而提升合成语音的自然度和表现力。

### 2. 论文提出的方法论

论文提出 **WeSCon**，一个两阶段的自训练框架，以 CosyVoice2 为骨干模型。

*   **第一阶段：教师模型**
    *   **词级情感控制**：采用**多轮推理**策略。将一个句子按情感标签分段，每轮使用一个情感提示语音合成该段内容。为解决拼接产生的声学不连续性，引入了**过渡平滑模块**：在每轮推理时，将上一轮生成的文本和语音末尾 Token 追加到当前提示中，实现“尾-头”链接，使模型以续写方式生成，确保过渡平滑。该平滑模块是一个轻量级、非因果的 Transformer 对齐器，仅用 ASR 数据训练，无需情感监督。
    *   **词级语速控制**：在每轮推理中，通过对提示语音 Token 进行**动态插值或下采样**来控制当前片段的语速（插值减速，下采样加速）。
    *   **说话人一致性**：在多轮推理中优选同一说话人的不同情感提示，并在最终的流匹配阶段引入目标说话人参考，以维系输出语音的说话人特征。
*   **第二阶段：自训练与学生模型**
    *   **自训练**：用第一阶段教师模型生成大量带有词级情感和语速变化的高质量合成语音，作为伪标签，并用**数据过滤机制**（根据字符准确率、情感相似度等筛选）保留优质数据，喂给原始 TTS 模型（学生）进行微调。
    *   **动态情感注意力偏置（DEAB）**：为实现端到端的词级控制，学生模型在输入中引入**情感标志 Token** 标记情感段落，并配备一个轻量级因果 Transformer 来**实时预测每一时刻的情感标签**。根据预测的情感，模型在自注意力层上叠加一组**动态偏置矩阵**，强制模型在生成特定情感片段时，只关注与该情感相关的提示 Token，抑制情感漂移。
    *   **损失函数**：学生模型训练时，在原有负对数似然损失（`L_tts`）基础上，加入情感标签预测的交叉熵损失（`L_e`），联合优化。

### 3. 实验设计

*   **数据集**：
    *   **训练数据**：第一阶段用 LibriSpeech-100-Clean（英语）和 AISHELL-1（中文）共 200 小时非情感数据训练对齐器。第二阶段使用 ESD 数据集中的非过渡情感语音作为提示，并用 GPT-4o 生成的包含情感过渡的文本作为合成目标。
    *   **测试数据**：基于 ESD 的测试集，通过 GPT-4o 生成 1000 条（中英各 500）含情感和语速变化的文本进行测试。此外，还用 CASIA（中文情感数据库）进行了域外泛化测试。
*   **对比基准**：Index-TTS， F5-TTS， Spark-TTS， CosyVoice2。所有基线均采用“多轮分段合成再拼接”的方式实现词级控制。
*   **评估指标**：
    *   **客观指标**：WER/CER（可懂度）、DNSV（过渡自然度，方差越小越好）、S-SIM（说话人相似度）、AutoPCP（韵律相似度）、Emo2v./Aro.（情感相似度）。
    *   **主观指标**：MOS 评分，包括 EMOS（情感匹配）、SPMOS（语速匹配）、SMOS（说话人相似度）、NMOS（过渡自然度）。

### 4. 资源与算力

*   **第一阶段**：在 **2 块 NVIDIA 3090 GPU** 上训练 40 万步。
*   **第二阶段**：在 **4 块 NVIDIA 3090 GPU** 上训练 60 万步。
*   **推理**：设置 `k=50`，`temperature=0.9`。

### 5. 实验数量与充分性

*   **主要对比实验**：在英、中两种语言上与 4 种基线进行客观指标和主观 MOS 对比，共 1 组（表 1、2）。
*   **消融实验**：针对过渡平滑机制、动态语速控制、动态情感注意力偏置、自训练数据格式（情感标志、统一格式）以及数据过滤策略，共包含**6 项消融研究**（表 4）。
*   **其他补充实验**：**零样本 TTS 能力保持**（表 3）、自训练数据规模的影响（图 5）、域外泛化测试（表 6）、训练过程中对齐精度监控（附录图 10、11）等。
*   **充分性与客观性**：实验覆盖了中英双语、多项客观与主观指标，且与多个强基线公平对比。消融实验系统地验证了每个提出的模块的有效性，且所有基线在词级控制任务上都采用相同的多轮拼接范式，比较公平。

### 6. 论文的主要结论与发现

*   **词级控制可达**：WeSCon 成功在零样本 TTS 模型上实现了词级情感和语速的精准控制，且**无需依赖句内情感过渡标注数据**。
*   **性能最优**：在情感相似度、过渡自然度、语速控制精确度等关键指标上，WeSCon 均超越了所有对比基准，达到了当前最佳水平。
*   **过渡平滑显著**：提出的过渡平滑和动态注意力偏置机制极大地降低了多情感拼接带来的声学不连续性（DNSV 大幅下降）。
*   **保持原有能力**：在获得词级控制能力的同时，模型在标准零样本 TTS 任务上的性能（可懂度、说话人相似度）基本保持不变。
*   **自训练有效但有上限**：随着自训练数据量增加，模型性能先升后降，存在过拟合风险，这源于 ESD 数据集的有限多样性。

### 7. 优点

*   **方法创新**：首创性地通过自训练框架，在无句内情感数据的情况下实现了零样本 TTS 的词级细粒度控制。
*   **工程精巧**：多轮推理的“尾-头”链接平滑机制和基于预测的动态注意力偏置，都是低成本、高效益的设计，未对预训练模型进行大规模结构调整。
*   **泛化与保持**：较好地平衡了新能力的注入和原有零样本能力的保持，并在域外数据上展现出一定的泛化性。
*   **实验扎实**：评估维度全面，消融实验设计清晰，开源数据和模型选择增强了可复现性。

### 8. 不足与局限

*   **情感建模深度有限**：仅支持离散情感的切换，无法模拟人类情感中自然的**渐变过程**（如从伤心缓慢过渡到平静），也未涉及复合情感的表达。
*   **控制方式受限**：情感过渡计划完全由外部（如 GPT-4o）预设，缺乏根据对话上下文动态、自主调整情感的能力。
*   **数据偏见风险**：自训练的监督信号来自教师模型，其上限受限于教师性能和选用的情感数据集（ESD）。且合成数据的过度使用导致模型在超出特定量后出现过拟合，限制了性能的进一步提升。
*   **伦理风险**：与其他高表现力 TTS 模型类似，WeSCon 存在被滥用于**说话人模仿和深度伪造**的潜在风险。

（完）
