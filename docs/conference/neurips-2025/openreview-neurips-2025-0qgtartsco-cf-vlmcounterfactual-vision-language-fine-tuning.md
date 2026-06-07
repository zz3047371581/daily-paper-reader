---
title: "CF-VLM:CounterFactual Vision-Language Fine-tuning"
title_zh: CF-VLM：反事实视觉-语言微调
authors: "Jusheng Zhang, Kaitong Cai, Yijia Fan, Jian Wang, Keze Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0qGtaRTsCo"
tags: ["query:affective-ai"]
score: 7.0
evidence: 提出反事实微调方法，增强视觉语言模型的因果推理和跨模态对齐。
tldr: 现有视觉语言模型依赖表面统计相关性，缺乏因果推理能力。本文提出CF-VLM，通过反事实样本微调，引入三种训练目标，增强跨模态对齐与因果推理。实验表明模型在细粒度鉴别和因果推理任务上取得提升。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 660, \"height\": 1232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1463, \"height\": 909, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1468, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1490, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1557, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1502, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 82, \"height\": 81, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 378, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 80, \"height\": 79, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 379, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 378, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 80, \"height\": 83, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 377, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 81, \"height\": 80, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 80, \"height\": 81, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 379, \"height\": 247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 79, \"height\": 81, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 85, \"height\": 82, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 283, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 67, \"height\": 63, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 70, \"height\": 71, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 375, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 374, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 69, \"height\": 68, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1603, \"height\": 835, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 930, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0qgtartsco/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1408, \"height\": 936, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0qgtartsco/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0qgtartsco/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0qgtartsco/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0qgtartsco/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0qgtartsco/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1458, \"height\": 841, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0qgtartsco/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0qgtartsco/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1454, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0qgtartsco/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 215, \"label\": \"Table\"}]"
motivation: VLMs缺乏因果推理与细粒度鉴别能力。
method: 提出反事实视觉语言微调CF-VLM框架。
result: 模型因果推理和对齐能力得到提升。
conclusion: CF-VLM通过反事实训练增强VLMs推理可解释性。
---

## Abstract
Recent advances in vision-language models (VLMs) have greatly improved cross-modal semantic understanding, yet significant limitations remain in fine-grained discrimination and deep causal reasoning tasks. Existing VLMs often rely on superficial statistical correlations, lacking the ability to capture the underlying causal logic between visual and textual content. To address this, we propose the **CounterFactual Vision-Language Fine-tuning Model (CF-VLM)**, a novel framework that enhances the causal reasoning capabilities of VLMs through the targeted use of counterfactual samples. CF-VLM introduces three complementary training objectives: maintaining foundational cross-modal alignment, reinforcing the uniqueness, and stability of factual scene representations against coherent counterfactuals, and sharpening the model’s sensitivity to minimal but critical causal edits. Extensive experiments demonstrate that CF-VLM consistently outperforms strong baselines and state-of-the-art methods on compositional reasoning and generalization benchmarks. Furthermore, it shows promise in mitigating visual hallucinations, indicating improved factual consistency. Our CF-VLM provides a robust foundation for deploying VLMs in high-stakes, real-world scenarios requiring reliable reasoning and interpretability.

---

## 论文详细总结（自动生成）

好的，这是对论文 **CF-VLM: Counterfactual Vision-Language Fine-tuning** 的详细分析与总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**: 当前的视觉-语言模型（VLMs）虽然在跨模态语义理解上取得了巨大进步，但在**细粒度鉴别**和**深层因果推理**任务上存在显著局限。
*   **根本原因**: 现有模型倾向于依赖视觉和文本内容之间的**表面统计相关性**，而不是去捕捉底层的**因果逻辑**。例如，模型可能知道“男人”和“踢球”常常一起出现，但无法理解“不踢”这个微小但关键的因果改变对语义匹配的决定性影响。
*   **研究动机与整体含义**: 为了解决这一问题，本文提出 **CF-VLM（反事实视觉-语言微调）** 框架。其核心思想是通过构建和使用**反事实样本**（counterfactual samples），强制模型关注并推理那些决定图文是否匹配的**因果决策点**，从而让模型不仅知道“是什么”，更理解“为什么”。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

CF-VLM 的核心在于构建多层次的反事实数据，并设计一套针对性强的联合训练目标。

*   **核心思想**: 不满足于让模型区分“匹配”与“不匹配”的图文对，而是要让模型对“为什么匹配/不匹配”产生深刻理解，特别是当差异由细微但因果关键的因素引起时。

*   **关键技术细节与流程**:
    1.  **反事实数据生成**: 从锚点图文对 $(I_a, T_a)$ 出发，通过精确干预构建两类反事实样本：
        *   **单对象属性修改**: 改变核心对象的颜色、类别、姿态、空间关系等。
        *   **关键因果关系调整**: 反转动作-结果关系（如“击中球” -> “没击中球”）。
        *   基于此，构建两种数据结构：
            *   **完整反事实场景对**: 图像和文本都修改，形成逻辑自洽但语义不同的新场景。
            *   **最小编辑反事实图像**: 只对图像施加单一关键编辑，并与原始锚点文本配对，作为困难负样本。

    2.  **三个互补的训练目标（损失函数）**:
        *   **基础跨模态对齐损失 ($L_{align}$)**: 使用标准的对称InfoNCE损失，旨在保留预训练模型对图文对的基本匹配能力，防止灾难性遗忘。
        *   **反事实场景判别损失 ($L_{csd}$)**: 采用铰链损失（Hinge Loss），强制模型将锚点事实场景 $(I_a, T_a)$ 的相似度 $S(I_a, T_a)$，提升到远高于任何完整反事实场景 $(I_{cf_k}, T_{cf_k})$ 的相似度 $S(I_{cf_k}, T_{cf_k})$ 之上。目标是让模型能清晰区分“现实”与“平行现实”。
            *   `Lcsd = 1/K * Σ max(0, S(Icf_k, Tcf_k) - S(Ia, Ta) + m1)`
        *   **细粒度因果判别损失 ($L_{fcd}$)**: 同样使用铰链损失,关注最难的最小编辑反事实样本。对于一个事实文本 $T_a$ 和一组微调图像 $\{I_{cf\_edit\_j}\}$，强制 $S(I_a, T_a)$ 大幅高于其中最相似的 $I_{cf\_edit\_j}$ 的相似度。这迫使模型对单个微小因果编辑带来的语义转变高度敏感。
            *   `Lfcd = max(0, max_j S(Icf_edit_j, Ta) - S(Ia, Ta) + m2)`
    3.  **整体目标**: 三个损失通过超参数加权组合：$L_{CF-VLM} = \alpha \cdot L_{align} + \beta \cdot L_{csd} + \gamma \cdot L_{fcd}$。

### 3. 实验设计：使用了哪些数据集/场景，基准是什么，对比了哪些方法

*   **训练数据集**:
    *   主要：过滤后的 **CC12M**（860万）和 **CC3M**（260万）图文对。
    *   反事实数据：通过 SDXL 和 Qwen2-72B-Instruct 为每个样本动态生成，数据量翻倍。
    *   可选分析：**MSCOCO Captions**（12万对）。

*   **评估基准与场景**:
    *   **组合推理 (Compositional Reasoning)**: 采用 **ConMe**、**ARO** 和 **VL-Checklist** 基准，测试模型在对象、属性和关系被替换时的鉴别能力。
    *   **泛化能力 (Generalization)**: **ImageNet-1k** 上的零样本分类，以及 **MSCOCO** 和 **Flickr30k** 上的零样本图文检索（Recall@K）。
    *   **幻觉缓解 (Hallucination Mitigation)**: 使用 **POPE** 和 **MME** 基准评估模型的物体存在性幻觉和属性级幻觉。

*   **对比方法**:
    *   **CLIP-based SOTA**: 对比了 NegCLIP, **TripletCLIP**, **CE-CLIP+**, **Structure-CLIP**, **COGT-CLIP** 以及零样本和标准微调基线。
    *   **LLM-based VLMs**: 对比了 **InstructBLIP**, **MiniGPT-4**, **LLaVA-1.5**，以及在这些模型上的零样本、标准微调（Std FT）和文本负样本微调（TextNeg FT）基线。

### 4. 资源与算力

*   论文明确指出，所有实验均使用**单块 NVIDIA A100 GPU** 进行训练。
*   训练采用混合精度 **bf16**。
*   优化器为 **AdamW**，峰值学习率 **1×10⁻⁵**（余弦衰减），批次大小 **256**。
*   CC12M数据集训练 **200K 步**，CC3M 数据集训练 **90K 步**。
*   论文在附录G中提供了详尽的训练成本分析，包括ViT-B/32和Qwen2.5-VL-7B模型的单步耗时、显存占用和吞吐量对比。

### 5. 实验数量与充分性：是否客观、公平

*   **实验数量**: 实验设计非常全面，进行了多组实验。
    *   **主实验**：在 CLIP-based 和 LLM-based 两大类模型上，于三个组合推理基准和多个泛化任务上与近10种SOTA或强基线方法对比。
    *   **消融实验**: 包含对反事实样本类型（图像/文本）、三个损失函数组件的单独与组合作用、以及反事实数据数量的影响分析（图4）。
    *   **扩展实验**: 专门评估了模型在幻觉基准上的表现，以证明方法在非直接优化的任务上也有正向迁移能力。
    *   **敏感性与成本分析**: 附录中包含详细的超参数敏感性分析（附录J）和训练成本效率分析（附录G）。
*   **充分性与公平性**: 实验非常充分。
    *   对比基线广泛且具有代表性，涵盖了CLIP和LLM时代的主流方法。
    *   消融实验清晰地证明了每个设计模块的有效性。
    *   所有结果均报告了三次随机种子运行的平均值和标准差，确保了结果的稳定性和可靠性。
    *   CF-VLM与标准微调的对比严格控制了变量（如优化器、学习率、数据量），确保了比较的公平性。

### 6. 论文的主要结论与发现

*   **CF-VLM显著提升了VLMs的组合推理能力**。无论是在轻量级的CLIP模型还是大参数的LLM模型上，CF-VLM在ConMe、ARO、VL-Checklist等多个基准上都大幅超越了标准微调和现有的SOTA方法（如TripletCLIP）。
*   **三个损失组件缺一不可，具有协同增效作用**。消融实验表明，$L_{align}$、$L_{csd}$ 和 $L_{fcd}$ 三者结合才能达到最佳性能，移除任何一个都会导致不同子任务上的性能下降。
*   **反事实监督有助于缓解幻觉**。CF-VLM在未经直接训练的POPE和MME幻觉基准上也表现出提升，尤其是在颜色、位置等属性相关任务上，证明了其微调出的细粒度语义理解能力有助于提升事实一致性。
*   **方法具有良好的泛化性和可迁移性**。CF-VLM在CLIP和LLaVA-1.5, Qwen-VL等多种模型架构上都取得了稳定的性能提升。

### 7. 优点：方法或实验设计上有哪些亮点

*   **创新性强的方法设计**: 首次将“完整反事实场景”和“最小因果编辑”两种类型的反事实数据系统性地结合，并辅以专门设计的多层次损失函数，这是对现有反事实学习范式的重要补充和深化。
*   **清晰且深刻的动机**: 论文准确地指出了VLMs从“相关”到“因果”的关键飞跃，通过“因果决策点”的概念清晰地阐述了其方法为何有效，立意深远。
*   **实验设计极为充分和严谨**: 丰富的对比基线、彻底的消融研究、对幻觉这一非直接目标任务的评估，以及对超参数稳定性和计算成本的详尽分析，使得结论极具说服力。
*   **端到端的实用框架**: CF-VLM提供了一个集数据生成、模型微调于一体的完整方案，可直接应用于多种预训练VLM，具有很强的实用价值。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

*   **数据合成依赖与偏差风险**: 反事实数据的质量和多样性完全依赖于SDXL和Qwen等生成模型，论文也明确指出这些合成数据可能引入固有的偏差或产生不符合物理真实世界的场景，可能限制模型对真实世界复杂变化的理解。
*   **有限的“因果”深度**: 尽管以“因果”冠名，其核心操作仍是识别和对比由“干预”引起的语义变化，更像是一种结构化的因果敏感性学习，而非严格遵循因果推断框架（如do-calculus）的推理。
*   **计算成本的权衡**: 附录G中的分析表明，虽然提升了样本效率，但反事实数据的生成和训练（特别是高比例时）会引入额外的计算开销，训练时间是标准微调的数倍。
*   **实验覆盖局限**: 尽管评估基准很全面，但主要集中在组合理解和幻觉上，缺乏对更复杂的视觉问答（VQA）、视觉常识推理等下游任务的评估，CF-VLM在这些场景下的表现有待验证。

（完）
