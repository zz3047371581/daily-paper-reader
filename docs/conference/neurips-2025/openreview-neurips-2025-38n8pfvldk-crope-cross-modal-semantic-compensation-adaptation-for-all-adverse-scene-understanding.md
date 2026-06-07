---
title: "CroPe: Cross-Modal Semantic Compensation Adaptation for All Adverse Scene Understanding"
title_zh: CroPe：针对所有恶劣场景理解的跨模态语义补偿适应
authors: "Qin Xu, Qihang Wu, Lu Hongtao, Xiaoxia Cheng, Bo Jiang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=38n8pFvldK"
tags: ["query:affective-ai"]
score: 8.0
evidence: 提出跨模态语义补偿适应方法，应对恶劣场景理解。
tldr: 恶劣条件下视觉退化导致场景理解困难。本文提出CroPe，通过互补感知文本生成模块提供多层次文本语义补偿，指导视觉特征学习。实验表明该方法在雾、雪、夜间等恶劣条件下实现了鲁棒场景理解。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1408, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 793, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 580, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 681, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1148, \"height\": 754, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1163, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1436, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1433, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1434, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-38n8pfvldk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1432, \"height\": 375, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 700, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 695, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 640, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 727, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1437, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1105, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1432, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1155, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1145, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-38n8pfvldk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 608, \"height\": 178, \"label\": \"Table\"}]"
motivation: 恶劣条件下视觉退化导致场景理解困难。
method: 提出跨模态语义补偿适应方法CroPe。
result: 在多种恶劣场景下实现鲁棒场景理解。
conclusion: CroPe通过文本语义补偿提升视觉鲁棒性。
---

## Abstract
Scene understanding in adverse conditions, such as fog, snow, and night, is challenging due to the visual appearance degeneration. In this context, we propose a Cross-modal Semantic Compensation Adaptation method (CroPe) for scene understanding. Distinct from the existing methods, which only use the visual information to learn the domain-invariant features, CroPe establishes a visual-textual paradigm which provides textual semantic compensation for visual features, enabling the model to learn more consistent representations. We propose the Complementary Perceptual Text Generation (CPTG) module which generates a set of multi-level complementary-perceptive text embeddings incorporating both generalization and domain awareness. To achieve cross-modal semantic compensation, the Reverse Chain Text-Visual Fusion (RCTVF) module is developed. By the unified attention and reverse decoding chain, compensation information is successively fused to the visual features from the deep (semantic dense) to shallow (semantic sparse) features, maximizing compensation gain. CroPe yields competitive results under all adverse conditions and significantly improves the state-of-the-art performance by 6.5 mIoU for ACDC-Night dataset and 1.2 mIoU for ACDC-All dataset, respectively.

---

## 论文详细总结（自动生成）

### 一、论文的核心问题与整体含义
- **研究背景与核心问题**：在雾、雪、夜间等恶劣天气或光照条件下，由于纹理丢失、能见度低、色彩失真等视觉退化现象，现有的无监督域自适应语义分割方法（UDASS）容易产生幻觉（如将天空错分为树木），难以学习到跨域一致的语义知识。
- **整体含义**：针对上述问题，本文提出了一种跨模态语义补偿自适应方法——**CroPe**。其核心创新在于首次将鲁棒的**文本模态**引入恶劣场景下的无监督域自适应分割任务，利用文本语义对环境变化不变的特点，作为高层引导模态来补偿退化中的视觉信息，从而学习到更一致的表征。

### 二、论文提出的方法论
- **核心思想**：构建视觉-文本（Visual-Textual）范式，通过生成具有互补感知能力的文本嵌入，并将其以从深到浅的反向链式融合方式注入多尺度视觉特征中，最大化语义补偿增益。
- **关键技术细节与模块**：
  - **互补感知文本生成模块 (CPTG)**：
    - **解耦策略**：将原始文本嵌入 $T$ 通过两个独立的MLP分解为领域特定嵌入 $T_S$ 和领域不变嵌入 $T_I$，并施加正交损失 $L_{orth} = \| \langle T_S, T_I \rangle \|_2$ 以确保语义独立。
    - **领域特定感知**：利用视觉编码器最后三层特征 $P_2,P_3,P_4$ 与 $T_S$ 通过注意力交互，捕捉多层次领域特定信息。
    - **领域不变正则化**：利用手工设计的通用提示（如"a photo of a [class]"）生成文本嵌入 $T_C$，通过余弦相似度软约束 $L_{align}=1-\langle T_I, T_C \rangle$ 防止 $T_I$ 过拟合。
    - **门控互补融合**：通过门控单元动态学习权重 $\alpha, \beta$，融合领域特定与不变嵌入及它们的原始融合特征，获得最终的多层次互补感知文本嵌入 $\hat{T}$。
  - **反向链式文本-视觉融合模块 (RCTVF)**：
    - **统一注意力**：结合多尺度可变性注意力和跨模态注意力，用 $\hat{T}$ 补偿并丰富视觉特征 $F$ 的语义密度。
    - **反向解码链**：利用反向链式机制，将经语义最稠密的深层特征（如 $F_4$ 与 $\hat{T}_3$ 融合）补偿后的特征上采样回传并叠加至浅层特征（$F_3$ 至 $F_2$），解决浅层语义稀疏问题，实现补偿增益最大化。
  - **总损失函数**：$L = L_{orth} + L_{align} + \lambda L_{ce}$。

### 三、实验设计
- **实验场景与数据集**：实验覆盖了四种恶劣天气/光照场景（雾、雨、雪、夜）以及正常场景，共计使用了**10个场景**下的**7个真实世界数据集**。
  - **正常场景域适应**：GTA5 → Cityscapes, SYNTHIA → Cityscapes。
  - **恶劣场景域适应**：Cityscapes (源域) → ACDC (目标域，含雾/夜/雨/雪四个子集)；Cityscapes → Dark Zurich (DZ) → Nighttime Driving (ND)/BDD100K-Night (BD) (泛化测试)；Cityscapes → Foggy Zurich (FZ) → Foggy Driving (FD) (泛化测试)。
- **对比基准 (Benchmark)**：与两类主流方法进行了对比。
  - **场景特定模型**：如CuDA-Net, FIFO, SAM-EDA, GCMA, MCGDA, DAEN等。
  - **场景无关模型(State-of-the-art)**：如AdaptSeg, DAFormer, SePiCo, STA, HRDA, MIC, PASS等。
- **评价指标**：使用平均交并比 (mIoU) 作为核心评估指标。

### 四、资源与算力
- **硬件**：所有实验在**单个RTX 4090 GPU**上完成。
- **训练耗时与资源消耗**：
  - 对比的SegFormer系方法（HRDA, MIC等）：训练时长约17-25小时，GPU显存占用约23.5 GB。
  - CroPe (ViT-L/14 全量微调)：训练时长约**12小时**，显存占用约**18.0 GB**。
  - CroPe (ViT-B/16 冻结骨干)：训练时长约**6小时**，显存占用仅**5.7 GB**。
  - CroPe (ViT-L/14 LoRA微调)：训练时长约**10小时**，显存占用约**12.0 GB**。
- **训练分辨率**：采用**512×512**的低分辨率训练策略，效率优于其他方法的1024×1024高分辨率。

### 五、实验数量与充分性
- **实验数量**：论文设计了非常详尽的实验验证体系，包括：
  1. **主实验 (Table 1)**：在10个不同场景/数据集上与大量SOTA方法进行全面性能对比。
  2. **模块有效性消融实验 (Table 2, 3, 4)**：逐步验证CPTG、RCTVF模块及其内部各组件（解耦、感知、正则化、反向链式）的性能增益。
  3. **损失函数消融实验 (Table 5)**：验证正交损失和对齐损失的必要性。
  4. **泛化性实验 (Table 6)**：在GTA5/SYNTHIA -> Cityscapes等正常场景下测试，证明方法的可扩展性。
  5. **效率与复杂度分析 (Table 7, 8)**：对比不同参数设置（冻结、全量、LoRA）下的参数量、训练成本、推理速度和性能。
  6. **特征可视化实验 (Figure 5, 8)**：通过特征图可视化，定性分析RCTVF模块在补偿视觉语义稀疏性方面的有效性。
  7. **域差异度量实验 (Figure 7)**：通过计算最大均值差异 (MMD) 量化地证明CroPe能更有效地缩小域间差距。
- **充分性与客观性**：实验设计非常**充分且客观**。消融研究细致入微，既有定量分析也有定性可视化佐证；对比的基线方法全面且包含了最先进的模型；效率分析证明了其在更低成本下达到高性能的优势，排除了“堆参数取胜”的嫌疑。

### 六、论文的主要结论与发现
- CroPe在所有恶劣条件下均取得极具竞争力的结果，在ACDC-Night数据集上以**66.8 mIoU** 超越现有SOTA方法6.5个百分点，在ACDC-All综合数据集上以**72.0 mIoU** 提升1.2个百分点。
- 引入文本模态作为语义补偿能有效缓解恶劣场景下纯视觉模型产生的**幻觉**问题（如误分类），并学习到更一致的跨域特征。
- 反向解码链 (Reverse-Chain) 优于无链式或正向链式融合，证明了**从语义稠密的深层向稀疏的浅层**传递语义补偿的有效性。
- CroPe相比于传统方法，在**更低训练分辨率、更短训练时间、更小显存占用**的情况下，仍能实现更高的分割精度，实现了性能与效率的更好平衡。

### 七、优点
- **范式创新**：首次将跨模态语义补偿思路引入恶劣场景的无监督域适应分割，为视觉鲁棒性研究提供了新视角。
- **方法设计精巧**：CPTG模块的解耦与互补融合机制，以及RCTVF模块的统一注意力与反向链式设计，逻辑清晰且有针对性。
- **实验极其扎实**：评估覆盖场景广、对比方法全、消融实验深入，并且包含效率、可视化、域差异度量等多维度分析，论证力强。
- **实用性强**：提供了冻结骨干和LoRA轻量化方案，在低算力下也具备优异的部署潜力。

### 八、不足与局限
- **模型参数量增加**：尽管提供了轻量化方案，但达到最优性能的ViT-L/14全量微调版本参数量高达**341.37 M**，远高于传统的SegFormer系方法。
- **对提示模板依赖**：虽然进行了消融实验，但模型性能一定程度上仍受“a typical driving scenario with a [class]”这类契合驾驶场景的手工提示影响，在非驾驶领域的泛化能力可能受限。
- **幻觉问题未完全根除**：虽然CroPe大幅减少了错分现象，但在极端恶劣场景下仍可能存在视觉信息严重缺失导致的偶发幻觉。

（完）
