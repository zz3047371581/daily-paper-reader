---
title: "Beyond Text: LLM-Based Multimodal and Cross-Lingual Transfer Learning for Low-Resource Tigrigna Sentiment Analysis"
title_zh: 超越文本：基于LLM的多模态与跨语言迁移学习用于低资源Tigrigna情感分析
authors: "Hagos Gebremedhin Gebremeskel, Chong Feng, Asefa Mebrahtu Abera"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=4fktVGNzQX"
tags: ["query:affective-ai"]
score: 8.0
evidence: 基于LLM的多模态跨语言低资源Tigrigna情感分析
tldr: 该论文提出了首个Tigrigna多模态情感数据集TigXMM和基于大语言模型的跨语言迁移框架，解决了多语言模型在处理表情、meme等多模态信号时的不足。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 低资源语言Tigrigna的情感分析缺乏多模态数据和有效方法。
method: 创建多模态数据集TigXMM，设计基于LLM的跨语言迁移学习框架。
result: 在基准模型上展示了多模态信号处理的局限，并验证了所提方法。
conclusion: LLM跨语言框架能有效提升低资源多模态情感分析。
---

## Abstract
Sentiment analysis in low-resource languages remains underexplored, particularly for Tigrigna, where communication frequently combines text, emojis, and memes. We introduce TigXMM, a cross-lingual, multilingual, and multimodal framework for Tigrigna sentiment analysis, along with the first multimodal sentiment dataset for this language. The dataset, collected from social media, integrates text, emojis, and meme content to capture real-world communication patterns. We benchmark widely used multilingual models, including mBERT, AfriBERTa, XLM-RoBERTa, XLNet, BLOOMZ, and LLaMA, and highlight their limitations in processing multimodal signals. To address these challenges, we design an LLM-based cross-lingual transfer model with multimodal adapters for text, emoji, and meme fusion using hybrid attention and additive–hierarchical strategies. Experimental results demonstrate that our approach consistently improves sentiment classification performance: from 78.4\% accuracy on text-only inputs to 81.2\% with emojis, 86.3\% with memes, and 89.7\% when combining all modalities, achieving state-of-the-art performance for Tigrigna sentiment analysis. Beyond performance gains, this work contributes the first multimodal dataset and a reproducible framework, providing open resources to advance sentiment analysis for underrepresented African languages.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **核心问题**：低资源语言提格里尼亚语（Tigrigna）的情感分析长期面临双重困境——既缺乏融合文本、表情符号（emojis）和梗图（memes）的多模态标注数据，又缺少能够有效处理此类多模态信号的方法。现有主流多语言预训练模型（如 mBERT、XLM‑RoBERTa 等）尽管在纯文本上表现尚可，但在理解表情、梗图等多模态社交信号时存在明显局限。
- **整体含义**：论文旨在填补这一空白，通过构建首个 Tigrigna 多模态情感数据集，并设计基于大语言模型（LLM）的跨语言迁移与多模态融合框架，系统性地证明：将文本、表情和梗图三种模态有层次地加入模型，可以稳定、显著地提升低资源语言的情感分类性能，为非洲代表性不足语言的资源建设与方法创新提供可复现的范例。

## 2. 论文提出的方法论

- **核心思想**：以预训练大语言模型作为跨语言知识迁移的骨干，引入面向文本、表情、梗图三种模态的可训练适配器（adapters），通过混合注意力（hybrid attention）和“加法‑层级”（additive–hierarchical）策略将不同模态的特征有层次地融合，最终实现多模态情感分类。
- **关键技术细节**：
  - **多模态数据集构建**：从社交媒体中采集包含文本、表情、梗图的真实交流数据，构建名为 **TigXMM** 的首个 Tigrigna 多模态情感数据集。
  - **跨语言迁移骨干**：选用大规模多语言 LLM（文中未指明具体模型名称，仅提及“LLM-based cross-lingual transfer model”）作为特征提取器，通过跨语言迁移将在高资源语言上习得的语义能力迁移至 Tigrigna。
  - **多模态适配器与融合**：
    - 分别为文本、表情、梗图设计独立的轻量级适配器，将原始信号映射到统一的语义空间。
    - 采用**混合注意力机制**捕捉文本与图像信号（表情/梗图）之间的跨模态交互。
    - 利用**加法‑层级融合策略**，先通过元素级加法整合初步特征，再以层级方式逐步叠加不同模态的信息（由纯文本→文本+表情→文本+梗图→全模态），形成最终的多模态表示。
  - **分类头**：在融合表示之上接一个线性分类器，输出情感极性。

## 3. 实验设计

- **数据集/场景**：
  - 使用自建的 **TigXMM** 数据集，所有样本均来自社交媒体，涵盖文本、表情、梗图三种模态的真实组合。
  - 数据集用于评测纯文本、文本+表情、文本+梗图以及全模态四种输入设定下的情感分类性能。
- **Benchmark 模型**：
  - 多语言预训练模型：**mBERT, AfriBERTa, XLM‑RoBERTa, XLNet, BLOOMZ, LLaMA**。
  - 重点考察这些模型在接收多模态信号时的局限性，作为后续方法改进的参照基线。
- **对比方法**：
  - 基准多语言模型（纯文本或多模态输入）的准确率。
  - 论文所提出的 **LLM‑based cross‑lingual transfer + multimodal adapters** 在四种模态组合下的准确率变化（78.4% → 81.2% → 86.3% → 89.7%），以此体现每个模态的增益并与基准形成对照。

## 4. 资源与算力

- 原文提供的摘要及元数据中**未明确说明**所使用的 GPU 型号、数量、训练时长等算力细节。文中仅提到模型框架包含大语言模型和多模态适配器，但未给出具体的硬件配置或训练开销。

## 5. 实验数量与充分性

- **实验组数**：
  - **基准对比**：至少涵盖 6 种主流多语言模型在 Tigrigna 情感分析任务上的性能。
  - **模态消融**：明确给出了纯文本、文本+表情、文本+梗图、全模态共 4 种输入的准确率提升路径，说明进行了系统的消融实验。
  - 除准确率外，摘要未提及是否报告 F1、精度、召回率等其他指标。
- **充分性与公平性**：
  - 实验设计遵循“同数据、多基线、逐步加模态”的原则，较为客观地展示了所提方法的增益。
  - 但未提及是否与已有的其他多模态融合框架（如 VisualBERT、MMBT、跨语言多模态模型）进行比较，对比的全面性尚有欠缺。
  - 数据集的规模、划分方式、标注一致性等细节未在摘要中披露，影响对实验可重复性的评估。

## 6. 主要结论与发现

- 将文本、表情、梗图三种模态有序地引入模型，能够持续提升情感分类性能：纯文本准确率 78.4%、加入 emojis 后 81.2%、加入 memes 后 86.3%、全模态融合后达到 **89.7%**，创下 Tigrigna 情感分析的新最优。
- 基于 LLM 的跨语言迁移与多模态适配器融合框架，可有效弥补现有多语言模型在处理表情、梗图等视觉化社交信号时的不足。
- 本工作贡献了首个 Tigrigna 多模态情感数据集（TigXMM）和一套可复现的开源框架，为低资源非洲语言的情感分析提供了重要的资源、基准和方法论支撑。

## 7. 优点

- **资源首创**：构建了第一个面向 Tigrigna 的多模态情感数据集，直接填补了低资源语言在表情、梗图等模态上的数据空缺。
- **方法渐进且解释性强**：通过逐模态叠加的实验范式，清晰量化了每一种模态对性能的贡献，增强了结果的可信度和解释性。
- **跨语言迁移的实用设计**：以 LLM 为基座并配合轻量级适配器融合多模态信息，避免了为低资源语言从头训练大型多模态模型的高昂成本，具备较好的可迁移性和可复现性。
- **性能显著提升**：全模态下准确率近 90%，相比纯文本基线提升超过 11 个百分点，效果扎实。

## 8. 不足与局限

- **算力与资源成本未披露**：论文未提及训练所需的 GPU 资源、训练时长，难以评估该方法在同等低资源场景下的实际部署门槛。
- **对比方法范围较窄**：主要对比多种纯文本多语言模型，缺少与专门的多模态融合模型（如对表情、图像有专门设计的跨语言情感分析框架）的直接比较。
- **评价指标单一**：仅呈现准确率，缺失对 F1、类间平衡性、鲁棒性等方面的分析，可能掩盖类别不平衡问题。
- **数据集代表性未知**：TigXMM 的规模、领域分布、时间跨度、标注质量等关键属性未在摘要中说明，可能限制结论的泛化性。
- **应用限制**：模型在社交媒体幽默、讽刺等复杂情感上的表现未经验证，且梗图理解可能受文化语境影响，跨文化迁移的有效性待考察。

（完）
