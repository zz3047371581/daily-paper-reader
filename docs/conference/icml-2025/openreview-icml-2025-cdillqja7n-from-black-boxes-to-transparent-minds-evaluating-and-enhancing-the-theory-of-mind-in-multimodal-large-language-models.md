---
title: "From Black Boxes to Transparent Minds: Evaluating and Enhancing the Theory of Mind in Multimodal Large Language Models"
title_zh: 从黑箱到透明心智：评估与增强多模态大模型的心智理论
authors: "Xinyang Li, Siqi Liu, Bochao Zou, Jiansheng Chen, Huimin Ma"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=CDillQjA7N"
tags: ["query:affective-ai"]
score: 5.0
evidence: 评估和增强多模态大模型的心智理论，与情感智力相关
tldr: 为探究多模态大语言模型的心智理论（ToM）能力，本文构建了包含多视角感知与信念测试的GridToM数据集，并采用可解释性方法分析其内部机制。研究发现现有模型在复杂ToM任务上存在局限，而特定注意力头的干预可提升表现。该工作为评测和增强LLM的社会情感智力提供了新基准与方法，有助于构建更具情感理解能力的智能体。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1755, \"height\": 1151, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1771, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1775, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1599, \"height\": 1975, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1413, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1412, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1398, \"height\": 920, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1220, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1219, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1222, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1226, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 990, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 992, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1024, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cdillqja7n/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1075, \"height\": 945, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-cdillqja7n/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 1045, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cdillqja7n/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1761, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cdillqja7n/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 666, \"height\": 332, \"label\": \"Table\"}]"
motivation: 现有机器ToM评估多针对单模态且缺乏可解释性，难以洞察多模态模型的社会认知机制。
method: 构建多模态ToM数据集GridToM，并采用基于内部机制的可解释性方法分析MLLMs的心智推理过程。
result: 发现了模型在不同信念任务上的能力差异，通过注意力干预可提升ToM表现。
conclusion: 可解释性评估有助于理解并增强MLLM的社会认知能力，为情感智能体发展提供参考。
---

## Abstract
As large language models evolve, there is growing anticipation that they will emulate human-like Theory of Mind (ToM) to assist with routine tasks. However, existing methods for evaluating machine ToM focus primarily on unimodal models and largely treat these models as black boxes, lacking an interpretative exploration of their internal mechanisms. In response, this study adopts an approach based on internal mechanisms to provide an interpretability-driven assessment of ToM in multimodal large language models (MLLMs). Specifically, we first construct a multimodal ToM test dataset, GridToM, which incorporates diverse belief testing tasks and perceptual information from multiple perspectives. Next, our analysis shows that attention heads in multimodal large models can distinguish cognitive information across perspectives, providing evidence of ToM capabilities. Furthermore, we present a lightweight, training-free approach that significantly enhances the model’s exhibited ToM by adjusting in the direction of the attention head.

---

## 论文详细总结（自动生成）

好的，以下是对该论文《From Black Boxes to Transparent Minds: Evaluating and Enhancing the Theory of Mind in Multimodal Large Language Models》的详细中文总结。

### 1. 论文的核心问题与整体含义

*   **研究背景**：心智理论（Theory of Mind, ToM）是人类社会认知和情感理解的基础，指推断自我和他人心理状态的能力。随着大语言模型（LLMs）的发展，人们期望其在人机交互中展现出类似人类的心智能力。
*   **核心问题**：
    *   **评估方法的局限**：现有的机器ToM评估主要存在两大不足。其一，大多聚焦于单一模态（文本或视频），忽略了人类整合多模态信息进行心智推理的本质。其二，普遍采用“黑箱”方法，仅通过问答任务的准确率来判断模型是否具备ToM，缺乏对模型内部机制的可解释性探索，导致评估结果容易受到幻觉等其他因素的干扰。
*   **整体含义**：本研究旨在通过构建多模态数据集，并结合对模型内部表征的可解释性分析，来更深入地评估和增强多模态大语言模型（MLLMs）的ToM能力，从“只看输出结果”转向“理解内部思考过程”。

### 2. 论文提出的方法论

*   **核心思想**：与其依赖问答准确率，不如直接探究MLLM内部是否形成了能区分不同智能体视角和信念的表征，并通过干预这些内部表征来增强其ToM能力。
*   **关键技术细节**：
    *   **注意力特征提取**：将多模态输入（视频和文本）输入MLLM后，提取每一层、每一个注意力头在处理完输入后的激活状态，作为模型对当前输入信息的内部表征。
    *   **探针（Probing）分析**：为识别哪些注意力头在处理多视角信念信息，论文采用逻辑回归训练一个线性分类器（探针）。该探针的任务是根据注意力头激活状态，区分输入数据对应的信念标签（正确/错误、全知视角/主角视角）。探针准确率高，则表明该注意力头的激活编码了可线性解码的ToM相关信息。
    *   **干预（Intervention）机制**：选定对ToM敏感的注意力头后，在模型推理过程中，沿着探针发现的、能将“正确/错误信念”分开的决策边界方向，对相应的注意力头激活施加一个偏移量。具体公式如下，其中 `α` 控制干预强度，`σ` 是沿目标方向激活的标准差，`θ` 是干预方向：
        `Tl+1 = Tl + Σ (Attn_hl(P_hl · Tl) + α · σ_hl · θ_hl) · W_ol`
    *   **方案特点**：该方法是一种轻量级的、无需训练的增强方式，仅通过在推理时调整特定注意力头的激活方向，即可影响模型最终的信念判断。

### 3. 实验设计

*   **数据集/场景**：
    *   **主要数据集：GridToM**。这是一个在2D网格世界中生成的多模态ToM数据集，包含1296个视频-文本对，覆盖了真信念（TB）和假信念（FB）任务，以及一阶、二阶信念推理。其特点是提供了每个智能体的完备视角信息，弥补了真实世界数据集的不足。
    *   **泛化验证数据集：MMToM-QA**。一个基于室内真实环境的视频问答数据集，用于验证探针方法的泛化能力。
*   **基准（Benchmark）对比**：
    *   **对比对象**：论文对比了多种主流MLLMs和LLMs，包括GPT-4o、Doubao-1.5-vision-pro、DeepSeek-vl2-small、LLaVA-Next-Video-7B、Qwen2-VL-7B、Llama-3.3-70B 等。
    *   **对比条件**：在GridToM上进行了多模态（视频+文本）、纯视频、纯文本三种输入设置下的基准测试，并以人类表现为上限。
*   **方法对比**：主要对比了应用注意力干预前后（`+α`）LLaVA-Next-Video-7B和Qwen2-VL-7B两个模型在ToM任务上的准确率变化。

### 4. 资源与算力

*   论文中**未明确提及**执行干预实验或训练探针所使用的GPU型号、数量或具体计算时长。文中提到使用了`LLaVA-Next-Video-7B`和`Qwen2-VL-7B`等需要一定算力推理的模型，但未给出具体的资源开销细节。

### 5. 实验数量与充分性

*   **实验数量**：实验设计较为丰富，主要包括：
    *   **1套基准测试实验**：对6种MLLMs和6种LLMs，在3种模态设置（多模态、纯视频、纯文本）下，分别测试了TB、FB和Both条件下的准确率。
    *   **2组探针分析实验**：在GridToM数据集上，对2个模型（LLaVA-Next-Video, Qwen2-VL）的一阶和二阶信念任务进行了注意力头探针分析；在MMToM-QA数据集上进行了泛化性验证。
    *   **2组干预实验**：在GridToM数据集上，对2个模型施加干预，并提供了详细的超参数（`K` 和 `α`）分析。
    *   **1组消融/分析实验**：分析了干预方向（主角视角 vs. 全知视角）和不同超参数组合对干预效果的影响。
*   **充分性与客观性**：
    *   **充分性**：实验覆盖了多个主流模型、多模态输入条件、不同信念任务，并进行了内部表征分析和干预增强，整体较为充分。
    *   **客观公平性**：评估采用零样本设定，统一抽取固定帧作为视频输入，并将模型温度设为0，确保了公平对比。人类基准测试也提供了上限参考。干预方法的有效性通过超参数敏感性分析进行了验证，表明其不是简单的参数调优。

### 6. 论文的主要结论与发现

*   **现有模型表现不平衡**：前沿MLLMs在GridToM上表现出严重的能力不平衡，例如在假信念（FB）任务上能得满分，却在真信念（TB）任务上得分极低，表现出对数据模式的过度敏感而非真正的推理能力。
*   **内部表征的证据**：探针分析揭示了MLLMs内部的注意力头确实能够以线性可分的方式编码不同视角的信念信息，这为模型具备某种形式的ToM内部机制提供了证据，即使其最终输出可能不正确。
*   **干预的有效性**：通过沿特定方向干预这些敏感的注意力头，可以显著、一致地提升模型在多模态条件下的一阶和二阶信念任务（包括TB和FB）的准确率，证明了该可解释性方法的实用价值。

### 7. 优点

*   **创新的数据集**：GridToM数据集通过简化的2D网格世界，提供了完整且可控的多智能体视角和信念信息，巧妙解决了真实数据集中感知信息不明确的问题，专注于评估核心ToM推理。
*   **可解释性驱动的评估范式**：从“黑箱”式的问答评估，转向分析模型内部表征的“透明心智”范式，为了解MLLM的认知过程提供了更深层次的见解，避免了仅凭输出错误就否定模型能力的片面性。
*   **轻量且有效的增强方法**：提出的注意力干预方法无需重新训练或微调模型，即可有效提升ToM表现，具有良好的实用性和效率。

### 8. 不足与局限

*   **任务覆盖有限**：GridToM目前仅覆盖了ATOMs框架中的一阶、二阶信念任务，而ToM理论包含更广泛的任务类型（如情感推理、欺骗检测等）。
*   **模型验证范围**：由于代码访问限制，干预方法的验证仅在LLaVA和Qwen两个MLLM上进行，其在不同架构模型上的普适性有待进一步证实。
*   **环境简化与泛化差距**：2D网格世界高度简化，与真实世界的复杂社会交互场景存在显著差距，模型在GridToM上学到的能力能否迁移至现实应用尚不明确。
*   **干预依赖性**：该方法依赖于探针分类器的准确性，需要部分标注数据来确定敏感注意力头和干预方向，不能完全无监督地应用。

（完）
