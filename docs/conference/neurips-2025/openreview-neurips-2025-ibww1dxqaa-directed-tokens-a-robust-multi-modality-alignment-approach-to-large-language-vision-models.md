---
title: "Directed-Tokens: A Robust Multi-Modality Alignment Approach to Large Language-Vision Models"
title_zh: Directed-Tokens：面向大型语言视觉模型的鲁棒多模态对齐方法
authors: "Thanh-Dat Truong, Huu-Thien Tran, Tran Thai Son, Bhiksha Raj, Khoa Luu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=iBwW1DxQaa"
tags: ["query:affective-ai"]
score: 9.0
evidence: 引入顺序重建任务增强视觉文本对齐的鲁棒性
tldr: 大型多模态模型在视觉与文本特征对齐上仍存在鲁棒性和泛化性不足。本文提出Directed-Tokens，在预训练和微调阶段加入图像顺序和文本顺序重建任务，以简单高效的方式增强跨模态对齐的鲁棒性。实验证明，该方法显著提升了推理能力、视觉理解和跨模态对齐效果。它为多模态模型的对齐训练提供了一种新颖而有效的学习机制。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibww1dxqaa/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 724, \"height\": 826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibww1dxqaa/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 722, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibww1dxqaa/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibww1dxqaa/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 710, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibww1dxqaa/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 734, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibww1dxqaa/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 735, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ibww1dxqaa/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1415, \"height\": 964, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 721, \"height\": 119, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 566, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 725, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 726, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 724, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1433, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1430, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 664, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 734, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ibww1dxqaa/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1441, \"height\": 263, \"label\": \"Table\"}]"
motivation: 多模态模型受限于视觉与文本特征对齐的鲁棒性和泛化性。
method: 提出Directed-Tokens，通过图像和文本顺序重建任务提升对齐鲁棒性。
result: 在多项任务上验证，模型推理、视觉理解和跨模态对齐能力显著提升。
conclusion: 顺序重建是一种简单有效的增强多模态对齐鲁棒性的方法。
---

## Abstract
Large multimodal models (LMMs) have gained impressive performance due to their outstanding capability in various understanding tasks. However, these models still suffer from some fundamental limitations related to robustness and generalization due to the alignment and correlation between visual and textual features. In this paper, we introduce a simple but efficient learning mechanism for improving the robust alignment between visual and textual modalities by solving shuffling problems. In particular, the proposed approach can improve reasoning capability, visual understanding, and cross-modality alignment by introducing two new tasks: reconstructing the image order and the text order into the LMM's pre-training and fine-tuning phases. In addition,  we propose a new directed-token approach to capture visual and textual knowledge, enabling the capability to reconstruct the correct order of visual inputs. Then, we introduce a new Image-to-Response Guided loss to further improve the visual understanding of the LMM in its responses. The proposed approach consistently achieves state-of-the-art (SoTA) performance compared with prior LMMs on academic task-oriented and instruction-following LMM benchmarks.

---

## 论文详细总结（自动生成）

好的，以下是对论文《Directed-Tokens: A Robust Multi-Modality Alignment Approach to Large Language-Vision Models》的详细结构化总结。

### 1. 论文的核心问题与整体含义

- **研究背景**：大型多模态模型（LMMs），如LLaVA，虽然在下游任务中表现优异，但其在视觉和文本特征的对齐上存在根本性局限，导致鲁棒性和泛化能力不足。
- **核心问题**：当前的LMMs严重偏向语言模态，常常“忽略”视觉输入信息。证据表明，即使将输入图像替换为全黑图像，模型依然能给出相似的回答（如论文Table 1所示），这说明多模态对齐并未被有效学习，语言模型主导了输出，导致幻觉、信息缺失和性能下降。
- **整体含义**：本文旨在提出一种简单高效的机制，通过解决“乱序”问题来强制模型学习视觉与文本模态间的鲁棒对齐，从而增强视觉理解与推理能力。作者将其归结为回答两个根本性问题：给定乱序的图像，模型能否重建正确顺序？给定乱序的文本描述，模型能否重建符合图像信息的正确句子？

### 2. 论文提出的方法论

论文的核心思想是通过在预训练和微调阶段引入“乱序重建”任务，并辅以定向令牌和注意力引导损失来增强跨模态对齐。

- **核心思想：乱序学习**
    - 受拼图游戏启发，通过对图像补丁和文本描述进行乱序，并强制LMM在语言或视觉上下文的辅助下重建其正确顺序，以此来深化模态间的关联。

- **关键技术细节与流程**
    - **任务一：图像顺序重建**
        - 在预训练和微调阶段，给定一个补丁被随机打乱的图像 `Ẋ`，要求模型根据该图像的文本描述 `p`，预测其正确的排列索引 `k`。
        - 通过此任务，模型不能仅仅依赖语言，而必须在视觉和文本信息间建立深层联系以还原图像。
    - **任务二：文本顺序重建**
        - 仅在预训练阶段进行。给定原始图像 `x` 和词序被打乱的文本描述 `ṗ`，要求模型预测出原始的、与视觉信息匹配的正确句子 `p`。
        - 这个任务反过来要求模型利用视觉信息来修正和还原文本，从而平衡语言模态的主导地位。
    - **定向令牌机制**：
        - 为高效解决图像顺序重建任务，作者引入一个可学习的“定向令牌” `d_rt`，将其放置在输入序列的末尾。
        - 由于自回归模型的因果注意力机制，末尾的 `d_rt` 可以捕获到其之前所有的视觉和文本信息，从而利用融合后的特征通过一个线性投影层来预测图像的正确排列索引 `k`，效果优于直接使用视觉令牌。
    - **图像到响应的引导损失**：
        - 为进一步增强视觉信息对模型最终回答的影响，提出了一种新的辅助损失函数。
        - 该损失函数通过最大化模型注意力层中，从视觉令牌到回答令牌的注意力分数，来引导模型在生成回复时更充分地“关注”和利用视觉特征。其公式为目标是最小化 `1 - α_{v,r}`，其中 `α_{v,r}` 是从视觉令牌 `v` 到回答令牌 `r` 的平均注意力权重。

- **训练目标**
    - **预训练阶段**：总损失 = 标准自回归交叉熵损失 + 图像顺序重建损失 + 文本顺序重建损失 + 图像到响应引导损失。
    - **微调阶段**：总损失 = 标准自回归交叉熵损失 + 图像顺序重建损失 + 图像到响应引导损失。（为避免破坏对话语境，移除文本顺序重建任务）

### 3. 实验设计

- **基准模型与实现**：基于LLaVA v1.5框架，使用CLIP-ViT-L-14作为视觉编码器，Multi-Layer Perception (MLP) 作为视觉-语言连接器。
- **语言模型**：测试了多种LLM，包括Vicuna 7B/13B、Qwen 7B和LLaMA3 8B。
- **训练数据**：采用LLaVA v1.5的预训练（558K样本）和微调数据（665K样本）。
- **评估基准**：
    - **学术任务导向基准（Academic Task-oriented）**：VQAv2， GQA， VizWiz， SciQA-IMG， TextVQA。
    - **指令遵循基准（Instruction-Following）**：POPE（评估幻觉）， SEED-Bench， MME， LLaVA-Wild， MM-Vet， MMMU-Val。
- **对比方法**：主要与BLIP-2、InstructBLIP、IDEFICS、Qwen-VL/Chat、Shikra以及最先进的LLaVA-1.5系列模型进行对比。

### 4. 资源与算力

- **GPU配置**：实验使用了 **32台 NVIDIA A100** GPU。
- **训练时长**：文中未明确提及总训练时长。

### 5. 实验数量与充分性

本论文进行了大量且充分的消融实验和对比实验，以验证所提方法的有效性、各组件贡献及其鲁棒性。

- **主要对比实验**：在两大基准集的十多个子任务上，与超过8种主流LMM方法进行了全面对比，证明了模型的SOTA性能。实验覆盖不同规模和种类的LLM。
- **消融实验**：
    - **LLM规模影响**：对比了Vicuna 7B vs 13B, Qwen 7B, LLaMA 8B，验证了方法在不同模型上的可扩展性。
    - **定向令牌有效性**：对比了使用“视觉令牌”与“定向令牌”`d_rt` 进行排列预测的效果，证实了后者的优越性。
    - **乱序学习阶段有效性**：分别验证了仅在预训练阶段、仅在微调阶段以及两者结合进行图像/文本乱序学习的效果。
    - **引导损失有效性**：通过添加/移除Image-to-Response Guided Loss，证明了该损失函数的增益效果。
    - **数据规模影响**：对比了在LLaVA v1（小数据）和LLaVA v1.5（大数据）配置下的表现，证明了大数据的效益。
    - **排列数量与令牌位置影响**：附录中探讨了不同排列数量（5k/10k/15k）和定向令牌放置位置（开头/结尾）的影响。
- **充分性与客观性**：实验设计全面、层层递进，对比基准广泛且公平（保持相同的训练数据和超参数），能客观有力地支撑论文的核心论点。

### 6. 论文的主要结论与发现

- **SOTA性能**：提出的Direct-LLaVA方法在多个学术任务导向和指令遵循的LMM基准测试中，一致性地达到了最先进的性能，显著超越了LLaVA-1.5等先前方法。
- **乱序学习的有效性**：通过重建图像和文本顺序的任务，能显著且根本地改善LMM对视觉信息的理解与对齐能力，解决了模型“盲从”语言模态的问题。
- **定向令牌的优势**：位于序列末尾的 `drt` 相比普通视觉令牌，能更有效地聚合多模态上下文信息，从而更准确地解决顺序重建问题。
- **引导损失的增效**：Image-to-Response Guided Loss通过直接强化视觉到文本的注意力流，进一步提升了模型的回应质量与视觉关联度。

### 7. 优点

- **方法简洁且新颖**：以“乱序重建”这一简单直观的学习机制作为切入点，巧妙地解决了多模态对齐不鲁棒这一复杂问题，几乎没有引入额外数据或复杂模块。
- **模块化设计清晰**：“定向令牌”和“引导损失”的设计目标明确，且各自有效，便于理解和迁移应用。
- **实验验证极为扎实**：论文提供了丰富的定量对比和消融分析，覆盖了多个LLM、多种任务和不同数据规模，结论可靠度很高。可视化分析（如Figure 5/6）也直观展示了模型在视觉理解上的提升。
- **理论-实验结合紧密**：从提出“视觉信息被忽略”的问题，到设计“定向令牌”解决自回归模型中信息聚合的因果依赖，逻辑链条完整。

### 8. 不足与局限

- **超参数探索有限**：论文明确指出，对不同学习目标之间的损失权重平衡（Loss Balancing）尚未进行充分探索，这可能会影响模型的最优表现。
- **模型与数据规模局限**：实验受限于计算资源，语言模型最大仅到13B参数，数据规模也限于LLaVA v1.5。虽然方法具备可扩展性的理论潜力，但在百亿甚至千亿参数级别的验证尚属空白。
- **应用泛化性待考**：论文核心思想是在已有视觉-语言基准上得到验证，但它在更细粒度任务（如指代表达理解REC、视觉定位）、生成任务（如图文并茂的创作）或更复杂的多图/视频理解上的效果，仍有待探索。
- **乱序策略的敏感性**：文中提到排列的选择（汉明距离）很重要，不同排列难度会影响学习效果。在实际应用中，这可能需要一个调参过程来寻找最优的乱序策略。

（完）
