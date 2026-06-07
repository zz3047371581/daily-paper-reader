---
title: Unifying Specialized Visual Encoders for Video Language Models
title_zh: 统一专用视觉编码器用于视频语言模型
authors: "Jihoon Chung, Tyler Zhu, Max Gonzalez Saez-Diez, Juan Carlos Niebles, Honglu Zhou, Olga Russakovsky"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oYzDcCZdR9"
tags: ["query:affective-ai"]
score: 9.0
evidence: 通过交叉注意力融合多视觉编码器用于视频语言模型，是跨模态对齐技术
tldr: 针对现有视频大语言模型仅用单一视觉编码器的问题，提出MERV方法，通过时空对齐和交叉注意力融合多编码器特征，获得更全面的视频表示，提升视频理解准确率。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1686, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 772, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 798, \"height\": 822, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 850, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1681, \"height\": 1586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1752, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1706, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1591, \"height\": 2048, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1687, \"height\": 1377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1702, \"height\": 887, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1782, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 497, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 500, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 510, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1431, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1613, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1260, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 943, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 942, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1603, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1686, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 587, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1690, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1693, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1605, \"height\": 360, \"label\": \"Table\"}]"
motivation: 单一视觉编码器限制视频语言模型获取多样视觉信息。
method: MERV对齐多编码器特征时空，投影后通过交叉注意力融合。
result: "在视频理解任务上准确率提升高达4.62%。"
conclusion: 多编码器融合是提升视频语言模型性能的有效途径。
---

## Abstract
Recent advances in vision backbones have yielded powerful and diverse visual and video encoders. Yet, current Video Large Language Models encode visual inputs using an encoder from a single backbone family, limiting the amount and type of visual information they can process. We propose MERV, a Multi-Encoder Video Representation, which utilizes multiple encoders for a comprehensive video representation. To optimize heterogeneous features from a broad spectrum of encoders and ensure efficient and coherent feature integration, MERV first aligns encoder features spatio-temporally, then projects them into a unified structure, and finally fuses them through cross-attention. Under fair comparison, MERV achieves up to 4.62% higher accuracy than its base model, while introducing minimal extra parameters and training faster than equivalent single-encoder methods after parallelizing visual processing. Qualitative analysis shows MERV successfully captures and integrates domain knowledge from each encoder, opening new possibilities for scaling enhanced video understanding.

---

## 论文详细总结（自动生成）

好的，遵照你的要求，以下是对这篇论文的详细中文总结。

### 1. 论文的核心问题与整体含义
*   **核心问题**：当前的视频大语言模型在编码视觉信息时，普遍仅依赖单一类型的视觉编码器。这种“一刀切”的做法制约了模型对视频的全面理解能力，因为不同的视觉编码器（如擅长语义对齐的CLIP/SigLIP、擅长细粒度目标理解的DINOv2、擅长时序动作建模的ViViT）各有其独特的优势和局限，单一编码器难以捕捉一部视频中的所有关键信息。
*   **整体含义**：本文旨在打破依赖单一视觉编码器的范式，提出一种能够有效整合多种异构视觉编码器特征的视频语言模型框架，通过对不同专家知识的互补利用，生成一个更全面、更具表征力的视频表示，从而显著提升视频理解的整体性能。

### 2. 论文提出的方法论
*   **核心思想**：提出 **MERV (Multi-Encoder Video Representation)** 方法，通过“时空对齐-统一投影-交叉注意力融合”的流程，将多个来源不同、特性各异的视觉编码器特征高效整合进一个大语言模型中。
*   **关键技术细节与流程**：
    1.  **多编码器特征提取 (Sec 3.1)**：精心选择四种代表性编码器，构成一个互补的专家集合。
        *   **空间专家**: DINOv2，擅长细粒度物体理解。
        *   **时序专家**: ViViT，擅长长程时序依赖建模。
        *   **图文对比专家**: SigLIP，擅长视觉-语言语义对齐。
        *   **视频-语言对比专家**: LanguageBind，擅长视频级高级语义与语言关联。
    2.  **时空对齐与预融合投影 (Sec 3.2)**：
        *   **对齐**：通过调整输入帧数，使得不同编码器（无论是否进行时序下采样）输出的时序维度一致；再通过`2D自适应平均池化`将空间维度统一到`h × w`。这样，所有编码器的输出特征图`v_e`在时空结构上实现了对齐。
        *   **投影**：将对齐后的特征用一个轻量级线性层`W_e`将其嵌入维度从各异的`d_e`统一投影到LLM的维度`d`。形成`x_e = P(v_e) We`，其中`x_e`是投影后的时空令牌序列。
    3.  **交叉注意力特征融合 (Sec 3.2)**：
        *   采用一个可学习的查询向量`Q`，与所有编码器特征的均值`X`进行交叉注意力计算，得到一个融合了所有专家信息的最终视觉嵌入`O`。
        *   核心计算公式为：`O = Softmax( (Q X^T) / sqrt(d) ) * X`。这个机制通过计算注意力权重来决定不同编码器特征的混合比例（线性混合），具有动态、输入依赖的优点。
    4.  **训练策略 (Sec 3.3)**：提出了两种训练方案：
        *   **MERV (frozen)**：只进行第二阶段的指令微调，训练速度快，性能强劲，作为默认设置。
        *   **MERV (full)**：包含第一阶段的对齐预训练和第二阶段的指令微调，且在预训练阶段解冻LLM，在部分复杂基准上表现更好。

### 3. 实验设计
*   **使用数据集与场景**：
    *   **训练数据**：沿用Video-LLaVA的混合数据，包括558k图像-文本对和702k视频-文本对用于预训练，665k图像-文本对和100k视频指令对用于指令微调。
    *   **评测基准 (Benchmark)**：在八个标准的视频理解数据集上进行了全面评估，覆盖了开放问答和多选题两种形式。
        *   **开放问答**: MSVD-QA, MSRVTT-QA, TGIF-QA, ActivityNet-QA
        *   **多选题**: NExT-QA, VLEP, TVQA, Perception Test
        *   **专项分析**: 构建了 Something-Something v2 的多选题版本来精细评估模型的细粒度时序理解能力。
*   **对比方法**：与多个同期或早期的视频语言模型进行了公平对比，包括 Video-LLaVA, LLaMA-VID, Video-ChatGPT, SeViLA 等。特别地与使用相同训练数据混合的 **Video-LLaVA** 进行了直接对比，以隔离方法本身带来的增益。

### 4. 资源与算力
*   **训练硬件与时长**：
    *   训练可在8块 L40-48GB GPU上在24小时内完成。
    *   若使用8块 H100 GPU，训练时间可缩短至8小时。
    *   与之对比，Video-LLaVA的代码库在相同L40配置下完成第二阶段训练需约38小时。作者利用 PyTorch FSDP 并行化视觉编码过程，使得多编码器方法在总训练时间上并未显著增加。

### 5. 实验数量与充分性
*   **实验组数**：论文进行了大量的消融和对比实验来验证设计的合理性，实验非常充分。
    *   **主体对比实验**：在8个基准上与多个现有方法进行性能对比。
    *   **消融研究 (Ablation)**：
        *   **预融合投影器**：对比了2D平均池化、注意力重采样器、2D/3D卷积等多种投影策略及其参数和FLOPs。
        *   **投影令牌长度**：探究了从1到256的不同令牌数对性能的影响。
        *   **特征融合策略**：对比了序列拼接、通道拼接、可学习权重混合、固定权重混合以及交叉注意力融合。
        *   **训练配方**：对比了仅第二阶段训练、完整两阶段训练、单阶段混合训练等不同策略。
        *   **编码器组合**：通过分别移除一个编码器或训练单编码器基准模型，论证了每个编码器对最终性能的贡献。
    *   **定性分析**：通过可视化交叉注意力权重、分析模型在WH-问题类型上的表现、以及在SSv2数据集上的时序vs.全局理解能力，深入剖析了模型行为。
*   **公平性**：实验设计力求公平，例如固定了与Video-LLaVA相同的训练数据，使用了相同的评测协议，并和相同大小的7B参数模型进行对比。

### 6. 论文的主要结论与发现
*   **性能提升显著**：MERV在多个基准上显著超越其基线模型Video-LLaVA，例如在TVQA上准确率提升高达4.62%，在Perception Test上也有大幅领先。
*   **多编码器协同有效**：实验证明，模型能够成功捕获并集成来自不同编码器的领域知识。例如，ViViT擅长辨别“向左推”和“向右推”这类时序模糊动作，而SigLIP则擅长理解需要场景语义的任务，MERV能同时兼顾这两者，且没有性能上的“此消彼长”。
*   **关键设计的作用**：
    *   时空对齐的2D平均池化是高效且性能优异的投影选择。
    *   基于交叉注意力的动态特征融合策略优于简单的拼接方法，且计算效率更高。
    *   即使只进行指令微调（MERV frozen），也能达到甚至超越完整两阶段训练的基线模型的性能，显示了该方法的高效性。
*   **计算开销可控**：通过并行化处理，引入多个视觉编码器带来的额外训练时间开销很小，主要被速度最慢的单编码器耗时所覆盖。

### 7. 优点
*   **方法论创新**：首次系统性地探索并验证了在视频语言模型中融合多种纯视觉（RGB）、但训练目标和架构各异的编码器的可能性与有效性，打破了单编码器的路径依赖。
*   **设计简洁高效**：提出的“池化+线性投影”的时空对齐方案极其轻量，而交叉注意力融合器则能以动态、解释性强的方式整合信息，整体方法在效率和性能间取得了很好的平衡。
*   **分析深刻**：不仅仅是性能刷榜，论文通过WH-问题类型分析、SSv2时序任务分析、注意力权重可视化等手段，深入揭示了“多专家”模型相较于“单专家”模型在能力上如何实现互补与协同，解释性强。
*   **可扩展性强**：方法本身不限于文中使用的四种编码器，作者已初步验证了增加新编码器的可行性，为未来持续扩展和增强视频理解模型提供了清晰的技术途径。

### 8. 不足与局限
*   **LLM依赖性强**：模型性能上限仍受限于所用的大语言模型（LLaMA-2 7B），更强或不同的LLM会带来不同的性能表现，且更强大的LLM计算成本更高。
*   **计算资源门槛**：尽管进行了优化，同时运行多个编码器和一个7B/13B级别的LLM依然对显存（VRAM）有较高要求，在资源受限的场景（如消费级显卡）上运行困难。
*   **编码器自身的局限性**：MERV的性能受限于其所集成的单个编码器的能力上限。如果一个编码器本身在某个方面存在缺陷，MERV无法“无中生有”地完全弥补。
*   **并行化策略的潜力未能完全发挥**：受限于PyTorch FSDP当前的能力，作者无法实现更精细、定制化的GPU着色策略，这暗示还有进一步提升计算效率的空间。
*   **数据集泛化能力**：作者也观察到，由于视频训练数据和评测基准之间的数据分布差异，零样本泛化性能可能未达到最优，模型的对齐能力仍有改进空间。

（完）
