---
title: "AlignVLM: Bridging Vision and Language Latent Spaces for Multimodal Document Understanding"
title_zh: AlignVLM：桥接视觉与语言潜空间用于多模态文档理解
authors: "Ahmed Masry, Juan A. Rodriguez, Tianyu Zhang, Suyuchen Wang, Chao Wang, Aarash Feizi, Akshay Kalkunte Suresh, Abhay Puri, Xiangru Jian, Pierre-Andre Noel, Sathwik Tejaswi Madhusudhan, Marco Pedersoli, Bang Liu, Nicolas Chapados, Yoshua Bengio, Enamul Hoque, Christopher Pal, Issam H. Laradji, David Vazquez, Perouz Taslakian, Spandana Gella, Sai Rajeswar"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vAxGuGmshO"
tags: ["query:affective-ai"]
score: 9.0
evidence: 提出利用LLM文本嵌入加权平均的视觉-文本对齐方法
tldr: 针对视觉语言模型中视觉特征与语言嵌入对齐时MLP连接器缺乏归纳偏置导致跨模态错位的问题，本文提出AlignVLM，将视觉特征映射为LLM文本嵌入的加权平均，利用语言先验约束视觉特征在语言空间中的表示。实验表明该方法在无需额外训练数据的情况下可学习高效对齐，显著提升多模态文档理解性能，为视觉语言预训练中的对齐模块设计提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 738, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 685, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 696, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1323, \"height\": 876, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1461, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 426, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 432, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 428, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 439, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 498, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 497, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 497, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 499, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 567, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 563, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 567, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vaxgugmsho/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 568, \"height\": 558, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 1082, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1325, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1026, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1331, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vaxgugmsho/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1387, \"height\": 258, \"label\": \"Table\"}]"
motivation: 现有视觉语言模型的连接器（如MLP）缺乏归纳偏置，难以将视觉特征约束在LLM语言结构内，导致数据需求大且跨模态错位。
method: 提出AlignVLM，将视觉特征映射为LLM文本嵌入的加权平均，利用语言先验保留语义相似性，通过轻量级连接器实现视觉-文本对齐。
result: 实验表明AlignVLM在多模态文档理解任务上优于MLP等连接器，对齐效果更稳定、高效。
conclusion: AlignVLM利用语言先验有效桥接视觉和语言潜空间，为VLM中的跨模态对齐提供了简洁有效的解决方案。
---

## Abstract
Aligning visual features with language embeddings is a key challenge in vision-language models (VLMs). The performance of such models hinges on having a good connector that maps visual features generated by a vision encoder to a shared embedding space with the LLM while preserving semantic similarity. Existing connectors, such as multilayer perceptrons (MLPs), lack inductive bias to constrain visual features within the linguistic structure of the LLM’s embedding space, making them data-hungry and prone to cross-modal misalignment. In this work, we propose a novel vision-text alignment method, AlignVLM, that maps visual features to a weighted average of LLM text embeddings. Our approach leverages the linguistic priors encoded by the LLM to ensure that visual features are mapped to regions of the space that the LLM can effectively interpret. AlignVLM is particularly effective for document understanding tasks, where visual and textual modalities are highly correlated. Our extensive experiments show that AlignVLM achieves state-of-the-art performance compared to prior alignment methods, with larger gains on document understanding and under low-resource setups. We provide further analysis demonstrating its efficiency and robustness to noise.

---

## 论文详细总结（自动生成）

好的，以下是基于您提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：现有的视觉语言模型（VLM）在将视觉编码器输出的连续视觉特征映射到大语言模型（LLM）的语义空间时，其连接器模块（如简单的多层感知机MLP）缺乏归纳偏置。这导致视觉特征可能落在LLM训练分布之外的区域，产生噪声或跨模态错位，使得模型数据需求大、在低资源场景下性能不佳。
*   **整体含义**：论文旨在解决多模态模型，特别是文档理解领域中，视觉与语言模态间存在的表征鸿沟。其核心贡献在于提出了一种新颖的连接器 `ALIGN`，通过强制视觉特征落在LLM文本嵌入空间的凸包内，利用语言先验来指导视觉特征的映射，从而实现更高效、更鲁棒的对齐。

### 2. 论文提出的方法论

*   **核心思想**：`ALIGN` 连接器并不直接将视觉特征投影到LLM的嵌入空间，而是将每个视觉特征向量转换为LLM词汇表上的一个概率分布，然后将LLM的文本嵌入进行加权求和，从而得到一个位于文本嵌入凸包内的视觉表征。
*   **关键技术细节与流程**：
    1.  **视觉编码**：使用SigLip-400M视觉编码器处理按比例分割的图像块（tile），输出视觉特征序列 \\(F\\) 。
    2.  **ALIGN 模块映射**：
        *   **线性投影**：首先通过线性层 \\(W_1\\) 将视觉特征 \\(F\\) 投影到LLM的文本嵌入维度。
        *   **生成词汇概率**：利用从LLM语言模型头初始化的线性层 \\(W_2\\) 继续投影，并通过Softmax操作，为每个视觉特征生成一个在LLM词汇表 \\(V\\) 上的概率分布 \\(P_{\text{vocab}}\\)。
        *   **加权平均**：使用LLM的文本嵌入矩阵 \\(E_{\text{text}}\\)，根据概率分布 \\(P_{\text{vocab}}\\) 进行加权求和，得到最终的对齐视觉特征 \\(F'_{\text{align}}\\)。公式为：\\(P_{\text{vocab}} = \text{softmax}(\text{LayerNorm}(W_2 \text{LayerNorm}(W_1F)))\\)，\\(F'_{\text{align}} = P_{\text{vocab}}^T E_{\text{text}}\\)。
    3.  **LLM输入**：将对齐后的视觉特征 \\(F'_{\text{align}}\\) 与文本指令的嵌入拼接，输入LLM生成回答。
*   **训练策略**：分三阶段进行：1) 在CC-12M数据集上预训练对齐能力；2) 在BigDocs-7.5M数据集上增强文档理解能力；3) 在DocDownstream数据集上进行指令微调。

### 3. 实验设计

*   **数据集**：
    *   **预训练**：CC-12M（约810万对图文数据）。
    *   **文档理解训练**： BigDocs-7.5M。
    *   **指令微调**： DocDownstream。
*   **基准（Benchmark）**：包括多个文档理解评测任务，如DocVQA, InfoVQA, DeepForm, KLC, WTQ, TabFact, ChartQA, TextVQA, TableVQA。在低资源实验中，还使用了通用视觉问答基准如MMMU, SeedBench, MMVet, POPE, GQA。
*   **对比方法**:
    *   **基础VLM对比**：Qwen2-VL-2B, DocOwl1.5-8B, Llama3.2-11B（均在相同的数据和设定下复现或微调）。
    *   **连接器设计对比**：广泛使用的MLP连接器、Perceiver Resampler、Ovis的视觉嵌入表、H-Reducer、HoneyBee。
    *   **外部模型对比**：包括Claude-3.5/GPT-4o等闭源模型，和Qwen2.5/InternVL等开源指令微调模型，以作参考。

### 4. 资源与算力

*   论文明确指出：所有实验均在 **8个节点共64块NVIDIA H100 GPU** 上进行。
*   训练框架使用了 **MS-Swift** 和 **DeepSpeed (ZeRO-3配置)** 进行分布式高效训练。
*   此外，论文通过附录表格提供了详细的训练超参数（如学习率、批次大小、训练周期等），但未提及具体的总训练时长（如GPU小时）。

### 5. 实验数量与充分性

实验设计相当充分、客观且公平，主要体现在：

*   **多维度对比实验**：
    1.  **主要结果**：与同等训练条件下的基础VLM、以及更大规模的开源/闭源指令模型对比。
    2.  **连接器对比**：在完全相同的训练配置下，对比了MLP、Perceiver Resampler、Ovis等多种主流连接器。
    3.  **低资源场景**：模拟数据稀缺环境（仅用~779K样本），对比多种连接器的数据效率。
*   **深入的分析与消融实验**：
    1.  **概率分布分析**：可视化了`ALIGN`产生的词汇概率分布，并通过PCA分析揭示其只依赖一个约3.4K的核心嵌入子集。
    2.  **噪声鲁棒性测试**：向视觉特征注入高斯噪声，对比了`ALIGN`与MLP连接器的性能下降程度，并量化了嵌入的余弦距离变化。
    3.  **像素级任务分析**：在VCR任务上测试模型对细粒度像素线索的利用能力。
    4.  **效率分析**：对比了不同连接器的推理速度和GPU内存占用。

### 6. 论文的主要结论与发现

*   `ALIGN` 连接器通过将视觉特征约束在LLM文本嵌入的凸包内，有效利用了语言先验，显著改善了跨模态对齐。
*   基于`ALIGN`的模型（ALIGN VLM）在多个文档理解基准上达到了最优性能，在同等规模下显著优于使用MLP等其他连接器的基线模型，实现了更快的收敛。
*   `ALIGN` 在低资源训练场景下优势更为突出，表现出了极高的数据效率。
*   `ALIGN` 对视觉特征中的高斯噪声具有很强的鲁棒性，远优于脆弱的MLP连接器。
*   `ALIGN` 模块引入的计算和内存开销极小，几乎不影响推理效率。

### 7. 优点

*   **方法简洁且有效**：通过一个巧妙的加权平均操作，利用预训练好的LLM文本嵌入来约束视觉特征，思想新颖且实现简单。
*   **性能优异**：在文档理解这一关键应用领域取得了顶级的性能表现。
*   **强鲁棒性与数据效率**：在抗噪声和少数据学习上的出色表现，证明了其相较于传统方法的显著优势，实用性更强。
*   **透彻的实验分析**：不仅仅是性能对比，还通过概率分布可视化、PCA、噪声注入实验等，深刻揭示了方法有效性的内在机理。
*   **对比公平客观**：严格在相同训练设定下复现和比较不同连接器，确保了结论的可信度。

### 8. 不足与局限

*   **任务泛化性**：虽然文中指出方法对文档理解任务增益显著，但从低资源实验结果（Table 3）看，在通用视觉任务上的提升相对较小。这表明该方法的优势可能更集中于视觉和文本高度耦合的场景。
*   **依赖文本嵌入的质量**：该方法的核心依赖于LLM的文本嵌入空间，若LLM本身的语言表征能力不足，可能会限制其效果。
*   **像素级任务的偏见**：在VCR任务的失败案例中，作者指出模型可能倾向于将视觉表征对齐到更常见的词汇（如将人名“Gorden”识别为“Garden”），这可能是一个潜在偏差。
*   **未报告误差棒**：论文提到由于计算资源昂贵，并未报告多次实验的误差棒，这在一定程度上降低了结果统计显著性的说服力。
*   **训练规模**：受限于资源，模型主要在最大8B参数量的LLM上进行实验，且动态分辨率最大为9个图像块，更大规模模型和更高分辨率下的效果尚待验证。

（完）
