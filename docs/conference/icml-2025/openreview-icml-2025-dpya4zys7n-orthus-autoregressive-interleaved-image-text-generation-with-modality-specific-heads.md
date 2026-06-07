---
title: "Orthus: Autoregressive Interleaved Image-Text Generation with Modality-Specific Heads"
title_zh: Orthus：基于模态专用头的自回归交错图文生成
authors: "Siqi Kou, Jiachun Jin, Zhihong Liu, Chang Liu, Ye Ma, Jian Jia, Quan Chen, Peng Jiang, Zhijie Deng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=dPyA4ZYs7n"
tags: ["query:affective-ai"]
score: 8.0
evidence: 用模态专用头统一自回归生成交错图文，实现跨模态表示学习
tldr: Orthus提出一种统一多模态模型，通过自回归方式同时处理离散文本token和连续图像特征，利用模态专用头（语言建模头预测文本，扩散头生成图像）实现交错图文生成。该方法克服了矢量量化导致的信息损失，简化了模态间关联建模。实验表明，Orthus在图文生成质量与连贯性上优于现有方法，为自回归多模态生成提供了高效框架。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1561, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1648, \"height\": 1059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1638, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 821, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 364, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 364, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 352, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 363, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 363, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 365, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 364, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 363, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 364, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 366, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 365, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 363, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 366, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 365, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 369, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 365, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1594, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1679, \"height\": 1444, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1743, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 883, \"height\": 643, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 905, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 850, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1079, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1051, \"height\": 280, \"label\": \"Table\"}]"
motivation: 现有统一多模态模型常因矢量量化导致视觉信息损失，且模态间关联建模复杂。
method: 提出Orthus，用自回归方式同时预测离散文本token和连续图像特征，分别由语言建模头和扩散头处理。
result: Orthus在交错图文生成任务上取得优于基线模型的效果，信息保留更好。
conclusion: 验证了全自回归建模和连续视觉处理在多模态生成中的优势。
---

## Abstract
We introduce Orthus, a unified multimodal model that excels in generating interleaved images and text from mixed-modality inputs by simultaneously handling discrete text tokens and continuous image features under the \textbf{AR} modeling principle. The continuous treatment of visual signals minimizes the information loss while the fully AR formulation renders the characterization of the correlation between modalities straightforward. Orthus leverages these advantages through its modality-specific heads---one regular language modeling (LM) head predicts discrete text tokens and one diffusion head generates continuous image features. We devise an efficient strategy for building Orthus---by substituting the Vector Quantization (VQ) operation in the existing unified AR model with a soft alternative, introducing a diffusion head, and tuning the added modules to reconstruct images, we can create an Orthus-base model effortlessly (e.g., within 72 A100 GPU hours). Orthus-base can further embrace post-training to craft lengthy interleaved image-text, reflecting the potential for handling intricate real-world tasks. For visual understanding and generation, Orthus achieves a GenEval score of 0.58 and an MME-P score of 1265.8 using 7B parameters, outperforming competing baselines including Show-o and Chameleon.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

本论文针对现有多模态基础模型在**统一处理交错图文生成（Interleaved Image-Text Generation）** 时面临的两大核心问题：
- **信息损失**：全自回归（Fully AR）模型（如 Chameleon）为将连续图像特征纳入离散 token 框架，必须使用矢量量化（VQ），这会导致高频细节（如 OCR、人脸）信息丢失。
- **噪声干扰**：融合扩散与自回归的混合模型（如 Transfusion）在训练时需向图像输入噪声，严重干扰了模型对“干净”图像的理解能力，难以实现真正的统一联合建模。

针对此，“Orthus” 旨在提出一种**简洁、无损的统一多模态架构**。其整体含义是：**通过完全自回归的范式，同时处理离散文本与连续图像特征，从而在保持生成灵活性的前提下，消除信息瓶颈与训练噪声冲突。**

### 2. 论文提出的方法论

Orthus 的设计遵循“同一 Transformer 主干 + 模态专用预测头”的思路，流程如下：

- **连续视觉表示 (Soft VQ)**：
  抛弃严格的 VQ 离散化，利用公式 $h_i = \sum_j w_j \frac{e^{-d(v_i, c_j)/\tau}}{\sum_k e^{-d(v_i, c_k)/\tau}}$ （其中 $\tau$ 设为 1）将图像 Patch 特征转化为加权嵌入。该微小的修改将原有离散 Codebook 转化为可训练的连续视觉嵌入层，使得特征可以带梯度微调，消除了信息瓶颈。

- **全自回归（CAUSAL）上下文建模**：
  嵌入后的图文序列被拼接后送入标准 Transformer 网络，使用单一路径的因果注意力（Causal Attention）来学习图像特征块与文本 Token 之间的相互依赖关系。这避免引入 Transfusion 那种混乱的图像加噪机制。

- **模态专用头（Modality-Specific Heads）**：
  - **LM 头 (Language Modeling Head)**：负责预测下一个离散的文本 Token（分类任务）。
  - **Diffusion 头 (Diffusion Head)**：一个多层感知机（MLP），它以 Transformer 对当前 Patch 的特征输出 $f_i$ 为条件，通过条件扩散建模（Equation 3）以噪声预测损失 $\mathcal{L}_{\text{diff}}$ 重构下一个连续图像 $v_{i+1}$。
  
- **高效构建策略**：
  基于预训练的全 AR 模型（如 Chameleon-7B），仅需将 VQ 操作替换为 Soft VQ，加入扩散头并冻结主干，仅微调上述简单模块（约 0.3B 参数量），便可在极短时间内获得基础模型（Orthus-base）。

- **交错生成推理**：
  自回归采样的过程中，当模型预测到特殊的开始符 `[BOI]` 时，切换至“下一 Patch 预测”；生成完固定数量的 Patch 后，插入结束符 `[EOI]` 并自动切回文本生成模式。

### 3. 实验设计

论文在以下三个核心方向上配置了 benchmark 并对比了主流方法：

- **交错图文生成能力**：
  - *数据集*：InstructPix2Pix（图文编辑）和 StoryStream（故事绘本生成）。
  - *Benchmark*：CLIP Similarity（-T, -I, -D）。
  - *对比方法*：PnP, SDEdit, InstructPix2Pix 等专用编辑模型。
  
- **视觉理解评测**：
  - *数据集/Benchmark*：POPE, MME-P（重点考察 OCR 类能力），VQAv2, GQA, MMMU。
  - *对比方法*：
    - 通用统一模型：Show-o, LWM, Chameleon（及使用相同数据后训练的同版 Chameleon）。
    - 理解专精模型：LLaVA-1.5, InstructBLIP, Emu3-Chat。
    
- **视觉生成评测**：
  - *Benchmark*：GenEval（综合对齐指标）和 HPS（人类偏好评分）。
  - *对比方法*：SDXL, DALL-E, Transfusion, Show-o, Chameleon 等。

### 4. 资源与算力

- **GPU 配置**：所有训练均使用 **8 张 NVIDIA A100 80GB GPU** 的服务器。
- **训练效率**：
  - **Orthus-base**：从 Chameleon 转换而来，仅需在 10K 高质量图像上训练 **15,000 步**，总计耗时 **72 A100 GPU Hours**（9 小时），成本极低。
  - **后训练微调**：在混合图文指令数据上，使用 batch size 16 训练 **35,000 步**。

### 5. 实验数量与充分性

论文实施了大量实验以确保结论的客观性，大概进行了 20 组以上的 Benchmark 对比及消融实验，具体包括：
- **多维度基准测试**：覆盖了视觉理解、图像生成、交错图文生成三大领域的数十个通用榜单。
- **公平性对比**：
  - 特别对基线 Chameleon 使用了与 Orthus **完全相同的数据集**进行了后训练再对比。
  - 对比了单独训练、统一训练的效果（Table 4），证实了联合训练能提升跨模态性能增益。
- **关键模块消融**：
  - 对比了 Soft VQ 与硬 VQ (argmin)、线性投影 (linear) 的效果（Table 5）。
  - 验证了 Diffusion Loss 相较于简单 MSE Loss 在视觉生成上能避免颜色单调和模式坍塌的问题。
  - 对比了 VQ-VAE 与修改后连续 VAE 的重建质量（Table 6）。

这些实验设计有效地控制了变量，且覆盖了架构中的关键设计选择，具备较强的充分性和客观性。

### 6. 论文的主要结论与发现

- **架构有效性**：通过在 Transformer 后端解耦扩散过程，Orthus 实现了在保持输入无损（无 VQ）的前提下，完美兼容图文理解与生成任务。
- **性能优势**：在 7B 参数量级下，超越了同体量统一模型 Show-o 和 Chameleon（在 MME-P 和 GenEval 上有显著提升），甚至在生成指标上超过了某些专用扩散模型如 DALL-E 2。
- **交错生成能力**：是少数在图像编辑中展现出**上下文学习（In-Context Learning）** 能力的统一模型，且在长篇故事生成中（图像+文本）展示了极强的逻辑连贯性。
- **高效率**：从废除了 VQ 的全 AR 模型升级到 Orthus，仅需极少的算力（72 GPU 小时），这为社区复现提供了极大便利。

### 7. 优点

- **无损连续表示**：通过对 VQ 的“软化”操作（Softmax 近似），巧妙解耦了信息保留与 AR 范式的矛盾，在视觉理解细节（如 OCR）上优势显著。
- **设计高度解耦**：将 Diffusion 完全放到输出头而不要输入加噪，解决了 Transfusion 等架构中“理解需干净输入、生成需噪声输入”的矛盾。
- **极致的构建效率**：从现有多模态模型“嫁接”成为 Orthus 的低成本路径，大大降低了预训练门槛。
- **联合训练增益**：实验验证了图文联合训练比单独微调理解/生成模块的效果更好，揭示了跨模态信息互补的有效性。

### 8. 不足与局限

- **推理延迟较高**：自回归生成图像的步骤需要多次通过扩散头去噪（使用了 100 步的 DDIM 采样），导致图像生成速度远慢于单步解码的 VQ 方案。
- **模型规模受限**：受限于计算资源，目前仅在 7B 参数的 Chameleon 上进行了验证，尚未探索其在更大规模模型（如 30B 或 MoE 架构）上的表现。
- **扩散头设计简化**：扩散头采用的仅是一个浅层 MLP（加 AdaLN），对于更高分辨率或更复杂的视频生成任务，这种轻量设计的容量可能不足。
- **图像编解码器的限制**：模型目前特化在 512x512 分辨率，且原始 VQ-VAE 微调后虽提升了重建质量，但仍继承了该架构的潜在限制。

（完）
