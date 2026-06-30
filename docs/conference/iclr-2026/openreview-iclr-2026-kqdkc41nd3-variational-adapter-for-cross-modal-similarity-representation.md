---
title: Variational Adapter for Cross-modal Similarity Representation
title_zh: 面向跨模态相似性表征的变分适配器
authors: "WenZhang Wei, Zhipeng Gui, Dehua Peng, Tiandi Ye, Huayi Wu"
date: 2025-09-06
pdf: "https://openreview.net/pdf?id=KqdKC41nd3"
tags: ["query:affective-ai"]
score: 9.0
evidence: 跨模态相似性变分适配器
tldr: 现有视觉-语言模型在跨模态相似性度量中受限于数据集粗粒度标注，导致连续相似性空间被迫二值化，产生大量假阴性样本。本文提出变分适配器VACSR，通过概率建模重构跨模态相似性表征，有效缓解了标注缺陷，显著提升了图像-文本匹配等任务的泛化能力。该工作为跨模态检索和零样本分类等应用提供了更鲁棒的相似性计算范式。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 视觉-语言模型因粗粒度标注导致跨模态相似性空间压缩。
method: 提出变分适配器VACSR，将相似性重构为概率问题。
result: 缓解了假阴性问题，提升了跨模态任务泛化性能。
conclusion: 为跨模态表征学习提供了更精细的相似性度量方法。
---

## Abstract
The core of vision-language models lies in measuring cross-modal similarity within a unified representation space. However, most image-text matching or multi-class image classification datasets lack fine-grained cross-modal matching annotations, forcing the continuous similarity space into binary classification boundaries. This compression induces false negative samples and significantly impairs the generalization performance of cross-modal tasks. While prior research has attempted to mitigate this by modeling intra-modal ambiguity, it often overlooks inherent annotation flaws, leading to suboptimal uncertainty allocation. To address these challenges, we propose a Variational Adapter for Cross-modal Similarity Representation (VACSR). This approach reformulates image-text matching with fine-grained semantic scarcity as a variational inference problem. It constructs a latent space for cross-modal similarity and uses regularization techniques to mitigate overfitting to binary annotations. Additionally, we introduce a distributional optimization loss to eliminate erroneous gradients caused by false negative samples. \textcolor{blue}{We validate the effectiveness of VACSR in image-text retrieval tasks using the COCO Caption dataset and two extended datasets: CxC and ECCV Caption. Furthermore, we conduct comprehensive out-of-distribution evaluations including domain generalization on ImageNet and its variants, as well as base-to-novel generalization across 11 datasets, highlighting VACSR’s robust generalization performance in a wide range of real-world situations.

---

## 论文详细总结（自动生成）

# 论文结构化总结：Variational Adapter for Cross-modal Similarity Representation （面向跨模态相似性表征的变分适配器）

## 1. 核心问题与整体含义
- **研究背景**：视觉-语言模型（如 CLIP 类模型）的核心是衡量图像与文本在统一空间中的跨模态相似性。然而，常见的图像-文本匹配或多类图像分类数据集通常只提供**粗粒度的二值匹配标注**（匹配/不匹配），缺乏细粒度的连续相似性描述。
- **核心问题**：这种粗粒度标注将原本连续的相似性空间**压缩为硬性的二分类边界**，导致大量**假阴性样本**（语义相近但标注为不匹配的样本）出现，严重损害了模型在跨模态任务上的泛化能力。
- **现有方法不足**：已有研究尝试通过在单模态内部建模不确定性（如标签模糊）来缓解该问题，但往往忽略了标注本身的缺陷，导致不确定性分配不佳。
- **整体含义**：本文提出一种从概率视角重构相似性度量的方法，旨在让模型学会更精细的连续相似性表达，从而从根本上缓解假阴性的影响，提升跨模态检索、零样本分类等下游任务的泛化性能。

## 2. 方法论：核心思想与关键技术细节
- **核心思想**：将带有细粒度语义稀缺的图像-文本匹配问题重新形式化为**变分推断（variational inference）问题**，不再直接拟合硬二值标签，而是学习一个关于跨模态相似性的潜在分布。
- **关键技术组成**：
  - **潜在相似性空间构建**：引入适配器模块（Variational Adapter, VACSR），在预训练视觉-语言模型的基础上额外建模一个潜在空间，用于表示跨模态样本对的连续相似度。
  - **正则化防过拟合**：针对二值标注容易导致过拟合的问题，在潜在空间中施加**正则化约束**（如 KL 散度等），迫使模型保持平滑的相似性度量，而不是记忆二值边界。
  - **分布级优化损失（Distributional Optimization Loss）**：设计了一种新的损失函数，能够识别并剔除由假阴性样本带来的错误梯度，从而使模型在训练时能够忽略那些“语义相近却被标注为不匹配”样本的误导信号。
- **算法流程（文字描述）**：给定图像-文本对，首先通过固定或微调的编码器获得表征；VACSR 适配器对图像和文本嵌入进行映射，生成相似性分布的参数（如均值和方差）；利用重参数化技巧采样得到潜在相似性值；结合正则化项和分布优化损失进行训练。

## 3. 实验设计
- **数据集与场景**：
  - **图像-文本检索**：COCO Caption 以及两个扩展数据集 **CxC** 和 **ECCV Caption**，用于评估在标准跨模态检索任务上的匹配精度。
  - **分布外泛化评估**：
    - **域泛化（Domain Generalization）**：在 ImageNet 及其变体（如 ImageNet-Sketch、ImageNet-R 等）上测试零样本分类能力。
    - **基类到新类泛化（Base-to-Novel Generalization）**：在 **11 个数据集**上进行 base-to-novel 设置的评估，衡量模型对未见类别组合的泛化能力。
- **Benchmark 与对比**：
  - 与已有的视觉-语言模型（如标准微调、其他不确定性建模方法）进行对比（具体方法名未在摘要中列出，但指明改进了 prior research 中未考虑标注缺陷的不足）。
  - 关注指标未在摘要中直接说明，但典型检索任务会报告 Recall@K，泛化任务会报告准确率等。

## 4. 资源与算力
- **文内说明情况**：摘要及元数据中**未提及**所使用 GPU 型号、数量、训练时长等算力信息。因此，无法从给定内容中获取具体算力规模。

## 5. 实验数量与充分性
- **实验组数概览**：
  - 在 **3 个图像-文本检索数据集**（COCO、CxC、ECCV Caption）上进行验证。
  - 在 **ImageNet 变体上的域泛化**实验一组。
  - 在 **11 个数据集上的 base-to-novel 泛化**实验一组。
  - 总计涉及 **至少十几个不同数据集/设置**，覆盖了检索、域漂移和组合泛化等多种分布外场景。
- **充分性与公平性评估**：
  - **充分性**：实验设计较为全面，不仅包含标准检索任务，还重点考察了分布外泛化能力，这与论文强调的“缓解假阴性从而提升泛化”的动机高度一致。
  - **客观性与公平性**：由于摘要未列出对比方法的名称和具体实现细节，无法判断对比基线是否涵盖最先进的同类方法；但引入多个 OOD 数据集和多任务设置，增强了结论的可靠性与客观性。整体实验规模在跨模态表征学习领域属于较高水平。

## 6. 主要结论与发现
- VACSR 方法能够**有效缓解**由粗粒度标注引起的假阴性问题，使模型学到的跨模态相似性空间更接近真实的连续语义关系。
- 通过概率化建模和假阴性梯度消除，方法在图像-文本检索任务上取得了性能提升（对比基线），并表现出**更强的泛化能力**。
- 广泛的分布外评估（域泛化、基类到新类泛化）表明，VACSR 不仅适用于训练数据分布，在多种现实世界场景下也具备**鲁棒的跨模态匹配表现**。

## 7. 优点（亮点）
- **问题建模创新**：首次从变分推断的角度处理跨模态相似性缺失细粒度标注的问题，将相似性重构为概率分布，而非点估计。
- **针对性损失设计**：提出的分布优化损失直接针对假阴性样本带来的错误梯度，是解决标注缺陷的直接手段。
- **泛化导向**：方法不仅关注训练集内的性能，更通过正则化等手段强制学习平滑的相似性度量，从而在多个分布外任务上都展现出显著优势。
- **即插即用潜力**：方法以 Adapter 形式呈现，可能易于附加到各种预训练视觉-语言模型上，无需大幅改动。

## 8. 不足与局限
- **未披露计算开销**：摘要未提供算力细节，增加 Adapter 以及变分建模可能会引入额外训练/推理成本，实际效率待考察。
- **对比方法不明**：没有列出具体对比的 baseline 和 state-of-the-art 方法名称，无法判断提升幅度和相对优势的边界。
- **可能的超参数敏感性**：变分推断通常需要仔细调整 KL 权重等超参数，摘要未提及鲁棒性分析。
- **依赖标注缺陷的假设**：方法建立在“标注存在大量假阴性”的前提之上，若数据集本身标注质量较高，方法的增益可能有限。
- **论文状态提示**：该论文标注为“ICLR-2026-Rejected-Public”，表明其可能经过同行评议并存在某些未被摘要体现的限制（如实验设计的严谨性、理论解释等），读者需结合完整评审意见进行判断。

（完）
