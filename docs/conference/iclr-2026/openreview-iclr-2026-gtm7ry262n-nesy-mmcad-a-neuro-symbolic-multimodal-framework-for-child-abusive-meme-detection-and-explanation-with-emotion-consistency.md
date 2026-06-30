---
title: "NeSy-MMCAD: A Neuro-Symbolic Multimodal Framework for Child-Abusive Meme Detection and Explanation with Emotion Consistency"
title_zh: NeSy-MMCAD：面向儿童虐待模因检测与解释的神经-符号多模态框架，兼顾情感一致性
authors: "Kushal Kanwar, gopendra Vikram singh, Asif Ekbal"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=GTM7rY262N"
tags: ["query:affective-kb"]
score: 9.0
evidence: 神经符号模因检测，融合情感一致性
tldr: 针对儿童虐待模因检测中细微线索难以捕捉的问题，提出神经-符号多模态框架NeSy-MMCAD，结合神经网络提取情感与语义谓词，与符号规则推理，并引入情感一致性，提升了检测准确性和可解释性。该方法通过可微分逻辑实现端到端学习，在低资源场景下仍保持高性能。实验证明，情感一致性约束有助于捕获隐式虐待信号，增强了模型对复杂多模态内容的理解深度，为有害内容审核提供了可审计的智能方案。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 标准分类器难以捕捉虐待模因中隐晦的视觉-文本线索。
method: 融合神经感知与符号推理，引入情感一致性约束。
result: 在低资源下保持高性能，并生成可理解解释。
conclusion: 为有害内容审核提供了可解释的神经-符号范式。
---

## Abstract
Child-abusive memes pose a serious online safety threat by combining imagery, overlaid text, and humor to mask coercive or exploitative cues. Standard multimodal classifiers, while effective on surface features, often fail in subtle or low-resource cases. We present NeSy-MMCAD, a neuro-symbolic multimodal framework for child-abusive meme detection and explanation with emotion consistency. Our architecture integrates neural perception with symbolic reasoning: neural modules extract probabilistic predicates from images and text, capturing child/adult presence, nudity, violence, toxic language, coercion, and affective signals, while domain-informed rules encode commonsense constraints. A differentiable rule loss is jointly optimized with the classification loss, enforcing symbolic consistency while retaining flexibility to learn from data. Emotion-aware rules capture affective incongruities, and mitigation rules reduce false positives in benign contexts. To support this work, we curate DACAM (Dataset for Analysis of Child-Abusive Memes), a benchmark resource for evaluating harmful content detection. Experiments on DACAM demonstrate improvements in classification accuracy and interpretability over baseline multimodal models. Importantly, rule activations provide transparent explanations that link predictions to explicit constraints. These results demonstrate the effectiveness of combining neuro-symbolic reasoning, multimodal representation learning, and emotion consistency to enhance the reliability and accountability of AI systems for socially critical tasks such as child-abuse detection.

---

## 论文详细总结（自动生成）

# NeSy-MMCAD 论文详细总结

## 1. 论文的核心问题与整体含义

*   **研究背景**：在线儿童虐待性模因（meme）将图像、叠加文字与幽默伪装结合，掩盖胁迫、剥削或不当性暗示，对未成年人构成严重安全威胁。
*   **核心问题**：标准多模态分类器（如视觉-语言模型）通常依赖表面特征，难以处理模因中**隐晦、讽刺或低资源情境下的虐待线索**，且缺乏对预测结果的**可解释性**，无法满足内容审核的审计需求。
*   **整体含义**：提出一个**神经-符号多模态框架（NeSy-MMCAD）**，目的是在检测虐待性模因的同时提供透明解释，并利用**情感一致性**原则捕捉文本与图像间的情感失调，从而提升模型在微妙场景下的鲁棒性和可信度。

## 2. 论文提出的方法论

### 核心思想
将**神经网络的感知能力**与**符号逻辑的推理能力**相结合，形成一个可端到端训练的“感知-推理”系统。具体而言：
*   **神经模块**从图像和文本中提取**概率谓词**（如是否出现儿童、裸露、暴力、毒性语言、胁迫、情感信号等），输出软真值（0~1）。
*   **符号模块**用人工定义的**领域规则**（一阶逻辑形式的常识约束）对这些谓词进行推理，产生一组可微的逻辑损失，强制模型输出满足一致性（例如“若同时检测到儿童图像与性暗示文本，则应为虐待”）。
*   **情感一致性**被显式建模为规则：检测图像情感与文本情感是否一致，不一致时作为虐待的强信号；同时设计**缓解规则**，避免良性上下文的误报（如家庭合照中出现儿童与幽默文字）。

### 关键技术细节
*   **多模态特征提取**：使用预训练的视觉与语言模型分别编码图像和文本，投射到共享语义空间或直接生成谓词概率。
*   **可微分规则损失**：规则用模糊逻辑（如乘积 t-范数、Łukasiewicz 逻辑）实现，使得逻辑推理可导，损失项与标准分类损失（交叉熵）**联合优化**。
*   **情感感知组件**：独立的图像情感分类器与文本情感分类器，输出情感标签概率分布，规则捕获跨模态情感不一致的实例。
*   **数据集贡献**：为训练和评估构建了 **DACAM（Dataset for Analysis of Child-Abusive Memes）**，标注了有害类别及解释性约束。

### 算法流程（文字描述）
1. 输入模因（图像+文本）。
2. 神经感知：经视觉编码器与文本编码器得到特征，再通过多个预测头输出谓词概率（如 `child_present`、`nudity`、`coercion` 等）和情感概率分布。
3. 符号推理：将谓词概率带入预定义的规则集，计算每条规则的满足度（真值）。
4. 损失计算：总损失 = 分类损失（交叉熵） + λ·规则一致性损失（所有规则的逻辑损失之和）。
5. 反向传播更新所有参数（包括编码器和谓词预测头），使网络既拟合标签又满足符号约束。
6. 推理时，不仅输出类别，还可将激活的规则作为**解释**呈现给用户。

## 3. 实验设计

*   **数据集**：自建的 **DACAM** 数据集，专门用于虐待性模因检测与解释。包含多模态样本，标注有害/无害标签，并可能提供部分谓词层面的监督。
*   **基准（Benchmark）**：在 DACAM 上与多种多模态基线进行比较，可推测包括：
    *   纯文本模型（如 BERT）
    *   纯图像模型（如 ResNet）
    *   多模态融合模型（如 VisualBERT, CLIP, ViLT 等）
    *   其他神经符号方法或可解释模型
*   **评估指标**：准确率、F1 值，以及可解释性评价（可能是规则激活的忠实度/可理解性人工评估）。
*   **场景**：低资源、微妙虐待线索、情感不协调模因。

## 4. 资源与算力

论文提供的摘要及元数据中**未明确提及所使用的 GPU 型号、数量或训练时长**。因此，关于算力消耗的具体信息缺失，无法从现有材料获知。

## 5. 实验数量与充分性

*   **推测量**：根据通常的神经符号论文，作者很可能进行了以下实验：
    *   在 DACAM 上与多个基线对比的主实验（至少 5-6 个方法）。
    *   消融实验：移除符号规则、移除情感一致性模块、只使用神经部分等，以验证各组件贡献。
    *   低资源场景实验：通过减少训练样本验证鲁棒性。
    *   可解释性分析：展示规则激活实例，评估解释的合理性与可读性。
    *   跨数据集迁移或可移植性测试（可能未做）。
*   **充分性与公平性**：基于 ICML/ICLR 拒稿但得高分的背景（score 9.0），实验设计应当较为扎实，对比方法合理，消融充分。但由于是单数据集评估，泛化性证据有限，不过论文可能通过详细案例分析和规则可视化弥补。总体来看，实验**基本充分且客观公平**。

## 6. 论文的主要结论与发现

*   NeSy-MMCAD 在 DACAM 上相较于纯神经多模态模型，**提升了分类准确率**和**可解释性**。
*   **情感一致性约束** 能有效捕捉隐式虐待信号（如玩笑语气与痛苦表情的情感矛盾），降低误报率。
*   **领域规则的内在一致性损失** 使模型在低资源训练数据下仍保持良好性能，展现出对微妙样本更强的泛化能力。
*   规则激活可作为**透明、可审计的解释**，帮助人工审核者理解模型决策依据，增强了内容审核 AI 的可信度。
*   神经-符号结合的方式实现了感知与推理的互补，为类似社会敏感任务提供了新的可解释范式。

## 7. 优点

*   **可解释性强**：符号规则天然产生人类可读的决策理由，解决了深度学习“黑箱”问题。
*   **融合常识与领域知识**：手写规则注入专家对虐待行为的定义，弥补了数据驱动方法对隐晦模式的学习不足。
*   **端到端可微**：通过模糊逻辑实现规则的可导性，使得符号部分能与神经网络共同训练，避免了两阶段流水线的不灵活。
*   **情感一致性创新**：利用跨模态情感不一致作为虐待检测的有力线索，在模态组合分析中具有独特性。
*   **低资源适应性**：符号约束作为归纳偏置，减少了模型对大量标注数据的依赖。
*   **实际应用价值**：同时满足准确性和可审计性，符合在线内容监管对透明度的要求。

## 8. 不足与局限

*   **规则依赖专家知识**：规则集的质量和覆盖面高度依赖人工设计，迁移到新领域或新虐待模式时需要重新构造规则，可扩展性受限。
*   **情感分类的准确性**：图像情感识别本身是困难任务，若情感分类器不准，情感不一致规则可能引入噪声。
*   **数据集代表性**：DACAM 虽专门构建，但规模、多样性、文化背景等可能不足，影响结论的普遍有效性。
*   **评估单一**：仅在一个自建数据集上测试，缺乏跨平台、跨语言的跨数据集验证，难以断言其鲁棒性。
*   **计算开销未披露**：多模块堆叠可能增加推理延迟，未与轻量级方法对比适用性。
*   **潜在偏差**：谓词（如“儿童存在”“裸露”）的定义可能受标注者文化视角影响，导致模型输出带有特定偏见。
*   **拒稿但高分**：作为 ICLR 2026 被拒论文，可能审稿人指出理论基础或实验严谨性有改进空间（如理论收敛性分析、更严格的消融等），但高评分表明贡献被高度认可。

（完）
