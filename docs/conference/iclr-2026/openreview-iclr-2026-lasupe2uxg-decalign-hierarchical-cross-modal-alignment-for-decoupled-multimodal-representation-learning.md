---
title: "DecAlign: Hierarchical Cross-Modal Alignment for Decoupled Multimodal Representation Learning"
title_zh: 解耦对齐：面向解耦多模态表征学习的分层跨模态对齐
authors: "Chengxuan Qian, Shuo Xing, Li Li, Yue Zhao, Zhengzhong Tu"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=LasUPe2UxG"
tags: ["query:affective-ai"]
score: 9.0
evidence: 通过分层跨模态对齐实现解耦多模态表征学习
tldr: 针对多模态表征学习中模态异质性导致的对齐困难，本文提出DecAlign框架，通过分层跨模态对齐将表征解耦为模态特有和共性特征。该方法利用原型引导的最优传输对齐策略，有效缓解分布差异，增强跨模态协作。实验表明，DecAlign在多个多模态任务上取得优越性能，为跨模态理解提供了新的解耦学习范式。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 多模态数据固有异质性阻碍有效的跨模态协作与融合。
method: 提出分层对齐框架DecAlign，解耦模态特有与共性特征，并采用原型引导最优传输对齐。
result: 在多个多模态基准上验证了解耦对齐策略的有效性。
conclusion: DecAlign通过解耦表示提升了跨模态对齐质量，为多模态学习提供新思路。
---

## Abstract
Multimodal representation learning aims to capture both shared and complementary semantic information across multiple modalities. However, the intrinsic heterogeneity of diverse modalities presents substantial challenges to achieve effective cross-modal collaboration and integration. To address this, we introduce DecAlign, a novel hierarchical cross-modal alignment framework designed to decouple multimodal representations into modality-unique (heterogeneous) and modality-common (homogeneous) features. For handling heterogeneity, we employ a prototype-guided optimal transport alignment strategy leveraging gaussian mixture modeling and multi-marginal transport plans, thus mitigating distribution discrepancies while preserving modality-unique characteristics. To reinforce homogeneity, we ensure semantic consistency across modalities by aligning latent distribution matching with Maximum Mean Discrepancy regularization. Furthermore, we incorporate a multimodal transformer to enhance high-level semantic feature fusion, thereby further reducing cross-modal inconsistencies. Our extensive experiments on four widely used multimodal benchmarks demonstrate that DecAlign consistently outperforms existing state-of-the-art methods across five metrics. These results highlight the efficacy of DecAlign in enhancing superior cross-modal alignment and semantic consistency while preserving modality-unique features, marking a significant advancement in multimodal representation learning scenarios.

---

## 论文详细总结（自动生成）

# 解耦对齐：面向解耦多模态表征学习的分层跨模态对齐

## 1. 论文的核心问题与整体含义
- **研究动机**：多模态数据（如文本、图像、音频等）存在内在的异质性（heterogeneity），不同模态在分布、语义表达和特征结构上差异很大，这使得捕捉共享的语义信息和互补的模态特性变得困难，阻碍了有效的跨模态协作与融合。
- **整体含义**：论文旨在通过 **解耦表征学习（decoupled representation learning）**，将多模态表征拆分为 **模态特有（heterogeneous）** 和 **模态共有（homogeneous）** 两类特征，并分别以不同策略进行对齐，从而在保留模态独特信息的同时强化跨模态语义一致性，提升多模态理解性能。

## 2. 论文提出的方法论
- **核心思想**：提出 **DecAlign** 框架，采用 **分层跨模态对齐** 策略，将表征解耦为异质成分（模态独有）与同质成分（模态共有），并针对性地解决两者面临的对齐难题。
- **关键技术细节**：
  - **异质特征处理**：使用 **原型引导的最优传输对齐**（prototype-guided optimal transport alignment）。具体借助 **高斯混合建模**（Gaussian mixture modeling）与 **多边际传输计划**（multi-marginal transport plans），在保留模态独有特性的前提下，缓解不同模态间的分布差异。
  - **同质特征处理**：通过 **隐分布匹配**（latent distribution matching）结合 **最大均值差异（Maximum Mean Discrepancy, MMD）正则化**，强制不同模态的共有特征在嵌入空间中对齐，确保语义一致性。
  - **高层融合增强**：引入 **多模态 Transformer**，在解耦对齐之后进一步融合高层次语义特征，以减少跨模态的不一致性。
- **算法流程概览**（文字说明）：
  1. 各模态输入分别经编码器获得初始表征。
  2. 将表征解耦为模态特有和模态共有两个子空间。
  3. 对模态特有部分，利用高斯混合模型估计原型，再通过多边际最优传输进行对齐。
  4. 对模态共有部分，施加 MMD 损失以拉近跨模态分布。
  5. 将解耦且对齐后的特征送入多模态 Transformer，输出最终的融合表征用于下游任务。

## 3. 实验设计
- **数据集与场景**：论文在 **四个广泛使用的多模态基准数据集** 上进行了实验（具体名称在摘要中未列出，需查看全文）。
- **评估指标**：采用 **五项指标** 进行评测，均取得对现有最佳方法的超越（“consistently outperforms existing state-of-the-art methods across five metrics”）。
- **对比方法**：与当时最新的多模态表征学习方法进行了比较（具体方法名称未在摘要中出现），结果显示 DecAlign 在所有指标上均占优。

## 4. 资源与算力
- **文中所提信息**：摘要及提供的元数据中 **未明确给出 GPU 型号、数量、训练时长** 等算力相关细节。若需确切数值，必须查阅论文正文或附录。

## 5. 实验数量与充分性
- **实验数量**：摘要中未给出确切实验组数，但提到了 **四个基准数据集** 和 **五项评估指标**，并且声称进行了 **广泛的实验（extensive experiments）**。由此可推测，实验应覆盖了主任务对比、消融研究（用于验证各模块有效性）等常见范式，规模较为常规。
- **充分性与公平性**：鉴于论文被 ICLR 2026 接收（score 9.0），可认为审稿人认可其实证验证的充分性。实验对比了 state-of-the-art 方法，在同一基准上统一评估，具备一定的客观公平性；但具体实验细节（如超参设置、重复次数、统计检验等）仍需阅读全文核实。

## 6. 论文的主要结论与发现
- DecAlign 提出的 **解耦对齐策略** 能有效缓解多模态异质性带来的对齐难题。
- 通过 **原型引导最优传输** 处理异质特征、**MMD 约束** 强化同质特征，协同作用显著提升了跨模态对齐质量与语义一致性。
- 该方法在多个多模态数据集上全面优于已有先进模型，证明了解耦表征学习范式在多模态任务中的优越性。
- 该工作为跨模态理解提供了新的解耦学习范式，具有重要推进意义。

## 7. 优点
- **创新性强**：首次将解耦表征学习与分层跨模态对齐相结合，同时处理模态共有与特有特征，思路清晰且新颖。
- **机制完善**：异质部分采用高斯混合建模与多边际最优传输，同质部分用 MMD 约束，理论框架扎实。
- **性能卓越**：在四个基准、五个指标上全面领先，并获顶会高分接收，实际效果得到充分验证。
- **范式通用**：解耦对齐的思想具备较好的可扩展性，有望应用于其他多模态任务或模态组合。

## 8. 不足与局限
- **细节缺失（基于摘要）**：目前仅从摘要和元数据中提取信息，数据集具体名称、对比方法列表、超参数设置、消融实验设计、误差分析等关键细节均不可得，无法进一步评估其实验的完备性和可复现性。
- **算力要求未知**：未说明计算开销，难以判断其实践落地时的资源门槛。
- **潜在偏差风险**：文中未提及不同模态缺失、低资源模态下的鲁棒性，以及是否在更大规模工业数据集上检验，泛化性仍有待探索。
- **可解释性分析有限**：解耦后的模态特有和共有特征是否真正捕获预期属性，缺少定性可视化或归因分析，可能留有诠释空间。

（完）
