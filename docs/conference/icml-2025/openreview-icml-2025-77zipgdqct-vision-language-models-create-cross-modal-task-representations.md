---
title: Vision-Language Models Create Cross-Modal Task Representations
title_zh: 视觉语言模型创建跨模态任务表征
authors: "Grace Luo, Trevor Darrell, Amir Bar"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=77ziPGdQct"
tags: ["query:affective-ai"]
score: 9.0
evidence: 发现视觉语言模型生成跨模态共享的任务向量，实现模态无关的表征对齐
tldr: 研究揭示自回归视觉语言模型将模态等价的输入对齐到一个共享任务向量中，该向量能跨模态迁移并优于直接提示，且可组合用于复合任务，为理解多模态模型内部的跨模态对齐提供了新视角，对视觉与语言表征学习的统一具有重要意义。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 836, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 840, \"height\": 836, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1301, \"height\": 1224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 779, \"height\": 283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 774, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 858, \"height\": 1177, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1755, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1425, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1594, \"height\": 1118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1798, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1517, \"height\": 2303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1137, \"height\": 2225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1432, \"height\": 1476, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1795, \"height\": 565, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1763, \"height\": 609, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 765, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1115, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1342, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 869, \"height\": 546, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 799, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1522, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1573, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1498, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1527, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 793, \"height\": 331, \"label\": \"Table\"}]"
motivation: 探究视觉语言模型处理多种任务的内部表征机制，揭示跨模态对齐现象。
method: 通过跨模态迁移实验测量任务向量，分析其模态不变性和格式无关性。
result: 单一任务向量即可跨模态触发正确生成，且优于完整提示，向量还可组合执行复合任务。
conclusion: 视觉语言模型自发形成共享任务表征，为理解多模态对齐提供了新视角和高效方法。
---

## Abstract
Autoregressive vision-language models (VLMs) can handle many tasks within a single model, yet the representations that enable this capability remain opaque. We find that VLMs align conceptually equivalent inputs into a shared task vector, which is invariant to modality (text, image) and format (examples, instruction), and may simplify VLM processing. We measure this alignment via cross-modal transfer--the ability of a task vector derived in one modality to trigger the correct generation in another--on a range of tasks and model architectures. Although the task vector is highly compressed, we find that this single vector outperforms prompting the model with the full task information, unique to this cross-modal case. Furthermore, we show that task vectors can be transferred from a base language model to its fine-tuned vision-language counterpart, and that they can be derived solely from instructions without the need for examples. Taken together, our findings shed light on how VLMs internally process task information, and how they map different modalities into common semantic representations.

---

## 论文详细总结（自动生成）

# 论文总结：Vision-Language Models Create Cross-Modal Task Representations

## 1. 论文的核心问题与整体含义
- **研究动机**：自回归视觉语言模型（VLM）在单一模型中可处理多种任务，但其内部表征机制仍不透明。用户可通过指令、文本示例或图像示例以不同方式定义同一任务，这给模型处理带来复杂性，需要某种压缩或共享机制。
- **核心问题**：VLMs 是否将不同模态（文本、图像）和不同格式（示例、指令）的概念等价输入，对齐到一个共享的任务表征（task vector）？该表征是否具有跨模态不变性？
- **整体含义**：论文试图揭示 VLMs 如何内部处理任务信息，探明不同模态如何映射到共同的语义表征，为理解多模态模型的对齐机制提供新视角，并可能简化 VLM 的实际应用。

## 2. 论文提出的方法论
- **核心思想**：引入“跨模态 patching（cross‑modal patching）”方法，验证并利用 VLMs 内部的共享任务向量。任务向量是从某个模态和格式的任务定义中提取的、位于模型特定层和特定 Token 位置（通常为最后一个分隔符 Token）的高层摘要表征。
- **关键技术细节**：
  - 设任务 \( t \)，模型 \( f \)，先从文本示例 \( p_{\text{txt}} \) 提取任务向量 \( h_t^{l,\text{txt}} = f(p_{\text{txt}}) \) 在层 \( l \) 的最后分隔符 Token 处的输出。
  - 对未见过的图像查询 \( x_{\text{img}} \)，将该任务向量替换（patch）到查询前向传播中对应层和对应 Token 位置，生成任务特定答案：\( y_{\text{img}} = f_{\text{patch}}(x_{\text{img}} \mid h_t^{l,\text{txt}}) \)，而不再需要额外提供任务定义。
  - 通过跨模态迁移（例如文本定义 → 图像查询）测量对齐程度。
  - 该方法还可以扩展为：从指令提取任务向量、从图像示例提取任务向量、甚至从基础大语言模型（LLM）提取向量注入相应 VLM。
- **与基线对比**：与传统的 few‑shot prompting（将任务定义与查询一同输入模型）进行对比，突出 patching 的优势。

## 3. 实验设计
- **数据集/场景**：
  - 设计了 6 个跨模态任务：Country‑Capital、Country‑Currency、Animal‑Latin、Animal‑Young、Food‑Color、Food‑Flavor。每个任务包含文本指令、文本示例和图像示例三种定义（表1）。
  - 对每个任务，将示例池划分为 30 个验证样本和 100 个测试样本，查询与示例不重叠。
  - 还扩展到“野生” VQA 任务（从 VQAv2 派生）以及任务覆盖场景（Semantic、Syntax、Creative Generation、Factual Recall）。
- **Benchmark 与对比方法**：
  - 三种 VLM 模型：LLaVA‑v1.5（late‑fusion）、Mantis‑Fuyu（early‑fusion）、Idefics2（late‑fusion，优化多模态 ICL）。
  - 对比的方法包括：
    - **No Context**（无任务信息）
    - **Prompt**（few‑shot prompting，文本示例或图像示例，图3b）
    - **Patch**（跨模态 patching，图3a）
    - 以及用于对比的模态组合（图像示例→图像查询、文本示例→文本查询等）
    - LLM‑to‑VLM transfer（基础 LLM 的任务向量注入到微调后的 VLM）
    - 指令基向量的性能，以及指令与示例基向量的集成（ensemble）
    - 噪声指令的鲁棒性

## 4. 资源与算力
- 文中**未明确说明**具体的 GPU 型号、数量或训练时长。
- 仅在附录（Table 7）中比较了“patching”与“prompting”在一次前向传播中的计算开销：patching 将运行时间从 2.20 秒降至 0.20 秒，VRAM 从 20.02 GB 降至 8.21 GB（在 30 个长文本示例的设定下），说明 patching 可大幅降低推理资源需求。

## 5. 实验数量与充分性
- **实验覆盖广泛**：
  - 核心实验涉及 3 个不同架构的 VLM，6 个专门设计的跨模态任务，每个模型均测试了 No Context、Prompt、Patch 等多种方法（Table 2）。
  - 额外进行 LLM→VLM 迁移实验（Table 3）。
  - 指令基向量的实验（Figure 6），并分析集成向量的样本效率。
  - 扩展 VQA 任务上的跨模态转移（Table 4）。
  - 任务覆盖（overriding）实验，涉及 4 种不同冲突类型，并与系统提示（system prompt）对比（Table 5，Figure 7）。
  - 表示演化的详细分析：不同层的解码结果（Figure 8, 14, 15）、t‑SNE 聚类（Figure 2）、任务向量解码为任务摘要（Table 6）。
  - 消融实验：所有模态组合的 patching（Table 12）、不同模板格式（Table 10）、噪声指令鲁棒性（Table 9）等。
- **实验客观公平性**：对比设置合理，所有方法使用相同划分的验证/测试集，多种子平均，具有可比性。所提的 patching 方法与标准 few‑shot prompting 直接对比，结果稳定且优势明显。
- **充分性**：实验设计充分展示了现象、验证了方法的有效性和通用性，消融实验也覆盖了模态组合、模型架构、指令与示例的复合等维度。

## 6. 论文的主要结论与发现
1. **共享任务向量存在**：VLMs 将概念等价的输入（不同模态、不同格式）对齐到共享的任务表征，该表征在特定层的分隔符 Token 处形成。
2. **跨模态 patching 高效且强大**：仅用一个高度压缩的任务向量进行跨模态 patching，能显著优于使用完整任务信息的 few‑shot prompting，尤其改善了 VLM 在跨模态场景下的劣质表现（如输入 regurgitation）。
3. **基础 LLM 到 VLM 的可迁移性**：基础 LLM 的任务向量能直接迁移至其微调后的 VLM，且表现甚至略优于 VLM 自身的向量，说明语言功能表征在视觉微调后得以保留。
4. **指令可独立形成任务向量**：任务向量不仅可从示例中提取，也能从单纯的指令中获取，且集成指令向量和示例向量能提高样本效率和降低方差。
5. **表示演化三阶段**：模型处理示例时，早期层解码输入 Token（如冒号），中间层解码任务摘要（如“物种”、“首都”），后期层解码具体答案；文本和图像 ICL 都遵循类似阶段。
6. **任务聚类而非模态聚类**：t‑SNE 可视化（Figure 2）显示任务向量按任务而非按模态聚集，而上下文嵌入仍强烈按模态分离，表明 VLM 在上下文保持模态特异性，但在任务向量层面整合跨模态信息。

## 7. 优点
- **方法简洁有效**：跨模态 patching 仅需单一向量，计算开销低，易于实现。
- **揭示深层机制**：通过表示解码和聚类分析，直观展示了 VLMs 内部的跨模态对齐现象，为可解释性研究提供重要证据。
- **实用价值高**：patching 可解决 few‑shot prompting 的失效问题，尤其适用于跨模态任务；指令向量可提高样本效率；任务覆盖场景中表现优于系统提示。
- **实验全面**：涵盖多种模型架构（early/late fusion）、多种任务和对比方法，结论具有较强的泛化性。
- **启发性强**：观察到 LLM 到 VLM 的转移能力，提示语言和视觉任务可共享底层函数表征，对多模态模型设计有指导意义。

## 8. 不足与局限
- **缺乏理论解释**：论文承认仅提供了共享表征的经验证据，未从理论上解释为何会产生这种对齐。
- **任务局限**：主要基于合成的百科知识任务和少量 VQA 任务，可能无法覆盖真实世界中更复杂的多模态指令和推理。
- **评价指标简单**：采用第一个生成 Token 的精确匹配，对开放生成或长答案任务可能不够鲁棒。
- **仅限自回归模型**：研究仅针对自回归 VLMs，未覆盖其他架构（如编码器‑解码器或扩散模型）。
- **覆盖场景有限**：虽做了任务覆盖实验，但主要针对“冲突”设定，日常多任务协调等场景尚未深入。
- **依赖激活 patching**：计算任务向量需额外前向传播，尽管可摊销，但仍增加了一次执行的延迟。
- **准确性瓶颈**：即便使用 patching，某些任务的准确率仍然有限（如 Animal‑Young 在某些模型上低于 20%），距离实际部署仍需提升。

（完）
