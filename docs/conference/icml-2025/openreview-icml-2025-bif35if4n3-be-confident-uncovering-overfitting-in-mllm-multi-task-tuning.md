---
title: "Be Confident: Uncovering Overfitting in MLLM Multi-Task Tuning"
title_zh: 保持自信：揭示多模态大语言模型多任务调优中的过拟合问题
authors: "Wenke Huang, Jian Liang, Guancheng Wan, Didi Zhu, He Li, Jiawei Shao, Mang Ye, Bo Du, Dacheng Tao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=bif35if4n3"
tags: ["query:affective-ai"]
score: 6.0
evidence: 提出噪声鲁棒置信度对齐以加强MLLM中视觉线索整合，有益于多模态情感任务
tldr: 针对多任务微调中多模态大语言模型在开放式响应上的过拟合问题，提出噪声鲁棒置信度对齐方法，通过高斯扰动确保模型在不同视觉质量下保持预测一致性，从而提升对视觉线索的依赖，增强跨域泛化能力，为多模态情感分析等任务提供更鲁棒的视觉语言融合策略。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bif35if4n3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 755, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bif35if4n3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 777, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bif35if4n3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 890, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bif35if4n3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 754, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bif35if4n3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 853, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bif35if4n3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 864, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bif35if4n3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 843, \"height\": 581, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bif35if4n3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bif35if4n3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 842, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bif35if4n3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bif35if4n3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1763, \"height\": 766, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bif35if4n3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 769, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bif35if4n3/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 837, \"height\": 675, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bif35if4n3/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1765, \"height\": 766, \"label\": \"Table\"}]"
motivation: 多任务微调常导致MLLM在开放式响应上过拟合，过度依赖语言先验而忽视视觉线索。
method: 提出噪声鲁棒置信度对齐，通过高斯扰动让模型在不同视觉输入质量下维持一致的预测模式。
result: 方法有效缓解了过拟合，提高了预测鲁棒性和跨域泛化能力。
conclusion: 强化视觉行为线索整合对提升多模态模型鲁棒性至关重要，所提方法为此提供了有效途径。
---

## Abstract
Fine-tuning Multimodal Large Language Models (MLLMs) in multi-task learning scenarios has emerged as an effective strategy for achieving cross-domain specialization. However, multi-task fine-tuning frequently induces performance degradation on open-response datasets. We posit that free-form answer generation primarily depends on language priors, and strengthening the integration of visual behavioral cues is critical for enhancing prediction robustness. In this work, we propose Noise Resilient Confidence Alignment to address the challenge of open-response overfitting during multi-task fine-tuning. Our approach prioritizes maintaining consistent prediction patterns in MLLMs across varying visual input qualities. To achieve this, we employ Gaussian perturbations to synthesize distorted visual inputs and enforce token prediction confidence alignment towards the normal visual branch. By explicitly linking confidence calibration to visual robustness, this method reduces over-reliance on language priors. We conduct extensive empirical evaluations across diverse multi-task downstream settings via popular MLLM architectures. The comprehensive experiment demonstrates the effectiveness of our method, showcasing its ability to alleviate open-response overfitting while maintaining satisfying multi-task fine-tuning performance.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将基于您提供的论文内容，使用中文并以 Markdown 形式，对该论文进行结构化、深入、客观的总结。

### **1. 论文的核心问题与整体含义**

*   **研究背景**：微调多模态大语言模型（MLLMs）是实现跨领域专业化的有效策略。在实际应用中，常需要模型在多个下游任务（如图像描述和视觉问答）上同时表现良好，即多任务微调。
*   **核心问题**：论文揭示了一个在 MLLM 多任务微调中常见的
现象：**开放响应任务（如生成式图像描述）在多任务混合训练时会出现严重的性能下降（过拟合）**，而**固定选项任务（如选择题形式的视觉问答）则表现稳定**。这种过拟合并非简单的灾难性遗忘，而是模型过度依赖训练数据中的语言先验知识来生成自由形式的答案，从而忽视了视觉信息。
*   **整体含义**：这篇论文的核心是定位并解决 MLLM 在多任务微调时对语言模态的“偏袒”所导致的过拟合问题。作者旨在通过增强模型对视觉信息的利用和鲁棒性，来抑制这种对语言先验的过拟合，从而在保持固定选项任务性能的同时，提升开放响应任务的泛化能力。

### **2. 论文提出的方法论：噪声鲁棒置信度对齐（NRCA）**

*   **核心思想**：为了缓解模型对语言先验的过度依赖，需要加强视觉表征在预测中的作用。NRCA 的核心思想是，强制 MLLM 在面对不同质量（正常与加噪）的视觉输入时，对同一问题产生一致的预测置信度。通过这种对齐，迫使模型更深入地“理解”视觉内容，而非死记硬背语言模式。
*   **关键技术细节**：
    1.  **噪声视觉混合**：为了解决传统图像增强（如裁剪、颜色抖动）可能改变图像语义的问题，NRCA 采用了一种更温和的扰动方式。它首先预测输入图像本身的特征均值（µ）和方差（σ²），然后从该高斯分布（𝒩(µ, σ²)）中采样噪声。最后，将原始图像和一个带噪版本进行混合 `x_v`，合成一个扭曲的视觉信号 `x_v`：
        *   `x_v = δ * 𝒩(µ, σ²) + (1 - δ) * x_v`
        *   这里 `δ` 是噪声比率，默认设为 0.5。这种方法保证了扰动不偏离原始语义太远。
    2.  **令牌置信度对齐**：MLLM 的输出是变长的，直接对齐整个概率分布会因词表庞大而不稳定。NRCA 创新的选择在**令牌置信度**层面进行对齐。
        *   首先，用 softmax 函数 `σ` 计算正常分支和扰动分支在每个令牌上的预测概率 `p_t` 和 `\tilde{p}_t`。
        *   然后，提取在真实标签 `y_t` 位置上的预测概率，得到每个样本的平均预测置信度 `I` 和 `\tilde{I}`。
        *   最后，构造一个正则化损失 **`L_NRCA`**，这个损失鼓励两个分支的置信度尽可能接近，并以其比值 `1 - \tilde{I} / I` 偏离 0 的程度作为惩罚项。
    3.  **公式与算法流程**：
        *   整体训练损失 `L = L_CE + λ * L_NRCA`。
        *   最终的 **`L_NRCA`** 被设计为 `|1 - \tilde{I} / I| * L_CE`，其中 `L_CE` 是标准的交叉熵损失。这个设计的巧妙之处在于，`L_CE` 作为加权因子，使得对“难拟合”的样本施加更强的视觉鲁棒性约束，而对“易拟合”的样本则较弱，从而实现精细化调控。算法流程为两阶段：前向传播生成正常和扰动输入的 logits，然后计算 `L_CE` 和 `L_NRCA` 进行联合优化。

### **3. 实验设计**

*   **数据集与场景**：
    *   构建了**多任务微调场景**，混合了两种类型的任务数据集进行训练。
    *   **开放响应任务**：`Flickr30k`（图像描述）、`COCO-Cap`（图像描述）。
    *   **固定选项任务**：`ScienceQA`（科学问答）、`IconQA`（图表问答）。
    *   对于每个数据集，作者随机抽取了 10，000 个实例进行混合训练，模拟真实的多任务微调。
*   **Benchmark 与基线方法**：
    *   **基准**：`Zero-shot`（未微调）和 `Full Fine-Tuning`（全量微调，记为 Full FT）。
    *   **对比方法**涵盖了该领域两类主要的抗过拟合微调策略：
        *   **部分更新掩码**：`Random Mask-Tuning`（随机冻结一半参数）和 `Magnitude Tuning`（基于权重大小选择更新参数）。
        *   **刚度惩罚正则化**：`L2-Regularization`（L2 正则）和 `Grafting`（L1 正则）。
*   **评估指标**：
    *   图像描述任务：**CIDEr** 分数。
    *   视觉问答任务：**Top-1 Accuracy**。
    *   整体性能：计算上述两个任务的平均值。

### **4. 资源与算力**

*   **硬件配置**：所有实验均在 8 块 **NVIDIA 4090 GPU**（每块 24GB 显存）上进行。
*   **模型选择**：受限于计算资源，作者选择了较小规模的模型进行实验，包括 LLaVA-1.5-7B 和 VILA1.5-3B。
*   **训练细节**：文中未明确提及总训练时长，但给出了详细的超参数，如训练轮次（`E = 3, 5`），批次大小 （`B = 16`），以及在两个模型架构上不同的学习率设置。

### **5. 实验数量与充分性**

*   **实验矩阵**：实验设计构建了一个较大的矩阵以评估方法的全面性，包括：
    *   **2 个模型架构** ×
    *   **4 种下游任务组合**（Flickr30k+ScienceQA， COCO-Cap+ScienceQA， Flickr30k+IconQA， COCO-Cap+IconQA） ×
    *   **2 种训练轮次**（E=3, 5）。
    *   结合 6 种方法（含 Zero-shot 和 Full FT），总计进行 **~96 组主要对比实验**。
*   **消融与分析实验**：
    *   对核心参数 `λ`（惩罚系数）和 `δ`（噪声比率）进行了详细的灵敏度分析。
    *   对 `NRCA` 损失的构成（是否包含 `L_CE` 加权）进行了消融。
    *   设计了额外的实验来验证方法动机，例如通过**噪声评估**（对比正常与加噪图像的性能差距）和 **注意力可视化**（分析模型在不同输入模态上的注意力分布）来证明 NRCA 确实增强了模型对视觉信息的依赖。
*   **公平性评估**：实验对比了当前主流的抗过拟合微调方法，超参数设置基本沿用各方法的默认配置，主要对比在相同训练设置下的性能差异，评判较为客观公平。`Flickr30k` 的数据采样也保证了实验的随机性起点。

### **6. 主要结论与发现**

*   **现象确认**：MLLM 在多任务微调中，主要由于开放响应任务过度依赖语言先验而导致性能下降。与固定选项任务相比，开放响应任务的损失曲线呈现“阶梯式”上升，表明模型在逐样本记忆而非学习底层模式。
*   **方法有效性**：提出的 NRCA 方法在所有实验设置下，均能显著优于 Full FT 以及其他抗过拟合方法，尤其是在大幅提升开放响应任务性能的同时，保持甚至提升了固定选项任务的性能。
*   **机制验证**：
    *   **噪声评估**结果表明，NRCA 训练出的模型在正常和噪声输入下的性能差距明显大于 Full FT，证明模型更依赖视觉线索。
    *   **注意力分配**分析显示，NRCA 能让模型将更多注意力从“系统”和“提示”令牌转移到“视觉”令牌上，直接证实了其对视觉依赖性的增强。
*   **资源效率**：与需要存储整个预训练模型权重的刚度惩罚方法相比，NRCA 引入的额外计算和存储开销（存储噪声输入和 logits）相对较小。

### **7. 优点**

*   **问题洞察深刻**：精确地指出现有过拟合解决方案多针对单任务，且未区分任务类型。NRCA 专门针对多任务场景中开放响应任务因语言先验导致的过拟合，问题定位精准。
*   **方法论设计精巧**：
    *   **高斯噪声混合**的引入，巧妙避免了传统数据增强破坏语义的风险。
    *   **令牌置信度对齐**而非完整分布对齐，解决了 MLLM 输出空间巨大的难题，并使用 `L_CE` 作为惩罚权重，实现了对难易样本的差异化处理，设计非常优雅。
*   **评估全面详实**：通过多个模型、多种任务组合、详尽的消融实验以及注意力可视化等分析手段，从现象、性能到机制都进行了充分验证。
*   **计算友好**：相比于其他需要复杂参数选择或保存大模型权重的方法，NRCA 在实现和资源成本上具有明显优势。

### **8. 不足与局限**

*   **场景局限性**：论文明确指出，其方法主要解决包含开放响应任务的多任务场景下的过拟合问题。当任务全部为固定选项类型时，过拟合问题不显著，方法的增益可能有限。
*   **扰动方式的通用性**：高斯噪声虽然语义安全，但其是否在所有类型的视觉数据（如文本密集的图表、医学图像）上都是最优或最安全的扰动方式，未作深入讨论。
*   **模型规模的泛化**：实验仅在 3B 和 7B 规模的模型上进行。虽然方法以模型无关为目标，但其在更大规模模型（如 13B， 70B）上的效果和效率仍有待验证。
*   **超参数敏感性**：虽然作者声称超参数稳定，但从消融实验看，性能和关键参数 `λ` 和 `δ` 之间仍然存在需要权衡的曲线关系，在不同任务组合下可能仍需微调。

（完）
