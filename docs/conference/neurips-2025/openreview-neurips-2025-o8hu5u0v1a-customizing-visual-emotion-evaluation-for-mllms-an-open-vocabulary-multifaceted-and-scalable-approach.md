---
title: "Customizing Visual Emotion Evaluation for MLLMs: An Open-vocabulary, Multifaceted, and Scalable Approach"
title_zh: 定制化多模态大模型的情感视觉评估：一种开放词汇、多面性且可扩展的方法
authors: "Daiqing Wu, Dongbao Yang, Sicheng Zhao, Can Ma, Yu ZHOU"
date: 2025-05-10
pdf: "https://openreview.net/pdf?id=O8Hu5u0v1A"
tags: ["query:affective-ai"]
score: 10.0
evidence: 通过开放词汇多面任务定制化评估多模态大模型的视觉情感感知
tldr: 多模态大模型的视觉情感感知能力评定不一致，源于以往方法忽视合理回复、情感分类有限、忽略背景因素且标注昂贵。本文提出情感陈述判断任务，突破这些束缚，实现开放词汇、多面性和可扩展的定制化评估。通过新基准测试，该方法能更精细地区分不同模型的情感理解差异。该工作为衡量多模态模型情感智能提供了标准化且可定制的评测工具，推动情感AI发展。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 917, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 1021, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1441, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1440, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-o8hu5u0v1a/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1440, \"height\": 400, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hu5u0v1a/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 878, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hu5u0v1a/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 516, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hu5u0v1a/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1310, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hu5u0v1a/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1311, \"height\": 515, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hu5u0v1a/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 1240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hu5u0v1a/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 876, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-o8hu5u0v1a/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 1120, \"label\": \"Table\"}]"
motivation: 现有评估方法导致多模态大模型视觉情感感知能力结论矛盾，亟需改进。
method: 提出情感陈述判断任务，实现开放词汇、多面性、可扩展的视觉情感评估。
result: 新评估方法能更细致地反映MLLM的情感理解差异。
conclusion: 情感陈述判断为多模态模型情感能力评估提供了可靠且可定制的解决方案。
---

## Abstract
Recently, Multimodal Large Language Models (MLLMs) have achieved exceptional performance across diverse tasks, continually surpassing previous expectations regarding their capabilities. Nevertheless, their proficiency in perceiving emotions from images remains debated, with studies yielding divergent results in zero-shot scenarios. We argue that this inconsistency stems partly from constraints in existing evaluation methods, including the oversight of plausible responses, limited emotional taxonomies, neglect of extra-visual factors, and labor-intensive annotations. To facilitate customized visual emotion evaluation for MLLMs, we propose an Emotion Statement Judgment task that overcomes these constraints. Complementing this task, we devise an automated pipeline that efficiently constructs emotion-centric statements with minimal human effort. Through systematically evaluating prevailing MLLMs, our study showcases their stronger performance in emotion interpretation and context-based emotion judgment, while revealing relative limitations in direct determination of sentiment polarity and personalized emotion prediction. When compared to humans, even top-performing MLLMs like GPT-4o demonstrate remarkable performance gaps, underscoring key areas for future improvement. By developing a fundamental evaluation framework and conducting a comprehensive MLLM assessment, we hope this work contributes to advancing emotional intelligence in MLLMs. Codes and data will be released.

---

## 论文详细总结（自动生成）

# 定制化多模态大模型的情感视觉评估：一种开放词汇、多面性且可扩展的方法

### 1. 论文的核心问题与整体含义
*   **研究动机与背景**
    *   多模态大模型在诸多任务上表现卓越，但其从图像中感知情感的能力仍存在争议，各项零样本研究结果相悖。
    *   核心问题在于现有评估方法存在四大局限：
        1.  **忽视合理性回复**：采用固定标准答案，排除了情感感知固有的主观性带来的其他合理回复。
        2.  **情感分类法有限**：多数基准数据集仅包含少数几个情绪类别，无法捕捉细微的情感差异。
        3.  **忽略图像外因素**：评估仅关注图像自身属性，忽视了场景背景、观察者身份与性格等外部语境因素的影响。
        4.  **标注劳动密集**：依赖多数投票机制确保标签可靠性，成本高昂且限制数据集的可扩展性。
*   **整体含义**
    *   本文旨在为多模态大模型定制更为精准、全面的视觉情感评估框架，通过设计新任务和自动化构建流程，系统性甄别现有多模态大模型在情感理解上的优势与不足，推动其情感智能的发展。

### 2. 论文提出的方法论
*   **核心思想：双组件解决方案**
    1.  **情感陈述判断任务**：
        *   将传统的开放式问答改为二元判断，要求模型对给定图像判断一条“情感中心陈述”的正确性，以缓解歧义并提升评估的广度和深度。
    2.  **INSETS（智能视觉情感标注与陈述构建器）管道**：
        *   一个自动化、可扩展的标注与数据集构建流程，仅需最少人力介入。
*   **关键技术细节与算法流程**
    1.  **开放词汇情感标注阶段**：
        *   **情感提取**：利用多种多模态大模型，从数据集中所有图像提取潜在的开放词汇情感词，汇集成情感池。
        *   **情感过滤与归类**：过滤掉不适合作为情感描述的词，并利用GPT-4将剩下的开放词汇归属到**Parrott层级情感模型**（包含6种主情绪、25种次情绪和113种三级情绪）中的最相近三级情绪类别，并由人类专家优化，生成**基于Parrott的开放词汇层级模型**。
        *   **集成投票标注**：基于POM模型，通过对多个多模态大模型的提取结果进行**集成多数投票**，为每张图像选择可靠且多元的开放词汇情感标签。
    2.  **情感陈述构建阶段**：
        *   首先为每个情感标签生成三类**原型陈述**：情感解读（原因）、场景背景（故事）和感知主观性（角色）。
        *   基于情感标签和原型陈述，从四个维度构建正确与错误的**情感中心陈述**：
            *   **情感极性**：依据POM模型判断图像的整体情感倾向，提出关于图像是纯积极、纯消极还是混合情感的陈述。
            *   **情感解读**：通过匹配或错配情感标签与情感起因描述来构陈述。错配策略包括跨图像（视觉相似情绪异、情绪相似视觉异）和图像内（交换正负极性标签的解释）干扰。
            *   **场景背景**：通过匹配或交换图像内的背景故事，或执行**极性翻转**操作（将情感标签替换为相反极性的随机情绪）来构陈述。
            *   **感知主观性**：设定角色对两种情绪的倾向性，通过将倾向设置为“偏好情绪大于非偏好情绪”的正序为正确陈述，反之为错误陈述。

### 3. 实验设计
*   **使用的数据集与基准**
    *   **图像来源**：选择高质量、带有丰富属性的**EmoSet**数据集。
    *   **构建的基准**：
        *   **INSETS-462K**：基于EmoSet的17,716张图像，构建了462,369个情感中心陈述。该数据集未经人工验证，但准确率预计超过85%。
        *   **INSETS-3K**：从INSETS-462K中抽取3,164个图像-陈述对进行人工验证，最终保留3,086个高质量对，形成精细化基准。该基准覆盖了丰富的情绪分布，如喜悦（40.3%）、悲伤（17.7%）等。
*   **任务与对比方法**
    *   **评估任务**：情感陈述判断任务，模型需判断给定图像-陈述对的陈述是否正确。
    *   **对比的多模态大模型**：本文评估了广泛的开源与闭源模型，包括**LLaVa-1.6、Mantis、mPLUG-Owl3、Idefics3、Phi-3.5-Vision、Qwen2-VL、Llama-3.2-Vision、Molmo、InternVL2.5、BLIP2、InstructBLIP、Otter、DeepSeek-VL、Paligemma、MiniCPM、Qwen2.5-VL、GPT4o-mini和GPT4o**。
    *   **与人类对比**：在INSETS-3K的子集上对比了顶尖多模态大模型与人类参与者的表现。

### 4. 资源与算力
*   **计算资源**：文中明确指出，所有实验均在 **NVIDIA GeForce RTX 4090 GPUs** 上进行。
*   **模型规模限制**：由于硬件计算限制，评估主要聚焦于参数量**100亿以下**的多模态大模型，排除了可能具备更强性能的更大规模开源模型。

### 5. 实验数量与充分性
*   **实验数量**：
    *   评估了**19款**多模态大模型。
    *   在两个规模的基准上进行测试：大规模基准INSETS-462K和人工精标基准INSETS-3K。
    *   进行了四维任务评测（情感极性、情感解读、场景背景、感知主观性）及与**25名人类参与者**的比较。
*   **充分性、客观性与公平性**：
    *   **充分性**：实验覆盖面广，模型多样，对比维度丰富，实验设计充分。
    *   **客观性与公平性**：
        *   为确保评估结果的稳健性，每个图像-陈述对被查询**三次**，取最频繁回答作为最终决策。
        *   引入了**正例比率**和**弃权比率**作为诊断指标，以识别和缓解模型回复偏差对准确率评估有效性的影响，增强了公平性。
        *   通过与人类表现对比，建立了当前模型的性能上限参考，使评估结论更为客观。

### 6. 论文的主要结论与发现
*   **性能分化**：较新的多模态大模型在通用视觉任务进步的驱动下，情感感知能力整体优于早期模型，但**没有单一模型在所有情感维度上达到最优**。
*   **优势领域**：多模态大模型在基于上下文的**情感判断和情感解读**方面表现较强。
*   **薄弱环节**：模型在**直接判断情感极性（基本的情绪基调）和感知主观性（个性化情感预测）**方面存在相对的局限性。
*   **人机差距**：即使是性能最强的GPT-4o，也与人类准确率存在显著差距（人类平均91.6%，人类最佳95.2%，GPT-4o 79.0%）。这表明多模态大模型的情感智能仍有巨大提升空间，特别是在感知个体差异和理解情绪基础正负倾向上。

### 7. 优点
*   **创新性任务设计**：提出的情感陈述判断任务，将主观评估转化为客观二元判断，有效解决了合理回答被误判的问题，具有开创性。
*   **自动化与可扩展性**：INSETS管道通过集成多个多模态大模型和精细设计的策略，实现了标签和陈述的自动化生成，极大降低了人力成本，使构建大规模、高质量的情感基准成为可能。
*   **多维度评估框架**：从情感极性、解读、背景、主观性四个维度进行综合评估，提供了比传统单一维度分类更全面、更细致的分析视角。
*   **开放词汇标签**：克服了传统固定情感分类的局限，能够捕捉更丰富和细微的情感表达。

### 8. 不足与局限
*   **模型覆盖范围有限**：受算力所限，评估主要针对100亿参数以下的模型，未包含更大规模的先进开源多模态大模型，结论的代表性有待扩展。
*   **语言单一**：当前基准为单语（英语）构建，虽声称可迁移，但缺乏多语言支持，存在文化偏见风险。
*   **基准噪声**：大规模基准INSETS-462K缺乏人工验证，不可避免地包含噪声和不准确性，可能影响评估结果的细微度。
*   **推理策略探索不足**：评估中未系统性地探索诸如上下文学习、思维链提示等高级推理策略，可能未能充分挖掘模型的全部情感推理潜力。

（完）
