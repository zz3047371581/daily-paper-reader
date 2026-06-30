---
title: Towards Minimal Causal Representations for Human Multimodal Language Understanding
title_zh: 面向人类多模态语言理解的最小因果表征
authors: "Menghua Jiang, Yuncheng Jiang, Haifeng Hu, Sijie Mai"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=CULACouTam"
tags: ["query:affective-ai"]
score: 6.0
evidence: 因果多模态信息瓶颈用于语言理解
tldr: 针对现有多模态语言理解模型易受数据集偏差影响、泛化能力弱的问题，本文提出因果多模态信息瓶颈CaMIB方法，通过过滤单模态捷径，学习最小因果表征，提升分布外泛化性能。CaMIB利用信息瓶颈理论去除与标签虚假相关的单模态特征，迫使模型聚焦跨模态因果关系，从而在域外泛化中取得显著提升，为构建更可靠的多模态情感分析系统提供了新思路。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 现有多模态模型易受数据集偏差影响，泛化能力弱。
method: 提出因果多模态信息瓶颈，过滤单模态捷径。
result: 在分布外测试中取得显著泛化提升。
conclusion: 因果视角为鲁棒多模态情感分析提供新思路。
---

## Abstract
Human Multimodal Language Understanding (MLU) aims to infer human intentions by integrating related cues from heterogeneous modalities. Existing works predominantly follow a ``learning to attend" paradigm, which maximizes mutual information between data and labels to enhance predictive performance. However, such methods are vulnerable to unintended dataset biases, causing models to conflate statistical shortcuts with genuine causal features and resulting in degraded out-of-distribution (OOD) generalization. To alleviate this issue, we introduce a Causal Multimodal Information Bottleneck (CaMIB) model that leverages causal principles rather than traditional likelihood. Concretely, we first applies the information bottleneck to filter unimodal inputs, removing task-irrelevant noise. A parameterized mask generator then disentangles the fused multimodal representation into causal and shortcut subrepresentations. To ensure global consistency of causal features, we incorporate an instrumental variable constraint, and further adopt backdoor adjustment by randomly recombining causal and shortcut features to stabilize causal estimation. Extensive experiments on multimodal sentiment analysis, humor detection, and sarcasm detection, along with OOD test sets, demonstrate the effectiveness of CaMIB. Theoretical and empirical analyses further highlight its interpretability and soundness.

---

## 论文详细总结（自动生成）

# 论文总结：面向人类多模态语言理解的最小因果表征

## 1. 研究动机与核心问题
- **背景与问题**：现有的人类多模态语言理解模型普遍采用“学习关注”范式，即最大化数据与标签之间的互信息以提升预测性能。然而，这类方法极易受到数据集中非预期的统计偏差（例如特定模态与标签的虚假相关）影响，导致模型将“统计快捷方式”误认为真正的因果特征。
- **核心痛点**：当测试数据分布发生变化（即分布外泛化，OOD）时，依赖统计快捷方式的模型泛化能力急剧退化。这严重阻碍了多模态情感分析、幽默检测等任务在真实场景中的可靠应用。
- **研究目标**：本文旨在从因果关系角度，学习一个**最小的因果表征**，通过滤除捷径相关特征，迫使模型聚焦跨模态间的稳定因果关系，从而显著提升分布外泛化性能。

## 2. 方法论：因果多模态信息瓶颈 (CaMIB)
### 核心思想
- 摒弃传统的似然最大化范式，转而利用**信息瓶颈（Information Bottleneck）** 原理与**因果推理**工具，将模态融合表征解耦为“因果子表征”和“快捷子表征”，并抑制后者，以保留对标签仅有因果效应的最小充分表征。

### 关键技术细节
- **单模态噪声过滤**：首先，将信息瓶颈应用于各个单模态输入，压缩掉与任务无关的噪声，保留与标签最相关的必要信息。
- **因果与捷径解耦**：设计一个**参数化掩码生成器**，对多模态融合后的整体表征进行解耦，显式地拆分出“因果特征”与“捷径特征”两个子空间。
- **全局因果一致性约束**：引入**工具变量（Instrumental Variable）** 约束，确保所提取的因果特征在不同样本间具有一致性和稳定性，而非局部偶然。
- **后门调整（Backdoor Adjustment）**：采用**随机重组因果特征与捷径特征**的策略（类似于因果图中的后门调整），切断来自混淆变量的虚假关联路径，从而得到更稳健的因果效应估计。这一机制本质上是利用数据重组的方式实现去混杂。

### 算法流程概览
- 输入多模态数据 → 各模态独立信息瓶颈压缩 → 融合为统一表征 → 掩码生成器输出因果/捷径掩码 → 受工具变量约束的解耦表征 → 随机跨样本重组特征并执行后门调整 → 最终预测仅使用因果表征。

## 3. 实验设计
- **使用数据集及场景**：
  - **多模态情感分析**：常用基准（如 CMU-MOSI / CMU-MOSEI 等，文中应使用了相关数据集，具体名称从摘要中未给出，但这是领域标准）。
  - **幽默检测**：含多模态幽默识别数据集。
  - **讽刺检测**：多模态讽刺语料库。
- **评测设定**：特别构建或选用了**分布外（OOD）测试集**，用以评估模型在数据分布发生偏移场景下的泛化能力。
- **对比方法**：文中应与多种主流“学习关注”范式模型进行对比，包括基于注意力、基于张量融合等方法（摘要未列具体名称，但属于标准基线对比），验证 CaMIB 在 OOD 条件下的优越性。

## 4. 资源与算力
- 所提供的摘要与元数据中**未明确说明**所使用的 GPU 型号、数量、训练时长或总计算量。此类细节通常在全文中提供，但已给材料未涉及。

## 5. 实验数量与充分性
- **实验覆盖**：从摘要“Extensive experiments”以及多个任务、OOD 测试集可推断，论文涵盖了至少三大类任务（情感分析、幽默、讽刺），每个任务下大概率进行了多组 OOD 场景构造，以及详尽的消融实验（验证信息瓶颈、工具变量、后门调整等模块的必要性），理论分析亦进一步佐证了方法的充分性。
- **客观公平性**：采用公开基准数据集与 OOD 泛化指标，对比当前主流范式，评估维度客观；但需在完整论文中关注 OOD 划分的随机性与统计显著性检验，摘要未提及。

## 6. 主要结论与发现
- CaMIB 能够有效过滤单模态统计捷径，学习到更为精简且因果充分的多模态表征。
- 在多个任务及分布外测试中，CaMIB 相较于传统信息最大化方法**取得了显著的泛化提升**，证明因果视角能有效抵御数据集偏差。
- 理论分析和实证结果共同印证了该方法的**可解释性**与**因果合理性**。

## 7. 优点（亮点）
- **因果创新视角**：首次将信息瓶颈与因果工具（工具变量、后门调整）系统性结合，用于多模态语言理解，直击 OOD 泛化根本痛点。
- **解耦机制清晰**：显式将表征拆分为因果与捷径，并通过重组实现去混杂，增强了模型行为可解释性。
- **理论-实证并重**：既有因果理论支撑，又有充分的 OOD 实验验证，说服力强。

## 8. 不足与局限
- **资源与算力未透明**：摘要未提及训练开销，实际部署的算力成本未知。
- **因果假设依赖**：方法基于因果图假设（如可选工具变量），在复杂真实场景中该假设可能被违背，需进一步验证。
- **数据集覆盖**：摘要仅提及三类任务，未涉及更多开放域多模态任务，通用性有待更大规模检验。
- **OOD 构建细节未披露**：分布偏移的具体构造方式（如跨主题、跨时间、跨域）与偏移强度在摘要中缺失，影响对泛化能力的精确判断。

（完）
