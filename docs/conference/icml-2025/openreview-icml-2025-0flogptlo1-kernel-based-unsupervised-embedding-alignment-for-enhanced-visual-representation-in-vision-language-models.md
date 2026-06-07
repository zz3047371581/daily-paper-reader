---
title: Kernel-based Unsupervised Embedding Alignment for Enhanced Visual Representation in Vision-language Models
title_zh: 基于核方法的无监督嵌入对齐以增强视觉语言模型中的视觉表示
authors: "Shizhan Gong, Yankai Jiang, Qi Dou, Farzan Farnia"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=0fLoGPTLo1"
tags: ["query:affective-ai"]
score: 7.0
evidence: 通过核回归对齐CLIP的视觉表示与细粒度视觉模型，增强跨模态感知。
tldr: 本文提出一种基于核的无监督方法，将CLIP的视觉表示与DINOv2对齐，从而在不破坏文本对齐的前提下，显著提升了视觉语言模型对细粒度细节的感知能力。该方法为增强跨模态理解中的视觉表示开辟了新途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1737, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 807, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1736, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1736, \"height\": 350, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 784, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1776, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 885, \"height\": 583, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 627, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1562, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 926, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1773, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1616, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 844, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1773, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1773, \"height\": 420, \"label\": \"Table\"}]"
motivation: CLIP有限的细粒度感知导致多模态大语言模型出现严重故障，而DINOv2擅长捕获细节但缺乏文本对齐。
method: 设计基于核回归的无监督对齐框架，将CLIP的视觉嵌入映射到DINOv2的细粒度表示空间，同时保持文本对齐。
result: 实验表明，对齐后的视觉表示在下游视觉语言任务中显著提升了细粒度理解性能。
conclusion: 该工作有效解决了CLIP的视觉表示瓶颈，为视觉语言模型提供了一种即插即用的细粒度增强方案。
---

## Abstract
Vision-language models, such as CLIP, have achieved significant success in aligning visual and textual representations, becoming essential components of many multi-modal large language models (MLLMs) like LLaVA and OpenFlamingo. However, numerous studies have identified CLIP's limited fine-grained perception as a critical drawback, leading to substantial failures in downstream MLLMs. In contrast, vision-centric foundation models like DINOv2 demonstrate remarkable capabilities in capturing fine details from images. In this work, we propose a novel kernel-based method to align CLIP's visual representation with that of DINOv2, ensuring that the resulting embeddings maintain compatibility with text embeddings while enhancing perceptual capabilities. Our alignment objective is designed for efficient stochastic optimization. Following this image-only alignment fine-tuning, the visual encoder retains compatibility with the frozen text encoder and exhibits significant improvements in zero-shot object recognition, fine-grained spatial reasoning, and localization. By integrating the aligned visual encoder, downstream MLLMs also demonstrate enhanced performance. The code and models are available at https://github.com/peterant330/KUEA.

---

## 论文详细总结（自动生成）

# 论文深度分析总结：基于核方法的无监督嵌入对齐增强视觉语言模型视觉表示

## 1. 研究动机与核心问题

*   **核心痛点**：以CLIP为代表的视觉语言模型（VLM）虽然在对齐视觉与文本表示上取得了巨大成功，成为多模态大模型（MLLM）的核心组件。但其训练依赖于全局文本描述，导致视觉编码器存在严重的**细粒度感知缺陷**，在颜色、空间关系、计数等细节任务上表现不佳，这种缺陷会进一步“污染”下游MLLM的性能。
*   **现有方案的局限**：
    *   **多编码器融合**：直接拼接DINOv2等视觉基础模型的编码器，虽能提升性能，但引入了巨大的计算开销。
    *   **视觉特征微调**：用视觉自监督任务微调CLIP编码器，虽然增强了定位能力，但**破坏了图像与文本特征之间的对齐**，导致零样本泛化能力下降，且下游MLLM需要完全重新训练，代价高昂。
    *   **特征蒸馏**：直接对齐CLIP与DINOv2的特征空间高度困难，因为两者的特征空间差异巨大，容易完全破坏原有的视觉-语言对齐结构。
*   **本文目标**：提出一种轻量级的、**仅基于图像的**无监督微调方法，将CLIP的视觉表示与以DINOv2为代表的、具备强细粒度感知能力的视觉表示对齐，从而**在保留CLIP原有文本兼容性及零样本能力的同时，让其“看得更细”**。

## 2. 方法论：核空间嵌入对齐

*   **核心思想**：不直接对齐特征空间（欧氏距离），而是在**再生核希尔伯特空间（RKHS）中对齐它们的关系结构**。通过核技巧度量样本间相似度，强制让CLIP视觉编码器产生与DINOv2相似的样本间相似性结构，借此增强其细粒度视觉感知而不扭曲特征空间基本面，从而保住与文本编码器的兼容性。
*   **关键技术细节**：
    *   **对齐目标**：最小化CLIP和DINOv2在图像 `I_i`、`I_j` 上的**核函数输出之差的平方期望**。优化目标如下：
        ```
        min_{θ} E_{I_i,I_j ~ D} [ (k1(f_θ(I_i), f_θ(I_j)) - k2(g(I_i), g(I_j)))^2 ]
        ```
        其中 `f_θ` 是CLIP视觉编码器，`g` 是冻结的目标编码器，`k1`、`k2` 是对应核函数。
    *   **核心核函数**：主要采用**归一化的3次多项式核**：`k(x, y) = (γ x^T y + c)^3` 后归一化。
    *   **关键正则**：添加特征L2距离正则项，约束对齐后的特征不偏离原始CLIP特征太远，从而从理论上保证文本对齐不被破坏：
        ```
        + E_{I_i~D} [ ||f_θ(I_i) - f_{θ0}(I_i)||^2 ]
        ```
        （其中 `θ0` 是冻结的原始CLIP参数）
    *   **可扩展优化**：基于向量伯恩斯坦不等式（命题3.1）证明了可以通过小批量采样样本对，高效计算无偏梯度，从而支持大规模数据的随机优化。

*   **算法流程总结**：
    1.  准备冻结的目标视觉编码器 `g`（文中用 DINOv2）和预训练的 CLIP 视觉编码器 `f_{θ0}`。
    2.  仅使用图像数据集，在每轮迭代中采样一批图像对 `(I_i, I_j)`。
    3.  分别计算在CLIP和目标编码器下的核相似度，最小化两者的MSE损失。
    4.  同时计算对齐前后的CLIP特征L2距离并加入损失作正则。
    5.  反向传播更新 CLIP 视觉编码器参数 `θ`，文本编码器保持冻结。

## 3. 实验设计

*   **训练与模型配置**：
    *   **目标模型**：DINOv2 (ViT-L/14)。
    *   **待对齐模型**：CLIP 的 ViT-B/16、ViT-L/14、ViT-L/14-336 版本。
    *   **训练数据**：仅用 ImageNet-1K 训练集（128万张纯图像），无需任何文本。

*   **基准测试与对比方法**：
    *   **视觉中心任务**：零样本图像识别（12个数据集）、图文检索（Flickr30K、COCO）、细粒度任务（计数、空间推理）、定位能力。
    *   **下游 MLLM 评测**：直接替换 LLaVA、OpenFlamingo 的视觉编码器，评测其在 VQA、物体定位（RefCOCO系列）等 Benchmark 上的表现。
    *   **对比基线**：
        *   原始 CLIP。
        *   **特征投影**：训练一个线性层将DINOv2特征映射到CLIP空间。
        *   **特征直接对齐**：最小化CLIP与线性变换后DINOv2特征的L2距离。
        *   **近期工作**：DIVA（基于扩散模型反馈微调CLIP），AM-RADIO，Additive-MoF等。

## 4. 资源与算力

*   文中**明确提及**了所用资源：
    *   **GPU 型号及数量**：**2块 NVIDIA GeForce RTX 4090**。
    *   **训练时长与成本**：对齐ViT-L-14版本的CLIP约需要**30小时**。作者强调此训练相对于CLIP的预训练和完全重训下游模型，是“极其高效且硬件友好的”。

## 5. 实验数量与充分性评估

*   **实验规模庞大且充分**：论文涵盖了超过20个不同维度的数据集及测试基准，进行了多组实验：
    *   **视觉感知能力（4组）**：12个零样本分类数据集、2个跨模态检索数据集、4个细粒度推理任务、COCO定位探针基准。
    *   **下游任务迁移（2组）**：LLaVA（12个基准）、OpenFlamingo（7个基准 + 少样本）。
    *   **泛化与消融（4组）**：在3个其它VLM（SigLIP, DFN, MetaCLIP）上做扩展实验；在4个维度（训练轮次、正则项、系数、核函数）做消融实验；与多重基线（AM-RADIO、MoF等）对比分析。
*   **客观性与公平性**：实验具有很高的客观性和公平性。对比方法覆盖了从直观基线（线性投影）到近期高水平工作（DIVA）。作者也坦诚地展示了该方法在一些指标上无法媲美需要重训整个MLLM的最优水平，只是在一个更具性价比的“即插即用”维度上实现了最佳提升，分析非常客观。

## 6. 主要结论与发现

*   **轻量高效的增强**：仅通过纯图像数据对CLIP视觉编码器进行短期微调，且不用重新对齐文本，就能显著提升视觉能力。
*   **“核”优于“特征”直接对齐**：直接对齐特征空间或线性映射容易特征崩溃，而核空间对齐灵活调整样本间相对关系，既能提升感知还保留文本对齐。
*   **完美兼容下游**：对齐后的视觉编码器是原CLIP的“即插即用”增强版本，不仅全兼容零样本文本分类，更能被下游预训练好的MLLM直接继承，丝毫不用重训大语言模型即可获得性能增益。
*   **泛化性**：该方法不仅适用CLIP，也能提升SigLIP等其它VLM的零样本表现；目标编码器不仅限DINOv2，替换成MLCD依然有效。

## 7. 优点与亮点

*   **即插即用的范式创新**：区别于所有需要重新训练MLLM或文本编码器的方案，是首个仅通过图像端对齐、保留完整文本兼容性的“单端升级”方案。
*   **优雅的理论设计**：将跨模型特征对齐巧妙映射到高维核空间，解决了特征空间不可比的根本难题，并通过正则项给予了理论保护。
*   **极强的现实意义**：计算成本极低（4090仅需30小时），数据仅需纯图，对世界上成千上万已经训练好的下游MLLM系统可以直接注入而不需推倒重来。
*   **实验全面且说服力强**：覆盖视觉诊断、通用VQA、定位等多种下游任务，且在多个VLM上做了泛化验证，证明了方法的普适性。

## 8. 不足与局限

*   **数据集规模局限**：受限于算力，只在中等规模的ImageNet-1K上对齐训练。若放大到更大规模图像集，性能上限还能涨多少未知。
*   **模型规模验证不足**：只在 7B 和 3B 的小型MLLM及ViT-B/L规模的CLIP上做了测试，未验证其在70B等级的大型MLLM上的表现。
*   **目标模型局限**：对齐对象集中在DINOv2，还未全方位扩展到SAM、MAE等其它多种卓越的自监督视觉基础模型。
*   **增益非颠覆性**：相较部分需要重训MLLM的方案，纯粹不调LLM的性能提升是克制的改进，在追求极致性能的场景下仍显不足。

（完）
