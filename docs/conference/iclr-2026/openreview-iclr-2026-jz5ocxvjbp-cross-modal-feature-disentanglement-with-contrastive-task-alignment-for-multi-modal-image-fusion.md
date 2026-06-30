---
title: Cross-Modal Feature Disentanglement with Contrastive Task Alignment for Multi-Modal Image Fusion
title_zh: 面向多模态图像融合的跨模态特征解耦与对比任务对齐
authors: "Shenghai Wu, Yue Lin"
date: 2025-09-06
pdf: "https://openreview.net/pdf?id=Jz5OcxVJbP"
tags: ["query:affective-ai"]
score: 7.0
evidence: 可微正交特征分解实现跨模态解耦
tldr: CMD-CTA通过可微正交特征分解和对比任务对齐，解决多模态图像融合中的特征纠缠问题，提升融合质量和泛化性。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 多模态图像融合中特征纠缠导致融合质量差和泛化有限。
method: 提出CMD-CTA，通过可微正交分解和对比任务对齐实现特征解耦。
result: 在融合基准上取得更好质量与泛化性。
conclusion: CMD-CTA为多模态融合中的特征解耦提供了理论驱动的方案。
---

## Abstract
Multi-modal image fusion suffers from feature entanglement, where modality-specific, content-specific, and task-specific information becomes conflated in unified representation spaces, leading to suboptimal fusion quality and limited generalization. This paper proposes Cross-Modal Feature Disentanglement with Contrastive Task Alignment (CMD-CTA), a framework that addresses this fundamental challenge through mathematically motivated feature separation and semantic alignment, supported by both theoretical analysis under idealized assumptions and empirical evidence on real-world fusion benchmarks. The approach introduces two key innovations: (1) differentiable orthogonal feature decomposition that encourages separation into content, modality, and task subspaces under information-theoretic sufficiency constraints; and (2) contrastive task alignment that establishes semantic bridges through learnable prototypes and multi-granularity contrastive learning. We further adopt hybrid Vision Mamba–Swin backbone to couple linear-complexity long-range modeling with windowed locality, thereby reducing parameters while preserving context. Extensive experiments across six fusion tasks and downstream object detection demonstrate 5.8--7.3\% improvements over state-of-the-art methods, 6.1\% higher mAP\@0.5, and 15.7$\times$ parameter efficiency. This empirically validated framework for representation learning in multi-modal fusion has broad implications for computer vision and autonomous systems.

---

## 论文详细总结（自动生成）

# 论文总结：面向多模态图像融合的跨模态特征解耦与对比任务对齐

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：多模态图像融合中，不同模态（如红外与可见光）、不同内容（如物体与背景）以及不同任务（如检测、分割）的特征在统一的表示空间中相互纠缠、混杂，导致融合质量欠佳，并且泛化能力受限。
- **研究动机**：现有方法难以将模态特有信息、内容共有信息和任务相关信息有效分离，从而阻碍了更高质量、更具可迁移性的融合表示学习。
- **整体含义**：本文提出一套理论驱动的特征解耦与语义对齐框架，试图从信息论和对比学习的角度解决特征纠缠这一基础性挑战，提升多模态图像融合的性能与泛化性，对计算机视觉与自主系统具有广泛应用前景。

## 2. 论文提出的方法论
- **总体框架**：Cross-Modal Feature Disentanglement with Contrastive Task Alignment（CMD-CTA），包含两个核心创新点。
- **创新点一：可微正交特征分解**
  - 通过数学上可微的正交约束，将融合后的特征分解为三个子空间：内容子空间、模态子空间和任务子空间。
  - 在信息论充分性约束下运行，保证各子空间包含必要且互不冗余的信息。
  - 实现特征层面的解耦，减少模态或任务之间的干扰。
- **创新点二：对比任务对齐**
  - 引入可学习的原型（prototypes），并通过多粒度对比学习构建跨模态的语义桥接。
  - 不同模态的特征通过向任务相关原型对齐，实现语义层次的联系，同时保持任务特定表达。
- **骨干网络**：采用混合 Vision Mamba–Swin 骨干，将线性复杂度的长程建模（Mamba）与窗口局部性（Swin）相结合，在减少参数量的同时保持全局上下文建模能力。
- **整体流程**：输入多模态图像 → 混合骨干特征提取 → 可微正交分解得到三个解耦子空间 → 多粒度对比学习对齐任务原型 → 融合输出与下游任务迁移。

## 3. 实验设计
- **数据集/场景**：论文未在给定摘要中列出具体数据集名称，但提及了“六种融合任务”以及下游目标检测任务，暗示覆盖多种标准多模态融合基准（例如红外–可见光、医学图像融合、多曝光融合等常见 benchmark）。
- **基准比较方法**：与已有最先进方法（state-of-the-art）进行全面比较，宣称在融合指标上达到 5.8–7.3% 的提升，并在下游目标检测任务中 mAP@0.5 提高 6.1%。
- **评估指标**：包括融合图像质量指标（如 PSNR、SSIM、FID 等，虽未完全列出）和下游任务指标（mAP）。
- **效率对比**：突出参数效率，相较某些方法具有 15.7× 的参数效率优势。

## 4. 资源与算力
- **说明情况**：所提供文本中未明确提及 GPU 型号、数量或训练时长等具体算力信息。论文可能将在完整版本中报告相关实验算力细节，但当前摘要和元数据未涉及。

## 5. 实验数量与充分性
- **实验规模推断**：
  - 涉及“六种融合任务”，意味着至少针对六种不同的模态组合或数据集进行了评测，总实验组数估计在几十组以上。
  - 包含下游目标检测作为泛化能力验证，进一步增加实验量。
  - 创新点通常需配合消融实验验证各个组件贡献（如解耦模块、对比对齐模块、混合骨干等），虽未列出具体消融细节，但一个完整的 ICLR 投稿通常会包含充分的消融研究。
- **充分性与公平性**：
  - 与 SOTA 方法的数值对比表明实验设置应遵循公开基准和标准协议，具备一定公平性。
  - 多种任务、下游迁移检验以及效率指标的综合评估，使得实验论证相对充分。但缺少具体数据集名称和详细配置，完整评估需待全文公开。

## 6. 论文的主要结论与发现
- CMD-CTA 通过特征解耦和对比对齐，有效缓解了多模态融合中的特征纠缠问题。
- 在六个融合任务上取得 5.8–7.3% 的性能提升，下游检测 mAP@0.5 提升 6.1%，且参数效率提升 15.7 倍，显示其高性价比。
- 理论分析与实证结果共同支持该框架在表示学习方面的优势，为多模态融合中的特征解耦提供了理论驱动的可行方案。

## 7. 优点
- **方法论创新明显**：
  - 从数学上提出可微正交分解，并赋予信息论解释，与单纯工程改进不同，具有较深的理论动机。
  - 对比任务对齐通过原型和对比学习建立语义桥接，思路新颖。
- **骨干设计高效**：
  - Vision Mamba–Swin 混合设计兼顾长程依赖与局部细节，并实现显著的参数效率。
- **实验全面性**：
  - 覆盖多种融合任务和下游迁移，从质量、效率、检测精度多维度验证。
- **同时重视理论与实践**：
  - 在理想化假设下提供理论分析，同时在真实基准上给出实证结果，增强了可靠性。

## 8. 不足与局限
- **实验细节不详**：摘要未提供具体数据集、对比方法名称和消融实验设计，难以完全判断实验覆盖度和公平性。
- **可能的偏差风险**：
  - 缺乏跨数据集泛化测试（若六大任务均来自类似分布，过拟合风险存在）。
  - 参数效率高可能部分源于特殊骨干设计，但跨架构公平比较是否调整过参数预算未说明。
- **应用限制**：
  - 方法基于正交分解和对齐，对极端模态差异（如完全异质传感器）的鲁棒性有待考证。
  - Mamba 模块的工程实现和推理速度在部分硬件上可能尚未完全优化。
- **未提及的限制**：鲁棒性实验（如噪声、配准误差）未见描述，理论假设在实际高噪声场景下的符合程度未知。

（完）
