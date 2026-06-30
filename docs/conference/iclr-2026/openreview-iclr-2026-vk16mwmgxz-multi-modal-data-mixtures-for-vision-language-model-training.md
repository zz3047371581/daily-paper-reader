---
title: Multi-modal Data Mixtures for Vision-Language Model Training
title_zh: 用于视觉语言模型训练的多模态数据混合方法
authors: "Wanyun Xie, Francesco Tonin, Volkan Cevher"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=vk16mWMGXz"
tags: ["query:affective-ai"]
score: 9.0
evidence: 自动确定视觉语言模型训练的多模态数据混合以提升跨模态对齐
tldr: 视觉语言模型训练通常依赖昂贵的手动调优数据混合。本文提出MMix框架，通过模态感知对齐最大化来自动化确定多模态数据配比，并能处理模态缺失场景。实验在0.5B和7B模型上证明，MMix以微小的计算开销显著提升多基准准确率，并匹配专家调优性能，为VLM高效训练提供了自动化解决方案。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: VLM训练依赖人工调优数据混合，成本高且效率低，影响模态对齐。
method: 提出MMix框架，通过模态感知对齐最大化自动确定域混合比例，处理模态缺失，集成纯语言域。
result: 在0.5B和7B VLM上，MMix以边际计算成本提升多基准准确率，匹配专家调优效果。
conclusion: 实现高效自动化的多模态数据配比，推动VLM训练范式的进步。
---

## Abstract
Vision-Language models (VLMs) are typically trained on a diverse set of multi-modal domains, yet current practices rely on costly manual tuning. This paper introduces MMix, a principled framework for automatically determining multi-modal data mixtures for VLM training. We formulate this task as a modality-aware alignment maximization over domains, deriving multi-modal alignment scores from the dual solution through inter-modal coupling variables. Our method is crucially designed to handle domains with missing modalities, allowing for the systematic integration of language-only domains. In experiments on both 0.5B and 7B VLMs, MMix boosts accuracies on diverse evaluation benchmarks with marginal computational cost. Remarkably, it matches the expert-tuned performance 1.28$\times$ faster in image-text tuning and extends to more complex multi-modal video scenarios outperforming uniform weights performance with only 33\% steps.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：当前视觉语言模型（VLM）训练依赖于在多个多模态域（如图文对、视频-文本等）上精心调配数据混合比例，该过程通常需要昂贵且耗时的人工手动调优，不仅效率低下，还难以保证跨模态对齐的最优性。
- **整体含义**：论文旨在提供一种有原则的自动化框架，无需人工反复试错，即可直接确定最优的多模态数据配比，从而降低训练成本并提升VLM的跨模态理解能力。这一方向对推动VLM高效、规模化训练具有重要的实践意义。

### 2. 论文提出的方法论
- **核心思想**：将数据混合问题形式化为**模态感知的对齐最大化**（modality-aware alignment maximization）问题，在多个域上自动寻找能够最大化整体跨模态对齐程度的数据混合权重。
- **关键技术细节**：
  - 利用**对偶解**（dual solution）中的**跨模态耦合变量**，从优化过程中推导出每个域的多模态对齐分数（multi-modal alignment scores）。
  - 框架专门设计为能够处理**模态缺失的域**（例如纯文本域），从而可以系统地将纯语言数据无缝融入到多模态训练中，实现更完整的数据混合。
  - 整体流程可概括为：给定多个候选域，通过求解对齐最大化问题获得各域的对齐分数，再依据分数自动分配训练数据采样权重，无需任何手动设置。
- **算法流程（文字描述）**：构建域间对齐度量，利用对偶方法同时计算每个域的对齐贡献度，生成权重向量；训练过程中按权重比例从各域抽取批次数据，并在混合时支持仅含单一模态的域。

### 3. 实验设计
- **数据集与场景**：
  - 规模：分别在**0.5B参数**和**7B参数**的VLM上进行验证。
  - 场景1：**图像-文本调优**，涵盖多个图文多模态域，以及可能的纯语言域。
  - 场景2：**更复杂的多模态视频场景**，验证方法在时序多模态数据上的扩展性。
- **Benchmark**：在多样的评估基准上测试准确率（具体基准名称未在摘要中列出，但强调“diverse evaluation benchmarks”）。
- **对比方法**：
  - **手工专家调优**（expert-tuned）的数据混合方案。
  - **均匀权重**（uniform weights）作为基线。
  - 从摘要推断，MMix与专家调优性能匹配，且大幅超过均匀权重方案。

### 4. 资源与算力
- 摘要中**未明确提及**所使用的GPU型号、数量、训练总时长等具体算力资源。
- 文中仅用定性描述“**marginal computational cost**（边际计算成本）”来强调MMix在计算开销上的极小增量，但缺乏定量算力报告。因此，**无法从现有信息中总结具体的硬件与训练时间投入**。

### 5. 实验数量与充分性
- **实验组数量**：至少覆盖了两个模型规模（0.5B和7B）和两种多模态场景（图像-文本、视频），并包含了与手工调优和均匀权重基线的对比。初步估计在多个基准上进行了综合性评估。
- **充分性与公平性**：
  - 在**不同模型大小**上都验证了有效性，增强了结论的泛化性。
  - 将MMix与代表实际最佳实践的手工调优方案对齐，同时与朴素均匀权重对比，**对比基线合理且具有实际参考价值**。
  - 图像-文本调优实验中达到“1.28× faster”且性能匹配专家，视频场景中以“仅33% steps”超越均匀权重，表明实验覆盖了效率与效果维度，设计较为**充分和客观**。
  - 未提及消融实验细节（如对齐分数模块是否有效、缺失模态处理的影响），但从总体结论看，实验为论文主张提供了实质性支撑。

### 6. 论文的主要结论与发现
- MMix能够**自动确定多模态数据混合比例**，并显著提升VLM在多种评估基准上的准确率。
- 在图文调优中，MMix仅需专家调优方案约**78%（1/1.28）的训练步数**即可达到同等性能，训练更快。
- 在视频多模态场景中，MMix仅使用**33%的训练步数**即超越均匀权重性能，展现出对复杂模态缺失场景的强适应能力。
- 框架以**极低的计算开销**实现了媲美甚至优于人工专家调优的效果，为VLM数据工程提供了高效、自动化的新范式。

### 7. 优点
- **自动化与免人工**：消除了对昂贵人工调参的依赖，首次为多模态数据混合提供了一个有理论支撑的自动配比方法。
- **模态缺失友好**：独特的设计使得纯语言域能自然融入，突破了许多方法仅能处理完整模态对的限制，扩大了可用数据源。
- **低计算开销**：仅在原有训练流程上增加边际成本，易于集成，实用性高。
- **跨规模与跨模态通用性**：从小规模（0.5B）到较大规模（7B），从静态图文到动态视频均验证有效，展示了较强的泛化潜力。
- **加速训练**：在达到同等或更优性能的同时显著减少训练步数，提升了效率。

### 8. 不足与局限
- **算力报告缺失**：未提供推理和训练对齐分数所需的具体算力开销（GPU型号、卡数、耗时），难以精确评估“边际成本”的实际量级。
- **基准覆盖面未详述**：摘要仅提及“diverse evaluation benchmarks”，未列出具体任务名称，无法判断其在不同难度或领域下游任务上的表现一致性。
- **模型结构限定**：实验仅基于特定VLM架构（未说明是否适用于其他对齐范式或模型结构，如不同视觉编码器、融合方式），方法的平台通用性待进一步证实。
- **理论假设的稳健性**：对偶解推导的对齐分数可能依赖于某些凸性假设或数据分布特性，在高度非独立同分布的工业级噪声数据下的稳健性未讨论。
- **未能接受（Rejected-Public）**：该论文在ICLR-2026投稿中被拒绝（公开），可能存在审稿人指出的未呈现的深层缺陷（如理论深度、对比方法老旧、或大规模扩展性问题），但限于仅获取摘要，无法得知具体拒稿原因。

（完）
