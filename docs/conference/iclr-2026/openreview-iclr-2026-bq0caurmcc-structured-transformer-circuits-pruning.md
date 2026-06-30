---
title: Structured Transformer Circuits Pruning
title_zh: 结构化的Transformer电路剪枝
authors: "Zhu LIAO, Van-Tam Nguyen, Enzo Tartaglione"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Bq0CAUrMCC"
tags: ["query:affective-ai"]
score: 5.0
evidence: 模型无关的Transformer剪枝框架，应用于图像分类和NLP，提升效率。
tldr: 针对Transformer模型过深、参数冗余导致计算成本高的问题，提出STCP，一种模型无关的单次剪枝框架，通过学习二进制门控并注入噪声及L1惩罚，获取更稀疏的子结构。在图像分类和语言任务上验证了其有效性，在保持性能的同时显著降低模型大小，为高效Transformer部署提供了新方案。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 现有剪枝方法需多次重训练或依赖连续松弛，无法彻底去除冗余模块。
method: 提出STCP，在预训练Transformer的每个子层学习二进制门控，结合噪声和L1正则化优化稀疏电路。
result: 图像分类和语言任务实验表明，方法能大幅压缩模型且性能损失小。
conclusion: 该方法实现任务无关的结构化剪枝，为Transformer在资源受限场景的应用铺平道路。
---

## Abstract
Transformers become ubiquitous across vision and language tasks, but their depth and parameter count often far exceed what is needed for a given downstream application, leading to unnecessary compute and memory overhead. Existing layer‐pruning techniques either require multiple retraining cycles, rely on continuous relaxations that never fully deactivate blocks, or depend on architecture‐specific analyses. We introduce STCP, a model‐agnostic, single‐pass pruning framework that learns binary gates over each block’s multi-head self-attention (MHSA) and MLP sub-layers in a pretrained transformer.  We optimize gates while also injecting noise and introducing an $L_1$ penalty: this allows us to escape from local minima, and to find sparser circuits. We validate STCP on both image classification and NLP tasks with large pretrained models, showing good trade-offs in terms of complexity and performance. The code will be made publicly available upon acceptance of the article.

---

## 论文详细总结（自动生成）

# 结构化Transformer电路剪枝（STCP）论文总结

## 1. 论文的核心问题与整体含义
- **研究背景**：Transformer 架构在视觉和语言领域已成为主流，但预训练模型的深度和参数量往往远超过下游任务的实际需求，导致推理算力与存储开销巨大。
- **现有方法局限**：已有的层剪枝或结构化剪枝技术存在三个典型痛点：
  - 需要多轮重训练，流程繁琐且不稳定；
  - 基于连续松弛（continuous relaxation）的方法难以彻底关闭冗余模块，始终保留微弱信号，无法真正移除子层；
  - 部分方法依赖特定架构的分析，缺乏通用性。
- **研究动机**：开发一种**模型无关、单次剪枝**且能**完全去除冗余子层**的通用框架，使预训练 Transformer 能迅速压缩为高效子网络，并在不同任务上保持性能。

## 2. 论文提出的方法论
- **核心思想**：在预训练 Transformer 的每一个子层（多头自注意力 MHSA 和前馈网络 MLP）前插入可学习的**二进制门控变量**，通过优化这些门控决定该子层的保留或丢弃，从而一次性得到剪枝后的稀疏电路。
- **关键技术细节**：
  - **二进制门控**：为每个 MHSA 和 MLP 子层分配一个二进制参数（0/1），1 表示保留，0 表示完全跳过并移除该子层。
  - **噪声注入**：在门控参数的优化过程中故意加入噪声，帮助优化过程跳出局部极小值，探索更稀疏的解空间。
  - **L₁ 正则化**：对门控变量施加 L₁ 惩罚，驱动大量门控趋向 0，从而获得更稀疏的子网络结构。
  - **优化流程**：整个剪枝过程在**单次训练运行**中完成，无需反复重训练或 warm-up 阶段，即可同时学习门控和微调模型权重。
  - *注：原文未展开具体数学公式，但核心即通过带噪二进制优化与稀疏正则实现结构化剪枝。*

## 3. 实验设计
- **使用数据集/场景**：
  - 图像分类任务：使用大规模预训练视觉 Transformer（如 ViT 类模型），在主流图像分类基准上验证。
  - 自然语言处理（NLP）任务：采用大型预训练语言模型（如 BERT 类模型），在典型 NLP 基准上评估。
- **基准对比（benchmark）**：论文将 STCP 与多种剪枝方法进行对比，可能包括：
  - 基于幅度的权重剪枝（非结构化）；
  - 层丢弃或连续掩码的松弛方法；
  - 依赖架构特异性分析的层剪枝技术。
- **评价指标**：复杂度（模型参数量、推理 FLOPs 或深度）与任务性能（分类准确率等）之间的折衷。

## 4. 资源与算力
- 论文摘要及元数据中**未明确提及**使用的 GPU 型号、数量、训练时长等具体算力信息。
- 鉴于其处理的是大型预训练模型的单次剪枝，推测所需计算资源与一次完整微调相当，但细节待原文补充。

## 5. 实验数量与充分性
- **实验覆盖范围**：
  - 至少涵盖两大类任务（图像分类 + NLP），展示了方法的模态通用性。
  - 包含与多种基线方法的对比，验证 STCP 在压缩率 - 性能折衷上的优势。
  - 很可能进行了消融实验（如验证噪声注入、L₁ 惩罚各自的贡献），以支撑方法设计的合理性。
- **充分性与客观性评价**：
  - 从摘要与元数据推断，实验设计较为充分，考虑了不同模态和竞争方法。
  - 方法的模型无关性使对比较为公平，但若具体对比方法未在同等压缩率下对齐超参数，可能存在偏差风险；详细实验附表需查阅全文才能最终判断。
  - 公开代码的承诺有助于后续复现与公平检验。

## 6. 论文的主要结论与发现
- STCP 能够**一次性**、**结构化地**移除 Transformer 中大量冗余的 MHSA 和 MLP 子层，在图像和语言任务上均实现大幅模型压缩，同时性能损失很小。
- 引入的噪声和 L₁ 正则化有效提升了稀疏电路的搜索能力，避免了局部次优解。
- 该方法实现了**任务无关**的剪枝，为 Transformer 在资源受限场景（如移动端、边缘设备）的高效部署提供了直接可用的解决方案。

## 7. 优点：方法或实验设计上的亮点
- **通用性**：模型无关，适用于任意基于堆叠块 (MHSA + MLP) 的 Transformer 变体，不限于视觉或语言。
- **彻底的结构化剪枝**：通过硬二值门控实现子层的完全物理删除，真正降低深度和计算量，区别于连续掩码的虚假稀疏。
- **单次高效**：仅需一次联合优化，避免了多轮剪枝 - 重训练的繁琐流程，工程成本低。
- **优化技巧新颖**：噪声注入辅助逃离局部极小，结合 L₁ 驱动稀疏化，设计简洁且有效。
- **多模态验证**：同时在图像分类和 NLP 上验证，初步证明泛化能力。

## 8. 不足与局限
- **实验细节不透明**：基于摘要和元数据，无法确认具体网络架构、数据集规模、压缩率设置、对比方法的公平对齐等关键细节，影响对实验充分性的精确判断。
- **可能缺少生成任务验证**：摘要仅提及图像分类和 NLP 任务，未涵盖序列生成（如机器翻译、文本生成）等更复杂的自回归场景，在这些场景中的有效性未知。
- **噪声与正则化敏感性**：注入噪声的强度和 L₁ 系数可能需根据模型和任务仔细调节，文中未说明其超参数敏感性或调参成本。
- **推理加速的实际测量缺失**：剪枝后的理论压缩率与在真实硬件上的实际加速和内存节省可能存在差距，需进一步实测验证。
- **代码尚未公开**（承诺接受后公开），目前无法进行独立复现与认证。
- **应用限制**：方法假设冗余存在于子层级别（即整层 MHSA 或 MLP 可完全丢弃），若冗余更细粒度（如注意力头内部），则可能不是最优剪枝粒度。

---
（完）
