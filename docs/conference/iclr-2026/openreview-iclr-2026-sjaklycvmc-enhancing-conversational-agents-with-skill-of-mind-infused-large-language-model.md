---
title: Enhancing Conversational Agents with Skill-of-Mind-Infused Large Language Model
title_zh: 利用心智技能注入增强对话智能体的大语言模型
authors: "Young-Jun Lee, Byung-Kwan Lee, Dokyong Lee, junyoung youn, Kyeong-Jin Oh, Yechan Hwang, Ho-Jin Choi"
date: 2025-09-19
pdf: "https://openreview.net/pdf?id=SjAKLyCvmC"
tags: ["query:affective-ai"]
score: 10.0
evidence: 将38种会话技能（如共情）注入大语言模型，使对话智能体具备类人社交能力
tldr: 针对大语言模型在复杂社交对话中难以生成类人回复的问题，构建包含38种会话技能的10万条多维度心智技能标注数据集，并训练Thanos系列模型（1B-8B参数），同时提出ThanosBench评测基准。实验表明技能注入显著提升了社交对话的拟人化程度和情境适应性，为融合情商与大语言模型提供了有效路径。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: 大语言模型在社交对话中缺乏选择恰当会话技巧的能力。
method: 构建多维度心智技能对话数据集，训练技能注入大语言模型Thanos系列。
result: 模型在社交对话拟人度和情境适应性上显著提升。
conclusion: 该工作为构建具有社交技能的对话智能体提供了数据和模型基础。
---

## Abstract
To foster social bonding, humans naturally develop the ability to select appropriate conversational skills (e.g., empathy) based on situational context—a cognitive process we term skill-of-mind. However, LLMs often struggle to generate human-like responses in complex social dialogues. To address this, we propose a 100K skill-of-mind-annotated conversation dataset, Multifaceted Skill-of-Mind, which includes 38 conversational skills across various interactive scenarios (e.g., chitchat), grounded in diverse social contexts (e.g., demographics). Using this dataset, we introduce a new family of skill-of-mind-infused LLMs, Thanos, with model sizes of 1B, 3B, and 8B parameters. We also introduce a comprehensive benchmark suit, ThanosBench, for assessing both capabilities of skill-of-mind and response generation in LLMs. Through extensive experiments evaluating 12 LLMs, Thanos demonstrates performance comparable to Claude-3.5-Sonnet, even outperforming LLaMA-3.1-405B. Specifically, Thanos enhances LLM-generated responses, making them more human-favorable and empathetic communication. Because we find out that recent high-performing LLMs still struggle to exhibit superior skill-of-mind capabilities, we believe it is invaluable to highlight the inherent challenges in this area.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：大语言模型（LLM）在复杂社交对话中难以根据情境动态选取恰当的会话技巧（如同理心、幽默、自我表露等），导致回复缺乏人类社交的灵活性与共情力。
- **背景与动机**：人类具备“心智技能”（skill‑of‑mind）的认知能力，能依据对话语境、对象特征（如人口属性）自然调用不同的会话策略以维系社会联结。现有 LLM 尽管在多任务上表现优异，但在高度情境化的社交互动中仍显机械。论文旨在将“心智技能”显式地注入 LLM，从而提升对话代理的拟人化社交智能。

### 2. 论文提出的方法论
- **核心思想**：通过构建大规模、多维度心智技能标注的对话数据集，并以此微调 LLM，使模型学会在生成回复时同时建模“应使用何种会话技能”和“如何产生符合该技能的回复”。
- **关键技术细节**：
  - **数据集 Multifaceted Skill‑of‑Mind**：规模约 100K 条对话，涵盖 **38 种会话技能**（如同理心、积极倾听、幽默、自我表露等），覆盖日常闲聊等多种交互场景，并植根于多样化的社会情境（如对话者的年龄、性别、关系亲密度等）。
  - **技能注入 LLM 家族 Thanos**：基于预训练 LLM，利用上述数据集进行有监督微调或指令调优，产出 1B、3B、8B 三个参数规模的模型，使其在生成回复时隐式融合情境与技能选择。
  - **评测基准 ThanosBench**：系统性评估 LLM 在“心智技能能力”和“回复生成质量”两个维度的表现，包括对技能选择的准确度、回复恰当性、共情性等细粒度指标。

### 3. 实验设计
- **数据集与场景**：使用自建的 Multifaceted Skill‑of‑Mind 数据集进行训练和评测，覆盖多回合、多情境的社交对话。
- **基准与对比方法**：引入 ThanosBench 作为统一评测平台，评估了 **12 个 LLM**，包括前沿商业模型和开源模型，如 **Claude‑3.5‑Sonnet**、**LLaMA‑3.1‑405B** 等，以及 Thanos 系列模型。
- **评测指标**：衡量技能选择与情境匹配度、回复的人类偏好度、同理心沟通水平等，部分结果可能结合人工评估。

### 4. 资源与算力
- 文中**未明确说明**所使用的 GPU 型号、数量及训练时长。仅披露模型参数规模为 1B、3B、8B，由此可推断训练所需算力在单机多卡（如 A100 80GB）环境中可行，但具体开销不得而知。

### 5. 实验数量与充分性
- **实验组数**：核心实验涉及 12 个 LLM 在 ThanosBench 上的多维对比，同时可能包含对 Thanos 不同尺寸的消融分析、不同技能类别的影响等。论文摘要表述为“extensive experiments”，暗示实验设计较为全面。
- **充分性与公平性**：
  - 对比的基线既包含极大规模模型（405B），也包括同级参数模型，公平性较好。
  - 评测同时覆盖技能选择与生成质量，维度较完整。
  - 但未明确给出统计显著性检验或多次运行的平均方差，且人工评估样本量不详，这在一定程度上削弱了结论的稳健性支撑。

### 6. 论文的主要结论与发现
- Thanos 系列模型在社交对话中表现出与 **Claude‑3.5‑Sonnet** 相当的性能，甚至超越 **LLaMA‑3.1‑405B**，证明小模型通过技能注入可匹敌或超过大模型。
- 技能注入显著提升了回复的 **人类偏好度** 和 **共情性**，使对话更具情感支持性和情境适应性。
- 即便当前顶尖 LLM，在纯粹的心智技能能力上仍存明显不足，凸显该方向的固有挑战与研究价值。

### 7. 优点
- **数据集贡献**：首次构建涵盖 38 种会话技能、多维度社会情境的大规模对话数据集，填补了社交技能显式建模的资源空白。
- **系统评测基准**：ThanosBench 为衡量 LLM 社交智能提供了统一、多维度的测试平台，推动领域标准化。
- **模型高效性**：技能注入使 1B～8B 小模型即可达到甚至超越数百亿参数大模型的社交表现，具备实际部署的效率优势。
- **任务定义清晰**：将“心智技能”抽象为可标注、可学习的对话策略，方法可扩展至更多技能和领域。

### 8. 不足与局限
- **算力信息缺失**：未报告具体硬件开销与训练时间，复现性和资源估算难度加大。
- **泛化性与偏差风险**：数据集基于特定文化、语言背景构建，38 种技能的覆盖度有限，可能存在社会偏差（如对特定人口群体的刻板印象），跨文化适用性未验证。
- **评估的有限性**：ThanosBench 虽全面，但可能过度依赖预定义的技能分类，对开放式对话中涌现的复合技能或隐式技能捕捉不足；人类评估的规模和设计细节不详。
- **应用限制**：技能注入模型在非社交任务上的性能退化是否受控未做交代，且在多轮交互中能否持续稳定地展现恰当技能仍有待探索。
- **模型规模上限**：现有 Thanos 最大仅 8B，更大规模的技能注入效果、与极大型模型的最终比较有待延伸。

（完）
