---
title: "DS-VLM: Diffusion Supervision Vision Language Model"
title_zh: DS-VLM：扩散监督视觉语言模型
authors: "Zhen Sun, Yunhang Shen, Jie Li, Xing Sun, Pingyang Dai, Liujuan Cao, Rongrong Ji"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NEBa0bs5LR"
tags: ["query:affective-ai"]
score: 8.0
evidence: 基于扩散的直接监督用于视觉-语言对齐，提升跨模态特征质量
tldr: 针对视觉语言模型中文本监督语义稀疏和梯度传播信息损失的问题，提出DS-VLM框架：通过以视觉编码器和连接器输出为条件的扩散模型重构输入图像，建立像素空间到视觉特征的短路径梯度通道。该方法在保持高层语义对齐的同时，利用扩散监督增强底层视觉细节。实验证明DS-VLM在多个视觉语言任务上一致提升性能，是可推广的对齐增强方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 770, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 789, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1328, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 841, \"height\": 546, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 803, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 801, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 802, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1764, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1222, \"height\": 192, \"label\": \"Table\"}]"
motivation: 现有视觉语言模型受限于文本监督稀疏和梯度传递损失，导致视觉表征细节不足。
method: 引入扩散模型作为直接监督，以重构图像方式建立像素到视觉特征的短路径梯度传播。
result: 在多个视觉语言任务上，DS-VLM一致提升基线模型性能，细节表征增强。
conclusion: 验证了扩散监督在视觉语言对齐中的有效性，为跨模态表示学习提供新途径。
---

## Abstract
Vision-Language Models (VLMs) face two critical limitations in visual representation learning: degraded supervision due to information loss during gradient propagation, and the inherent semantic sparsity of textual supervision compared to visual data. We propose the Diffusion Supervision Vision-Language Model (DS-VLM), a plug-and-play framework that introduces diffusion-based direct supervision for vision-language alignment. By reconstructing input images through a diffusion model conditioned on outputs of the visual encoder and the connector, our method establishes a short-path gradient propagation channel from pixel space to visual features. This approach simultaneously preserves high-level semantic alignment through conventional text supervision while enhancing visual feature quality via pixel-level reconstruction constraints. Extensive experiments conducted across various visual encoders and LLMs of different scales demonstrate the effectiveness of our approach.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
当前视觉语言模型（VLM）在视觉表示学习中存在两个关键瓶颈：  
- **梯度传播过程中的信息损失**：文本监督信号需经由参数量庞大的大语言模型（LLM）回传至视觉编码器与连接器，优化路径过长导致知识衰减严重。  
- **文本监督自身的语义稀疏性**：相较图像，文本包含的细粒度视觉语义（如结构、布局、纹理）远不够丰富，难以完整约束视觉特征。  

论文提出 **DS-VLM**，一种即插即用的扩散监督框架，通过以视觉编码器与连接器的输出为条件重建输入图像，在像素空间与视觉特征之间建立**短路径梯度传播通道**，从而在保留常规文本语义对齐的同时，利用图像本身的高信息密度直接增强视觉表示质量。

### 2. 方法论
DS-VLM 的核心思想是：在训练阶段引入一个预训练的潜扩散模型（Stable Diffusion）作为“知识中介”，将图像的重建损失直接反传到视觉编码器和连接器，无需经过 LLM。

**关键技术细节**：
- **监督特征的划分**  
  - **图像模态监督特征**：从视觉编码器的低、中、高层分别提取特征（例如 CLIP ViT-L 的第 8、16、24 层），以涵盖不同粒度的视觉语义。  
  - **文本模态监督特征**：连接器（MLP projector）输出的特征因已映射至文本嵌入空间，视为文本模态监督。  

- **Multi-Adapter Diffusion（多适配器扩散）**  
  基于 Stable Diffusion 的 U‑Net 架构，为不同模态的特征设计独立的适配器，并引入 **MOE Cross Attention** 机制：  
  - 在原有文本交叉注意力层之外，为低、中、高三层图像特征各添加一个交叉注意力层。  
  - 所有交叉注意力的输出通过一个可学习的路由权重（Softmax 归一化）进行加权融合：  
    \[
    Z_{\text{new}} = P_0 Z' + \sum_{i=1}^3 P_i Z''_i
    \]  
    其中 \(Z'\) 为原有文本注意力输出，\(Z''_i\) 为第 \(i\) 层图像注意力输出，\(P\) 由查询特征 \(Q\) 经过线性投影和池化后计算得到。  
  - 图像注意力的 key/value 投影矩阵以文本注意力的对应权重初始化，加速收敛。

- **重建损失的选择**  
  比较了三种粒度的重建损失：像素级 MAE、结构级 SSIM、语义级感知损失（Perceptual Loss）。实验表明**感知损失**最能保留图像细节和语义信息，作为默认设置。

- **训练与推理**  
  - 训练时扩散模型与视觉编码器、连接器联合优化，LLM 仍通过文本 next-token prediction 保持高层语义对齐。  
  - 推理时**移除扩散模型**，不增加任何参数和计算开销，做到即插即用。

### 3. 实验设计
**数据集**  
完全沿用 LLaVA-1.5 的开源数据：  
- 预训练：558K 图像-标题对  
- 指令微调：665K 多轮对话  
同时在 Mini-Gemini 的更大规模数据（1.2M + 1.5M）上验证可扩展性。

**Benchmark**  
在 10 个广泛使用的 VLM 基准上评估：  
MMBench、MMStar、MMMU、MathVista、OCRBench、AI2D、HallusionBench、LLaVABench、ScienceQA、MME。

**对比方法**  
- **基线**：LLaVA-1.5 在不同 LLM（Vicuna‑7B/13B, Llama‑3‑8B, Qwen2‑7B）和视觉编码器（CLIP‑L, SigLIP‑SO）下的原始版本。  
- **SoTA**：MiniGPT4、Qwen‑VL、VisualGLM、PandaGPT、mPLUG‑Owl2、Emu2‑chat、Yi‑VL、ShareGPT‑4V。  
- **消融**：对监督特征类型、重建损失、注意力机制、适配器结构等进行剥离实验。

### 4. 资源与算力
论文**未明确提及**使用的 GPU 型号、数量、训练时长或任何具体算力开销。文中仅在实现细节中说明训练基于 PyTorch 框架、LoRA 秩设为 8、扩散模型采样步数 50 等超参数，但未提供硬件资源信息。

### 5. 实验数量与充分性
论文设计了**多层次、多维度**的实验：
- **主实验（Table 1）**：4 种 LLM + 2 种视觉编码器 + 2 种数据规模，共 8 组配置对比原始 LLaVA‑1.5，涵盖 10 个 benchmark。  
- **SoTA 对比（Table 2）**：与 8 个主流方法在相同基准上横向比较。  
- **消融研究**：
  - 监督特征组合（Table 3）：从纯文本监督到文本+低/中/高图像全监督的 6 组实验。  
  - 重建损失类型（Table 4）：MAE、SSIM、感知损失。  
  - 独立 vs 共享交叉注意力（Table 5）。  
  - 适配器结构（Table 6）：线性 MLP 与 Q‑Former。  
- **补充实验**：
  - 与可训练编码器的 LLaVA‑1.5 对比（Table 7）。  
  - 验证视觉编码器在训练中真正被优化（Table 8）：冻结编码器与联合训练的重建损失对比。

实验设置**公平**（统一数据和超参数），对比全面，消融维度丰富，能充分证明方法的有效性及各模块的贡献。

### 6. 主要结论与发现
- DS‑VLM 在各种配置下均能**一致提升**基线模型性能。例如，在 Vicuna‑7B + CLIP‑L 下，10 个基准平均提升约 1.4%；MMBench 提升 2.4%，MMMU 提升 2.1%，LLaVABench 提升 2.5%。  
- 扩散监督带来的短路径梯度传播能**更有效地优化视觉编码器和连接器**，提升视觉特征细节和语义丰富度。  
- 方法对视觉编码器（CLIP、SigLIP）和 LLM（Vicuna、Llama3、Qwen2）均表现出良好的**通用性和可移植性**。  
- 多层级图像监督与文本监督的组合能使模型在**细粒度感知、空间结构理解、抗幻觉能力**方面获得显著增益。

### 7. 优点
- **即插即用，无推理代价**：训练时加入扩散模型，推理时去除，保持原有 VLM 的推理速度。  
- **短路径监督**：直接利用图像重建误差优化视觉前端，避免长链传播的信息损失。  
- **多模态、多层级监督融合**：巧妙地将视觉编码的中间层特征和连接器输出作为扩散条件，兼顾底层纹理与高层语义。  
- **设计精巧的 MOE 交叉注意力**：独立建模不同模态特征，通过可学习路由融合，有效避免模态干扰。  
- **实验扎实全面**：在多个主干网络、数据规模和任务上的广泛验证，以及细致的消融分析，结论可信度高。

### 8. 不足与局限
- **训练成本未明**：虽然推理无额外开销，但训练时需运行扩散模型，会增加显存与时间消耗，但论文未提供量化数据，无法评估实际可行性。  
- **扩散模型依赖**：方法依赖于预训练的 Stable Diffusion，若下游任务图像域与扩散模型训练域存在较大偏差，重建质量可能下降，影响监督效果。  
- **仅在公开的指令微调范式下验证**，且视觉主干限于 ViT 架构的 CLIP/SigLIP；对于其他类型的视觉编码器（如 CNN、层次化 ViT）或更大规模的数据集（如数十亿样本）的适应性未探讨。  
- **评估偏向通用 VLM 基准**，缺乏在专业领域（医学、遥感等）或需要极高精度的定位、计数任务上的测试，方法的泛化边界待进一步明确。  
- 未与其它直接优化视觉特征的对齐方法（如对比学习、特征蒸馏）进行直接比较，难以判断相对优势的幅度。

（完）
