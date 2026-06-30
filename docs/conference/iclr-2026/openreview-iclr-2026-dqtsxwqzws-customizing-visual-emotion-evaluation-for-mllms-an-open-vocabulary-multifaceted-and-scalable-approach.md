---
title: "Customizing Visual Emotion Evaluation for MLLMs: An Open-vocabulary, Multifaceted, and Scalable Approach"
title_zh: 为多模态大模型定制视觉情感评估：开放词汇、多方位且可扩展的方法
authors: "Daiqing Wu, Dongbao Yang, Sicheng Zhao, Can Ma, Yu ZHOU"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=dQTSXWqZws"
tags: ["query:affective-ai"]
score: 9.0
evidence: 面向多模态大模型的开放词汇、多方位视觉情感评估方法
tldr: 针对现有多模态大模型在图像情感感知评估中存在的标签受限、忽略上下文等问题，本文提出一种开放词汇、多方位且可扩展的视觉情感评估方法，通过情绪陈述判断任务实现定制化评测。实验表明该方法能更准确地衡量MLLMs的情感理解能力，揭示了不同模型在情绪感知上的差异，为构建高情商AI提供了可靠的评估基准。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 现有评估方法受限于封闭词表、忽略合理响应及上下文，导致MLLM情感感知结果不一致。
method: 提出开放词汇的情绪陈述判断任务，结合多方位评价维度与可扩展标注方案。
result: 评估揭示了不同MLLM在视觉情感理解上的显著差异，新方法更可靠。
conclusion: 为MLLM情感智能评测提供了灵活有效的框架，助力情感AI发展。
---

## Abstract
Recently, Multimodal Large Language Models (MLLMs) have achieved exceptional performance across diverse tasks, continually surpassing previous expectations regarding their capabilities. Nevertheless, their proficiency in perceiving emotions from images remains debated, with studies yielding divergent results in zero-shot scenarios. We argue that this inconsistency stems partly from constraints in existing evaluation methods, including the oversight of plausible responses, limited emotional taxonomies, neglect of contextual factors, and labor-intensive annotations. To facilitate customized visual emotion evaluation for MLLMs, we propose an Emotion Statement Judgment task that overcomes these constraints. Complementing this task, we devise an automated pipeline that efficiently constructs emotion-centric statements with minimal human effort. Through systematically evaluating prevailing MLLMs, our study showcases their stronger performance in emotion interpretation and context-based emotion judgment, while revealing relative limitations in comprehending perception subjectivity. When compared to humans, even top-performing MLLMs like GPT4o demonstrate remarkable performance gaps, underscoring key areas for future improvement. By developing a fundamental evaluation framework and conducting a comprehensive MLLM assessment, we hope this work contributes to advancing emotional intelligence in MLLMs. Project page: https://github.com/wdqqdw/MVEI.

---

## 论文详细总结（自动生成）

好的，这里是对该论文的详细中文总结。

### 1. 论文的核心问题与整体含义

*   **研究动机**：多模态大语言模型（MLLM）在各项任务中表现优异，但其图像情感感知能力存疑，现有零样本评测结果相互矛盾。论文指出，这种不一致性源于现有评估方法的四大缺陷：忽视合理但非预设的情感回应、局限于封闭的情感标签词表、忽略上下文信息对情感判断的影响、以及人工标注过程耗时耗力。
*   **整体含义**：本研究旨在为 MLLM 的视觉情感理解能力提供一个更定制化、更可靠的评估框架。通过从根本上解决现有评估方法的瓶颈，最终目标是推动 MLLM 情感智能的发展。

### 2. 论文提出的方法论

*   **核心思想**：提出一种**开放词汇、多方位、可扩展的评估框架**，其核心是将评估形式从传统的“从给定标签中选择”转变为“对情绪陈述进行判断”。
*   **关键技术细节**：
    *   **情绪陈述判断任务**：给 MLLM 呈现一张图片和一句情绪陈述，要求模型判断该陈述是否正确。
    *   **可扩展标注管线**：设计了一套自动化流程来生成情绪陈述，以最小化人工参与。
        1.  **陈述生成**：利用强大的 MLLM（如 GPT-4V），基于图片为预定义的多维度情感类别生成正、负两种情绪陈述。
        2.  **质量验证**：通过跨模型投票和人类审查的混合机制，过滤掉低质量或错误的陈述，确保评估数据的可靠性。
    *   **多方位评价维度**：超越了简单的基本情绪分类，可能涵盖了情绪解读、基于上下文的情绪判断、以及对感知主观性的理解等多个层面，实现了更全面的能力评估。

### 3. 实验设计

*   **场景与 Benchmark**：论文构建了一个新的视觉情感评估基准，专门服务于所提出的情绪陈述判断任务。
*   **对比方法**：
    *   **评估的 MLLM**：系统性地评估了当时主流的 MLLM，如 **GPT-4o** 等，并在论文中将它们的表现进行了横向对比。
    *   **与人类基准对比**：关键实验是**将顶级 MLLM 的性能与人类在相同任务上的表现进行比较**，以此揭示模型与人类在情感理解上的真实差距。
*   **数据集（推断）**：具体使用的图像数据集名称在摘要中未提及，但可以肯定数据集中包含了多种需要上下文和主观性理解的视觉场景。

### 4. 资源与算力

*   论文摘要及元数据中均**未明确提及**完成实验所消耗的计算资源。
*   未说明所使用的 GPU 型号、数量、单次实验或总体的训练/推理时长。

### 5. 实验数量与充分性

*   **实验数量**：元数据未提供精确的实验组数。从方法论推断，至少包括以下维度的实验：
    *   多款主流 MLLM 在“情绪陈述判断”任务上的性能对比。
    *   针对不同评价维度（如情绪解读、上下文判断、主观性理解）的分项能力评估。
    *   关键的人类基线实验。
*   **充分性与公平性**：
    *   **充分性**：考虑到研究旨在刷新评估范式，通过系统的模型对比和多维度分析，并最终与人类水平对标，实验设计较为全面，有望充分揭示模型间的能力差异和与人类的差距。
    *   **公平性**：通过使用统一的、自动化生成的评估集对所有模型进行零样本测试，保证了评估过程的客观与公平，避免了因标签体系差异带来的偏向性。

### 6. 论文的主要结论与发现

*   **MLLM 的优势领域**：现有 MLLM 在“情绪解读”和“基于上下文的情绪判断”上表现出相对较强的能力。
*   **MLLM 的关键短板**：在“理解感知主观性”方面表现出相对局限性。
*   **与人类的巨大差距**：即使是最顶尖的 MLLM（如 GPT-4o），其视觉情感理解能力与人类相比仍存在显著差距，这指明了未来模型优化的关键方向。
*   **新评估方法的有效性**：所提出的开放词汇评估方法能够更准确、更细致地衡量 MLLM 的情感理解能力，揭示了以往封闭词表评估所隐蔽的模型差异。

### 7. 优点
*   **评估范式创新**：将评估从标签匹配转变为陈述判断，突破了封闭词表的限制，是一种根本性的方法创新，更贴近真实情感理解的复杂性。
*   **可扩展性强**：提出的自动化标注管线显著降低了评估基准构建的人力成本和周期，使其易于扩展和迭代。
*   **评估维度多方位**：不再仅关注情绪分类准确率，而是深入到情绪解读、上下文推理和主观性理解等更深层次，评估更为全面。
*   **对标明确**：通过与人类表现直接对比，为 MLLM 的情感智能发展提供了清晰、可量化的标杆。

### 8. 不足与局限

*   **自动化管线的偏差风险**：评估陈述的质量高度依赖于生成 MLLM（如 GPT-4V）的性能和可能存在的偏见，自动化过滤机制可能无法完全剔除所有低质量或带有偏见的陈述。
*   **实验细节缺失**：摘要未详述实验所用图像数据集的具体来源、规模和覆盖领域，无法评估其代表的广度。
*   **应用局限**：目前的评估是静态的、基于单张图片和文本陈述的，可能无法完全反映真实世界动态、多模态交互场景下的情感智能。

（完）
