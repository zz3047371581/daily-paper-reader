---
title: Global and Fine-Grained Framework for CLIP with Cross-Modal Mamba in Few-Shot Image Classification
title_zh: 面向少样本图像分类的全局与细粒度CLIP跨模态Mamba框架
authors: "Junchen Cai, Zhi Chen, Qiaoqin Li, Rongyao Hu, Yongguo Liu"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=qz7g2MC32U"
tags: ["query:affective-ai"]
score: 8.0
evidence: 提出跨模态Mamba使CLIP相互编码文本和图像
tldr: GF4FC通过跨模态Mamba增强CLIP在少样本图像分类中的性能，实现文本与图像的动态交互编码，并保持线性时间复杂度，提升分类效果。
source: ICLR-2026-Public
selection_source: conference_retrieval
motivation: CLIP编码器独立运行，缺乏动态跨模态交互，限制了少样本分类性能。
method: 提出GF4FC，引入CLIMA模块利用Transformer和ViT相互编码文本与图像。
result: 在少样本分类上实现高效高精度，且保持线性时间复杂度。
conclusion: GF4FC展示了跨模态Mamba在视觉少样本任务中的有效性。
---

## Abstract
CLIP is a highly efficient cross-modal text-image embedding model with remarkable generalization ability. However, the encoders in CLIP usually operate independently without dynamic cross-modal interaction, leading to suboptimal performance in few-shot classification. Therefore, we propose a Global and Fine-Grained Framework for CLIP with Cross-Modal Mamba in Few-Shot Image Classification (GF4FC). Specifically, the CLIP with Cross-Modal Mamba module (CLIMA) is conducted to leverage Transformer and Vision-Transformer to interdependently encode text and image. These cross-modal representations then serve as mutual prompts to refine the embedding space, while the proposed Cross-Modal Mamba module ensures efficient time complexity. Moreover, we design a Fine-Grained Capture module (FGC) to enhance CLIMA's image representations using a Vssm module to extract prior fine-grained information. Furthermore, the Local Feature Supplementation (LFS) module is conducted to supplement CLIP's logits with FGC-derived fine-grained representations through a residual structure. Finally, the Adaptive Logits Fusion module is constructed to dynamically fuses logits using learned adaptive weights. Experiments on seven datasets demonstrate that GF4FC achieves superior performance compared with state-of-the-art methods in few-show image classification.

---

## 论文详细总结（自动生成）

# GF4FC 论文总结：面向少样本图像分类的全局与细粒度 CLIP 跨模态 Mamba 框架

## 1. 研究动机与核心问题
- **背景**：CLIP（Contrastive Language-Image Pre-training）是一种强大的跨模态嵌入模型，具有出色的泛化能力，在零样本分类等任务中表现出色。
- **核心问题**：在**少样本图像分类**场景下，标准的 CLIP 模型其文本编码器与图像编码器**独立运行**，缺乏动态的跨模态交互。这种“各自为政”的编码方式导致模型无法充分利用图文信息之间的互补性，从而使得分类性能难以达到最优。
- **整体含义**：本文旨在打破 CLIP 编码器间的独立性，通过引入高效的跨模态交互机制和细粒度特征增强，显著提升 CLIP 在少样本分类任务中的表现。

## 2. 方法论
论文提出了一个全局与细粒度结合的新框架 **GF4FC**，其核心由三个模块构成：
- **跨模态 Mamba 模块 (CLIMA)**：
  - 核心思想是让文本和图像**相互依赖地编码**。它利用 Transformer 和 Vision-Transformer 以对方模态的信息作为引导（互提示），对各自特征进行精炼，生成富含跨模态信息的联合表示。
  - 引入 **Cross-Modal Mamba** 结构来实现这种互编码，保证了模型的计算复杂度为**线性时间复杂度**，避免了传统交叉注意力机制的平方级开销。
- **细粒度捕捉模块 (FGC)**：
  - 为了进一步增强图像表示，该模块使用 **Vssm** (视觉状态空间模型) 模块，从图像中提取**先验的细粒度信息**，为分类提供更丰富的视觉线索。
- **局部特征补充与自适应融合 (LFS + Adaptive Logits Fusion)**：
  - **LFS 模块**：将 FGC 提取的细粒度表示通过**残差结构**补充到 CLIP 原始的预测结果 (logits) 中，强化局部判别力。
  - **自适应 Logits 融合**：最后，使用由学习得到的自适应权重，动态地融合来自不同路径的 logits，得出最终预测。

## 3. 实验设计
- **数据集**：在 **7 个公开数据集**上进行了评估，以验证方法的泛化能力（摘要中未列出具体数据集名称，推测可能涵盖通用物体、细粒度、场景等不同类别）。
- **基准设定**：遵循少样本图像分类的标准评测协议。
- **对比方法**：与当前最先进的（state-of-the-art）方法进行对比，结果显示 GF4FC 取得了更优的性能。

## 4. 资源与算力
- 论文摘要及所提供的元数据中**未明确提及**实现所用的 GPU 型号、数量、训练时长等具体算力信息。
- 仅在方法部分理论性地强调了跨模态 Mamba 模块的**线性时间复杂度**，暗示其计算效率较高，但缺乏实测的硬件开销数据。

## 5. 实验数量与充分性
- **实验规模**：在 7 个数据集上进行了主要实验对比，覆盖范围较广。
- **实验充分性**：鉴于方法包含多个子模块（CLIMA, FGC, LFS, 自适应融合），推测原文可能包含**消融实验**来验证各模块的有效性。然而，现有摘要**并未提供**消融研究、超参数设置或定量结果的任何细节，故无法在此判断其消融实验是否充分、客观。
- **公平性**：宣称与 SOTA 方法对比并取得优越性能，但未给出具体对比对象和性能数值，其对比的公平性有待原文验证。

## 6. 主要结论与发现
- **跨模态交互是有效的**：通过 CLIMA 模块实现的图文动态互编码，为少样本分类带来了显著的性能增益。
- **细粒度信息至关重要**：FGC 和 LFS 模块提取并融合的细粒度特征，有效补充了全局语义，进一步提升了分类精度。
- **高效率与高性能可兼得**：跨模态 Mamba 的设计使得模型在实现复杂跨模态交互的同时，保持了线性时间复杂度，证明了该框架在计算效率和分类效果上的双重优势。

## 7. 优点
- **创新性强**：首次将状态空间模型（Mamba）应用于 CLIP 的跨模态交互，提出了一种新颖且高效的 **Cross-Modal Mamba** 机制。
- **框架设计完整**：构建了一个从全局跨模态交互（CLIMA）到局部细粒度挖掘（FGC、LFS），再到自适应融合的多层次、结构清晰的框架。
- **兼顾效率与性能**：明确从方法设计上解决了传统交叉注意力的高计算量问题，实现了线性时间复杂度，这是当前大模型研究关注的重点。
- **验证较为广泛**：在多达 7 个数据集上进行了评估，体现了方法的潜在泛化能力。

## 8. 不足与局限
- **关键实验细节缺失**：摘要未透露任何数据集名称、具体对比方法、数值结果或超参数配置，严重影响了对其实际性能和实验严谨性的客观判断。
- **消融研究不明**：各个精心设计的模块（尤其是不同 Mamba 交互方式）究竟带来了多少独立贡献尚未可知。
- **应用范围受限**：目前仅验证了在少样本图像分类任务上的有效性，其在零样本学习、跨模态检索等其他 CLIP 主流下游任务上的表现有待探索。
- **潜在偏差风险**：作为基于 CLIP 的方法，其性能上限可能受限于 CLIP 预训练权重本身的偏差和知识边界，文中未讨论此局限。

（完）
