---
title: "Glance2Gaze: Efficient Vision-Language Models from Glance Fusion to Gaze Compression"
title_zh: 从一瞥到凝视：从扫视融合到凝视压缩的视觉语言模型高效框架
authors: "Juan Chen, Honglin liu, Yingying Ao, Ting Zhang, Yan Huang, Xudong Liu, Biao Li, Jintao Fang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gm65gK3uOJ"
tags: ["query:affective-ai"]
score: 7.0
evidence: 受认知科学启发的两阶段注意力机制提升VLM效率
tldr: 针对视觉语言模型中视觉表征效率瓶颈，受人类视觉认知过程启发，提出Glance2Gaze框架。该框架包含瞥视融合和凝视压缩两个模块，通过文本感知注意力整合多层视觉变换特征，在保持性能的同时大幅降低计算开销。为高效VLM设计提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1415, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1449, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gm65gk3uoj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1340, \"height\": 449, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 717, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 786, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1327, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1078, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1367, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 905, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1074, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1078, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1031, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gm65gk3uoj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 522, \"label\": \"Table\"}]"
motivation: 现有VLM视觉标记压缩方法难以兼顾效率与语义保留。
method: 模仿人类扫视-凝视过程，设计瞥见融合与注视压缩模块。
result: 在视觉语言任务上实现高效压缩且性能损失小。
conclusion: 为认知启发的高效多模态学习开辟了新方向。
---

## Abstract
Vision-language models heavily rely on visual representations, yet ensuring its efficiency remains a critical challenge. Most existing approaches focus on reducing visual tokens either at the visual encoder phase or during the LLM decoder stage. Inspired by human visual cognition, where an initial global glance precedes focused attention on semantically salient regions, we introduce Glance2Gaze, a cognitively inspired framework that mimics the human two-stage attention process. The framework consists of two key components: the Glance Fusion module, which integrates multi-layer vision transformer features with text-aware attention to generate a semantically enriched global representation, and the Gaze Compression module, which utilizes a novel query-guided mechanism to selectively compress visual tokens based on their semantic relevance. Experimental results on widely adopted benchmarks demonstrate that Glance2Gaze outperforms existing methods, achieving superior performance with equal or lower computational cost. Furthermore, it generalizes well to high-resolution and video scenarios, showcasing robust and scalable efficiency improvements in VLMs.

---

## 论文详细总结（自动生成）

好的，以下是基于给定论文《Glance2Gaze: Efficient Vision-Language Models from Glance Fusion to Gaze Compression》的详细中文总结。

---

### 1. 核心问题与整体含义

- **研究问题**：大型视觉-语言模型（VLMs）依赖大量视觉标记以捕获细粒度信息，但这导致推理延迟和显存消耗随标记数量平方级增长，严重制约实际部署效率。
- **现有方法局限**：当前压缩视觉标记的方法多在视觉编码器阶段或语言模型解码阶段进行粗粒度剪枝，忽略了人类视觉认知中**先全局扫视再局部凝视**的层级化注意力过程，导致压缩时语义信息损失或适应性不足。
- **整体含义**：受认知科学启发，论文提出 **Glance2Gaze** 框架，模拟人类“一瞥”建立全局语义、“凝视”聚焦关键区域的二阶段注意力机制，从认知角度为高效视觉-语言建模提供新范式。

### 2. 方法论

整体框架由 **Glance Fusion（瞥见融合）** 和 **Gaze Compression（凝视压缩）** 两个核心模块组成，分别置于语言模型前后。

#### 2.1 Glance Fusion（瞥见融合）

- **目的**：在不增加视觉标记数量的前提下，动态融合视觉 Transformer（ViT）多层特征，生成富含指令相关语义的全局表示。
- **核心技术细节**：
  - 从 ViT 预设的层集合 \(L=\{l_1,...,l_S\}\) 中抽取多层视觉标记 \(\tilde{V} \in \mathbb{R}^{S\times N\times d_v}\)。
  - 通过投影器将其映射至文本嵌入空间，得到 \(\tilde{V}^Q\)；同时将指令文本嵌入 \(E_{ins}\) 经过层特异的线性投影，得到 \(E_{ins}^s\)。
  - 以 \(\tilde{V}^Q_s\) 为查询、\(E_{ins}^s\) 为键，计算缩放点积注意力矩阵 \(A_{v2t}^s\)，沿行平均后得到文本相关的空间相关性得分 \(G_{v2t} \in \mathbb{R}^{S\times N}\)。
  - 对 \(G_{v2t}\) 在层维度上应用 Softmax 得到权重，与各层视觉特征加权求和，获得**指令导向的增强视觉标记 \(V^Q\)**。
- **关键公式**：
  - \(A_{v2t}^s = \frac{\tilde{V}^Q_s E_{ins}^{s\top}}{\sqrt{d_t}}\)
  - \(G_{v2t} = \text{concat}(avg(A_{v2t}^s))\)
  - \(V^Q = \sum_{s=1}^S \tilde{V}^Q_s \odot \tilde{G}_{v2t}^s\)

#### 2.2 Gaze Compression（凝视压缩）

- **目的**：在 LLM 解码器中渐进式压缩视觉标记，模拟从全局凝视到局部聚焦的过程，降低深层计算量。
- **核心技术细节**：
  - 保留浅层全部标记，从预设第 \(r\) 层开始压缩。
  - 定义一个单调递减序列 \(P=[p_r, p_{r+1},...,p_R]\)，\(p_l\) 为第 \(l\) 层保留的压缩标记数。
  - 引入**共享的可学习查询池 \(Q_s \in \mathbb{R}^{p_r\times d_t}\)**，每层只取前 \(p_l\) 个查询，通过交叉注意力将上一层的视觉标记 \(H_{l-1}\) 压缩为 \(H_l\)。
  - 使用 2D 旋转位置编码增强查询的空间感知能力。
- **关键公式**：
  - \(H_l = F_o\left(\text{softmax}\left(\frac{F_q(PE(Q_l^s))F_k(H_{l-1})^\top}{\sqrt{d_t}}\right)F_v(H_{l-1})\right)\)
- **效率分析**：总计算量包含 LLM 标准前向 FLOPs 与压缩模块额外开销，整体可控制在同等或更低 FLOPs 水平（例如 33%、22%、11%、6%）。

### 3. 实验设计

- **图像理解任务**：
  - 数据集：TextVQA、POPE、GQA、VQAv2、SEEDBench、MMBench、MME、ScienceQA-IMG、MMVet、LLaVA-Bench-in-the-Wild。
  - 基准模型：LLaVA-1.5-7B 与高分辨率变体 LLaVA-NeXT-7B。
  - 对比方法：FastV、SparseVLM、PDrop、VisionZip 等最新视觉标记压缩方案。
  - 压缩配置：在 33%、22%、11% FLOPs（及 5% 极高压缩率）下全面评估。
- **视频理解任务**：
  - 数据集：TGIF、MSVD、MSRVTT、ActivityNet。
  - 基准模型：Video-LLaVA（每视频 8 帧，共 2048 个视觉标记）。
  - 压缩配置：仅 6% FLOPs 的极端压缩下对比其他方法。
- **效率测试**：在 A100-80G 上测量实际 CUDA 预填充时间、整体延迟与吞吐量。

### 4. 资源与算力

- **硬件**：所有实验在 **8 块 NVIDIA-A100-80G** GPU 上完成。
- **训练时长**（见补充材料 Table 10）：
  - LLaVA-1.5-7B 全模型训练需 **104 GPU 小时**；对应 Glance2Gaze（33% FLOPs）为 72 GPU 小时。
  - LLaVA-NeXT-7B 全模型训练需 **366 GPU 小时**；对应 Glance2Gaze（22% FLOPs）为 242 GPU 小时。
  - Video-LLaVA 全模型训练需 **297 GPU 小时**；Glance2Gaze（6% FLOPs）为 151 GPU 小时。
- **补充说明**：训练成本随压缩率增大而明显降低，符合高效压缩的预期。

### 5. 实验数量与充分性

- **实验组数量**：涉及 3 种骨干模型（LLaVA-1.5-7B、LLaVA-NeXT-7B、Video-LLaVA），超过 10 个基准数据集，4 种压缩率，与 4 个核心基线全面对比，合计数十组主要结果。
- **消融研究**：
  - 共享查询池 vs. 逐层独立查询；
  - 有无 Glance Fusion 的对比；
  - 压缩起始层 \(r\) 和查询尺寸 \(p_r\) 的影响；
  - Glance Fusion 中融合层数及是否注入指令的作用；
  - Gaze Compression 与基于注意力的静态剪枝方法对比（含微调与无微调）。
- **充分性与公平性**：实验设计覆盖静态图像、高分辨率、视频三大场景，不仅比较准确率，还严格对比 FLOPs、延迟与吞吐量，消融系统全面，基线方法均严格按照原论文配置复现或采用开源实现，评估公平客观。

### 6. 主要结论与发现

- Glance2Gaze 在相同或更低计算量下，**性能持续优于** FastV、SparseVLM、PDrop、VisionZip 等主流方法。
- 在 33% FLOPs 下可保持 99.9% 原始性能；极端压缩至 11% FLOPs 时仍保留 95.6%，鲁棒性突出。
- 高分辨率场景（LLaVA-NeXT）中优势更加显著，平均超越第二名 1.2–1.3 个百分点。
- 视频理解仅用 6% FLOPs 即达到原模型 96.2% 的性能，极适合实时大规模视频分析。
- 实际推理速度：预填充时间加速 6.39 倍，整体延迟降低 3.15 倍，吞吐量提升 3.14 倍。
- 认知启发的二阶段设计有效弥合了粗粒度剪枝与细粒度语义保留之间的差距。

### 7. 优点

- **新颖的认知视角**：首次将人类“扫视-凝视”的眼动模式系统性引入 VLM 视觉标记压缩，为高效多模态学习提供生物启发路径。
- **模块化与即插即用**：Glance Fusion 和 Gaze Compression 均可方便集成到现有 VLM 架构，不改变基础模型结构。
- **无损轻量融合**：Glance Fusion 利用文本感知注意力动态聚合多层 ViT 特征，额外计算开销可忽略（< 2.72% 总 FLOPs），却能带来显著性能提升。
- **渐进式压缩策略**：保留浅层全量标记、深层逐步压缩的设计平衡了语义理解与计算效率，且共享查询池设计减少参数量的同时保持了压缩质量。
- **完备的效率评估**：同时报告 FLOPs、CUDA 时间、端到端延迟和吞吐量，贴近实际部署需求。
- **泛化能力强**：在静态图像、高分辨率 OCR、长序列视频场景中均表现优异，验证了框架的通用性。

### 8. 不足与局限

- **启发式设计**：融合和压缩策略很大程度上仍是经验主义设计，未显式建模人类认知过程的神经机制，理论可解释性与精细度尚有提升空间。
- **VLMs 骨架局限**：实验仅基于 LLaVA 系列和 Video-LLaVA，对其他架构（如 Flamingo、BLIP-2 等）的适用性未验证。
- **训练依赖与数据限制**：依赖于 LLaVA 特定的指令调优数据，若换用其他风格的数据集或任务，微调策略和效果可能波动。
- **极端压缩的细节损失**：在 11% 或更低的 FLOPs 下，虽然平均性能维持较好，但个别需要极精细 OCR 的数据集（如 TextVQA）仍有一定降幅。
- **认知建模不完整**：凝视压缩主要依赖学习到的查询，缺乏对注视点转移、扫视抑制等真实生物机制的模拟，可能限制在高复杂度推理任务中的表现。
- **未报告统计显著性**：实验未提供多次运行的误差线或显著性检验，结果波动性未量化。

---

（完）
