---
title: "Overcoming Multi-step Complexity in Multimodal Theory-of-Mind Reasoning: A Scalable Bayesian Planner"
title_zh: 克服多模态心理理论推理的多步复杂性：一种可扩展的贝叶斯规划器
authors: "Chunhui Zhang, Zhongyu Ouyang, Kwonjoon Lee, Nakul Agarwal, Sean Dae Houlihan, Soroush Vosoughi, Shao-Yuan Lo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2dz6psiiA0"
tags: ["query:affective-ai"]
score: 7.0
evidence: 为多模态心理理论推理开发可扩展的贝叶斯规划器，这是智能体情感智能的核心组成。
tldr: 针对现有多模态心理理论（ToM）方法在多步推理中可扩展性差的问题，提出一种可扩展贝叶斯规划器，通过逐步贝叶斯更新分解复杂度，并利用弱到强控制提升概率估计精度，实现了在复杂多模态环境下的高效心理状态推断，为构建具有情感社交智能的智能体奠定了基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2dz6psiia0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 806, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2dz6psiia0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2dz6psiia0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 677, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2dz6psiia0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 903, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2dz6psiia0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1774, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2dz6psiia0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 845, \"height\": 334, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1340, \"height\": 913, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1508, \"height\": 947, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1514, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1766, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 888, \"height\": 150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 586, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 897, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1160, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1426, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1772, \"height\": 1201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 861, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 888, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2dz6psiia0/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 890, \"height\": 293, \"label\": \"Table\"}]"
motivation: 现有多模态ToM计算方法随任务复杂性增加而难以泛化，存在多步规划困境。
method: 提出可扩展贝叶斯ToM规划器，将推理分解为逐步贝叶斯更新，并用小语言模型提炼似然估计。
result: 所提方法在多模态环境中成功扩展了ToM推理，性能优于现有结构化方法。
conclusion: 该方法为通用社交智能提供了可扩展的多模态推理框架，可望用于情感智能体。
---

## Abstract
Theory-of-mind (ToM) enables humans to infer mental states—such as beliefs, desires, and intentions—forming the foundation of social cognition. Existing computational ToM methods rely on structured workflows with ToM-specific priors or deep model fine-tuning but struggle with scalability in multimodal environments. They remain trapped within the gravitational pull of multi-step planning complexity, failing to generalize as task demands increase. To overcome these limitations, we propose a scalable Bayesian ToM planner. It breaks down ToM complexity into stepwise Bayesian updates. Meanwhile, weak-to-strong control specializes smaller LMs to refine ToM-specific likelihood estimation, transferring their ToM reasoning behavior to larger LMs (7B to 405B) for social and world knowledge integration. This synergistic approach enables scalability, aligning large-model inference with human mental states with Bayesian principles. Extensive experiments demonstrate a 4.6% improvement in accuracy over state-of-the-art methods on multimodal ToM benchmarks, including unseen scenarios, establishing a new standard for modeling human mental states in complex environments.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以 Markdown 格式，对提供的论文进行结构化、深入且客观的总结。

### 1. 论文的核心问题与整体含义

*   **核心问题：** 论文旨在解决多模态心理理论推理中的核心挑战——**多步推理的复杂性与可扩展性之间的矛盾**。
    *   **背景：** 心理理论是人工智能实现深层社会交互的关键。现有方法主要分为两类：1）依赖结构化流程和特定先验的贝叶斯模型；2）对深度模型（尤其是语言模型，LM）进行微调的端到端方法。
    *   **痛点：** 这两种方法在多模态环境（需整合视觉、文本、上下文）中都面临**可扩展性障碍**。如图1所示，随着规划步数增加，小型LM或仅靠推理时扩展（如思维链、o1系统）的性能会迅速下降，陷入“多步规划复杂性的引力井”，无法泛化。
*   **整体含义：** 论文提出，**解决这一问题的关键在于将结构化推理框架与大规模模型的丰富世界知识相结合**，并通过一种“弱到强”的机制，在不直接微调大模型的前提下，将其强大的泛化能力引导至特定的ToM任务上。

### 2. 论文提出的方法论

*   **核心思想：** 提出一个**可扩展的贝叶斯ToM规划器**，它通过两大策略协同工作：1）利用贝叶斯逆规划（BIP）将ToM推理分解为模块化的逐步贝叶斯更新；2）通过**“弱到强”控制**机制，让小型LM的ToM特定行为来引导大型LM的推理，实现推理能力的可扩展性。
*   **关键技术细节与流程：**
    *   **问题形式化：** 将智能体行为建模为部分可观察马尔可夫决策过程，并通过贝叶斯逆规划来推断其目标 `g` 和信念 `b`。后验概率 `P(g, b_t | s_{1:t}, a_{1:t-1})` 正比于时间步长内的策略 `π(a_τ | g, b_τ)` 与信念更新 `P(b_τ | b_{τ-1}, s_τ)` 的乘积。
    *   **“弱到强”控制机制：** 这是方法的核心，分为两个阶段。
        *   **后训练阶段（小型LM，`π_E`）：** 对一个**小规模LM**（如7B/8B）进行后训练，使其成为ToM任务的政策模型。训练分为两步：1）**指令微调**，让它学会根据状态、信念、目标来预测动作；2）**偏好优化**，使用修改后的DPO损失函数，使其在有效动作（`a+`）和无效动作（`a-`）之间做出区分，从而强化ToM特定的推理行为。
        *   **推理阶段（大型LM，`π_L`）：** 在推理时，使用一个未经ToM特定后训练的**大规模LM**（如70B/405B）作为政策模型。它的输出分布 `π̄_L` 通过一个公式进行动态调整：
            `π̄_L = (1/Z) * π_L * (π_E / π_N) `
            其中，`π_N` 是原始未后训练的小型LM。该公式的直观含义是：**利用已后训练小型LM (`π_E`) 相对于其原始状态 (`π_N`) 的行为变化（比率 `π_E/π_N`）来重定向大型LM (`π_L`) 的推理方向**。其理论基础由**定理1**支撑，该定理证明，小型LM学习到的行为调整量 `Δs` 近似于大型LM交叉熵损失的梯度，使得经过弱到强控制的模型近似于直接后训练的大型模型，且两者的KL散度有理论上限。

### 3. 实验设计

*   **数据集/场景：**
    *   **后训练：** 使用 **MMToM** 数据集，该数据集包含从虚拟家庭模拟器 VirtualHome 中程序化生成的1000个视频，每个视频都标注了状态、目标、信念和动作。
    *   **评估基准：**
        *   **MMToM-QA:** 包含134个视频和600个问题，分为**信念推断**（如真/误信念、长期追踪）和**目标推断**（基于不同信念状态）共7个子任务。
        *   **未见过场景的泛化性测试：** 构建了5个新主题的场景数据集（如安徒生童话、古埃及、外太空），以评估模型的跨域迁移能力。
        *   **补充评估：** 在更侧重于真实世界社交互动的 **MuMA-ToM** 基准上也进行了评测。
*   **对比方法：**
    *   **纯文本模型:** GPT-4, GPT-3.5, Llama2-7B, OpenAI-o3-mini, DeepSeek-R1-671B, SimToM (w/ GPT-4), SymbolicToM (w/ GPT-4)。
    *   **多模态模型:** GPT-4V, Video-Llama2, LLaVA, BIPALM (结合GPT-J-6B或Llama2-7B)。
    *   **人类表现:** 作为性能的黄金标准。

### 4. 资源与算力

*   **小型LM后训练：** 使用**单张NVIDIA H100 GPU**, 在BF16精度下进行。以Llama3.1-8B为例，批大小为16，学习率5e-5，训练3个epoch，显存消耗低于60GB，训练耗时约8小时。
*   **大型LM推理：** 只进行推理，不做后训练。在8B+70B配置下处理600个问题，耗时约14-15.5分钟（每问1.4-1.55秒），与未引导的70B模型推理时间相当，显示弱到强控制的额外计算开销很小。
*   **对比实验：** 进行了全量微调和LoRA微调的对比实验，这些实验使用了**8张NVIDIA A100 80GB GPU**。

### 5. 实验数量与充分性

实验设计**非常充分、客观且公平**。

*   **多维度评估：** 不仅评估了整体和子任务准确率，还分别测试了视觉、文本、多模态三种输入模式下的性能。
*   **大规模消融研究：**
    *   **强组件扩展实验（表2）：** 系统对比了从7B到405B的Llama系列模型在零样本、直接后训练、以及弱到强控制下的表现，验证了模型规模与性能的正相关性。
    *   **弱组件缩减实验（表3）：** 将8B控制器缩小到4B（宽度和深度缩减两种），证明小型控制器依然有效且具有成本效益。
    *   **泛化性实验（表4）：** 在5个未见过的新场景中测试了方法的迁移能力，证明了其鲁棒性。
    *   **机制性分析（图3、图4、表5、表14）：** 深入分析了弱到强控制在推理过程中的重定向效果、后训练如何影响概念层级的似然估计、以及单纯组合逻辑的不足，从机制层面验证了方法的有效性。
*   **基准对比的全面性：** 包含了文本、多模态、以及专门的ToM增强方法（如SimToM, BIPALM）和最新的顶级模型（如GPT-4, DeepSeek-R1）。

### 6. 论文的主要结论与发现

1.  **可扩展性得到验证：** 论文成功证明了通过"弱到强"控制，能将小型LM的特定推理行为有效传递给大型LM（最高至405B），使其在复杂多步ToM任务中保持高准确率，解决了小型模型及仅靠推理时扩展方法的性能瓶颈。
2.  **性能达到新标杆：** 所提方法在多模态MMToM-QA基准上取得了**81.3%的准确率，超越现有最优方法4.6个百分点**，接近人类表现。
3.  **双重优势融合：** 该框架巧妙地融合了大型LM的广阔世界知识（有利于信念推断）和通过后训练获得的环境动态适应能力（有利于目标推断），克服了前人方法的“跷跷板效应”。
4.  **鲁棒的泛化能力：** 即使在从未见过的不同主题场景中，该方法也能保持稳定且优越的性能，展现了强大的域迁移能力。
5.  **高效与实用：** 避免了直接微调大模型的巨大成本，通过仅微调小型模型并结合高效推理机制，达到了甚至超越了直接微调大模型的效果，具有很高的实用性。

### 7. 优点

*   **方法论创新：** "弱到强"控制机制是一个巧妙的创新，为解决大模型在特定任务上微调成本高、灾难性遗忘等问题提供了新思路。
*   **理论与实践结合：** 不仅有扎实的贝叶斯理论框架作为支撑，还通过KL散度分析提供了理论解释（定理1），并结合了最新的认知科学思想。
*   **实验严谨且全面：** 实验设计极其周密，从基础性能到泛化能力，从宏观测评到微观机制分析，多层次、多角度地验证了方法的有效性和可解释性。
*   **资源友好与可应用性强：** 方法论的高度可扩展性和相对低的资源消耗（仅需单张H100 GPU进行后训练），使其具备极高的实用价值和应用前景。

### 8. 不足与局限

*   **前提依赖：** 方法高度依赖准确的**多模态符号化表示**，视频和文本解析器的性能会直接影响整体推理效果，这在实际复杂视觉场景中可能是一个潜在瓶颈。
*   **控制器的局限性：** 小型LM的行为若训练不充分或存在偏差，可能会对大型LM产生误导。论文缺乏对小型LM控制器质量下限的讨论。
*   **动态环境复杂度：** 测试环境虽然比传统数据集更动态，但与真实世界无约束的社会交互相比仍有一定差距。现实中的目标和信念空间几乎是无限的，更具挑战性。
*   **假设的明确性：** 方法聚焦于推断明确给出的、有限的目标/信念假设对（`g1` vs `g2`），即让模型从给定的A或B选项中做选择，属于判别任务，与开放式的心理状态生成任务仍有区别。

（完）
