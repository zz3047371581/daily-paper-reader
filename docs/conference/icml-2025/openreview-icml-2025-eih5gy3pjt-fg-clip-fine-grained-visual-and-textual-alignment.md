---
title: "FG-CLIP: Fine-Grained Visual and Textual Alignment"
title_zh: FG-CLIP：细粒度视觉与文本对齐
authors: "Chunyu Xie, Bin Wang, Fanjing Kong, Jincheng Li, Dawei Liang, Gengshen Zhang, Dawei Leng, Yuhui Yin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=eih5Gy3Pjt"
tags: ["query:affective-ai"]
score: 8.0
evidence: 提出FG-CLIP以改善图像与文本的细粒度跨模态对齐。
tldr: 针对CLIP缺乏细粒度理解的问题，FG-CLIP通过利用大规模长描述、区域级对齐和困难负样本挖掘，显著提升了图像-文本跨模态检索和零样本分类性能。该工作为视觉语言模型的细粒度对齐提供了有效范例。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1763, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 401, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 396, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 397, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 583, \"height\": 2024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1617, \"height\": 1073, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1586, \"height\": 971, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1592, \"height\": 1136, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 678, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1646, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1525, \"height\": 1895, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1495, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1382, \"height\": 252, \"label\": \"Table\"}]"
motivation: CLIP因依赖粗粒度短描述而缺乏细粒度理解，限制了其在复杂视觉语言任务中的应用。
method: FG-CLIP利用大模型生成16亿长描述，构建1200万图像与4000万区域对齐数据集，并引入1000万困难负样本提升判别力。
result: 模型在多个图像-文本检索和零样本分类基准上取得最优结果，显著增强细粒度语义捕获。
conclusion: FG-CLIP有效解决了CLIP的细粒度缺陷，为视觉语言预训练提供了高质量数据与训练策略，推动了跨模态理解前沿。
---

## Abstract
Contrastive Language-Image Pre-training (CLIP) excels in multimodal tasks such as image-text retrieval and zero-shot classification but struggles with fine-grained understanding due to its focus on coarse-grained short captions. To address this, we propose Fine-Grained CLIP (FG-CLIP), which enhances fine-grained understanding through three key innovations. First, we leverage large multimodal models to generate 1.6 billion long caption-image pairs for capturing global-level semantic details. Second, a high-quality dataset is constructed with 12 million images and 40 million region-specific bounding boxes aligned with detailed captions to ensure precise, context-rich representations. Third, 10 million hard fine-grained negative samples are incorporated to improve the model's ability to distinguish subtle semantic differences. We construct a comprehensive dataset, termed FineHARD, by integrating high-quality region-specific annotations with challenging fine-grained negative samples. Corresponding training methods are meticulously designed for these data. Extensive experiments demonstrate that FG-CLIP outperforms the original CLIP and other state-of-the-art methods across various downstream tasks, including fine-grained understanding, open-vocabulary object detection, image-text retrieval, and general multimodal benchmarks. These results highlight FG-CLIP's effectiveness in capturing fine-grained image details and improving overall model performance. The data, code, and models are available at https://github.com/360CVGroup/FG-CLIP.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以Markdown形式，对《FG-CLIP: Fine-Grained Visual and Textual Alignment》这篇论文进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **核心问题：** 现有的对比语言-图像预训练模型（如CLIP）虽然在多模态任务中表现出色，但在**细粒度理解（Fine-Grained Understanding）** 方面存在显著不足。具体表现为难以精细地识别物体的属性、关系以及局部区域的细节。
*   **问题根源：** 论文指出了两个主要原因：
    1.  **文本端限制：** CLIP的文本编码器通常只支持77个词元，无法处理包含丰富细节的长文本描述。
    2.  **对齐粒度过粗：** CLIP在全局层面将整张图像与整个文本描述进行对齐，缺乏对图像特定区域与对应文本片段之间的精确对齐机制。
    3.  **训练数据缺乏挑战：** 现有数据集中缺少“困难细粒度负样本”，导致模型难以分辨同一类别下具有不同属性（如“红色汽车”与“蓝色汽车”）的细微特征。
*   **整体含义：** 本研究旨在解决视觉-语言模型在精细粒度语义对齐上的核心瓶颈，通过提出FG-CLIP模型和一个高质量数据集，显著提升了模型对图像局部细节和复杂文本描述的理解能力，推动了多模态模型向更精细、更鲁棒的方向发展。

### 2. 方法论

FG-CLIP的核心思想是通过**数据增强**和**多阶段训练**来系统性地提升模型的细粒度对齐能力。整个架构扩展了CLIP的双塔结构，并分为两个训练阶段。

*   **阶段一：全局对比学习**
    *   **目标：** 提升模型对图像整体语义细节的感知能力。
    *   **关键技术：**
        1.  **大规模长描述重生成：** 利用大型多模态模型（如CogVLM2-19B）为LAION-2B数据集中的16亿张图像重新生成了详细的长描述，以替代原始简短、粗糙的标签。
        2.  **长文本编码器适配：** 将文本编码器的位置编码通过线性插值从77扩展到248个词元，以处理长文本。
    *   **训练策略：** 每一张图像同时与一条短描述和一条长描述进行对齐。使用基于InfoNCE的**全局对比损失**来拉近匹配的图像-文本对在共享嵌入空间中的距离。

*   **阶段二：区域对比学习与困难负样本学习**
    *   **目标：** 实现图像区域与文本片段之间的精确对齐，并增强模型对细微语义差别的判别能力。
    *   **关键技术：**
        1.  **高质量视觉定位数据集（FineHARD）：**
            *   包含1200万张图像和4000万个带有精细文本描述的边界框。
            *   通过大模型生成整图详细描述，再使用SpaCy和Yolo-World模型将描述片段与图像中的具体区域进行对齐。
        2.  **困难细粒度负样本挖掘：**
            *   使用Llama-3.1-70B模型，对每个区域的正样本文本描述进行属性修改（如改变颜色、材质），但保持主体不变，生成10个语义相近但细节不同的负样本描述，总计1000万个。
    *   **训练策略：**
        *   **区域对比损失：** 使用RoIAlign从图像特征图中提取区域特征，并与对应的正样本文本片段特征进行对齐。
        *   **困难负样本损失：** 对于每个区域特征，不仅与正样本文本计算相似度，也与所有对应的困难负样本文本计算，迫使模型学会区分细微差异。
    *   **联合优化：** 阶段二的最终损失函数为三个损失的加权和，公式如下：
        *   `L = L_global + 0.1 * L_regional + 0.5 * L_hard`

### 3. 实验设计

*   **使用数据集与场景：**
    *   **预训练数据：** 使用了增强后的LAION-2B（16亿对）和自建的FineHARD数据集（1200万图像）。
    *   **评估基准与任务：**
        *   **细粒度理解：** FG-OVD基准，包含 `hard`, `medium`, `easy`, `trivial` 四个难度子集。
        *   **边界框分类：** COCO-val2017, LVIS, Open Images。
        *   **开放词汇目标检测：** OV-COCO基准，使用F-ViT检测框架。
        *   **图像-文本检索：** 长文本检索（ShareGPT4V, DCI），短文本检索（MSCOCO, Flickr30k）。
        *   **零样本图像分类：** ImageNet-1K, ImageNet-v2。
        *   **通用多模态基准：** 作为LLaVA的视觉编码器，在GQA, POPE, RefCOCO上进行评估。
*   **对比方法：**
    *   **基础模型：** 原始CLIP。
    *   **同类细粒度增强模型：** EVA-CLIP， Long-CLIP， FineCLIP。
    *   **目标检测模型：** OV-RCNN， RegionCLIP， Detic， VLDet等。

### 4. 资源与算力

*   **硬件与算力：**
    *   数据生成和处理阶段使用了包含**160个910B NPU**的集群，耗时分别为30天（阶段一数据重描述）和7天（FineHARD数据集构建）。
    *   模型训练阶段第一阶段的批次大小为每个NPU **384**，第二阶段为每个GPU **512**。使用了DeepSpeed Zero-2优化、Bfloat16或TF32精度加速。具体GPU型号未明确说明，但提及了NPU和GPU的使用。
*   **训练时长：** 文章明确指出两个阶段的训练均只进行了**一个Epoch**，这在充分利用大规模数据的同时，也暗示了极高的训练吞吐效率。

### 5. 实验数量与充分性

*   **实验数量：** 论文进行了非常广泛的实验，覆盖了不同模型大小（ViT-B/16, ViT-L/14）和大约10个下游任务基准，总计约十几组主要对比实验。
*   **消融实验：** 详细的消融研究（Table 6）系统地验证了每个核心组件（长描述/全局学习、区域对齐学习、困难负样本学习）的独立贡献，实验设计逻辑清晰，说服力强。
*   **充分性与公平性：**
    *   **充分性：** 实验覆盖了从区域级（边界框分类、细粒度理解）到图像级（检索、分类）再到通用多模态评估的全面任务，充分证明了方法的有效性。
    *   **公平性：** 对比了同期最新工作，并在同一基准下报告结果。特别是在Table 8中，FG-CLIP和FineCLIP在**相同数据集（12M）** 上的直接对比，增强了其性能归因于模型架构和训练方法的可信度。

### 6. 主要结论与发现

*   FG-CLIP在所有评估的细粒度任务上均**显著超越**了原始CLIP和其他SOTA方法，尤其在FG-OVD的 `hard` 子集上，提升幅度巨大（如ViT-L/14从15.4%提升至48.4%）。
*   引入的**困难负样本学习**是提升模型辨别细微语义差异能力的关键，消融实验证明了这一点。
*   FG-CLIP不仅能作为独立的视觉语言模型，还能有效作为**大型多模态模型的视觉编码器**，提升其在属性分析和物体定位任务上的性能。
*   高质量的、细粒度的**数据构建**对于提升模型深层理解能力至关重要。

### 7. 优点与亮点

*   **问题拆解与系统性创新：** 将“细粒度不足”这个宏大问题拆解为文本长度限制、对齐粒度和难例判别三个具体层面，并分别提出对应的创新解决方案，逻辑严密。
*   **数据集构建质量高：** FineHARD数据集的构建流程（LMM重描述->对齐->LLM生成负样本）设计精巧，规模宏大且质量可控，为后续研究提供了宝贵资源。
*   **硬负样本挖掘策略：** 专为细粒度任务设计，通过不改主体只改属性的方式生成假性相似的负样本，针对性强，效果显著。
*   **实验论证充分：** 尤其消融实验和可视化分析，非常直观地展示了各个组件的作用和模型的精准定位能力。

### 8. 不足与局限

*   **算力门槛高：** 16亿数据重描述和复杂的多阶段训练/数据构建流程极度依赖于强大的算力（如160个NPU集群），普通研究团队难以复现。
*   **数据偏差风险：** 重描述和负样本生成高度依赖于使用的LMM（如CogVLM2）和LLM（如Llama-3.1）的性能和内在偏见，这些大模型的错误可能会被引入并放大。
*   **真实世界覆盖有限：** 困难负样本的生成方式是模板化的（修改属性），可能与真实世界中更复杂多样的细粒度差异（如状态、关系、抽象概念）存在差距。
*   **训练效率细节缺失：** 尽管论文报告了仅训练1个Epoch，但未提供精确的单次训练时间或更具体的GPU型号，使得算力-效率的全貌不够清晰。

（完）
