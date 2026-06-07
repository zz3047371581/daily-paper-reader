---
title: EEG-Language Pretraining for Highly Label-Efficient Clinical Phenotyping
title_zh: 脑电图-语言预训练用于高标签效率的临床表型分析
authors: "Sam Gijsen, Kerstin Ritter"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yaI2ZYFmeD"
tags: ["query:affective-ai"]
score: 4.0
evidence: 通过多模态预训练对齐脑电图信号与语言，用于临床任务。
tldr: 该论文首次将多模态预训练拓展到脑电图与语言数据，通过时序裁剪和文本分割缓解对齐噪声，在四项临床评估中显著超越仅使用EEG的模型，并首次实现脑电信号与报告的零样本分类和检索。这一成果展示了将大脑活动与语言相连接的潜力，为脑启发式人工智能研究提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1734, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1412, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 834, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1570, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1394, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1765, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 886, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1320, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 867, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 871, \"height\": 1057, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1321, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1572, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1043, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1227, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1225, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1227, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1228, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yai2zyfmed/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1418, \"height\": 723, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 835, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1504, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 725, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 874, \"height\": 639, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 400, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 466, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 836, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 388, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1185, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1500, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 567, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 825, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1110, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1106, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 772, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yai2zyfmed/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1313, \"height\": 877, \"label\": \"Table\"}]"
motivation: 多模态语言模型尚未探索功能脑数据在临床表型分析中的应用，缺乏对EEG和语言的有效对齐。
method: 提出EEG-语言模型，结合多模态对齐、时序裁剪与多示例学习，以缓解无关片段间的错误对齐。
result: 模型在四项临床表型任务上大幅优于单一模态基线，首次实现EEG-报告的零样本分类与检索。
conclusion: 该工作证明了大脑信号与语言联合建模的有效性，为低标签神经数据分析提供了高效方案。
---

## Abstract
Multimodal language modeling has enabled breakthroughs for representation learning, yet remains unexplored in the realm of functional brain data for clinical phenotyping. This paper pioneers EEG-language models (ELMs) trained on clinical reports and 15000 EEGs. We propose to combine multimodal alignment in this novel domain with timeseries cropping and text segmentation, enabling an extension based on multiple instance learning to alleviate misalignment between irrelevant EEG or text segments. Our multimodal models significantly improve over EEG-only models across four clinical evaluations and for the first time enable zero-shot classification as well as retrieval of both neural signals and reports. In sum, these results highlight the potential of ELMs, representing significant progress for clinical applications.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文、以 Markdown 形式，对提供的论文进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：深度学习在医学脑电图（EEG）的临床表型分析（如病理检测）中的应用，长期受限于高质量标注数据的稀缺。现有的自监督学习方法虽能利用无标签数据，但因EEG信号的低信噪比、病理间高相似性以及难以设计有效数据增强等因素，进展缓慢。
*   **研究动机**：受计算机视觉领域通过“视觉-语言”多模态预训练取得突破的启发，该论文旨在探索是否能首次将自然语言（即临床报告）作为监督信号，与EEG数据进行对齐，从而学习到更具临床意义和泛化能力的表征。
*   **整体含义**：该研究开创性地提出了脑电图-语言模型（EEG-Language Models, ELMs），证明了将功能脑数据与医学文本信息联合建模的可行性与巨大潜力。这不仅为高标签效率的临床检测提供了新范式，也首次实现了脑电信号与报告的零样本分类和双向检索，标志着该领域的重要进展。

### 2. 论文提出的方法论

*   **核心思想：子单元对齐（Sub-unit Alignment）**
    *   针对EEG长时序和临床报告多段落的特点，将EEG记录裁剪为多个非重叠时段（Crop），并将报告分割为多个文本段落（Segment）。模型在“裁剪-段落”的子单元级别进行对齐，极大增加了训练样本量。

*   **关键技术：多示例学习对齐（MIL-InfoNCE）**
    *   为缓解EEG片段与报告段落间可能存在的弱相关或无关对齐问题，提出了基于多示例学习（MIL）的扩展对齐策略。
    *   **双向松弛对齐**：不强制每个EEG裁剪只与一个报告段落强对齐，而是同时建模 `P(Report|EEG)` 和 `P(EEG|Report)` 的分布。对于一个报告，从配对EEG中采样多个正样本片段；反之亦然。
    *   **损失函数**：扩展了InfoNCE损失，使其能处理多个正样本对，并在批次内归一化相似度分数。这允许模型在存在噪声对齐的情况下，仍能学习到平均而言更具代表性的跨模态关系。

*   **模型架构变体**
    *   **ELM e,l**：EEG和文本编码器分别通过投影头映射到一个新的共享潜在空间进行对齐（类似CLIP）。
    *   **ELM l**：将EEG嵌入直接映射到冻结、预训练的语言模型的输出空间，并采用复合损失函数（`L_align + L_orth`）以防止潜在空间坍塌。
    *   **ELM-MIL e,l**：在**ELM e,l**基础上应用MIL-InfoNCE损失，是最终的优选模型。

### 3. 实验设计

*   **数据集与任务**
    *   **预训练集**：**TUEG** 数据集，包含15,144份EEG记录及11,785份配对临床报告（经子采样以平衡类别）。
    *   **核心下游任务（临床表型）**：
        *   **TUAB**：记录级别的“正常/异常”二分类任务，并测试零样本分类能力。
        *   **NMT**：外部验证数据集，用于记录级异常分类。
        *   **TUSZ**：5秒级癫痫发作检测（二分类）。
        *   **TUEV**：1秒级临床事件分类（六分类）。
    *   **检索任务**：基于余弦相似度的EEG-报告双向检索能力评估。
*   **基准对比方法**
    *   **监督学习**：端到端训练的分类模型。
    *   **EEG专用自监督方法**：BYOL、VICReg、ContraWR、相对位置（RP）、时间打乱（TS）、对比预测编码（CPC）。
    *   **大型脑电基础模型**：LaBraM（作为参考对象）。
*   **评估设置**：主要通过在不同比例（1%, 10%, 100%）的标注数据上训练一个线性分类器来评估冻结的EEG编码器所学的表征质量。

### 4. 资源与算力

*   **硬件**：模型训练均在单个Nvidia GeForce GTX 3090 或 Tesla V100 GPU上完成，所需内存低于24GB。
*   **训练时长**：对于EEG-语言模型，完成50个epoch的预训练大约需要**9小时**；而EEG-only的自监督模型因需要大量的数据增强，训练时间约为**18小时**。
*   **计算效率**：论文强调，该方法相比需要海量参数（数亿）和数据的EEG基础模型（如369M参数的LaBraM-Huge），其**0.93M参数的编码器**在计算成本和训练时间上具有显著优势。

### 5. 实验数量与充分性

*   **实验数量众多**：
    *   **策略消融**：对不同对齐策略（`ELM e,l` vs `ELM l` vs `ELM-MIL e,l`）、文本源（临床历史、记录描述、用药、诊断解读、LLM总结及其组合）和温度参数 τ 进行了详尽的对比。
    *   **方法对比**：在**4个不同临床任务**上，与**1个监督基线**和**6个EEG-only自监督基线**进行了全面比较，并在不同标注数据比例（1%, 10%, 100%）下进行。
    *   **外部验证**：在出域的**NMT数据集**上验证了模型的泛化能力。
    *   **深入研究**：对模型学习了语言无关子单元对齐效应的分析、对零样本提示词敏感性的测试、以及零样本学习要求（文本投影头、诊断类文本、双向对齐）的分析。
*   **充分性、客观性与公平性**：
    *   **充分**：实验设计非常全面，覆盖了模型设计的各个关键方面（对齐方式、文本源、温度参数），并在多个任务和数据集上进行了验证。
    *   **客观公平**：所有方法（包括基线）均使用**相同的EEG编码器架构和预训练数据集**，确保了对比的公平性。对大型预训练模型（LaBraM）的比较也通过统一用线性探测进行了公平测试。

### 6. 论文的主要结论与发现

*   **性能显著提升**：ELM-MIL e,l 模型在所有临床表型任务中均显著优于EEG-only的自监督方法。在**仅用1%标注数据**时，异常检测（TUAB）的AUROC提升高达**9.7%**，展现出极高的标签效率。
*   **实现零样本能力**：首次实现了基于语言的EEG零样本病理分类，其性能达到、甚至超越了用少量标注数据训练的模型。
*   **出色的检索能力**：模型能够有效地进行EEG信号和临床报告的双向检索，证明其学习到了有语义意义的跨模态对齐。
*   **MIL策略的必要性**：MIL-InfoNCE损失通过处理弱对齐问题，优于标准的InfoNCE损失，尤其是在零样本和检索任务上。
*   **文本内容至关重要**：对诊断解读和总体临床状态的文本进行对齐，比临床病史等不直接描述EEG的文本更有效。
*   **表征的临床语义性**：模型能自动对齐特定临床事件（如癫痫放电）与其对应的文本描述，甚至在没有明确时间标签的情况下实现了**时间选择性对齐**。

### 7. 优点

*   **开创性应用**：首次成功地将视觉-语言模型预训练范式迁移到医学EEG领域，开创了脑电图-语言建模方向。
*   **方法创新性强**：提出的子单元对齐和MIL-InfoNCE策略有效地解决了长时序、多段落、弱对齐的挑战，具有很强的针对性和创新性。
*   **极高的数据效率**：在极端低标签场景下的卓越表现，对临床实践具有重大价值。
*   **多功能性**：单一模型不仅支持多种临床分型任务，还解锁了零样本分类和跨模态检索等新能力。
*   **计算高效**：该方法能以较小的模型规模和较低的计算成本达到甚至超越大型预训练模型的效果，降低了应用门槛。
*   **实验严谨全面**：与多种基线进行了公平对比，并通过多任务、多数据集、外部验证和详尽的消融实验验证了方法的优越性和鲁棒性。

### 8. 不足与局限

*   **数据集规模与来源限制**：预训练数据仅来自公开的TUEG数据集，样本量（~1.5万）远小于视觉-语言领域，且数据来源相对单一，可能限制了模型性能的进一步提升。
*   **文本处理偏差**：依赖于LLM生成报告摘要进行训练数据平衡，LLM本身的偏差可能被引入模型。
*   **对非文本描述事件的敏感性**：模型在检测“伪影”和“眼动”等临床报告中较少描述的事件上性能下降，表明其对文本中不存在的事件类型不敏感。
*   **缺乏可解释性量化**：虽然展示了时间选择性对齐的可视化，但未能提供如通道级归因等更深入的可解释性分析。
*   **未探索模型缩放**：受计算资源限制，未进行模型参数量缩放的相关实验，这是一个待探索的未来方向。
*   **应用限制**：目前仅支持20通道的TCP蒙太奇，且排除了过长的记录，普适性有待验证。

（完）
