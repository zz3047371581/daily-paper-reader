---
title: "AVERE: Improving Audiovisual Emotion Reasoning with Preference Optimization"
title_zh: AVERE：利用偏好优化改进视听情感推理
authors: "Ashutosh Chaubey, Jiacheng Pang, Maksim Siniukov, Mohammad Soleymani"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=td682AAuPr"
tags: ["query:affective-ai"]
score: 10.0
evidence: 视听情感推理偏好优化
tldr: 针对多模态大语言模型在视听情感推理中存在的虚假关联和幻觉问题，本文构建了EmoReAlM基准以量化评估线索—情感关联、幻觉及模态一致性，并提出AVEm-DPO偏好优化技术，通过构造偏好对对齐模型响应与视听输入，显著提升了情感推理的鲁棒性。实验表明，该方法有效抑制了无关线索的影响，增强了模型对情感相关线索的关注，为构建社会智能体提供了关键技术支持。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 多模态大语言模型在视听情感推理中存在虚假关联和幻觉。
method: 构建EmoReAlM基准并提出AVEm-DPO偏好优化技术。
result: 有效减少了虚假关联，提升了情感推理准确性。
conclusion: 为构建社会智能体提供了更鲁棒的情感推理方法。
---

## Abstract
Emotion understanding is essential for building socially intelligent agents. Although recent multimodal large language models (MLLMs) have shown strong performance on this task, two key challenges remain: (i) spurious associations between emotions and irrelevant audiovisual cues and (ii) hallucination of audiovisual cues driven by text priors in the language model backbone. To quantify and understand these issues, we introduce **EmoReAlM**, a benchmark designed to evaluate MLLMs for cue–emotion associations, hallucinations and modality agreement. We then propose **AVEm-DPO**, a preference optimization technique that aligns model responses with both audiovisual inputs and emotion-centric queries. Specifically, we construct preferences over (i) responses exhibiting spurious associations or hallucinations and (ii) audiovisual input pairs guided by textual prompts. We also include a regularization term that penalizes reliance on text priors, thereby mitigating modality-specific cue hallucinations. Experimental results on DFEW, RAVDESS and EMER demonstrate that our method significantly improves the performance of the reference baseline models (6-19\% of relative performance) in zero-shot settings. By providing both a rigorous benchmark and a robust optimization framework, this work enables principled evaluation and improvement of MLLMs for emotion understanding and social AI.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：当前多模态大语言模型（MLLMs）在视听情感推理任务中表现虽强，但存在两类根本缺陷：
  - **虚假关联**：模型倾向于将情感状态与不相关的视听线索（如光照、背景噪声）错误绑定。
  - **幻觉**：模型依赖语言模型内部的文本先验，生成在视听输入中并不存在的线索（如“看到微笑”而实际视频中并无该表情）。
- **整体含义**：这两个问题严重阻碍了 MLLMs 在社会智能体中的可靠应用。论文旨在通过构建专用评测基准与偏好优化方法，量化并缓解这些缺陷，从而推动更鲁棒的情感理解系统。

### 2. 论文提出的方法论
- **核心思想**：通过偏好优化（Preference Optimization）技术，将 MLLM 的生成响应与真实视听输入对齐，抑制幻觉和虚假关联。
- **关键技术细节**：
  - **EmoReAlM 基准**：用于系统评估 MLLMs 在“线索-情感关联（cue–emotion associations）”“幻觉（hallucinations）”和“模态一致性（modality agreement）”三个维度上的表现。
  - **AVEm-DPO（Audiovisual Emotion Direct Preference Optimization）**：一种偏好优化方法，其构造包括：
    - **偏好对构造**：将模型生成的含虚假关联或幻觉的响应作为“被拒绝样本”，将更忠实于视听输入的响应作为“偏好样本”；同时利用文本引导的视听输入对构建比较样本。
    - **正则项**：引入惩罚项以抑制模型对文本先验的依赖，减少仅由语言模型引发的模态特异性线索幻觉。
- **算法流程（文字概括）**：  
  在给定视听输入和情感查询后，模型采样多个响应，经人工或自动评估标记出“好响应”（无幻觉/无虚假关联）和“坏响应”，构成偏好对；随后通过 DPO 目标函数优化模型，使模型更倾向于生成偏好响应，并加入正则化项避免文本偏置。

### 3. 实验设计
- **数据集**：三个广泛使用的视听情感数据集：**DFEW**（动态面部表情）、**RAVDESS**（多模态情感言语与歌唱）和**EMER**（多模态情感识别）。
- **基准（Benchmark）**：自建的 **EmoReAlM**，专门量化线索-情感关联、幻觉和模态一致性。
- **对比/参考方法**：文中未列出具体对比方法名，但提到在零样本（zero-shot）设置下与**参考基线模型（reference baseline models）**对比，表明该方法作为优化手段应用于现有 MLLM 之上。

### 4. 资源与算力
- 提供的文本中**未明确提及** GPU 型号、数量、训练时长等细节。由于摘要和元数据篇幅有限，具体硬件与训练开销信息缺省。

### 5. 实验数量与充分性
- **实验组数**：至少覆盖 3 个数据集的零样本评估，以及基于 EmoReAlM 的诊断性实验。文中提及相对性能提升在 6‑19% 之间，暗示进行了多个基线模型与消融实验。
- **充分性**：从提供信息看，实验覆盖多种情感数据集，评估维度系统（虚假关联、幻觉、模态一致性），方法通过构建偏好对和正则化进行多角度验证，实验设计相对充分、客观。但未呈现代码或具体消融细节，无法进一步评判。

### 6. 主要结论与发现
- AVEm-DPO 能有效减少 MLLM 对无关视听线索的虚假关联。
- 该方法显著降低了由文本先验导致的模态特异性幻觉。
- 在零样本情感推理任务中，优化后的模型相对于基线获得 6~19% 的相对性能提升。
- EmoReAlM 基准为评测 MLLM 的社会情感推理可靠性提供了标准化工具。

### 7. 优点（方法或实验设计亮点）
- **问题驱动**：精准定位虚假关联与幻觉这两大关键瓶颈。
- **基准创新**：EmoReAlM 是对音频、视频、文本多模态情感模型进行精细化评估的稀缺资源。
- **方法优雅**：将偏好优化（DPO）引入视听情感领域，通过构造负例与正则项直接对齐多模态输入，无需额外标注大规模人类偏好数据（或利用自动/自生成方式）。
- **实验验证多维**：在 3 个不同数据集、多个评估维度上验证，展示较好的泛化性。

### 8. 不足与局限
- **元信息缺失**：无法获知训练资源、具体模型架构细节、偏好对的质量控制方式。
- **未提供对比基线名称**：难以评估方法与当前最先进（SOTA）MLLM 的绝对差距。
- **偏好对构造依赖**：若采用自动生成“坏响应”或规则化筛选，可能引入新的偏置；未说明人工参与程度。
- **数据集局限**：DFEW、RAVDESS、EMER 多为受控/实验室环境数据，实际场景的分布外泛化能力待验证。
- **模态覆盖**：论文主要针对视听输入，未涉及文本-情感推理中可能存在的其他幻觉类型。

（完）
