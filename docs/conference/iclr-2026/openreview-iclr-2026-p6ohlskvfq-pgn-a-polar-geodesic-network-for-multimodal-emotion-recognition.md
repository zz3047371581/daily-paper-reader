---
title: "PGN: A Polar Geodesic Network for Multimodal Emotion Recognition"
title_zh: PGN：一种用于多模态情感识别的极地测地网络
authors: "Ruyi Wang, J. Michael Herrmann"
date: 2025-09-20
pdf: "https://openreview.net/pdf?id=p6ohlskvFq"
tags: ["query:affective-ai"]
score: 9.0
evidence: 基于心理径向结构的多模态情感识别极地测地网络，在MELD和IEMOCAP上评估。
tldr: "该论文针对多模态情感识别中的语义模糊、噪声及模态缺失问题，提出极地测地网络，将模态嵌入映射到径向空间，通过可靠性感知的测地融合保持圆形拓扑，并利用Transformer细化表示。在MELD和IEMOCAP数据集上分别达到68.35%和73.40%准确率，证明几何感知融合能有效提升多模态情感识别性能。"
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 多模态情感识别存在语义模糊、噪声和跨模态干扰，现有方法忽视情绪的径向几何结构，导致融合时积累方向噪声。
method: 将模态嵌入映射到径向空间，进行可靠性感知的测地融合以保持圆形拓扑，再用Transformer捕获跨维度交互。
result: 在统一冻结骨干协议下，PGN在MELD上达到0.6835准确率，IEMOCAP上达到0.7340准确率。
conclusion: 几何感知融合为多模态情感识别带来了互补增益。
---

## Abstract
Multimodal emotion recognition faces semantic ambiguity, significant noise, and cross-modal interference, including missing modalities. Psychological research supports a radial structure of emotions, yet many methods overlook this geometry and accumulate directional noise during fusion. The Polar Geodesic Network maps modality embeddings into a radial space, performs reliability-aware geodesic fusion to preserve circular topology, and then uses a Transformer to refine the fused representation and capture cross-dimensional interactions. Under a unified frozen-backbone protocol, PGN attains 0.6835 Accuracy and 0.6756 Weighted-F1 on MELD, and 0.7340 Accuracy and 0.690 Macro-F1 on IEMOCAP. Ablation results indicate complementary gains from geometry-aware fusion and the subsequent Transformer. These findings show that explicit modelling in radial space improves recognition accuracy and robustness.

---

## 论文详细总结（自动生成）

# 论文总结：PGN——用于多模态情感识别的极地测地网络

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：多模态情感识别面临**语义模糊、严重噪声、跨模态干扰**以及**模态缺失**等挑战。
- **研究背景**：心理学研究表明情绪具有**径向结构**，情绪的相似性与圆环拓扑有关；然而现有方法普遍**忽视这种几何特性**，在融合多模态特征时积累了**方向噪声**，导致识别精度和鲁棒性不足。
- **整体含义**：论文提出**显式在径向空间建模**，利用情绪的圆形拓扑来消除方向噪声，从而提升多模态情感识别的准确性和鲁棒性。

## 2. 论文提出的方法论
- **核心思想**：将不同模态的嵌入向量**映射到极地（径向）空间**，在圆形拓扑约束下进行融合，再通过Transformer细化融合表示。
- **关键技术流程**：
  1. **模态嵌入径向映射**：将每个模态的表示（如文本、语音、视觉）映射到统一的径向空间中，保留方向信息与幅度信息。
  2. **可靠性感知的测地融合**：根据每个模态嵌入的可靠性（幅度），在圆形流形上进行**测地线插值**以融合不同模态，从而保持圆形拓扑结构，减少方向噪声的累积。
  3. **Transformer细化**：融合后的表示送入Transformer，捕捉跨维度（如角度与强度）的交互，进一步优化最终的情感表征。
- **公式/算法流程**：文中未给出具体公式，但整体为 **“映射→测地融合→Transformer精炼”** 三阶段流水线。

## 3. 实验设计
- **数据集**：
  - **MELD**（多模态多方对话情感数据集）
  - **IEMOCAP**（互动情感二元多模态捕捉数据集）
- **评价指标**：
  - MELD：准确率（Accuracy）、加权F1（Weighted-F1）
  - IEMOCAP：准确率（Accuracy）、宏F1（Macro-F1）
- **对比协议**：采用**统一冻结骨干网络协议**（unified frozen-backbone protocol），确保不同方法在相同特征提取器下公平比较。
- **对比方法**：文中未列出具体对比模型名称，但通过此协议与现有主流多模态情感识别方法进行对比。

## 4. 资源与算力
- 所提供文本**未提及**使用的GPU型号、数量、训练时长等算力细节。
- 因此无法给出具体的算力总结。可能存在原文中省略或因页面屏蔽未展示，需阅读完整论文获取。

## 5. 实验数量与充分性
- 从摘要和元数据可知至少做了以下实验：
  - 在两个标准数据集（MELD、IEMOCAP）上的主流指标评测。
  - **消融实验**（ablation results），以验证几何感知融合与后续Transformer的互补增益。
- 实验覆盖两个对话情感识别基准，消融实验验证了各模块的有效性，**整体设计较为充分**。
- 公平性方面，采用统一冻结骨干协议，减少了特征提取差异带来的偏差，实验对比**相对客观**。

## 6. 论文的主要结论与发现
- PGN在MELD上达到 **0.6835准确率、0.6756加权F1**，在IEMOCAP上达到 **0.7340准确率、0.690宏F1**。
- 显式建模情绪的径向几何结构能有效**提升识别精度和鲁棒性**。
- 几何感知融合（测地融合）与后续Transformer构成 **互补增益**，二者结合效果优于单独使用。
- 说明将心理学上的圆形拓扑引入多模态融合是一种有效路径。

## 7. 优点（方法与实验设计亮点）
- **创新性几何融合**：首次将情绪的径向心理学结构转化为极地空间中的测地融合策略，针对性地解决方向噪声问题。
- **模块化设计**：映射、融合、精炼三阶段清晰，易于理解和扩展。
- **公平对比协议**：采用统一冻结骨干，避免因视觉/文本骨干差异造成的性能虚高。
- **可靠性感知机制**：融合时考虑模态嵌入的幅度（可靠性），增强了缺失或噪声模态下的鲁棒性。

## 8. 不足与局限
- **实验覆盖范围**：仅在两个英文对话数据集上测评，缺乏对其他语言、更多样化场景（如独白、电影片段）的验证。
- **未提供技术细节**：摘要中未呈现具体测地融合公式、损失函数等，难以判断数学实现。
- **算力需求不明**：论文未报告计算量、推理速度等效率指标，实际部署成本未知。
- **对比方法不详**：摘要未列出所比方法的具体名称和性能，无法评估当前领先性。
- **偏差风险**：数据集本身存在标注主观性，且MELD和IEMOCAP均为英语多模态，地理/文化泛化性未验证。

（完）
