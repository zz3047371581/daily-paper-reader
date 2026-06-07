---
title: "Surrogate Prompt Learning: Towards Efficient and Diverse Prompt Learning for Vision-Language Models"
title_zh: 替代提示学习：面向视觉-语言模型的高效多样提示学习
authors: "Liangchen Liu, Nannan Wang, Xi Yang, Xinbo Gao, Tongliang Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zjG9GRG462"
tags: ["query:affective-ai"]
score: 6.0
evidence: 提出替代提示学习，为视觉-语言模型高效生成多样提示，增强跨模态对齐。
tldr: 现有视觉-语言模型的多样提示学习计算开销巨大，本文提出替代提示学习框架SurPL，不直接学习众多文本提示，而是通过替代模型直接生成多样的文本特征，在保持多样性的同时大幅降低计算成本，为视觉-语言任务提供高效参数微调方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zjg9grg462/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zjg9grg462/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1750, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zjg9grg462/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 812, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zjg9grg462/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zjg9grg462/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1387, \"height\": 2041, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 815, \"height\": 592, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 800, \"height\": 503, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1701, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 875, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1666, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 808, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1591, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1540, \"height\": 670, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1646, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1718, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1728, \"height\": 523, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1710, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1547, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1576, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1662, \"height\": 704, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1703, \"height\": 1214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zjg9grg462/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1636, \"height\": 600, \"label\": \"Table\"}]"
motivation: 多样提示学习能全面刻画视觉概念但计算资源需求巨大，效率问题尚未解决。
method: 构建SurPL框架，通过一个轻量替代模型直接从图片上下文生成期望的文本特征，替代多样提示的直接学习。
result: SurPL在多个基准上以更低的计算开销达到了与多样提示学习方法相当甚至更优的性能。
conclusion: 该框架解决了多样提示学习的效率瓶颈，为视觉-语言模型的大规模应用提供了可能。
---

## Abstract
Prompt learning is a cutting-edge parameter-efficient fine-tuning technique for pre-trained vision-language models (VLMs). Instead of learning a single text prompt, recent works have revealed that learning diverse text prompts can effectively boost the performances on downstream tasks, as the diverse prompted text features can comprehensively depict the visual concepts from different perspectives. However, diverse prompt learning demands enormous computational resources. This efficiency issue still remains unexplored. To achieve efficient and diverse prompt learning, this paper proposes a novel \textbf{Surrogate Prompt Learning (SurPL)} framework. Instead of learning diverse text prompts, SurPL directly generates the desired prompted text features via a lightweight \textbf{Surrogate Feature Generator (SFG)}, thereby avoiding the complex gradient computation procedure of conventional diverse prompt learning. Concretely, based on a basic prompted text feature, SFG can directly and efficiently generate diverse prompted features according to different pre-defined conditional signals. Extensive experiments indicate the effectiveness of the surrogate prompted text features, and show compelling performances and efficiency of SurPL on various benchmarks.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以中文、Markdown 格式，对提供的论文《Surrogate Prompt Learning: Towards Efficient and Diverse Prompt Learning for Vision-Language Models》进行结构化、深入且客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究背景**：在大模型时代，针对预训练视觉-语言模型（VLMs，如CLIP）进行下游任务微调时，**提示学习** 已成为一种前沿的参数高效微调技术。其核心思想是学习一些额外的提示词元，为文本编码器注入任务特定知识。
*   **核心问题**：近期研究表明，学习**多样的文本提示**（如实例依赖提示、细粒度提示）能显著提升VLM在下游任务的表现，因为它们能从不同角度全面描述视觉概念。然而，这种多样提示学习的**计算效率问题异常严峻**。
*   **效率瓶颈**：传统的多样提示学习需要为每个样本（实例依赖）或每个局部特征（细粒度）反复通过整个文本编码器进行反向传播计算梯度，导致GPU显存和训练时间消耗呈倍数级增长，从 `O(M)` 增加到 `O(B × M)` 或 `O(Z × M)`。
*   **整体目标与含义**：本文旨在解决“如何在保持甚至超越多样提示学习性能的同时，大幅提升其计算效率”这一未被充分探索的问题。其核心贡献是提出了一个名为**替代提示学习（Surrogate Prompt Learning）** 的统一框架，该框架不直接学习多样提示，而是“生成”提示特征，从而绕开巨大的算力开销。

### 2. 论文提出的方法论

论文的核心思想是**绕开对多样文本提示的“学习-通过编码器”过程，直接“生成”它们所产生的文本特征**。这通过一个名为**替代特征生成器** 的轻量模块实现。

*   **核心模块：替代特征生成器**
    *   **结构**：SFG本质上是一个轻量化的**交叉注意力模块**。它通过降低隐藏层维度（如减半）来保持参数高效。
    *   **输入**：
        1.  **Query（查询）**：一个**基础提示文本特征**（由任意单提示学习基线模型获得）。
        2.  **Key/Value（键/值）**：**预定义的条件信号**。这些信号非常灵活，可以是先验知识（如视觉实例特征），也可以是可学习的词元。
    *   **工作流程**：SFG通过交叉注意力机制，让基础特征根据条件信号的指引，**一次性生成对应的、具有特定知识（如实例级或细粒度级）的多样化文本特征**。这避免了为每个条件信号都从头学习一个文本提示并让其通过整个文本编码器。
    *   **公式示意**：生成过程可概括为 `h = MLP(softmax(wα^T/√d_k)α)`，其中 `h` 是生成的替代特征，`w` 是基础特征，`α` 是条件信号。

*   **两种具体的替代提示学习实现**：
    1.  **实例依赖替代提示学习**：
        *   **条件信号**：直接使用**视觉编码器输出的视觉特征**作为条件信号。
        *   **效果**：为每一张输入图片动态生成一个独特的替代文本特征 `hID`，使其捕获了该实例的特定信息。
    2.  **细粒度替代提示学习**：
        *   **条件信号**：使用**一组可学习的词元**作为条件信号，自动捕获细粒度线索。
        *   **效果**：生成一组（`Z` 个）替代细粒度文本特征 `hFG`，与图像中从粗到细的局部视觉区域进行对齐。

*   **优化与推理**：
    *   **损失函数**：总损失 `L = L_GI_CE + L_ID_CE + L_FG_CE`。其中，`L_GI_CE` 是全量不变损失，包括基础提示的交叉熵损失和一个防止遗忘零样本能力的正则项（`|w_GI - w_zs|` 和 `|f_hat - f_hat_zs|`）。
    *   **泛化性增强**：为提高模型在新类别上的泛化能力，提出了**SurPL-G**版本，采用**锐度感知最小化** 优化策略，通过惩罚损失函数的陡峭度来寻找更平坦的损失最小值点。
    *   **推理**：最终预测概率由全局不变、实例依赖和细粒度三种特征分别预测的结果取平均得到。

### 3. 实验设计

*   **数据集与场景**：
    *   **数据集**：在**15个公开图像分类数据集**上进行了评估，涵盖通用物体（ImageNet, Caltech101）、细粒度分类（Aircraft, Cars, Flowers, Food, Pets）、场景（SUN397）、纹理（DTD）、卫星图（EuroSAT）和动作识别（UCF101）等。
    *   **实验场景**：设置了四种主流的泛化性测试场景：
        1.  **少样本学习**：在少量（16-shot）样本上训练并在同类别测试集评估。
        2.  **基类到新类泛化**：训练和测试的类别不重叠，考验模型对新概念的泛化能力。
        3.  **跨数据集泛化**：在ImageNet上训练，直接在其他10个不同的数据集上测试。
        4.  **跨域泛化**：在ImageNet上训练，在其领域偏移版本（ImageNetV2, -Sketch, -A, -R）上测试。
*   **基准对比方法**：与多种先进方法进行了全面比较，包括：
    *   **单提示学习**：CoOp, MaPLe, PSRC, LLaMP等。
    *   **多样提示学习**：CoCoOp, PLOT++, ALIGN, GalLoP等。
    *   **其他参数高效微调**：CLIP-Adapter, Tip-Adapter, CLIP-LoRA等。
    *   **泛化性方法**：ProGrad, KgCoOp, DePT, TCP等。

### 4. 资源与算力

*   **硬件**：所有实验均在**单个NVIDIA RTX 3090 (24GB) GPU**上进行。
*   **效率对比数据**：论文通过表格明确指出训练/测试时间和显存占用。
    *   在包含100个类的Aircraft数据集上，训练时间为 **2分36秒**（vs. GalLoP的5分52秒、ALIGN的31分23秒），显存为 **7.37GB**（vs. GalLoP的18.77GB、ALIGN的23.37GB）。
    *   在包含1000个类的ImageNet上，SurPL仅占 **23.80GB** 显存，训练用时 **8分03秒**，而其他多样提示学习方法（CoCoOp, PLOT++, ALIGN, GalLoP）均显示**显存溢出**，无法在4块RTX3090上运行。SurPL的表现接近甚至优于单提示学习方法。

### 5. 实验数量与充分性

*   **实验数量充足**：论文进行了**逾15组不同维度的大型实验**，覆盖了效率分析、消融研究、四种主流泛化场景下的性能对比、与多种微调范式的比较等。
*   **实验充分性高**：
    *   **效率分析**：通过对比多种方法的显存、训练/测试时间和精度，直接证明了SurPL在效率和性能上的双赢。
    *   **消融实验**：系统地验证了全局不变、实例依赖和细粒度三个组件各自带来的增益，证明了它们的互补性（平均精度从基准的82.92%逐步提升至85.12%）。
    *   **公平性**：实验设置严格遵循先前工作（如PSRC），使用标准基准（如CLIP ViT-B/16），每个结果基于**三个随机种子**的平均值，确保了比较的客观与公正。

### 6. 论文的主要结论与发现

*   **有效性**：替代特征生成器（SFG）生成的“替代文本特征” **足够有效，可以替代** 传统方法中通过复杂计算学习到的多样化文本特征。
*   **高效性**：SurPL框架成功地将多样提示学习的**计算复杂度从 `O(B × M)` 或 `O(Z × M)` 拉低至与单提示学习相当的 `O(M)` 级别**，解决了巨大资源开销的痛点。
*   **优越性**：通过简单结合实例依赖和细粒度的概念，SurPL在**少样本学习**（平均准确率85.12%）和**基类到新类泛化**（HM 81.03%）等多种任务上，**取得了超越现有最先进方法的性能**。
*   **兼容性**：SurPL具有良好适应性，可集成到CoOp、MaPLe、PSRC等不同的单提示学习基线上，并均带来显著提升。

### 7. 优点

*   **创新性高**：从一个全新视角——**“直接生成特征而非学习提示”**——解决了多样提示学习的效率瓶颈，而非简单优化提示学习策略本身。
*   **框架统一且灵活**：SFG通过灵活的“条件信号”设计，能够很自然地整合实例依赖、细粒度等不同类型的多样化需求，并可通过调整信号适配更多场景。
*   **实用价值强**：大幅降低的GPU显存占用和训练时间，使得原本近乎无法在大数据集上运行的多样提示学习方法具备了**实际可部署性**，对于工业界和研究社区都有重要意义。
*   **分析深入**：通过可视化（注意力热图、特征相似度）等手段，不仅展示了“是什么”，还分析了“为什么”有效，增强了结论的可信度。

### 8. 不足与局限

*   **参数效率的考量**：论文主要关注**计算效率**（时间/显存），但SFG模块本身引入了**额外参数量**（1.641M），虽然仍小于一些方法（如MaPLe），但比基线模型（0.061M）有一定增加。论文仅在附录表格中提及，正文未深入讨论，可能被视为一个trade-off。
*   **SFG结构简单**：论文承认SFG是一个相对“过时的”交叉注意力模块，未来可探索更高效、高性能的生成器结构。
*   **泛化能力依赖额外优化**：SurPL原始模型（ERM优化）的泛化性不足，需要借助SAM优化策略（SurPL-G）才能与他人匹敌，这意味着性能提升部分源于优化技巧，而不仅是模型结构自身。
*   **多样性类型有限**：目前仅探索了实例依赖和细粒度两种主要的多样提示学习范式，该框架能否轻易拓展到其他更复杂的多样性类型（如空间、尺度多样性）存疑。

（完）
