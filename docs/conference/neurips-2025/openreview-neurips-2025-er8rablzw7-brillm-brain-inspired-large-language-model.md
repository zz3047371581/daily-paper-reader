---
title: "BriLLM: Brain-inspired Large Language Model"
title_zh: BriLLM：类脑大语言模型
authors: "hai zhao, Hongqiu Wu, Dongjie Yang, Anni Zou, Jiale Hong"
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=eR8raBLZW7"
tags: ["query:affective-ai"]
score: 4.0
evidence: 类脑架构的大语言模型，但未专门针对情感智能
tldr: 提出BriLLM，一种基于有向图信号全连接流动的类脑大语言模型，完全抛弃Transformer架构。所有节点可解释，通过最小阻力原则预测下一token，为脑启发学习提供了新范式，但未直接涉及情感处理。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-er8rablzw7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1311, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-er8rablzw7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1074, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-er8rablzw7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1240, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-er8rablzw7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1166, \"height\": 597, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-er8rablzw7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 750, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-er8rablzw7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1409, \"height\": 1622, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-er8rablzw7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1463, \"height\": 2033, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-er8rablzw7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1462, \"height\": 204, \"label\": \"Table\"}]"
motivation: 传统语言模型缺乏可解释性，且与大脑机制脱节。
method: 设计基于有向图和信号流的类脑架构，非Transformer。
result: BriLLM具有一定的生成能力，节点可解释。
conclusion: 为探索类脑语言模型提供了新思路，但还需验证性能。
---

## Abstract
This paper reports the brain-inspired large language model (BriLLM). This is a non-Transformer, non-GPT, non-traditional machine learning input-output controlled generative language model. The model is based on the Signal Fully-connected flowing (SiFu) definition on the directed graph in terms of the neural network, and has the interpretability of all nodes on the graph of the whole model, instead of the traditional machine learning model that only has limited interpretability at the input and output ends. In the language model scenario, the token is defined as a node in the graph. A randomly shaped or user-defined signal flow flows between nodes on the principle of "least resistance" along paths. The next token or node to be predicted or generated is the target of the signal flow. As a language model, BriLLM theoretically supports infinitely long $n$-gram models when the model size is independent of the input and predicted length of the model. The model's working signal flow provides the possibility of recall activation and innate multi-modal support similar to the cognitive patterns of the human brain. At present, we released the first BriLLM versions in Chinese and English, with 4000 tokens, 32-dimensional node size, 32-token sequence prediction ability, model sizes around 2B and 1B respectively, bringing language model prediction performance comparable to GPT-1.

---

## 论文详细总结（自动生成）

# BriLLM: Brain-inspired Large Language Model 论文总结

## 1. 核心问题与研究动机
- **研究背景**：当前主流大语言模型（如 GPT 系列）均基于 Transformer 架构，虽性能强大，但缺乏内部可解释性——模型内部的大量参数如同黑箱，仅在输入和输出端具备有限的可解释性。
- **关键矛盾**：这些模型的工作机制与人类大脑的认知过程（如可解释的神经元、记忆激活、多模态自然融合）相脱节。
- **核心问题**：能否构建一个完全非 Transformer、非 GPT 式的语言模型，使其内在结构具有全面的可解释性，并且更贴近大脑的工作模式？
- **整体含义**：本文试图开辟一条“类脑语言模型”新路径，以有向图信号流替代传统的逐层前馈计算，为语言生成提供一种更具生物学启发性的计算范式。

## 2. 方法论
### 2.1 核心思想
- **完全抛弃 Transformer**：BriLLM 不使用自注意力、前馈网络等 Transformer 组件，而是建立一个基于有向图的神经网络。
- **信号全连接流动 (SiFu)**：在整张有向图上定义一种“信号全连接流动”机制。图中每个节点即为一个 token（词元）。
- **最小阻力原则**：信号流会在节点之间沿“阻力最小”的路径传播，模型通过动态寻找该路径来完成序列建模。
- **可解释节点**：图中任意一个节点（token）的行为都可以被解释，改变了传统模型仅在输入/输出端具有可解释性的局限。

### 2.2 关键技术要点
- **n‑gram 扩展能力**：理论上支持无限长的 n‑gram，且模型尺寸不随输入序列长度或预测长度而增长。
- **token 级别的图结构**：将语言建模转化为图上的信号传播任务，下一 token 即为信号流的目标节点。
- **与认知科学的映射**：信号流机制为类似人脑的“回忆激活”模式提供了可能，并天然支持多模态融合（信号可在不同模态的节点间流动）。
- **当前版本参数**：已发布的中文版本约 2B 参数，英文版本约 1B 参数；节点维度为 32，可处理 4000 token 的词汇表，支持 32 token 长的序列预测。

## 3. 实验设计
- **声称性能对比**：论文指出其生成性能与 GPT‑1 相当，但**摘要及元数据中未给出具体的评测数据集、benchmark 名称、对比方法及详细指标**。
- **已发布的模型**：提供了首个中英文 BriLLM 版本，具备一定的生成能力，且节点可解释。
- **评估维度**：除生成能力外，重点强调了模型内部节点的可解释性，但缺乏量化实验结果的报告（如困惑度、下游任务得分等）。
- **客观性与公平性**：由于未公布评测框架与对比基线细节，无法判断实验的客观性与公平性。

## 4. 资源与算力
- **未明确说明**：摘要及已提供的元数据中**完全没有提及**所使用的 GPU 型号、数量、训练时长、批大小或能耗等信息。
- 文中仅有模型参数规模（约 1B–2B）的记载，缺乏必要的算力透明度。

## 5. 实验数量与充分性
- **实验组数未知**：从现有信息无法推断进行了多少组实验（如不同数据集、不同规模的消融实验等）。
- **充分性存疑**：仅声称性能与 GPT‑1 相当，并未展示与现代基准（如 LLaMA、GPT‑3 等）的对比，也没有提供系统的消融研究或下游任务评测，实验的覆盖面和深度明显不足。
- **客观性风险**：由于缺少可复现的评测设置，论文的结论高度依赖作者自身宣称，外部难以验证其有效性。

## 6. 主要结论与发现
- BriLLM 作为一种全新的、非 Transformer 的类脑大语言模型，**在架构上具备所有节点的可解释性**。
- 最小阻力信号流机制成功实现了语言序列的生成，初步验证了基于有向图节点预测下一个 token 的可行性。
- 该模型为未来融合“回忆激活”、多模态信号等类脑认知功能提供了结构基础。
- 作者认为 BriLLM “为脑启发学习提供了新范式”，但现阶段性能远未达到实用水平，仍需大量后续工作。

## 7. 优点与亮点
- **架构创新**：彻底抛弃 Transformer，提出以有向图信号流为核心的语言模型，理论简洁且富有新意。
- **全局可解释性**：图中全部节点可解释，有望解决大模型黑箱问题，对安全、调试和认知科学均有价值。
- **理论灵活性**：支持无限长 n‑gram，模型大小与序列长度解耦；天然兼容多模态信号传播。
- **神经科学启发**：路线贴合人脑工作机制，可能为强人工智能研究提供新的思路。

## 8. 不足与局限
- **性能严重落后**：仅与 GPT‑1 相比，而 GPT‑1 已是 2018 年的模型，远远落后于当前 SOTA。论文未展示在标准基准上与同代模型的对比。
- **实验信息极度匮乏**：未说明训练数据集、评测基准、超参数、算力资源等关键细节，可复现性差。
- **可扩展性未验证**：仅推出 1B‑2B 规模、32 维节点的版本，能否扩展到更大规模、更复杂任务仍是未知数。
- **应用范围限制**：目前仅展示了一定的生成能力和节点可解释性，未在常识推理、知识问答、多模态理解等实际应用中证明自己。
- **信号流机制的计算效率**：有向图上的信号流传播可能面临计算瓶颈，论文未讨论推理速度与内存开销。
- **偏差与公平性**：缺少任何关于数据偏见、公平性或伦理影响的讨论，方法本身也未经充分审查。

（完）
