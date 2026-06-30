---
title: Cross-Modal Redundancy and the Geometry of Vision–Language Embeddings
title_zh: 跨模态冗余与视觉-语言嵌入几何
authors: "Grégoire DHIMOÏLA, Thomas Fel, Victor Boutin, Agustin Martin Picard"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=VYQuICALXj"
tags: ["query:affective-ai"]
score: 9.0
evidence: 利用能量一致性对齐稀疏自编码器分析视觉-语言嵌入中的跨模态冗余，改善对齐几何
tldr: 针对视觉-语言模型共享嵌入空间几何理解不足的问题，提出等能量假设，并设计对齐稀疏自编码器在训练中强制模态间能量一致性以分析跨模态冗余。受控实验表明该归纳偏置在不影响重建的前提下改善了对齐质量，为理解VLM的表示几何和优化跨模态学习提供了新工具。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 视觉-语言模型嵌入空间几何缺乏深入理解。
method: 提出等能量假设，设计对齐稀疏自编码器强制能量一致性。
result: 自编码器改变了解结构，提升了跨模态对齐。
conclusion: 该工作揭示了能量一致性对跨模态表示对齐的重要性。
---

## Abstract
Vision–language models (VLMs) align images and text with remarkable success, yet the geometry of their shared embedding space remains poorly understood. 
To probe this geometry, we begin from the Iso-Energy Assumption, which exploits cross-modal redundancy: a concept that is truly shared should exhibit the same average energy across modalities.
We operationalize this assumption with an Aligned Sparse Autoencoder (SAE) that encourages energy consistency during training while preserving reconstruction.
We find that this inductive bias changes the SAE solution without harming reconstruction, giving us a representation that serves as a tool for geometric analysis.
Sanity checks on controlled data with known ground truth confirm that alignment improves when Iso-Energy holds and remains neutral when it does not.
Applied to foundational VLMs, our framework reveals a clear structure with practical consequences: 
**(*i*)** sparse *bimodal* atoms carry the entire *cross-modal* alignment signal; 
**(*ii*)** *unimodal* atoms act as *modality-specific* biases and fully explain the modality gap; 
**(*iii*)** removing unimodal atoms collapses the gap without harming performance; 
**(*iv*)** restricting vector arithmetic to the bimodal subspace yields in-distribution edits and improved retrieval. 
These findings suggest that the right inductive bias can both preserve model fidelity and render the latent geometry interpretable and actionable.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义  
- **研究动机**：视觉–语言模型（VLM）在图像和文本对齐上取得显著成功，但其共享嵌入空间的几何结构仍缺乏深入理解。  
- **核心问题**：如何揭示跨模态嵌入的几何特性，特别是图像和文本的冗余如何映射到潜在表示上，以及如何利用这种冗余提升对齐的可解释性和可控性。  
- **整体含义**：提出“等能量假设”（Iso‑Energy Assumption）——真正跨模态共享的概念应在不同模态中具有相同的平均激活能量。通过设计满足该假设的稀疏自编码器，论文旨在在保持模型重建能力的前提下，获得更可解释、更具操作性的几何表示，从而为跨模态学习提供新的分析工具和归纳偏置。

## 2. 论文提出的方法论  
- **核心思想**：将跨模态冗余形式化为**等能量约束**，并将其作为稀疏自编码器（SAE）训练时的归纳偏置。  
- **关键技术细节**：  
  - 提出**对齐稀疏自编码器（Aligned Sparse Autoencoder）**，在传统的稀疏重建损失之外，引入鼓励能量一致性的正则项。  
  - 训练过程中强制每个潜在原子在视觉和语言样本上的平均激活值（能量）相互接近。  
  - 该自编码器仍保持对原始嵌入的重建能力，因此不会显著损失模型保真度。  
- **算法流程（文字描述）**：  
  1. 从预训练的 VLM 中获取图像和文本的嵌入表示。  
  2. 对两种模态的嵌入分别训练一个稀疏自编码器，但其潜在字典共享或对齐。  
  3. 在损失函数中加入等能量惩罚项，使每个原子的模态间平均激活差异最小化。  
  4. 优化结束后的潜在表示即可作为几何分析工具，自然分解出“双模态”（跨模态共享）和“单模态”（模态特有）原子。

## 3. 实验设计  
- **受控数据验证**：  
  - 使用已知真实对齐结构的人工合成数据，进行健全性检查。  
  - 验证在真实跨模态冗余存在时，等能量偏置能提升对齐；在冗余不存在时，该偏置保持中性（不会引入虚假结构）。  
- **真实模型应用**：  
  - 将对齐稀疏自编码器应用于**基础性视觉–语言模型**（foundational VLMs，文中未指定具体模型名称，但暗示为广泛使用的大规模预训练模型）。  
  - 分析嵌入空间的几何结构、移除单模态原子的影响，以及在双模态子空间中进行向量算术和检索编辑。  
- **对比方法**：文中未明确罗列对比的基准方法，但隐含对比对象为标准稀疏自编码器（无等能量约束），通过比较几何结构和下游行为体现改进。

## 4. 资源与算力  
- **信息缺失**：所提供的摘要和元数据中**未说明**所用的 GPU 型号、数量、训练时长或计算量等资源信息。  

## 5. 实验数量与充分性  
- **实验规模推测**：  
  - 至少包含 **受控数据** 和 **真实 VLM** 两大类实验。  
  - 在真实模型上进行了多项分析实验：双模态原子识别、模态间隙解释、单模态原子移除、双模态子空间内的向量运算和检索编辑。  
- **充分性与公平性评估**：  
  - 受控实验提供了因果性检验，方法论的可靠性得到初步验证。  
  - 在基础 VLM 上的发现具有一般性，但未提供与多种 VLM 架构或尺度的横向比较，也未详细对比其他几何分析方法，实验覆盖面有限，部分结论的普适性待进一步确认。

## 6. 论文的主要结论与发现  
- **（i）** 稀疏的**双模态原子**承载了几乎全部的跨模态对齐信号。  
- **（ii）** **单模态原子**作为模态特有的偏置项，能够完整解释著名的“模态间隙”（modality gap）。  
- **（iii）** 移除所有单模态原子即可消除模态间隙，且**不损害模型性能**。  
- **（iv）** 将向量算术运算限制在双模态子空间中，能够产生符合分布内特性的编辑，并改进跨模态检索效果。  
- 总体结论：恰当的归纳偏置（等能量假设）可在保留模型忠实度的同时，使潜在几何变得可解释与可操作。

## 7. 优点  
- **新颖的几何视角**：首次将等能量假设引入跨模态冗余分析，提供了一种理论基础和操作手段。  
- **分析方法非侵入式**：对齐稀疏自编码器通过重建保真度约束，确保分析不严重扭曲原模型表示。  
- **因果验证严谨**：在受控数据上进行“有冗余/无冗余”的对照实验，证明偏置只在必要时生效，降低了误发现风险。  
- **发现具有实用价值**：所揭示的单/双模态原子结构和模态间隙的解释，可直接用于间隙消除、检索增强和可控编辑。

## 8. 不足与局限  
- **算力与实现细节未披露**：论文元数据中缺乏计算资源与训练代价的报告，可复现性受影响。  
- **模型与数据覆盖局限**：仅在“基础”VLM 上验证，未对比多种主流架构（如 CLIP、SigLIP、BLIP 等），也未讨论在不同规模、不同预训练策略下的几何稳定性。  
- **评估基准简略**：缺乏与现有几何分析方法（如线性探测、流形分析）的系统性量化比较，仅以受控检查和定性发现为主。  
- **应用风险未讨论**：移除单模态原子可能在某些需要模态特异性信息的任务（如图文不一致检测）中带来负面效应，未进行讨论。  
- **等能量假设的普适性未知**：该假设依赖于平均能量对齐，若模态能量分布存在本质不对称，偏置的有效性可能下降，需更多任务和领域验证。

（完）
