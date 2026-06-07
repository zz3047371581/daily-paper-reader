---
title: On the Value of Cross-Modal Misalignment in Multimodal Representation Learning
title_zh: 论跨模态错配在多模态表示学习中的价值
authors: "Yichao Cai, Yuhang Liu, Erdun Gao, Tianjiao Jiang, Zhen Zhang, Anton van den Hengel, Javen Qinfeng Shi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3KtPujOw5z"
tags: ["query:affective-ai"]
score: 7.0
evidence: 提供跨模态错配处理的形式化分析与实践指南
tldr: 在图像-文本多模态对比学习中，错配现象普遍存在，但既有研究分为缓解错配和利用错配两派。本文通过潜变量模型对错配进行理论建模，调和了这两种观点，并基于实验提出一套实践方案，指导何时该修正错配、何时可利用错配来增强表示学习。该框架不仅深化了对错配的理论理解，也为多模态框架设计提供了原则性建议。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 584, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 513, \"height\": 181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 665, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 515, \"height\": 181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 634, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1410, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1421, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1448, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1446, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1444, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1448, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1444, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1454, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1441, \"height\": 1212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 663, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 666, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 664, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 638, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1444, \"height\": 2038, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ktpujow5z/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1470, \"height\": 2426, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 1934, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1128, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1133, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1456, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1458, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 529, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1192, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1299, \"height\": 762, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 662, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1440, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1455, \"height\": 1693, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 1035, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ktpujow5z/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 2254, \"label\": \"Table\"}]"
motivation: 多模态对比学习依赖图像-文本精确对齐，但实际数据常存在错配，需理清其影响。
method: 使用潜变量模型形式化跨模态错配，并进行理论分析与实验验证。
result: 发现根据任务性质，缓解或利用错配各有优势，提供了具体的选择原则。
conclusion: 该研究为多模态学习中的错配处理提供了理论依据和实践指南，有助于训练更强健的模型。
---

## Abstract
Multimodal representation learning, exemplified by multimodal contrastive learning (MMCL) using image-text pairs, aims to learn powerful representations by aligning cues across modalities. This approach relies on the core assumption that the exemplar image-text pairs constitute two representations of an identical concept. However, recent research has revealed that real-world datasets often exhibit cross-modal misalignment. There are two distinct viewpoints on how to address this issue: one suggests mitigating the misalignment, and the other leveraging it. We seek here to reconcile these seemingly opposing perspectives, and to provide a practical guide for practitioners. Using latent variable models we thus formalize cross-modal misalignment by introducing two specific mechanisms: Selection bias, where some semantic variables are absent in the text, and perturbation bias, where semantic variables are altered—both leading to misalignment in data pairs. Our theoretical analysis demonstrates that, under mild assumptions, the representations learned by MMCL capture exactly the information related to the subset of the semantic variables invariant to selection and perturbation biases. This provides a unified perspective for understanding misalignment. Based on this, we further offer actionable insights into how misalignment should inform the design of real-world ML systems. We validate our theoretical findings via extensive empirical studies on both synthetic data and real image-text datasets, shedding light on the nuanced impact of cross-modal misalignment on multimodal representation learning.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文，以Markdown形式对给定的论文进行结构化、深入、客观的总结。

# 论文深度分析总结：论跨模态错配在多模态表示学习中的价值

### 1. 论文的核心问题与整体含义

*   **核心问题**：多模态对比学习(MMCL)的基础假设是图像和文本对是完美对齐的，即表达完全相同的信息。然而，现实世界的数据集普遍存在**跨模态错配 (Cross-Modal Misalignment)** 现象。当前研究对此有两种看似矛盾的观点：
    1.  **缓解论**：视错配为有害噪声，应予以修正或过滤。
    2.  **利用论**：认为适当的错配反而能增强模型的鲁棒性。
*   **整体含义与目标**：本文旨在从理论上**调和这两种对立观点**，并为实践者提供一个指导性的框架，以决定在何时、以何种方式处理跨模态错配。核心目标不是简单地评判孰对孰错，而是揭示在何种条件下错配是有害的，何种条件下是有益的。

### 2. 论文提出的方法论

*   **核心思想**：通过构建一个刻画数据生成过程的**潜变量模型(LVM)**，对跨模态错配进行形式化定义，并在此模型下对MMCL的表示学习过程进行理论可辨识性分析。
*   **关键技术细节：潜变量模型 (LVM)**
    *   **潜空间划分**：将潜空间分为三个部分：
        *   **语义变量 ($s$)**：所有模态共有的、可解释的信息（如物体形状、颜色）。
        *   **图像特定变量 ($m_x$)**：与语义无关的图像噪声或背景。
        *   **文本特定变量 ($m_t$)**：与语义无关的文本风格或语调。
    *   **错配建模机制**：专门针对文本模态，引入了两种“偏差”：
        1.  **选择偏差 ($\theta$)**：指部分语义信息在文本描述中被**完全省略**。例如，描述一只猫时只提及颜色而忽略其大小。
        2.  **扰动偏差 ($\rho$)**：指文本中的语义元素被**随机替换或错误描述**。例如，一只黑色的猫被错误描述为“红色”。
*   **理论分析与公式思路**：
    *   **学习目标**：采用对称的对比学习目标函数的渐近形式，该形式可被分解为对齐项（最小化成对样本距离）和均匀项（最大化特征熵）。
    *   **核心定理 (Theorem 4.1)**：作者证明了，在温和假设下，通过最小化上述目标函数，MMCL学得的表示将**精确地仅保留那些未被选择偏差排除且未被扰动偏差影响的语义变量子集($s_{I_c^ρ}$)的信息**。该子集是可以被“块辨识(Block-Identifiability)”的。任何被省略或扰动的语义变量信息都会被完全丢弃。
    *   **实践推论**：
        *   **推论 4.1 (全量语义辨识)**：当没有错配时，模型能够完整地辨识所有语义变量。这对应大规模预训练场景，需要保证标注的完整性和一致性。
        *   **推论 4.2 (不变语义辨识)**：当错配（省略和扰动）恰好只作用于那些在训练和测试环境间会发生变化的语义变量时，模型将只学习对环境变化鲁棒的不变表征。这对应不变性表征学习和领域泛化场景，错配反而成为了一种有益的“正则化器”。

### 3. 实验设计

*   **数据集/场景**:
    *   **数值仿真**：自定义的数据生成过程，模拟带因果依赖关系的10维语义变量和5维模态特定变量。
    *   **真实图像-文本数据集**:
        1.  **MPI3D-Complex**：包含7个独立解耦因子（颜色、形状等）的真实世界图像，用于生成文本并注入错配。
        2.  **Causal3DIdent**：一个半合成数据集，其潜变量之间存在显式定义的因果图（共10个变量，含连续和离散类型），用于研究在复杂因果结构下的错配影响。
    *   **案例研究**：使用在LAION-400M上预训练的**OpenCLIP模型 (ViT-B-32, ViT-L-14)**，分析其在不同视觉概念（共15组，146个概念）上的零样本分类性能，并关联其在训练数据中的标题覆盖率。
*   **Benchmark与对比方法**: 本文并非提出新方法与SOTA进行Benchmark对比，而是**系统性验证其理论猜想**。实验设计通过**控制变量的方式**：
    *   系统地改变语义变量的选择偏差（逐步增加或减少文本包含的属性）和扰动偏差（逐步改变被随机替换的属性数量）。
    *   评估不同错配配置下，学得的表示对每个潜变量的**预测能力（用R²或MCC衡量）**，以此验证定理中“保留无偏变量，丢弃错配变量”的结论。
*   **下游任务设计**: 在数值仿真中设计了回归和分类（含分布外泛化）任务，用于分析错配对下游性能的影响。

### 4. 资源与算力

*   论文有明确的算力说明：
    *   **硬件配置**: 使用了配备 `4x NVIDIA A100 GPUs (40GB each)` 的计算集群，以及一台单独的 `NVIDIA RTX 4090 (24GB)` GPU工作站用于渲染Causal3DIdent的图像。
    *   **训练时长**:
        *   数值仿真：超过120个模型，总计约**70 GPU-hours**。
        *   MPI3D-Complex数据集：36个模型，总计约**27 GPU-hours**。
        *   Causal3DIdent数据集：42个模型，总计约**25 GPU-hours**。
        *   Causal3DIdent图像渲染：使用Blender在RTX 4090工作站上花费**四天**时间生成10000张图像。

### 5. 实验数量与充分性

*   **实验数量**: 实验设计系统且全面，可以认为非常充分。
    *   **多维度验证**: 覆盖了从纯数值仿真、到真实世界解耦数据、再到复杂因果结构半合成数据，最后到真实大规模预训练模型的多个层面，形成了一条完整的证据链。
    *   **大工作量**: 涉及数百次模型训练和大量图像渲染，每个实验均运行**3个随机种子**并报告平均值，确保了结果的稳定性。
    *   **详细的消融与额外分析**: 包括了对线性/非线性回归性能的对比、编码器维度设定错误的影响、以及选择与扰动偏差共存等边界的分析。附录中提供了所有实验的完整超参数、模型架构和数据细节，保证了可复现性。
*   **客观性与公平性**:
    *   实验设计的核心是**验证理论，而非与其他方法竞争**。通过严格的变量控制，客观地关联错配模式与表示行为。
    *   评估指标（R², MCC, F1）是针对具体任务（回归、分类）的标准选择，公平且可解释。
    *   OpenCLIP案例研究通过分析预训练模型的行为，提供了真实世界的佐证，避免了只在玩具数据集上验证理论的偏见。

### 6. 论文的主要结论与发现

1.  **理论统一了两种观点**：MMCL学到的表示仅捕获跨模态间**无偏的共享语义信息**。
    *   **不利的一面**：如果下游任务需要被省略或扰动的语义信息（例如需要识别物体的大小，但标题中从未提及），那么错配会导致性能下降，此时应当**缓解错配**。
    *   **有利的一面**：如果被省略/扰动的是环境相关的、不稳定的语义信息（如背景、风格），那么错配可以作为一道天然的“过滤器”，强制模型学习**不变的核心语义**，提升对分布偏移的鲁棒性。
2.  **实践指导**：
    *   在预训练通用基础模型时，**必须保证文本标注的全面性和准确性**，以避免语义盲区。
    *   在追求领域泛化或鲁棒表示时，可以**策略性地引入或利用数据中的错配**，通过文本审核来删除或扰动敏感性语义，比直接干预图像更精准、可解释。

### 7. 优点

*   **理论贡献突出**：首次为跨模态错配这一普遍问题建立了形式化的数学模型，并给出了严格的可辨识性理论证明，揭示了其影响的本质。
*   **观点新颖且具有统一性**：成功调和了社区内长期存在的“缓解派”与“利用派”之争，提供了一个更高层次、更辩证的看待错配的视角。
*   **理论与实践的桥梁**：通过推论和案例研究，将抽象的理论结果清晰地转化为可操作的实践指南，直接指导了基础模型训练和不变性学习中的数据工程。
*   **实验设计严谨扎实**：从仿真到真实数据，再到大规模预训练模型的案例分析，形成了一个逻辑严密、证据充分的验证闭环。实验细节透明，可复现性强。附录中的混淆矩阵（Figure 23）直观地揭示了由于缺乏训练引起的系统性误分类，论证有力。
*   **对潜变量因果结构不做硬性假设**：理论分析允许语义变量之间存在任意的因果关系，这显著增强了模型的现实适用性，优于许多依赖强假设的先前工作。

### 8. 不足与局限

*   **错配类型的覆盖有限**：该研究聚焦于**语义层面的错配**（省略、错误描述）。现实世界中还存在其他类型的错配，如视频中的时间戳不对齐、多模态间的粒度不匹配等，这些未被框架所覆盖。
*   **理论中关于“文本特定变量独立”的假设**：在现实中，文本的风格（$m_t$）有时会和语义（$s$）有微妙关联，比如描述“一个悲伤的场景”时会倾向于使用特定的文学风格，绝对独立的假设可能不完全成立。
*   **线性辨识的未解之谜**：虽然理论保证了一般可逆映射下的块辨识，实证显示学到的表示和真值之间常是线性关系，但理论未能充分解释这种线性现象产生的条件，这仍是一个开放问题。当不满足条件时，学到的非线性变换可能在解耦性上较差。
*   **选择偏差的指标较粗糙**：在OpenCLIP案例中，用关键词在标题库中的“覆盖率”作为选择偏差的代理指标是一个近似，它无法区分“标题全面描述了物体但未提及该概念”和“标题本身就很少描述此类事物”的情况。
*   **“高阶语义”的建模缺失**：论文承认，目前的框架无法建模那些需要跨模态非线性融合才能涌现的语义，如“讽刺”、“幽默”，这是一个重要的局限性。

（完）
