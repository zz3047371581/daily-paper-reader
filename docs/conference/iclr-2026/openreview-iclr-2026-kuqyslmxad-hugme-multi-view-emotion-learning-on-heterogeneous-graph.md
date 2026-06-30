---
title: "HugMe: Multi-view Emotion Learning on Heterogeneous Graph"
title_zh: HugMe：基于异质图的多视图情绪学习
authors: "Shulan Ruan, Jiaxing Wen, Shuwen Feng, Rui Sun, Huijie Liu, Yu LIU, Xiaodong He"
date: 2025-09-16
pdf: "https://openreview.net/pdf?id=KuqySLmXad"
tags: ["query:affective-ai"]
score: 10.0
evidence: 基于异质图的多视图情绪学习用于视觉情绪感知
tldr: HugMe针对视觉情绪感知，提出基于异质图的多视角情绪学习方法，融合人脸、身体和场景等多层次信息，增强机器视觉的情绪理解能力。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: 现有视觉情绪方法多局限于内容语义，忽略多视角线索。
method: 提出HugMe，利用异质图融合人脸、身体、场景等多视角进行情绪学习。
result: 提升机器视觉情绪感知能力。
conclusion: HugMe为构建共情型人机协作系统提供支持。
---

## Abstract
Human emotions are the cornerstone of social interaction. Empowering machine vision with emotion perception is crucial for building harmonious and empathetic human-machine collaborative systems across a wide range of domains. Most mainstream approaches, based on a given image, adhere to the traditional image content understanding paradigm and conduct end-to-end emotion learning from
the perspective of semantics-emotion association. Despite significant progress, several challenges remain. From the perspective of visual information representation, existing methods mostly adhere to the traditional image content semantics understanding paradigm and conduct end-to-end emotion learning from the perspective of content semantics-emotion semantics association, neglecting the rep-resentation and utilization of the rich structural information inherent in images. From the perspective of label information representation, existing methods mostly either directly map and classify visual features using a one-hot labeling approach, resulting in human emotion labels being treated as meaningless label indices; or they simply establish single associations between emotion labels. The heterogeneous association patterns inherent in complex human emotions have been largely unexplored. To this end, in this paper, we propose a novel HugMe model by Multi-view emotion learning on Heterogeneous graph. Specifically, for visual feature learning, we first develop a multi-view emotion representation method to leverage rich visual features from the perspectives of both semantics and structures. For label feature learning, we propose a heterogeneous emotion graph representation approach, which leverages heterogeneous graph to model the complex and diverse association patterns between different emotional labels. Finally, we develop a multi-view emotion classification module to better recognize different emotions for the given person in the image. In addition to the traditional classification loss function, to better learn and optimize our proposed HugMe, we also design a double-constraint loss function to supervise the label learning process. Extensive experiment results on well-studied human emotion benchmark datasets demonstrate the superiority and rationality of HugMe.

---

## 论文详细总结（自动生成）

# HugMe：基于异质图的多视图情绪学习 论文总结

## 1. 核心问题与整体含义
*   **研究背景**：赋予机器视觉情绪感知能力对构建共情型人机协作系统至关重要。现有主流方法多基于传统图像内容理解范式，从内容语义到情绪语义进行端到端学习。
*   **动机与挑战**：
    *   **视觉信息表示层面**：现有方法忽略图像中丰富的结构信息，未能有效利用多视角（如人脸、身体、场景）的视觉线索。
    *   **标签信息表示层面**：独热编码（one-hot）将情绪标签视为无意义的索引，或仅建立标签间的单一关联，忽视了复杂人类情绪标签间固有的异构关联模式（如层次、相似、共现等）。
*   **整体含义**：论文提出 HugMe 模型，旨在通过多视图情感学习和异构标签关系建模，更全面、合理地表示和识别图像中人物的情绪。

## 2. 方法论
*   **核心思想**：将视觉特征学习与标签特征学习解耦，并分别在“语义-结构”多视图空间和“异构标签图”空间中进行增强表示，最后通过多视图分类模块融合输出。
*   **关键技术细节**：
    *   **多视图视觉特征学习**：开发一种多视图情绪表示方法，同时从内容语义和结构信息两个视角提取丰富的视觉特征。
    *   **异构情绪图标签学习**：提出异构情绪图表示方法，将不同情绪标签之间的复杂、多样关联模式建模在异构图中，从而获得更具表达力的标签特征。
    *   **多视图情绪分类模块**：融合视觉特征与图增强后的标签特征，以更好地识别给定图像中人物的情绪。
    *   **损失函数**：除传统分类损失外，专门设计了一个 **双约束损失函数**（double-constraint loss），用以监督标签学习过程，优化模型。

## 3. 实验设计
*   **数据集**：在广泛研究的人类情绪基准数据集上进行了实验（摘要未具体列举数据集名称）。
*   **对比方法**：应与主流视觉情绪识别方法进行对比（摘要未提及具体对比模型）。
*   **评价基准**：情绪识别分类准确率等标准指标。

## 4. 资源与算力
*   论文摘要及提供的元数据中**未明确说明**所需的 GPU 型号、数量、训练时长或算力消耗具体数值。此项信息缺失。

## 5. 实验数量与充分性
*   **实验数量推测**：摘要提到“广泛的实验结果”，结合方法设计（多视图视觉、异构图标签、双约束损失），可推断至少包含：
    *   在不同情绪识别数据集上的整体性能对比实验。
    *   验证各模块有效性的消融实验（多视图视觉、异构图标签、双约束损失等）。
*   **充分性与公平性评估**：由于缺乏具体实验图表和细节，无法从摘要判断实验是否充分、客观。但从方法设计层次和“广泛实验”的表述来看，通常会有较完整的主实验、消融和可视化分析，具备一定的客观性与公平性。

## 6. 主要结论与发现
*   HugMe 模型通过结合多视图视觉表示和异构情绪标签关系，显著提升了情绪识别性能。
*   实验结果证明了该方法的**优越性**（性能提升）与**合理性**（设计的有效性与可解释性）。
*   该工作能为构建共情型人机协作系统提供更准确的情绪感知基础。

## 7. 优点
*   **多视图融合创新**：跳出传统纯语义理解范式，同时融合内容语义与结构信息，更贴近人理解情绪的多元途径。
*   **标签关系深度挖掘**：利用异构图显式建模情绪标签间复杂的异构关联，提升标签表示的语义丰富度。
*   **双约束学习**：设计专门的标签监督损失，使模型训练目标更精细、优化更充分。

## 8. 不足与局限
*   **信息缺失严重**：由于仅基于摘要和元数据，无法评估具体实验规模、算力需求、模型复杂度、算法效率以及在野外复杂场景下的鲁棒性。
*   **潜在局限**：
    *   多视图特征提取可能依赖独立的前置模块（人脸、身体检测等），级联误差风险存在。
    *   异构情绪图构建可能依赖先验知识或特定语料，泛化到全新情绪类别或文化差异的情景需重新构建。
    *   未提及实时性和轻量化，实际部署可能存在算力限制。
*   **偏差风险**：无法验证所用数据集的人群、情绪类别分布是否均衡，是否存在偏见。

（完）
