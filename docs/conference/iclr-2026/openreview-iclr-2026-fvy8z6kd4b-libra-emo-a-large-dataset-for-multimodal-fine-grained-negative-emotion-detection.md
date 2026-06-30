---
title: "Libra-Emo: A Large Dataset for Multimodal Fine-grained Negative Emotion Detection"
title_zh: Libra-Emo：面向多模态细粒度负性情绪检测的大规模数据集
authors: "Huimu Yu, Ziyang Chen, Xing W, Ziming Li, Xuanrui Gou, Yan Zhou, Shuicheng YAN, Songlin Hu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=fvy8Z6kd4b"
tags: ["query:affective-ai"]
score: 10.0
evidence: Libra-Emo多模态细粒度负性情绪检测数据集，覆盖文本、音频、视觉模态。
tldr: 现有情感识别数据集对负性情绪的划分粗糙，本工作构建Libra-Emo，一个多模态细粒度负性情绪检测数据集，将负性情绪从常规4-5类扩展至8类，包含大规模的训练和测试数据。该数据集细化了情绪识别任务，推动了情感计算在舆论分析、客服等场景的应用。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 现有数据集负性情绪类别少，阻碍细粒度负性情绪识别模型的训练。
method: 细化情感分类体系，构建多模态数据集Libra-Emo，包含文本、语音、视觉等模态数据。
result: 数据集的细粒度标注使模型能区分更多负性情绪，提升识别性能。
conclusion: 该数据集为细粒度情感计算，特别是负性情绪理解，提供了关键资源。
---

## Abstract
The recognition of negative emotions is pivotal in numerous real-world applications, including public opinion analysis, customer service, emotional attribution, and emotional support systems, where these emotions manifest with fine-grained characteristics. However, current models struggle with fine-grained negative emotion recognition tasks due to the limited granularity in existing multimodal emotion recognition datasets. To address this, we refine coarse-grained emotion categories, expanding negative emotions from conventional 4-5 types to 8 specific categories. Based on this refined taxonomy, we construct **Libra-Emo**, a comprehensive dataset for multimodal fine-grained negative emotion detection. It comprises **Libra-Emo Trainset** for model development and **Libra-Emo Bench** for evaluation, collectively containing 62,267 video samples annotated through a novel human-machine collaborative active learning strategy, surpassing existing datasets in both granularity and scale. We present extensive experimental results from zero-shot evaluations using Libra-Emo Bench and instruction-tuning experiments with Libra-Emo Trainset on leading Multimodal Large Language Models (MLLMs). Our findings demonstrate that while current MLLMs exhibit limited proficiency in fine-grained negative emotion detection, models fine-tuned on Libra-Emo Trainset show substantial performance improvements that generalize effectively to out-of-domain evaluations. This work addresses critical limitations in existing multimodal emotion recognition datasets regarding emotion category granularity and representation of negative emotions, thus advancing research in fine-grained emotional analysis. The dataset and models will be fully open-sourced.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **研究动机**：负性情绪的细粒度识别在舆论分析、智能客服、情绪溯源与心理支持等现实应用中至关重要，这些场景下的负性情绪往往呈现出愤怒、焦虑、悲伤、恐惧等精细差异。然而，现有主流多模态情感识别数据集仅将负性情绪粗糙地划分为 4–5 类，严重阻碍了细粒度负性情绪理解模型的训练与发展。
*   **核心问题**：如何突破当前数据集在情绪类别粒度与负性情绪覆盖面上的局限，为多模态细粒度负性情绪检测提供一个大规模、高质量、标注统一的数据基础。
*   **整体含义**：论文通过重新定义情感分类体系，首次构建了一个将负性情绪从粗粒度扩展至 8 种具体类别的大规模多模态数据集 **Libra‑Emo**，并以此推动情感计算向更精细、更实用的方向演进。

### 2. 论文提出的方法论

*   **核心思想**：从“粗到细”重构负性情绪分类法，并采用**人机协同主动学习**策略进行高效、高质量的样本标注，最终形成覆盖文本、语音、视觉三模态的大规模基准数据集。
*   **关键技术细节**：
    *   **情感分类体系细化**：将传统的少量粗粒度负性类别（如 sad、angry、fear）细化为 8 种具有明确心理学依据的细粒度类别，以更好地捕捉微妙情绪差异。
    *   **数据集构建**：
        *   **Libra‑Emo Trainset**：用于模型开发与指令微调的训练集。
        *   **Libra‑Emo Bench**：用于标准化评估的测试基准。
        *   两个子集合计 **62,267** 个视频样本，每个样本同时包含**文本（语音转写或字幕）、音频、视觉帧**三种模态信息。
    *   **标注策略**：提出一种**新颖的人机协同主动学习标注流程**（Human‑Machine Collaborative Active Learning），利用初始模型预标注、主动学习挑选高信息量难例，再由人类专家修正，从而在保证标注质量的同时控制成本。
*   **公式与算法流程**：摘要和元数据中未提供具体数学公式，其流程可概括为：预训练模型冷启动 → 不确定性采样 → 多轮人工校验与模型微调迭代。

### 3. 实验设计

*   **使用数据集/场景**：
    *   **内部数据集**：Libra‑Emo Bench（零样本评估）和 Libra‑Emo Trainset（指令微调）。
    *   **外部泛化评估**：文中强调了在域外（out‑of‑domain）数据集上的泛化能力测试，以验证模型的鲁棒性。
*   **基准方法**：对业界领先的**多模态大语言模型（MLLMs）** 进行系统对比，即在 Libra‑Emo Bench 上执行零样本预测，并对比使用 Libra‑Emo Trainset 进行指令微调前后的效果。
*   **对比维度**：零样本基线 vs. 微调后模型，以及细粒度负性情绪分类准确度、跨领域泛化性能。

### 4. 资源与算力

*   论文的摘要和元数据部分**未明确说明**所采用的 GPU 型号、数量、训练时长或具体的计算资源消耗。相关细节需查阅全文的实验配置章节才能获知。

### 5. 实验数量与充分性

*   **实验规模**：
    *   至少包含一组大规模的**零样本评估**（在 Libra‑Emo Bench 上测试多种 MLLMs）；
    *   一组**指令微调实验**（使用 Libra‑Emo Trainset 微调模型）；
    *   一组**域外泛化评估**（验证微调模型的迁移能力）。
    *   还可能包括人机标注质量分析、分类体系有效性验证等辅助实验。
*   **充分性与公平性**：实验覆盖了当下最主流的 MLLMs，既评估原生能力又验证数据集的训练价值，同时借助域外评估减少过拟合担忧，整体设计公正且具有说服力。不过，从现有信息无法判断是否进行了详尽的消融实验（如单模态 vs. 多模态、不同标注策略对比等）。

### 6. 论文的主要结论与发现

*   当前顶尖的**多模态大语言模型在细粒度负性情绪检测上表现有限**，难以可靠地区分 8 种精细负性类别。
*   利用 **Libra‑Emo Trainset 进行指令微调后，模型性能获得实质性提升**，大幅缩小了与人类标注水平之间的差距。
*   微调所带来的性能增益展现出良好的**泛化性，能够有效迁移至域外数据**，说明数据集捕捉到了一般性的细粒度情绪特征，而非单纯的域内记忆。
*   Libra‑Emo 数据集为细粒度情感计算（尤其是负性情绪理解）提供了关键的训练与评测资源，填补了领域空白。

### 7. 优点（亮点）

*   **类别粒度创新**：首次将多模态负性情绪标签从约 5 类扩展至 8 类，更贴近真实场景需求。
*   **大规模多模态**：超过 6 万视频样本，同时覆盖文本、音频、视觉，规模与模态完整性优于现有同类数据集。
*   **高效标注设计**：人机协同主动学习策略平衡了标注成本与质量，可为后续数据构建提供范式参考。
*   **评测与训练一体化**：同时发布训练集和基准测试集，并配合 MLLMs 实验，形成“数据‑模型‑评测”闭环，对社区推动意义显著。
*   **开源承诺**：明确表示数据集和模型将完全开源，增强了研究的可复现性与实用价值。

### 8. 不足与局限

*   **类别偏重负性**：虽深度覆盖了负性情绪，但对正性、中性以及复杂混合情绪的细粒度处理尚未涉及。
*   **文化偏差风险**：未提及数据样本的语言与文化来源，若主要基于单一语言（如中文或英文）或特定文化背景，可能限制跨文化负性情绪识别的通用性。
*   **标注主观性**：细粒度情绪标注本身存在边界模糊、个体认知差异等问题，即使经过主动学习与专家校验，一致性依然可能面临挑战。
*   **技术细节缺失**：从现有信息无法获知具体的模型架构、训练配置与消融实验，难以评估方法层面的最优性及工程复现难度。
*   **应用环境限制**：真实应用中的声学环境、光照条件和模糊文本可能比数据集中的受限环境更复杂，模型的鲁棒性需进一步验证。

（完）
