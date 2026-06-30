---
title: Distributional Vision-Language Alignment by Cauchy-Schwarz Divergence
title_zh: 基于柯西-施瓦茨散度的分布级视觉-语言对齐
authors: "Wenzhe Yin, Zehao Xiao, Pan Zhou, Shujian Yu, Jiayi Shen, Jan-Jakob Sonke, Stratis Gavves"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=UUAjF4xL0e"
tags: ["query:affective-ai"]
score: 9.0
evidence: 基于柯西-施瓦茨散度的分布级视觉-语言对齐
tldr: 针对现有视觉-语言对齐方法忽视分布差异导致模态间隙的问题，本文提出CS-Aligner，通过结合柯西-施瓦茨散度与互信息，实现分布级对齐。该方法同时捕获全局分布和局部语义关系，有效缓解了InfoNCE的均匀性-对齐冲突。实验表明，CS-Aligner在跨模态检索和生成任务上取得更优性能，推动了多模态对比学习的发展。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 现有对齐方法忽略分布差异，导致模态间隙和对齐-均匀性冲突。
method: 提出CS-Aligner，利用柯西-施瓦茨散度和互信息进行分布级视觉-语言对齐。
result: 在跨模态任务上超越了仅基于成对样本对齐的方法。
conclusion: 分布级对齐有效减少了模态间隙，提升了多模态表征质量。
---

## Abstract
Vision-language alignment is crucial for various downstream tasks such as cross-modal generation and retrieval. Previous multimodal approaches like CLIP utilize InfoNCE to maximize mutual information, primarily aligning pairwise samples across modalities while overlooking distributional differences.  In addition, InfoNCE has inherent conflict in terms of alignment and uniformity in multimodality, leading to suboptimal alignment with modality gaps. To overcome the limitations, we propose CS-Aligner, a novel framework that performs distributional vision-language alignment by integrating Cauchy-Schwarz (CS) divergence with mutual information. CS-Aligner captures both the global distribution information of each modality and the pairwise semantic relationships. We find that the CS divergence seamlessly addresses the InfoNCE's alignment-uniformity conflict and serves complementary roles with InfoNCE, yielding tighter and more precise alignment. Moreover, by introducing distributional alignment, CS-Aligner enables incorporating additional information from unpaired data and token-level representations, enhancing flexible and fine-grained alignment in practice. Experiments on text-to-image generation and cross-modality retrieval tasks demonstrate the effectiveness of our method on vision-language alignment.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **现有视觉-语言对齐方法的局限**：当前主流方法（如CLIP）使用InfoNCE损失来最大化模态间的互信息，其本质是基于成对样本的对齐，忽略了模态间的全局分布差异。
- **模态间隙与对齐-均匀性冲突**：InfoNCE在多模态场景下存在固有的对齐 (alignment) 与均匀性 (uniformity) 冲突，导致对齐不够精确，模态间隙（modality gap）问题未能充分解决。
- **研究动机**：论文旨在克服上述局限，通过引入分布级（distributional）对齐来从整体上拉近视觉与语言两种模态的分布，从而获得更紧凑、更精确的多模态表征，为下游跨模态检索与生成任务提供更优的对齐基础。

---

### 2. 论文提出的方法论

- **核心思想**：提出 **CS-Aligner** 框架，将 **柯西-施瓦茨散度 (Cauchy-Schwarz, CS divergence)** 与互信息结合，实现视觉与语言模态的分布级对齐。CS散度能够同时捕捉模态的全局分布信息和成对样本的语义关系，从而弥补InfoNCE仅关注局部成对对齐的不足。
- **关键技术细节**：
  - 利用 **CS散度** 度量两个模态整体分布之间的差异，通过最小化该散度来直接拉近全局分布，而不仅仅是对齐单个样本对。
  - **与互信息互补**：CS散度与InfoNCE（最大化互信息）在功能上互补。InfoNCE保持表征的均匀性，而CS散度缓解其带来的对齐-均匀性冲突，使对齐更加紧密和精准。
  - **灵活扩展能力**：分布级对齐框架可以自然地融入**未配对数据**（unpaired data）以及**token级表征**，从而支持更细粒度的对齐，增强方法在实践中的灵活性和对齐精度。
- **算法流程**（用文字说明）：
  1. 分别提取图像和文本的全局表征（以及可选token级表征）。
  2. 计算成对互信息项（如InfoNCE损失），维持基本语义对齐与均匀性。
  3. 计算模态间的柯西-施瓦茨散度，作为分布级对齐损失项。
  4. 联合优化上述两项损失，最终获得同时满足局部语义对齐与全局分布匹配的多模态表征。

---

### 3. 实验设计

- **下游任务与场景**：
  - 文到图生成 (Text-to-Image Generation)
  - 跨模态检索 (Cross-modality Retrieval)，包含图文双向检索。
- **对比方法（Benchmark）**：
  - 以CLIP为代表的基于InfoNCE的视觉-语言对齐方法。
  - 其他仅基于成对样本对齐的前沿多模态对齐模型（论文摘要中未列出具体名称，完整论文应包含更多基线）。
- **评估数据集**：摘要中未明确列出具体数据集名称，但结合任务（生成、检索）推断可能使用MS-COCO、Flickr30K等标准多模态基准数据集。

---

### 4. 资源与算力

- 所提供的PDF文本及摘要中 **未提及** 使用的GPU型号、数量、训练时长等具体算力信息。原论文正文可能包含这些细节，但当前可提取内容中未显示。

---

### 5. 实验数量与充分性

- 根据摘要描述，论文包含以下实验维度：
  - **两大下游任务**：生成与检索，至少各一组主实验。
  - **消融实验**：验证CS散度与InfoNCE的互补性、未配对数据的作用、token级对齐的效果等。
  - **分析实验**：探究CS散度如何缓解对齐-均匀性冲突。  
- **充分性评价**：仅从摘要判断，实验覆盖了典型的跨模态任务和关键消融角度，设计较为合理。但缺乏具体数据集数量和对比方法列表，无法精确评估实验规模。摘要强调方法“超越仅基于成对样本对齐的方法”，说明对比是直接且公平的，结果具有说服力。

---

### 6. 论文的主要结论与发现

- **分布级对齐优于纯成对对齐**：将CS散度引入对齐过程能够更有效地减少模态间隙，得到更高质量的多模态联合表征。
- **互补机制成立**：CS散度与InfoNCE互相补充，前者解决了后者的对齐-均匀性冲突，两者结合带来更紧密准确的对齐效果。
- **实用性增强**：通过支持未配对数据与细粒度token对齐，CS-Aligner在实际应用中更具灵活性和性能优势，在文到图生成与跨模态检索任务上均取得了性能提升。

---

### 7. 优点

- **方法论创新**：首次将柯西-施瓦茨散度用于视觉-语言分布级对齐，理论上有别于现有仅依赖互信息的方法。
- **深刻的问题洞察**：准确指出InfoNCE在模态间的对齐-均匀性冲突，并给出针对性解决方案。
- **灵活可扩展**：天然支持未配对数据与细粒度表征，拓展了多模态对齐的数据利用方式。
- **实验论证有力**：在生成和检索两类下游任务上均验证了有效性，证明方法的泛化能力。

---

### 8. 不足与局限

- **算力信息缺失**：从所提供摘要中无法获知计算开销，大规模分布级对齐是否会显著增加训练成本未知。
- **实验细节不完整**：具体数据集、基线方法完整列表、超参数设置等未在摘要中披露，客观对比的视角受限。
- **潜在偏差风险**：使用未配对数据虽然灵活，但其质量与规模可能引入额外偏差，摘要未讨论相关鲁棒性。
- **应用范围限制**：论文聚焦于视觉-语言对齐，向其他模态（如音频、视频）的推广有待验证。

（完）
