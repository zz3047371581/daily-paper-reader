---
title: "Vision as a Dialect: Unifying Visual Understanding and Generation via Text-Aligned Representations"
title_zh: 视觉作为一种方言：通过文本对齐表征统一视觉理解与生成
authors: "Jiaming Han, Hao Chen, Yang Zhao, Hanyu Wang, Qi Zhao, Ziyan Yang, Hao He, Xiangyu Yue, Lu Jiang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ILr4UNiZcQ"
tags: ["query:affective-ai"]
score: 9.0
evidence: 通过文本对齐的离散令牌统一视觉理解与生成；跨模态大语言模型
tldr: 本文提出文本对齐分词器TA-Tok，将图像转换为从LLM词汇表投影的离散令牌，并通过扩展词汇表构建多模态大语言模型Tar，实现视觉理解与生成的统一框架。尺度自适应编解码和生成式去分词器保证了高效与高质量输出。实验表明，该统一架构在多模态任务上达到了有竞争力的性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 568, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1437, \"height\": 848, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1431, \"height\": 250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1435, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1431, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1431, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilr4unizcq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1434, \"height\": 250, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 834, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 900, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 602, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 701, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 653, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 704, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 487, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1387, \"height\": 790, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1023, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1112, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1229, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1452, \"height\": 958, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilr4unizcq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1233, \"height\": 804, \"label\": \"Table\"}]"
motivation: 现有视觉与语言模型多为任务专用设计，缺乏统一的语义空间和跨模态生成能力。
method: 设计文本对齐的视觉分词器，将图像投影到LLM语义空间，并通过多模态大语言模型实现统一理解与生成。
result: 在多项视觉问答和图像生成基准上，Tar展现出一致的性能优势和高保真输出。
conclusion: 该框架通过统一表征促进了视觉与语言的深度融合，为通用多模态智能提供了新路径。
---

## Abstract
This paper presents a multimodal framework that attempts to unify visual understanding and generation within a shared discrete semantic representation. At its core is the Text-Aligned Tokenizer (TA-Tok), which converts images into discrete tokens using a text-aligned codebook projected from a large language model's (LLM) vocabulary. By integrating vision and text into a unified space with an expanded vocabulary, our multimodal LLM, **Tar**, enables cross-modal input and output through a shared interface, without the need for modality-specific designs. Additionally, we propose scale-adaptive encoding and decoding to balance efficiency and visual detail, along with a 
generative de-tokenizer to produce high-fidelity visual outputs. To address diverse decoding needs, we utilize two complementary de-tokenizers: a fast autoregressive model and a diffusion-based model. To enhance modality fusion, we investigate advanced pre-training tasks, demonstrating improvements in both visual understanding and generation. Experiments across benchmarks show that **Tar** matches or surpasses existing multimodal LLM methods, achieving faster convergence and greater training efficiency. All code, models, and data will be made publicly available.

---

## 论文详细总结（自动生成）

# 论文深度解析：《Vision as a Dialect: Unifying Visual Understanding and Generation via Text-Aligned Representations》

---

## 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：如何在一个统一的多模态大语言模型（MLLM）中，同时实现高性能的视觉理解（如图像描述、问答）与视觉生成（如文本生成图像），而不依赖针对不同任务的独立编码器或不同模态的特定设计。
*   **现有方法局限**：
    *   **分离表征**：视觉理解常用连续语义特征（如 CLIP），视觉生成常用像素级离散特征（如 VQVAE）。这种分离阻碍了统一推理和交替生成/编辑等任务。
    *   **连续表征**：虽利于理解，但需回归或扩散等目标才能生成，偏离了 LLM 的自回归范式。
    *   **离散表征**：虽与 LLM 自回归预测天然兼容，但往往存在量化误差，且难以同时捕获高层语义和底层细节。
*   **整体含义**：论文提出将视觉视为一种“方言”，通过与语言共享的离散语义空间，消除模态壁垒，实现在一个统一的、全离散的、语义驱动的框架内无缝处理视觉输入与输出，推动真正多模态智能的发展。

---

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 核心思想
构建一个完全离散、语义对齐的共享表示空间，使 LLM 能够像处理文本一样统一地理解和生成图像，无需模态特定的编解码器或训练目标。

### 2.2 关键技术组件
*   **文本对齐分词器（Text-Aligned Tokenizer, TA-Tok）**：
    *   **目的**：将图像编码为与 LLM 语义空间对齐的离散视觉 Token。
    *   **架构**：SigLIP2 视觉编码器 -> 尺度自适应池化（SAP） -> 文本对齐码本（TA Codebook） -> 矢量量化 -> 尺度自适应解码（SAD）& SigLIP2 教师模型（仅训练时）。
    *   **文本对齐码本（Text-Aligned Codebook）**：码本条目由预训练 LLM 的 Token 嵌入矩阵 `E` 通过可训练投影矩阵 `W` 初始化，即 `C = EW`。例如，从 Qwen2.5 的 15 万词表中选取 65536 个代表性嵌入。这确保了视觉 Token 与文本 Token 在 LLM 的潜在空间中是语义相关的。
    *   **训练目标**：结合特征重建损失 `L_rec`（使解码特征逼近教师模型输出）和码本损失 `L_code`，仅训练投影矩阵 `W`，冻结 LLM 嵌入 `E`。

*   **尺度自适应池化与解码（Scale-Adaptive Pooling & Decoding, SAP & SAD）**：
    *   **目的**：根据不同任务对视觉细节的需求（生成可粗糙，理解需精细）动态调整 Token 序列长度。
    *   **实现**：对 384x384 输入，使用尺度因子 `s ∈ {1, 2, 3}`，通过自适应池化分别生成 `{729, 169, 81}` 个 Token，实现多粒度特征提取。

*   **生成式去分词器（Generative De-Tokenizers）**：
    *   **目的**：将 TA-Tok 产生的语义 Token 解码为高保真图像，弥补语义表征缺失底层细节的不足。
    *   **两种变体**：
        1.  **自回归去分词器（AR-DTok）**：将解码视为基于 VQVAE 图像 Token 和 TA-Tok 视觉条件 Token 的自回归预测任务，推理快，与离散空间天然兼容。
        2.  **扩散去分词器（Dif-DTok）**：基于预训练扩散模型（如 SANA），将视觉条件 Token 通过交叉注意力注入，仅需少量数据微调即可获得高质量图像。

*   **统一多模态 LLM（Tar）**：
    *   **架构**：将文本嵌入矩阵 `E` 与视觉码本 `C` 拼接，扩展 LLM 词汇表。模型在由文本 Token 和视觉 Token 混合组成的序列上，以标准的自回归交叉熵损失进行下一个 Token 预测。
    *   **推理**：视觉理解时，输入图像 Token + 文本，生成文本；视觉生成时，输入文本，自回归采样生成图像 Token，再送入去分词器。
    *   **高级预训练任务**：除了常规的图像到文本（I→T）、文本到图像（T→I）等任务外，创新性地引入图像到图像（I→I）和文本-图像到图像（TI→I）任务，以促进模态深度融合。例如，TI→I 任务要求模型结合一张图像和一段描述性文本来生成目标图像。

### 2.3 关键公式与流程
*   **码本初始化**：`C = EW`，其中 `E` 为冻结的 LLM 词嵌入，`W` 为可学习投影矩阵。
*   **损失函数**：
    *   重构损失：`L_rec = 1 - cos(z_y, ẑ_y)`（余弦相似度损失）。
    *   码本损失：`L_code = ||sg(E·W) - z_q||² + ||EW - sg(z_q)||²`。
*   **MLLM 训练损失**：标准交叉熵 `L_CE = -Σ log p(u_i|u<ifinish_thought>); θ)`，其中 `u_i` 可以是文本或视觉 Token。

---

## 3. 实验设计

*   **数据集**：
    *   **分词器/去分词器训练**：LAION-5B（100M 原始图像 + 100M 美学过滤图像）、23M 高质量的合成图像（由 FLUX 模型基于 Qwen2.5-VL 生成的详细描述及用户提示词生成）、Megalith-10M、JourneyDB 等。
    *   **MLLM 预训练/微调**：多样化的数据混合，包括 LLaVA-Recap-CC12M、DataComp（I2T）、合成数据集 Gen23M（T2I）、专门构建的 I2I 和 TI2I 数据集，以及来自 Magpie、WebInstruct 等的纯文本数据。
*   **基准（Benchmarks）**：
    *   **视觉理解**：POPE, MME, MMBench, SEED-Bench, GQA, MMMU。
    *   **视觉生成**：GenEval, DPG-Bench。
*   **对比方法**：
    *   **纯理解模型**：LLaVA-v1.5, Qwen-VL-Chat, DeepSeekVL 等。
    *   **统一模型**：Janus/Janus-Pro, Emu3, Chameleon, Show-o, Transfusion, ILLUME, VILA-U, UniTok, MetaMorph 等。
    *   **纯生成模型**：SDXL, Playground v2.5, Hunyuan DiT, PixArt-Σ, DALLE 3, SD3-Medium, SANA-1.5 等。

---

## 4. 资源与算力

*   **论文中未提供具体的 GPU 型号、数量及总训练时长（GPU hours）信息**。仅在各组件训练参数表中提供了优化器、学习率、批次大小等超参数。例如，TA-Tok 使用总样本 200M，总批次 512；AR-DTok 在 256px 分辨率使用总批次 768 等。读者无法从文中直接评估实际的算力开销。

---

## 5. 实验数量与充分性

*   **实验数量可观且体系完整**：
    *   **主结果实验**：分别报告了在 7 大视觉理解基准和 2 大生成基准上，与 10 余种代表性统一方法及专用方法的性能对比，覆盖了 1.5B 和 7B 两个模型规模。
    *   **详尽的消融研究**：
        1.  视觉表征对比（VQVAE vs. Janus 式分离表征 vs. 混合表征 vs. 本文 TA-Tok），从 1M 到 10M 数据规模，同时评估理解和生成性能。
        2.  MLLM 嵌入初始化（随机 vs. 预对齐 vs. TA-Tok）。
        3.  不同去分词器（AR 不同尺寸/分辨率 vs. 扩散）。
        4.  尺度自适应池化的影响。
        5.  联合训练 vs. 分离训练对各个任务的影响。
        6.  高级预训练任务（I2I, TI2I）的贡献。
        7.  文本对齐码本设置（维度、大小、初始化）。
        8.  Self-Reflect 策略的增益。
*   **充分性与公平性判断**：实验设计较为全面和公平。对比方法广泛，涵盖了同期最先进的统一模型。消融实验严格控制变量，清晰揭示了各个设计带来的增益。特别是在多数据规模下的表征对比，有力地证明了 TA-Tok 的缩放能力和平衡性。

---

## 6. 论文的主要结论与发现

*   **统一框架的有效性**：完全离散、语义对齐的 **Tar** 模型，在不依赖任何模态特定设计的情况下，能够在视觉理解任务上与使用连续 Token 的最优模型（如 Janus-Pro）匹敌，并在视觉生成任务上显著超越所有同类统一模型。
*   **TA-Tok 表征的优势**：与 VQVAE（像素级）和混合（像素+语义）表征相比，文本对齐的离散语义表征在生成质量上表现出绝对优势，且随数据增加表现出更佳的规模效应，同时在理解任务上接近连续语义表征的性能。
*   **联合训练的互促作用**：当使用共享表征时，视觉理解和生成任务可以相互促进，特别是生成任务能从联合训练中获得显著提升（在本文中达 5.3%）。
*   **模态融合的深化**：新提出的 I2I 和 TI2I 预训练任务能够有效加速模型收敛，并提升生成性能，缩小“理解”与“创作”之间的鸿沟，甚至涌现出主题驱动的组合生成能力。
*   **实用设计的有效性**：尺度自适应编解码有效平衡了效率与细节；生成式去分词器（特别是基于扩散的变体）利用预训练先验，大幅提升了图像输出的保真度。

---

## 7. 优点

*   **概念简洁优雅**：将视觉统一于语言模型的“方言”思想，通过一个可扩展的码本实现，架构清晰，消除了对不同编码器和连接器的依赖。
*   **统一且高效**：首次在完全离散的语义空间下，实现了与专用模型相竞争的理解与生成性能，特别是文本对齐的码本初始化方法，省去了额外的特征对齐阶段，训练更高效。
*   **出色的平衡性**：尺度自适应机制为处理不同粒度的视觉任务提供了灵活的解决方案。
*   **深入的实验验证**：对比实验丰富、消融分析透彻，特别是多数据规模的对比实验，有力地支撑了方法优于已有分离/混合方案的结论。
*   **良好的扩展潜力**：文本对齐的码本构建方式、与预训练扩散模型的结合策略，均体现了良好的兼容性和未来扩展潜力。

---

## 8. 不足与局限

*   **算力信息缺失**：论文没有披露任何计算资源使用的细节（如 GPU 型号、训练时长），使读者无法评估其真正效率和复现门槛。
*   **量化误差与重建瓶颈**：论文承认矢量量化会带来信息损失，尤其在细粒度理解（如 OCR）任务上可能受限。同时，依赖生成式去分词器进行重建，在像素级精确还原上弱于传统图像自编码器（如 VQVAE）。
*   **实验覆盖不全**：
    *   **图像编辑/多轮交互**：尽管文章声称统一表征利于图像编辑，但未提供相关实验结果。
    *   **安全性与偏见**：尽管在附录中泛泛提及了社会影响，但未对模型在偏见、毒性、深度伪造防范等方面进行任何定量评估。
    *   **数据效率对比**：与其他方法在相同数据规模下的性能对比可以更细致，尤其是在微调阶段。
*   **应用限制**：该统一模型在复杂、需要精确像素操控的交互式图像编辑任务上可能表现不佳，且生成高度依赖去分词器的独立训练质量。

---

（完）
