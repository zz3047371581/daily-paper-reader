---
title: Federated Dialogue-Semantic Diffusion for Emotion Recognition under Incomplete Modalities
title_zh: 联邦对话语义扩散用于不完备模态下的情感识别
authors: "Xihang Qiu, Jiarong Cheng, Yuhao Fang, Wanpeng Zhang, Yao Lu, Ye Zhang, Chun Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=mI9HqgVuTS"
tags: ["query:affective-ai"]
score: 10.0
evidence: 联邦扩散框架用于多模态对话情感识别中缺失模态恢复
tldr: 针对多模态对话情感识别中由不可预测模态缺失导致的性能下降问题，该文提出FedDISC框架，首次将联邦学习引入缺失模态恢复。通过联合多个客户端上训练的模态特定及对话引导扩散模型，在保持语义一致性的同时生成缺失特征，解决固定模态缺失下的语义扭曲。实验表明该方法在多种缺失条件下显著优于现有方案，提升了真实场景中多模态情感理解的鲁棒性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mi9hqgvuts/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 724, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mi9hqgvuts/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mi9hqgvuts/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mi9hqgvuts/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mi9hqgvuts/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1429, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mi9hqgvuts/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 1397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mi9hqgvuts/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 1303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mi9hqgvuts/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1453, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mi9hqgvuts/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1467, \"height\": 1839, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mi9hqgvuts/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 579, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mi9hqgvuts/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mi9hqgvuts/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mi9hqgvuts/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1304, \"height\": 999, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mi9hqgvuts/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1323, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mi9hqgvuts/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1368, \"height\": 295, \"label\": \"Table\"}]"
motivation: 现实场景中模态缺失会严重影响多模态对话情感识别性能，传统恢复方法在极端分布下易出现语义扭曲。
method: 提出FedDISC框架，通过联邦学习联合训练模态特定扩散模型，利用对话引导和语义一致性扩散恢复缺失模态特征。
result: 在多个对话情感识别数据集上，FedDISC在固定模态缺失等极端条件下大幅优于基线方法。
conclusion: FedDISC通过联邦扩散模型为不完备模态下的情感识别提供了鲁棒且隐私保护的解决方案。
---

## Abstract
Multimodal Emotion Recognition in Conversations (MERC) enhances emotional understanding through the fusion of multimodal signals. However, unpredictable modality absence in real-world scenarios significantly degrades the performance of existing methods. Conventional missing-modality recovery approaches, which depend on training with complete multimodal data, often suffer from semantic distortion under extreme data distributions, such as fixed-modality absence. To address this, we propose the Federated Dialogue-guided and Semantic-Consistent Diffusion (FedDISC) framework, pioneering the integration of federated learning into missing-modality recovery. By federated aggregation of modality-specific diffusion models trained on clients and broadcasting them to clients missing corresponding modalities, FedDISC overcomes single-client reliance on modality completeness. Additionally, the DISC-Diffusion module ensures consistency in context, speaker identity, and semantics between recovered and available modalities, using a Dialogue Graph Network to capture conversational dependencies and a Semantic Conditioning Network to enforce semantic alignment. We further introduce a novel Alternating Frozen Aggregation strategy, which cyclically freezes recovery and classifier modules to facilitate collaborative optimization. Extensive experiments on the IEMOCAP, CMUMOSI, and CMUMOSEI datasets demonstrate that FedDISC achieves superior emotion classification performance across diverse missing modality patterns, outperforming existing approaches.

---

## 论文详细总结（自动生成）

好的，这是对论文《Federated Dialogue-Semantic Diffusion for Emotion Recognition under Incomplete Modalities》的结构化总结。

# 论文结构化总结：FedDISC

### 1. 论文的核心问题与整体含义

-   **研究动机**：多模态对话情感识别（MERC）依赖于文本、语音、视觉等多模态信号的融合。然而，在现实世界应用中，由于传感器故障、环境噪声或隐私限制等因素，经常出现不可预测的模态缺失问题，导致现有模型性能急剧下降。
-   **核心问题**：现有的缺失模态恢复方法（无论是潜在空间恢复还是显式生成恢复）普遍依赖于使用完整的多模态数据进行训练。在“固定模态缺失”的极端场景下（即某个或某些模态在本地数据集中完全不存在），这些方法会因缺乏分布先验和对齐监督而出现严重的语义扭曲或彻底失效。
-   **整体含义**：本文提出了一个名为 **FedDISC** 的联邦对话引导语义一致扩散框架。它开创性地将联邦学习范式引入缺失模态恢复领域，旨在解决单客户端因模态不完整而无法有效训练生成式恢复模型的根本矛盾，同时保护数据隐私。

### 2. 论文提出的方法论

-   **核心思想**：通过联邦学习，在不同客户端上利用其本地可用的模态数据，独立训练模态特定的扩散模型。服务器聚合这些模型，再分发给缺失相应模态的客户端，使其能够进行零样本的跨客户端模态恢复。这从架构上解除了对本地模态完整性的依赖。
-   **关键技术细节**：
    -   **对话图网络**：用于从可用模态的对话历史中捕捉上下文依赖（`Context Graph`）和说话人关系（`Speaker Graph`）。它构建了一个基于滑动窗口的关系图，并使用关系图卷积网络（R-GCN）来聚合特征，输出对话依赖表示 \(z^m_i\)。
    -   **语义条件网络**：利用跨模态注意力机制（`Cross-Attention`）从可用模态中提取跨模态语义信息，实现语义对齐。它通过计算模态间互注意力，并提取其输出序列的 `[head]` token 作为语义总结。
    -   **DISC-Diffusion 模型**：将 DGN 和 SCN 的输出拼接为条件嵌入 `c`，通过 U-Net 的交叉注意力层注入，引导缺失模态特征的去噪生成过程。训练时，该模型被训练为条件噪声预测网络。
    -   **交替冻结策略**：为解决扩散恢复模块和情感分类器在联合训练中的优化冲突，该策略分两个阶段进行层次化联邦训练。
        1.  **阶段一（恢复模块训练）**：冻结分类器，客户端训练并上传模态特定的扩散模型，服务器按模态聚合后广播给所有客户端。
        2.  **阶段二（分类器优化）**：冻结恢复模块，客户端使用聚合后的全局扩散模型恢复缺失模态，获得完整特征后训练分类器，服务器再聚合分类器参数。

### 3. 实验设计

-   **数据集与场景**：
    -   **IEMOCAP**：用于测试**固定缺失协议**。模拟了从 `{l}`, `{v}`, `{a}`, `{l, v}`, `{l, a}`, `{v, a}` 七种模态可用模式。
    -   **CMU-MOSI 和 CMU-MOSEI**：用于测试**随机缺失协议**。设置了从 0.0 到 0.7 共 8 个不同缺失率 \(\eta\)。
-   **评估指标**：IEMOCAP 使用加权平均 F1 值（WAF1）和准确率（ACC）；CMU-MOSI/MOSEI 使用 ACC 和 WAF1。
-   **对比方法**：与 GCNet、CIF-MMIN、SDR-GNN、IMDer、DiCMoR 等 SOTA 恢复方法，以及非恢复方法 DCCAE 进行了全面比较。

### 4. 资源与算力

-   **算力资源**：所有实验均在**两块 NVIDIA L40S GPU（每块 48GB 显存）**上完成。
-   **训练耗时**：对于 IEMOCAP 数据集，使用 DDPM（时间步 t=1000）时的平均推理时间为 **2.13 分钟/轮**；使用 DDIM（t=50）时则显著降低至 **5.7 秒/轮**。
-   **通信成本**：每轮通信开销为 **10.57 MB/客户端**（DDPM） 或 **7.18 MB/客户端**（DDIM），相比传统联邦平均（FedAvg）结构减少了超过一半。

### 5. 实验数量与充分性

-   **实验数量**：实验设计充分。
    -   **主实验**：在 3 个标准数据集上，进行了 2 种缺失协议下的全面对比（固定缺失约 7 种模式 x 2 种标签方案；随机缺失 8 种缺失率 x 2 个数据集）。
    -   **消融实验**：针对 DGN、SCN 模块和 AFS 策略设计了可视化与定量消融实验，验证各组件的有效性。
    -   **可视化分析**：使用 t-SNE 可视化了恢复特征分布与真实特征的对比。
-   **充分性与公平性**：实验对比了广泛的主流方法，并明确指出了对比模型训练数据量的差异（如 FedDISC 客户端仅分得 \(1/n_c\) 数据），分析客观。**统计显著性检验**（Wilcoxon 符号秩检验）增加了结果的可信度。

### 6. 论文的主要结论与发现

-   FedDISC 在两种模态缺失协议下均取得了优异性能，尤其在**高缺失率和固定模态缺失**的极端场景下，显著优于所有对比的 SOTA 方法。
-   尽管联邦学习场景下客户端数据量少，但 FedDISC 仍能生成高质量的缺失模态特征，可视化结果显示其恢复的特征分布与真实分布最接近。
-   提出的 **DGN 和 SCN** 模块能有效引导扩散模型的生成，确保恢复模态与可用模态在上下文、说话人和语义上保持三维一致性。
-   **AFS 策略**能有效解耦恢复与分类任务的优化冲突，提升协作训练效果。

### 7. 优点

-   **创新性强**：首次将联邦学习与生成式扩散模型结合，为解决模态缺失问题提供了全新的去中心化范式，并天然支持隐私保护。
-   **方法设计完备**：DGN、SCN 和 AFS 三个组件分别从对话依赖、语义对齐和优化协同三个层面系统性地解决了问题，逻辑清晰。
-   **实验扎实**：实验覆盖多种数据集、缺失协议与主流基线，并提供了统计检验和丰富的可视化分析，论证充分。
-   **实用前景好**：通信成本低，且框架允许灵活替换为更轻量的生成模型（如 DDIM），具备实际部署的潜力。

### 8. 不足与局限

-   **采样效率与计算成本权衡**：扩散模型的迭代去噪需要多步推理，在追求高质量恢复和低计算成本之间存在矛盾。尽管可替换为 DDIM，但论文未能完全解决。
-   **联邦学习假设**：框架假设客户端和服务器进行同步联邦训练，这在真实世界的异步设备或动态模态缺失环境中可能受限。
-   **无误差线报告**：由于实验成本高昂，论文未提供多次运行的结果误差线，难以评估结果的方差和稳定性。
-   **潜在偏见风险**：联邦学习框架下，若客户端数据存在文化或人口统计学上的偏见，可能通过模型聚合传播到全局，影响公平性。

（完）
