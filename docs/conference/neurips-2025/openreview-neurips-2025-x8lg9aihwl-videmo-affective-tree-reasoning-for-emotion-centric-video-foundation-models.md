---
title: "VidEmo: Affective-Tree Reasoning for Emotion-Centric Video Foundation Models"
title_zh: VidEmo：面向情感中心视频基础模型的情感树推理
authors: "Zhicheng Zhang, Weicheng Wang, Yongjie Zhu, Wenyu Qin, Pengfei Wan, Di ZHANG, Jufeng Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=x8lg9aihwl"
tags: ["query:affective-ai"]
score: 10.0
evidence: 提出情感线索引导的推理框架用于视频情感理解
tldr: 视频情感理解面临情绪开放集、动态变化和上下文依赖的挑战。本文提出 VidEmo 系列视频情感基础模型，采用情感线索引导的树状推理框架，分阶段进行基本属性感知、表情分析和高层情感理解。模型通过链式思维训练和奖励机制产生可解释的情感推理。实验表明，VidEmo 在多个视频情感基准上达到领先水平，并能提供合理的情感推理链条。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 742, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 82, \"height\": 82, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1375, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 686, \"height\": 179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 698, \"height\": 180, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1417, \"height\": 149, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1407, \"height\": 141, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 685, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1443, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1447, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1320, \"height\": 806, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1319, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1410, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1220, \"height\": 1738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1223, \"height\": 217, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1212, \"height\": 213, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1226, \"height\": 1163, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1229, \"height\": 1932, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1220, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1222, \"height\": 1161, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1230, \"height\": 1311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1227, \"height\": 1501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1209, \"height\": 121, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1198, \"height\": 169, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1437, \"height\": 251, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1435, \"height\": 147, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1437, \"height\": 1374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1452, \"height\": 153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1416, \"height\": 145, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1417, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1410, \"height\": 146, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1423, \"height\": 150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1415, \"height\": 150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1423, \"height\": 152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1420, \"height\": 150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1421, \"height\": 149, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1405, \"height\": 148, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1420, \"height\": 145, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x8lg9aihwl/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1432, \"height\": 1133, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 788, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 842, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 662, \"height\": 564, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 553, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 906, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 1582, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1133, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1097, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1094, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1432, \"height\": 1539, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x8lg9aihwl/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1446, \"height\": 506, \"label\": \"Table\"}]"
motivation: 视频情感具有开放集、动态和上下文依赖等特性，现有方法难以提供合理理解。
method: 构建情感线索指引的树状推理框架，分阶段进行属性感知、表达分析和高层情感理解。
result: VidEmo 在多个视频情感基准上取得领先，并能输出可解释的情感推理链。
conclusion: 该工作为视频情感分析提供了新的基础模型范式，有望推动情感 AI 的发展。
---

## Abstract
Understanding and predicting emotions from videos has gathered significant attention in recent studies, driven by advancements in video large language models (VideoLLMs). While advanced methods have made progress in video emotion analysis, the intrinsic nature of emotions—characterized by their open-set, dynamic, and context-dependent properties—poses challenge in understanding complex and evolving emotional states with reasonable rationale. To tackle these challenges, we propose a novel affective cues-guided reasoning framework that unifies fundamental attribute perception, expression analysis, and high-level emotional understanding in a stage-wise manner. At the core of our approach is a family of video emotion foundation models (VidEmo), specifically designed for emotion reasoning and instruction-following. These models undergo a two-stage tuning process: first, curriculum emotion learning for injecting emotion knowledge, followed by affective-tree reinforcement learning for emotion reasoning. Moreover, we establish a foundational data infrastructure and introduce a emotion-centric fine-grained dataset (Emo-CFG) consisting of 2.1M diverse instruction-based samples. Emo-CFG includes explainable emotional question-answering, fine-grained captions, and associated rationales, providing essential resources for advancing emotion understanding tasks. Experimental results demonstrate that our approach achieves competitive performance, setting a new milestone across 15 face perception tasks.

---

## 论文详细总结（自动生成）

好的，以下是对论文《VidEmo: Affective-Tree Reasoning for Emotion-Centric Video Foundation Models》的结构化中文总结。

### 1. 核心问题与研究动机

*   **核心问题**：视频情感理解面临三大核心挑战：**情绪的开放性**、**动态演变性**，以及**对上下文的高度依赖性**。现有视频大语言模型虽取得进展，但难以对复杂、变化的情感状态提供准确、可解释的推理。
*   **研究动机**：当前最先进模型在细粒度情感分析上表现不佳，揭示了性能差距。因此，需要一种能整合面部属性、表达与高层情感，并能给出基于线索的、可解释的推理框架，以提升视频情感的认知理解能力。

### 2. 方法论

本工作核心贡献是提出了**VidEmo**系列视频情感基础模型和一个名为**Emo-CFG**的大规模情感中心数据集。其方法框架围绕“情感线索引导的树状推理”展开，具体包括：

*   **情感树推理框架**: 将情感理解分解为**属性感知 → 表达式分析 → 情感推理**的阶段性递进流程，模拟从基础线索到高层语义的推理路径。
*   **两阶段模型训练**:
    1.  **预训练阶段 — 课程情感学习**：分三个阶段逐步向基础模型注入情感知识，从简单的属性识别，到复杂的表达式分析，最后到高层情感理解，难度递增。
    2.  **后训练阶段 — 基于GRPO的混合情感树奖励**：
        *   采用**群组相对策略优化**进行强化学习。
        *   引入**混合奖励机制**：包括基于规则的问答奖励（准确率、F1值）、基于模型的描述奖励，以及核心的**基于情感树的细粒度描述奖励**。
        *   **情感树奖励**：将模型生成的描述解析为`属性 → 表达式 → 情感`的三层情感树，并与真实标注树通过**树编辑距离**比较。奖励值\( R = \exp(-\lambda \cdot \text{Edit}(T_{gt}, T_{pred})) \)，越低奖励越高，以此鼓励模型生成结构上可解释的、符合人类推理模式的情感描述。
*   **推理阶段**: 采用分层搜索策略，在属性、表达式、情感三个层级分别采样多个候选输出，由奖励模型筛选最佳结果，自底向上构成推理轨迹。
*   **Emo-CFG数据集**: 构建了一个包含210万多样本的数据集，通过**因果情感推理**策略（利用先进模型分阶段生成标签）和**委员会投票验证**机制，保证了数据的多样性、可靠性和可解释性。

### 3. 实验设计

*   **主要基准测试**: 在自建的 **Emo-CFG基准**上进行测试，涵盖**15个面部感知任务**，分为三大类：属性感知（6个闭集 + 12个开集任务）、表达式分析（9个任务）和高层情感理解（6个任务）。
*   **对比方法**: 对比了18种领先模型，分为两类：
    *   **闭源API模型**: Gemini 2.0, Claude 3.5 Sonnet, GPT-4o等。
    *   **开源视频大语言模型**: Qwen2.5-VL, InternVL2.5, VideoLLaMA3等，参数规模从1B到8B不等。
*   **下游任务验证**: 在DFEW和MAFW等动态面部表情识别数据集上进行微调和评估。
*   **数据集质量验证**: 通过与CelebV-Text数据集的人工对比研究，评估生成数据的精确性、合理性和互补性。
*   **消融实验**: 对课程情感学习、情感树奖励和情感推理三个核心组件进行组件级的消融分析。

### 4. 资源与算力

*   论文**未明确说明**具体使用的GPU型号、数量及总训练时长。
*   文中仅提及了训练超参数，如预训练批次大小为1024（3个epoch），后训练批次大小为128（1个epoch），以及使用AdamW优化器和余弦学习率调度策略。

### 5. 实验数量与充分性

*   **实验组数**: 实验规模庞大，在Emo-CFG基准上对比了18个模型的40项指标，并进行了下游任务评估、数据集质量用户研究和组件消融实验。
*   **充分性与公平性**:
    *   **充分性**: 实验覆盖了属性、表达、情感的全栈任务，并包含闭源/开源、不同参数规模的SOTA模型，验证全面。消融实验清晰展示了各组件的贡献。
    *   **客观性与公平性**: 使用统一的评估基准和指标进行对比，具有客观性。但对闭源模型的评估可能受到其训练数据不透明的影响，存在一定的不公平性风险。论文在推理阶段对比SOTA时特意禁用了“情感推理”（ER）策略，保证了单次响应下的公平比较。

### 6. 主要结论与发现

*   **性能领先**: VidEmo在所有15个任务上均超越所有对比的开源和闭源视频大语言模型，尤其在1-3B和7-8B规模上，较最强基线平均提升超过16.3%和12.4%。
*   **组件有效性**: 课程情感学习、情感树奖励和情感推理三个设计均对性能有积极贡献，组合使用时效果最佳。后训练和推理阶段能持续提升模型的情感推理能力。
*   **数据质量**: 构建的Emo-CFG数据集在精确性、合理性和互补性上均显著优于现有最大的人工标注视频情感数据集，验证了其数据管道的有效性。
*   **可解释性**: 通过情感树结构，VidEmo能够为其情感判断提供从底层属性到高层语义的合理推理链条，实现了可解释的细粒度情感理解。

### 7. 优点

*   **框架创新性**: 提出的“属性-表达-情感”树状推理框架，为情感分析提供了结构化的、可解释的新范式。
*   **训练策略独特**: 结合“课程学习”与“基于GRPO的树编辑距离奖励”的两阶段训练方法，有效将情感知识和推理能力注入模型。
*   **数据基础坚实**: 构建的Emo-CFG数据集规模大、标注细、经过质量验证，为情感计算领域提供了宝贵的基础设施。
*   **性能表现卓越**: 在广泛的任务和模型对比中取得了全面领先的性能，验证了方法的有效性。

### 8. 不足与局限

*   **内容幻觉风险**: 与大多数视频大语言模型一样，VidEmo可能生成不符合事实的描述或情感不一致的叙述。
*   **模态单一性**: 研究当前仅聚焦于视觉模态。情感本质上是由音频、文本等多模态线索共同表达的，融合这些模态有望进一步增强推理能力。
*   **泛化性风险**: 尽管在多个测试集上表现优异，但模型和数据集主要围绕面部视频构建，其在非面部或抽象场景下的泛化能力尚未得到充分验证。
*   **算力开销不明确**: 因其未披露详细的算力消耗，难以评估其训练成本的可复现性。

（完）
