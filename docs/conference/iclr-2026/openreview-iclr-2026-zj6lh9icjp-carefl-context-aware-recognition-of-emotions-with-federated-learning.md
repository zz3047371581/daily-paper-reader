---
title: "CAREFL: Context-Aware Recognition of Emotions with Federated Learning"
title_zh: CAREFL：基于联邦学习的上下文感知情感识别
authors: "Jose Alejandro Lopez Quel, Carlo Marcelo Revoredo da Silva, Bruno J T Fernandes, Alexander Fabisch"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Zj6lH9ICjP"
tags: ["query:affective-ai"]
score: 9.0
evidence: 利用大视觉语言模型生成上下文描述并联邦微调小模型实现图像情感识别
tldr: 针对图像情感识别需丰富上下文但大模型计算开销大且涉及隐私的问题，本文提出CAREFL框架：利用大视觉语言模型生成丰富的上下文描述，再以小模型在联邦学习设置下通过量化低秩适配进行微调。该方法在保持高精度的同时降低计算负载并保护数据隐私，为分布式场景下的可扩展情感识别提供了新方案。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 图像情感识别依赖上下文线索，但大模型计算成本高且集中式训练存在隐私问题。
method: 结合大型VLM生成上下文描述与小模型联邦学习微调，采用量化低秩适配实现高效隐私保护。
result: 在保护隐私的前提下，以小模型实现准确的情感识别，平衡计算开销与性能。
conclusion: 提出一种隐私友好的高效情感识别范式，适用于分布式场景。
---

## Abstract
Emotion recognition from images is a challenging task due to its dependence on subtle visual cues and contextual information. Recent advances in Vision-Language Models (VLMs) have demonstrated strong performance in this domain. Still, they are often limited by their large computational footprint and the privacy concerns associated with centralized training. To address these challenges, we propose CAREFL (Context-Aware Recognition of Emotions with Federated Learning), a framework for efficient emotion recognition. CAREFL combines large VLMs, specifically LLaVA 1.5, for generating rich contextual descriptions with lightweight small VLMs, SMOLVLM2, fine-tuned under a federated learning setup using Quantized Low-Rank Adaptation. This design enables accurate, privacy-preserving, and resource-efficient training on edge devices. Although this work evaluates CAREFL in the context of emotion recognition, the framework is general by design: leveraging VLMs, it can also be fine-tuned for a wide range of multimodal description and classification tasks beyond emotion analysis.
Extensive experiments demonstrate that CAREFL outperforms state-of-the-art baselines, achieving up to 96.49\% mAP and 50.36\% F1-score, surpassing heavier models such as GPT-4o, LLaVA, and EMOTIC. An ablation study further confirms the contribution of contextual enrichment, prompt design, and quantization in enhancing performance. The results show that federated fine-tuning of lightweight VLMs, when guided by contextual reasoning from large-scale models, provides a practical and scalable solution for emotion recognition in privacy-sensitive and resource-constrained environments.

---

## 论文详细总结（自动生成）

# CAREFL：基于联邦学习的上下文感知情感识别 论文总结

## 1. 研究动机与核心问题

*   **核心问题**：图像情感识别高度依赖微妙的视觉线索与丰富的上下文信息，但现有方案面临两难困境。
*   **背景与动机**：
    *   大型视觉语言模型在情感识别上表现强劲，但其**计算开销巨大**，难以部署在资源受限的边缘设备上。
    *   常规的**集中式训练**需要将用户图像数据上传至中心服务器，引发严重的**数据隐私隐忧**。
    *   亟需一种既能利用上下文推理能力、又能保护隐私、且计算高效的图像情感识别新范式。

## 2. 方法论

*   **整体框架**：CAREFL，核心思想是**大模型生成上下文，小模型联邦微调**，实现高效且保护隐私的情感识别。
*   **关键技术细节**：
    *   **上下文生成**：利用大型视觉语言模型 LLaVA 1.5 为图像生成丰富的上下文描述，作为额外的“语义提示”输入。
    *   **模型微调**：选用轻量级小模型 SMOLVLM2 作为下游任务模型。
    *   **联邦学习**：采用联邦学习设置，模型在分布式边缘设备上利用本地数据训练，无需共享原始图像，仅交换模型参数。
    *   **高效适配**：在联邦微调中引入**量化低秩适配**技术，进一步压缩模型计算量与通信开销，使其适合边缘侧训练。
*   **泛化设计**：虽然本文聚焦于情感识别，但该框架理论上可扩展至任意多模态描述与分类任务。

## 3. 实验设计

*   **对比方法与 Benchmark**：论文将 CAREFL 与当前最优基线进行对比，包括：
    *   重量级大模型：GPT-4o, LLaVA 系列。
    *   专业情感分析模型：EMOTIC 等。
*   **评估指标**：采用 mAP（平均精度均值）和 F1-score 作为核心评价指标。
*   **消融实验**：为验证各组件的有效性，设计了消融研究，具体验证方向包括：
    *   上下文信息的贡献；
    *   提示词设计的影响；
    *   量化技术对性能的增益。

## 4. 资源与算力

*   **论文明确提及情况**：**未明确说明**。在提供的文本信息中，没有提及实验所使用的 GPU 型号、数量、具体训练时长或显存消耗等算力细节。
*   *说明*：鉴于原 PDF 提取受限，此部分信息可能存在于原论文的实验配置章节，但基于现有文本无法总结。

## 5. 实验充分性与客观性

*   **实验组数**：据摘要描述，论文包含“大量实验”，涵盖了与 SOTA 模型的性能对比、消融实验等，但具体的绝对组数因文本缺失暂不明确。
*   **充分性与公平性**：
    *   **充分性**：实验维度设计较为合理，既对比了外部强基线（大模型），又通过消融实验自证了框架各组件的有效性。
    *   **客观公平性**：对比对象包含了参数量远超自己的大模型，具有一定的挑战性。在与大模型对比时，其在计算效率与隐私保护上的优势是公平的考量维度。

## 6. 主要结论与发现

*   **性能突破**：CAREFL 在性能上超越了此前的 SOTA 方法，实现了最高 **96.49% 的 mAP** 和 **50.36% 的 F1-score**，甚至优于 GPT-4o 等大模型。
*   **有效性验证**：
    *   由大模型生成的上下文信息能显著提升小模型的识别效果。
    *   在联邦学习场景下，结合量化技术的轻量级 VLM 微调是可行的。
*   **范式确立**：联邦微调轻量级 VLM，并由大模型提供上下文引导，为隐私敏感和资源受限环境提供了实用且可扩展的情感识别方案。

## 7. 优点与亮点

*   **架构创新**：巧妙解耦了大模型的推理能力与小模型的部署能力，实现“大模型指导，小模型执行”的协同范式。
*   **隐私保护**：引入联邦学习机制，从根本上避免了原始图像的隐私泄露风险，符合数据合规趋势。
*   **资源友好**：通过量化低秩适配技术，使得训练和推理可在边缘设备完成，大幅降低了落地门槛。
*   **评分佐证**：该论文在检索指标中获得 **9.0** 的高分，表明其方法论获得了检索体系的高度认可。

## 8. 不足与局限

*   **内容不可见导致的评估盲区**：由于原 PDF 文本实际为验证页面，未能获取论文正文、图表及详细实验数据，以下局限性基于摘要推断：
*   **大模型依赖传递**：训练过程中仍需依赖 LLaVA 1.5 进行上下文生成，若边缘端完全无大模型辅助，这可能成为离线的瓶颈。虽然生成阶段可离线或服务端完成，但增加了一道预处理工序。
*   **实验覆盖度存疑**：
    *   未从文本中观测到关于**非独立同分布数据**的详细测试，而这正是联邦学习中的核心挑战。
    *   未观测到关于**通信成本**的具体量化分析，量化后的联邦通信效率提升幅度未知。
*   **应用限制**：F1 分数（50.36%）相较 mAP（96.49%）差距明显，暗示模型在**类别不均衡场景**下可能仍存在精确率与召回率失衡的问题。

（完）
