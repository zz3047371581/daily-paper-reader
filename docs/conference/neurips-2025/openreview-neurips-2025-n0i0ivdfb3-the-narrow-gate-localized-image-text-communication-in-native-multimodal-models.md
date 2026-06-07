---
title: "The Narrow Gate: Localized Image-Text Communication in Native Multimodal Models"
title_zh: 窄门：原生多模态模型中局部化的图文通信
authors: "Alessandro Pietro Serra, Francesco Ortu, Emanuele Panizon, Lucrezia Valeriani, Lorenzo Basile, Alessio ansuini, Diego Doimo, Alberto Cazzaniga"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=n0I0IvdfB3"
tags: ["query:affective-ai"]
score: 7.0
evidence: 分析视觉语言模型中跨模态信息流和嵌入分离
tldr: 本文深入研究视觉语言模型处理图像理解任务时的信息传递机制，对比原生与非原生多模态VLM。发现原生模型中图像和文本嵌入在残差流中更分离，且信息流动局部化，不同模型间差异显著。这些发现为改进跨模态对齐和融合提供了可解释性指导，深化了对多模态模型内部机制的理解。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-n0i0ivdfb3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1388, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n0i0ivdfb3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 954, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n0i0ivdfb3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1316, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n0i0ivdfb3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1316, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n0i0ivdfb3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 974, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n0i0ivdfb3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n0i0ivdfb3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1030, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n0i0ivdfb3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1316, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n0i0ivdfb3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1181, \"height\": 1757, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-n0i0ivdfb3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1012, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n0i0ivdfb3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n0i0ivdfb3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1230, \"height\": 1105, \"label\": \"Table\"}]"
motivation: 需要理解多模态视觉语言模型内部如何传递和处理视觉信息。
method: 对比分析原生与非原生多模态VLM，研究信息流和嵌入分离特性。
result: 发现原生模型中图像和文本嵌入更分离，信息传递局部化。
conclusion: 模型架构影响跨模态通信模式，为优化对齐提供新视角。
---

## Abstract
Recent advances in multimodal training have significantly improved the integration of image understanding and generation within a unified model. This study investigates how vision-language models (VLMs) handle image-understanding tasks, focusing on how visual information is processed and transferred to the textual domain. We compare *native multimodal VLMs*, models trained from scratch on multimodal data to generate both text and images, and *non-native multimodal VLMs*, models adapted from pre-trained large language models or capable of generating only text, highlighting key differences in information flow. We find that in native multimodal VLMs, image and text embeddings are more separated within the residual stream. Moreover, VLMs differ in how visual information reaches text: non-native multimodal VLMs exhibit a distributed communication pattern, where information is exchanged through multiple image tokens, whereas models trained natively for joint image and text generation tend to rely on a single post-image token that acts as a *narrow gate* for visual information. We show that ablating this single token significantly deteriorates image-understanding performance, whereas targeted, token-level interventions reliably steer image semantics and downstream text with fine-grained control.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以 Markdown 形式，对这篇论文进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：研究旨在探究视觉语言模型（VLM）在处理图像理解任务时，视觉信息是如何被处理并传递到文本域的。核心问题是：不同类型的VLM（原生 vs. 非原生）内部是否采用了不同的跨模态通信机制？
*   **研究动机**：随着多模态基础模型的发展，尽管它们能同时理解与生成视觉内容，但其内部表征如何交互仍是黑盒。过往研究多集中于非原生（如基于LLM适配）的VLM，缺乏对从零开始训练的原生多模态模型内部机制的理解。
*   **核心发现与整体含义**：研究发现了一种显著的架构性差异。原生多模态VLM采用一种局部化的“窄门”通信模式，视觉信息会汇聚到单个特殊的图像结束标记（[EOI]）上，再传递给文本。而非原生VLM则采用一种分布式的通信模式，视觉信息通过多个内部图像标记来传递。这一发现揭示了架构和训练范式选择会从根本上塑造模型内部的跨模态信息流。

### 2. 论文提出的方法论

论文主要通过对比分析、因果干预和几何分析三类工具来探究信息流：

*   **对比分析对象**：
    *   **原生多模态VLM**：Chameleon (7B, 34B), Emu3 (8B)。特征为：从零开始多模态数据训练，统一输出图像和文本。
    *   **非原生多模态VLM**：LLaVA (7B), Pixtral (12B)，Janus (1.3B), VILA-U (7B)。特征为：适配自预训练大语言模型，或仅生成文本。
*   **核心技术细节**：
    *   **跨模态注意力量化**：定义了一个指标 \(f^l_j\)，用于量化所有文本标记（位置 > [EOI]）对某个图像标记 \(j\) 的平均注意力权重，以识别关键的跨模态通信标记位置。
    *   **注意力剔除（Attention Knockout）**：一种因果干预方法，通过在特定层将所有注意力头中从源标记集到目标标记集的注意力权重置零，来阻断通信。文中用于阻断“文本→[EOI]”和“文本→所有图像标记”的通信。
    *   **语义探测（Neighborhood Overlap）**：使用 \( \chi^{l,gt}_k \) 度量在某一层 \(l\) 的残差流表征的 \(k\)-近邻与参考集（如图像类别标签或文本嵌入）\(k\)-近邻的重叠度，以此评估表征中编码的抽象语义信息量。公式为 \( \chi^{l,gt}_{k} = \frac{1}{nk} \sum_{i=1}^{n} |N^l_k(i) \cap N^{gt}_k(i)| \)。
    *   **激化修补（Activation Patching）**：将目标输入的特定层激活值 \(\hat{x}^l_i\) 替换到基础输入的相同位置，观察模型输出分布向目标分布的偏移程度，以此检验该表征的因果作用。使用Jaccard相似度 \( \sum_i \min(q_i, p_i) \) 量化偏移。

### 3. 实验设计

*   **数据集**：
    *   **图像问答 (VQA)**：VQAv2
    *   **图像描述 (Captioning)**：Flickr30k，MS-COCO
    *   **图像分类 (Classification)**：ImageNet (100个动物类别)
*   **基准 (Benchmark) 与评估指标**：
    *   在VQA任务上比较不同消融下的性能，使用VQA准确率指标。
    *   在Captioning任务上使用CIDEr分数评估。
    *   在ImageNet上使用邻域重叠度 \( \chi \) 评估。
*   **对比方法**：
    *   **模型间对比**：原生多模态模型 vs. 非原生多模态模型，在相同任务和分析（注意力、语义、消融）下进行横向对比。
    *   **消融对比**：针对每个模型，进行“无消融（基线）”、“消融`[EOI]`”（阻断`text→[EOI]`注意力）与“消融所有图像”（阻断`text→img`注意力）三种条件下的性能对比。
    *   **微调对比**：在原生模型上进行标准微调与“遮盖`[EOI]`”微调的性能对比。

### 4. 资源与算力

*   **硬件平台**：实验主要使用单块NVIDIA A100 GPU (40GB VRAM) 完成。
*   **大型模型需求**：对于 Chameleon 34B 模型，需要使用两块 40GB A100 GPU。
*   **训练时长**：文中未明确给出所有实验的总耗时，但提到了对Emu3和窄门消除的微调实验，训练了一个epoch，但未提及具体时间。所有模型均使用HuggingFace实现，并提供了代码库链接以复现结果。

### 5. 实验数量与充分性

论文实验设计系统且全面，具有很高的充分性和客观性。
*   **实验组数**：
    1.  **模态鸿沟分析 (Modality Gap)**：利用余弦相似度和聚类纯度对6个模型进行跨层分析。
    2.  **跨模态注意力分析**：对6个模型，在ImageNet数据集上逐层量化不同图像标记的注意力贡献。
    3.  **语义内容探测**：对6个模型，在ImageNet和MS-COCO两个数据集上，对不同的图像标记进行逐层语义探针分析。
    4.  **注意力剔除实验**：对7个模型（含34B），在VQAv2， Flickr30k, MS-COCO, ImageNet 四个下游任务上进行消融实验。
    5.  **激化修补实验**：对4个代表性模型，在ImageNet的10个类别对上执行针对性语义操控，并进行性能评估。
    6.  **鲁棒性微调实验**：对2个原生模型（Chameleon-7B, Emu3-8B）执行遮盖`[EOI]`的微调并在MS-COCO和VQAv2上评估。
*   **充分性与公平性**：实验覆盖了两个完整的技术范式（原生与非原生），包含多种模型规模和架构变体，使用了多个标准视觉-语言基准。所有对比分析都在相同的实验设置下进行，确保了结果的客观性和公平性。

### 6. 论文的主要结论与发现

1.  **模态分离**：在原生多模态VLM中，图像和文本的嵌入在整个残差流中保持高度分离，形成显著的模态鸿沟；而在非原生模型中，两者在深层逐渐混合。
2.  **窄门通信**：原生VLM演化出一种独特的跨模态通信机制。`[EOI]`标记成为一个信息瓶颈或“窄门”，它既汇聚了绝大部分的跨模态注意力，又承载了最丰富的图像语义信息。
3.  **功能因果性**：消融`[EOI]`标记会导致图像理解任务性能崩溃，其破坏性甚至超过阻断所有图像标记的注意力。通过编辑`[EOI]`标记的表征，可以可靠地操控下游文本的语义内容。这证明了该单一标记是信息传递的核心功能通道。
4.  **分布式通信**：非原生VLM表现出完全相反的模式，其跨模态通信是分布式的，由众多内部图像标记共同承担，`[EOI]`标记作用甚微。
5.  **架构决定性**：这些差异表明，通信模式并非偶然，而是由“多模态输出目标”、“从零开始的训练历史”和“低层视觉分词器”等架构和训练因素共同决定的。

### 7. 优点

*   **洞察深刻**：首次清晰地揭示了原生和非原生多模态VLM之间显著的、系统性的内部通信机制差异（“窄门” vs. “分布式”）。
*   **实验设计严谨**：综合运用了表征几何分析、信息论探针、因果干预（消融和修补）以及微调等多种可解释性技术，从“是什么”、“在哪里”到“有何作用”形成了完整的证据链。
*   **对比维度丰富**：涵盖了多种模型架构、不同模型规模（1.3B到34B）和多个标准基准任务，增强了结论的普适性。
*   **理论与应用结合**：不仅分析了现象，还通过激活修补展示了精准可操控性的应用潜力，并提出了通过微调增强鲁棒性的解决方案。

### 8. 不足与局限

*   **通信方向局限**：研究仅关注了从**图像到文本**的单向信息流，未分析**文本到图像**生成过程中的通信机制。
*   **模型架构覆盖不全面**：主要研究了基于早期融合和离散标记（如VQ-VAE）的原生模型，结论是否能推广到使用更高层、连续编码或基于扩散解码器的原生模型尚不明确。
*   **模态类型局限**：研究局限于视觉和语言两种模态，其“窄门”机制在涉及更多模态（如音频、视频）的原生多模态模型中的适用性仍有待探索。
*   **潜在偏差风险**：所有分析都基于特定的提示模板（如“This animal is a”），虽然这在研究中很常见，但不同的提示结构可能会影响注意力分布和语义编码模式。

（完）
