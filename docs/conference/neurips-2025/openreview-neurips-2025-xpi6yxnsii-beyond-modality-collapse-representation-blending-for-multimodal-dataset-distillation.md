---
title: "Beyond Modality Collapse: Representation Blending for Multimodal Dataset Distillation"
title_zh: 超越模态坍塌：多模态数据集蒸馏的表征混合方法
authors: "Xin Zhang, Ziruo Zhang, Jiawei Du, Zuozhu Liu, Joey Tianyi Zhou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Xpi6YxNSiI"
tags: ["query:affective-ai"]
score: 8.0
evidence: 多模态数据集蒸馏；通过表征混合缓解模态坍塌
tldr: 本文首次指出多模态数据集蒸馏中存在模态坍塌问题：模态内表征过度集中、模态间分布差距大。归因于蒸馏过压缩与对比目标监督的冲突，提出RepBlend框架，通过弱化过强的跨模态监督并引入表征混合来校正。在多个图像-文本基准上，RepBlend生成的合成数据集在下游任务中性能显著优于先前方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1086, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 660, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 510, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 669, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 668, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1362, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1314, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 625, \"height\": 348, \"label\": \"Table\"}]"
motivation: 现有多模态蒸馏方法压缩时导致模态内表征坍塌与模态间分布不一致。
method: 提出RepBlend，通过表征混合策略平衡跨模态对比监督强度，缓解模态坍塌。
result: 在性能保持相同水平下，合成数据集的模态分布对齐度大幅提升。
conclusion: RepBlend为多模态蒸馏的模态坍塌问题提供了首次分析和有效解决方案。
---

## Abstract
Multimodal Dataset Distillation (MDD) seeks to condense large-scale image-text datasets into compact surrogates while retaining their effectiveness for cross-modal learning. Despite recent progress, existing MDD approaches often suffer from ***Modality Collapse***, characterized by over-concentrated intra-modal representations and enlarged distributional gap across modalities. In this paper, at the first time, we identify this issue as stemming from a fundamental conflict between the over-compression behavior inherent in dataset distillation and the cross-modal supervision imposed by contrastive objectives. To alleviate modality collapse, we introduce **RepBlend**, a novel MDD framework that weakens overdominant cross-modal supervision via representation blending, thereby significantly enhancing intra-modal diversity. Additionally, we observe that current MDD methods impose asymmetric supervision across modalities, resulting in biased optimization. To address this, we propose symmetric projection trajectory matching, which synchronizes the optimization dynamics using modality-specific projection heads, thereby promoting balanced supervision and enhancing cross-modal alignment.
Experiments on Flickr-30K and MS-COCO show that RepBlend consistently outperforms prior state-of-the-art MDD methods, achieving significant gains in retrieval performance (e.g., +9.4 IR@10, +6.3 TR@10 under the 100-pair setting) and offering up to 6.7$\times$ distillation speedup.

---

## 论文详细总结（自动生成）

# 论文总结：超越模态坍塌：多模态数据集蒸馏的表征混合方法

## 1. 论文的核心问题与整体含义
- **研究背景**：大规模多模态（如图文）数据集的训练成本高昂，数据集蒸馏（DD）旨在合成紧凑的代理数据集以降低开销。将DD扩展到多模态场景（MDD）面临独特挑战。
- **核心问题**：现有MDD方法普遍存在“模态坍塌”（Modality Collapse）现象，表现为：
  - 模态内表征过度集中，丧失多样性。
  - 模态间分布差距扩大，跨模态对齐恶化。
- **根本原因**：作者首次从理论上指出，这是由数据集蒸馏固有的过度压缩特性与对比学习强加的跨模态监督之间相互强化造成的。过度压缩导致优化方向被少数主导特征吸引，而对比目标进一步放大这种集中趋势。
- **整体含义**：模态坍塌严重损害合成数据的实例级判别能力和语义对齐，亟需一种既能压缩数据又能保持模态内多样性与模态间一致性的新框架。

## 2. 论文提出的方法论
- **核心思想**：通过弱化过强的跨模态监督来提升模态内多样性，同时平衡不对称的模态优化以加强跨模态对齐。
- **关键技术细节**：
  - **表征混合（Representation Blending）**：在表征空间内，通过将不同合成样本的表征进行插值混合（类似MixUp，但作用于表示层），注入结构化且保留语义的扰动，从而降低模态内相似度、缓解坍塌，且不损害跨模态对齐。公式表示为 
    \[\tilde{\omega}_m^{blend} = \text{Normalize}(f_{textP}((1-\varrho)\tilde{\omega}_m + \varrho\tilde{\omega}_i))\]
    其中 \(\varrho\) 为混合比例，\(\tilde{\omega}_i\) 为另一实例的文本表示。图像侧同样操作。
  - **对称投影轨迹匹配（Symmetric Projection Trajectory Matching）**：传统方法仅匹配文本投影头和图像编码器的轨迹，导致图像侧监督信号弱、优化不平衡。本方法为图像编码器额外引入一个图像投影头，并同时匹配两个投影头的优化轨迹，使两模态的更新幅度和损失下降趋势更一致，从而提升跨模态对齐并加速蒸馏。
  - **整体流程**：在蒸馏阶段，对每个小批次执行表征混合，计算加权BCE对比损失以更新投影头；再利用匹配两个模态投影头的专家轨迹来优化合成数据。算法伪代码详见论文Algorithm 1。
- **损失函数**：延续LoRS中的加权二元交叉熵（wBCE），通过阈值\(\varpi\)划分正负对。

## 3. 实验设计
- **数据集**：
  - 图文：Flickr-30K（31k 图像）、MS-COCO（123k 图像），每个图像配5个描述。
  - 更大规模：LLaVA-cc3m（334k 训练对，10k 验证对）。
  - 音频-文本：AudioCaps（验证跨模态泛化能力）。
- **任务与评估指标**：
  - 跨模态检索：图像到文本检索（IR@K）和文本到图像检索（TR@K），K=1,5,10。
  - 零样本泛化：在ImageNet-10分类和TextCaps检索任务上评估。
- **对比方法**：
  - 核心集选择：Random、Herding、K-Center、Forgetting。
  - 数据集蒸馏：MTT-VL、TESLA-VL、LoRS（SOTA）。
  - 所有方法在相同蒸馏预算（100、200、500对）下比较。
- **模型架构**：
  - 主干网络：NFNet、RegNet、ResNet-50、ViT 作为图像编码器；BERT、DistilBERT 作为文本编码器。
  - 大模型验证：DiNo-v2（86M）+ BGE-1.5（109M）。

## 4. 资源与算力
- 文中明确说明实验使用 **两张 NVIDIA RTX 3090 GPU** 和 **一张 NVIDIA H100 GPU**。
- 蒸馏效率提升显著：与LoRS相比，专家轨迹生成时间从70分钟/轨迹降至40分钟（1.75倍加速），占用内存从1.63 GB降至0.73 GB；蒸馏迭代速度从11.5秒/迭代降至1.71秒（6.7倍加速），峰值显存从21.78 GB降至10.17 GB。
- 未给出全部实验的总GPU时数，但具体加速数据体现了方法的轻量高效。

## 5. 实验数量与充分性
- **主要实验矩阵**：
  - 2个主数据集（Flickr、COCO） × 3个蒸馏预算（100、200、500） × 6项指标（IR/TR@1,5,10），每个结果均带标准差，重复5次取平均。
  - 4组跨架构泛化实验（训练于NFNet+BERT，测试于ResNet、RegNet等）。
  - 1个大模型+大数据实验（DiNo-v2+BGE-1.5, LLaVA-cc3m）。
  - 1个音频-文本跨模态实验。
- **消融实验**：
  - 表征混合与对称匹配的独立性消融（Figure 5）。
  - 噪声扰动水平对模态坍塌指标的影响（Figure 3）。
  - 不同架构组合下的性能对比（Figure 6、7）。
- **公平性**：所有对比方法使用相同的评估协议和蒸馏预算，领先方法LoRS和RepBlend均因相似矩阵占用预算而少合成一对数据（如100对蒸馏实际合成99对），实验设计严密。实验数量充分，客观性强。

## 6. 论文的主要结论与发现
- **现象揭示**：模态坍塌在MDD中普遍存在，表现为蒸馏过程中模态内相似度持续上升、模态间相似度分布趋于均匀，严重影响软标签的跨模态关系编码能力。
- **方法有效性**：RepBlend通过表征混合与对称轨迹匹配，同时降低了模态内相似度、减小了模态间差距，在多个基准上大幅超越SOTA方法（如Flickr 100对下IR@10从35.1%提至44.5%，TR@10从49.2%提至55.5%），且蒸馏效率数倍提升。
- **泛化能力**：方法在多种编码器架构、更大规模数据集以及音频-文本跨模态场景下均保持优势，具有良好的通用性。

## 7. 优点
- **理论洞见**：首次将模态坍塌归因于蒸馏过压缩与对比监督的冲突，为理解MDD失败模式提供了新视角。
- **轻量高效**：仅增加少量投影头计算，却带来了显著的蒸馏加速和内存降低，性价比高。
- **设计优雅**：表征混合无需修改网络结构或损失函数，易于集成入现有MDD流程。
- **实验全面**：覆盖多种数据集、多组预算、多架构、多模态，证据链完整且坚实。
- **可复现性**：提供了代码链接及详细超参数表，实验报告规范。

## 8. 不足与局限
- **建模粒度受限**：方法仍限于图文对级别的全局匹配，缺乏对文本token与图像区域等细粒度对齐的支持，可能制约复杂场景下的性能。
- **跨实例交互缺失**：蒸馏过程中未显式利用合成实例间的关系，可能限制了更丰富的语义保留。
- **任务覆盖有限**：主要验证于跨模态检索，未涉及视觉问答、推理等更复杂的多模态下游任务。
- **数据噪声敏感**：表征混合比例\(\varrho\)等超参数可能需要针对不同数据集调整，文中未探讨其对性能的鲁棒性。
- **理论分析限定**：模态坍塌的命题推导在特定形式和假设下给出，实际蒸馏动态的泛化性有待更深入的理论刻画。

（完）
