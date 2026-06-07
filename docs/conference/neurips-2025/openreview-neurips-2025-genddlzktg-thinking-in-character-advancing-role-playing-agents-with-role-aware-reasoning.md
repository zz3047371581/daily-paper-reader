---
title: "Thinking in Character: Advancing Role-Playing Agents with Role-Aware Reasoning"
title_zh: 角色内思考：通过角色感知推理提升角色扮演智能体
authors: "Yihong Tang, Kehai Chen, Muyun Yang, Zheng-Yu Niu, Jing Li, Tiejun Zhao, Min Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=geNdDlzKTG"
tags: ["query:affective-ai"]
score: 8.0
evidence: 面向情感陪伴的角色扮演智能体，角色感知推理用于情感LLM
tldr: 针对现有角色扮演智能体缺乏深度内心思考、角色遗忘和风格偏移等问题，提出角色感知推理方法RAR，通过角色注意力校准和风格对齐，使智能体在情感陪伴等应用中展现出更一致的角色化推理和情感表达，提升了交互真实感。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-genddlzktg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1404, \"height\": 928, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-genddlzktg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1401, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-genddlzktg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1404, \"height\": 466, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-genddlzktg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-genddlzktg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-genddlzktg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-genddlzktg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1160, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-genddlzktg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 673, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-genddlzktg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 1048, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-genddlzktg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1195, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-genddlzktg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1312, \"height\": 922, \"label\": \"Table\"}]"
motivation: 情感陪伴应用中，角色扮演智能体缺乏类人内部思考，表现浅层。
method: 提出角色感知推理RAR，包含注意力校准和风格对齐。
result: RAR改善了角色一致性推理，减少风格漂移，提升情感表达。
conclusion: RAR使角色扮演智能体更自然地进行情感交互。
---

## Abstract
The advancement of Large Language Models (LLMs) has spurred significant interest in Role-Playing Agents (RPAs) for applications such as emotional companionship and virtual interaction. However, recent RPAs are often built on explicit dialogue data, lacking deep, human-like internal thought processes, resulting in superficial knowledge and style expression. While Large Reasoning Models (LRMs) can be employed to simulate character thought, their direct application is hindered by attention diversion (i.e., RPAs forget their role) and style drift (i.e., overly formal and rigid reasoning rather than character-consistent reasoning). To address these challenges, this paper introduces a novel Role-Aware Reasoning (RAR) method, which consists of two important stages: Role Identity Activation (RIA) and Reasoning Style Optimization (RSO). RIA explicitly guides the model with character profiles during reasoning to counteract attention diversion, and then RSO aligns reasoning style with the character and scene via LRM distillation to mitigate style drift. Extensive experiments demonstrate that the proposed RAR significantly enhances the performance of RPAs by effectively addressing attention diversion and style drift.

---

## 论文详细总结（自动生成）

根据论文内容，以下是结构化的中文总结：

### 1. 论文的核心问题与研究动机
- **核心问题**：当前基于大语言模型的角色扮演智能体（RPA）主要依赖表面对话数据，缺乏深层次、类人化的内心思考过程，导致其知识和风格的表达流于表面。
- **关键挑战**：虽然大型推理模型（LRM）可用于模拟角色思考，但直接应用会产生两个根本性问题：
  - **注意力转移**：模型在推理时容易忘记自己所扮演的角色，转而关注通用的任务或问题解决。
  - **风格漂移**：模型倾向于生成结构严谨、逻辑化但过于正式的推理过程，而非符合角色设定、生动且富有情感的内心独白。
- **研究目标**：提出一种新方法，使模型能够进行符合角色设定、深度且一致的内部推理，从而生成更传神的角色化回复。

### 2. 方法论：角色感知推理（RAR）
论文提出角色感知推理方法，旨在将大型推理模型的推理能力有效迁移到角色扮演任务中，其核心包含两个阶段：

- **角色身份激活 (RIA)**
  - **核心思想**：通过在推理的关键步骤持续注入与角色相关的约束信息，解决注意力转移问题，确保模型在思考时始终保持角色自我意识。
  - **具体实现**：首先，使用大型推理模型自动从角色设定中提取核心元素（如情感、经历、立场、动机）。然后，将这些元素作为指令`CR`来引导大型推理模型生成包含思考轨迹 `yCoT` 和最终回复 `yans` 的角色感知训练数据 `DR`。最终，通过监督微调，将这种角色感知推理能力从大型推理模型蒸馏到普通大语言模型中。

- **推理风格优化 (RSO)**
  - **核心思想**：使模型能根据当前对话场景动态调整其内部思考的表达风格（如逻辑分析型或生动情感型），以解决风格漂移问题。
  - **具体实现**：定义事实型 `CFact` 和角色知识型 `CKnow` 两种推理风格提示，与两种典型场景（逻辑分析型 `XLogic`、生动交互型 `XStory`）进行配对，生成风格与场景一致的正例（D⁺S）和不一致的负例（D⁻S）。随后，通过对比学习损失函数进行优化，使模型学会根据上下文选择合适的推理风格。

### 3. 实验设计
- **数据集与场景**：
  - **训练数据**：来源于RoleBench，包含从95个角色生成的约13.8万条角色扮演样本。
  - **评测基准**：
    - **CharacterBench**：包含约2.3万条数据，用于评估角色扮演的忠实度，涵盖记忆、知识、人格、情感、道德等11个维度。
    - **SocialBench**：包含6000多个问题，通过多选题评估智能体在个体和群体交互中的社交智能，如角色知识、幽默感、社交偏好等。

- **对比方法**：
  - **基础方法**：Vanilla（原始数据微调）、RAG、Distill（普通蒸馏）。
  - **思考模式控制**：基于Distill的ZeroThink、LessThink、MoreThink等解码策略。
  - **专用模型**：Neeko、CharacterGLM等专为角色扮演设计的模型。

### 4. 资源与算力
- **基础模型**：LLaMA-3-8B。
- **教师模型**：Qwen2-32B（作为大型推理模型）。
- **硬件配置**：8 × H20 GPU。
- **训练时长**：非推理模型约5小时，推理模型约20小时。
- **其他技术**：统一采用4比特量化和LoRA技术进行高效微调。

### 5. 实验数量与充分性
论文进行了多组、多维度的实验，较为充分和客观：

- **主实验**：在CharacterBench和SocialBench两个权威基准上，与9种不同方法进行对比。
- **消融实验**：
  - 验证RAR的两个核心模块（RIA和RSO）的各自贡献。
  - 在RIA内部，逐一移除“情感、经历、立场、动机”四个要素，分析其有效性。
- **深入分析**：
  - **推理轨迹质量评估**：使用GPT-4o对推理的连贯性、角色相关性、有效性、简洁性进行打分，并辅以人工评估验证。
  - **可视化分析**：使用t-SNE可视化隐含层状态，证明RSO能有效分离不同推理风格。
  - **案例分析**：通过具体对话例子进行定性比较。
- **公平性**：所有对比方法均基于相同的基础模型和统一的量化与LoRA配置，确保了比较的公平性。

### 6. 主要结论与发现
- RAR在角色扮演性能上显著优于所有基线方法，尤其是在角色人格一致性、记忆一致性和社交偏好理解方面。
- RIA通过持续注入角色核心特征，有效解决了“注意力转移”问题，是模型保持角色稳定性的关键。
- RSO使模型能根据场景动态调整推理风格，显著缓解了“风格漂移”，并提升了角色的可信度和用户参与度。
- 仅仅增加推理长度（如MoreThink）但缺乏引导，反而会损害角色扮演性能。

### 7. 优点与亮点
- **创新性强**：首次系统性地将大型推理模型的长链思考能力适配到角色扮演领域，并明确指出和解决了“注意力转移”和“风格漂移”两大挑战。
- **方法设计精巧**：RIA和RSO两个模块分别针对特定问题，相互协同，理论清晰，实现合理。
- **实验全面严谨**：在两个不同侧重点的基准上进行了多维度评估，结合细致的消融实验和可视化分析，论据充分。
- **解释性好**：通过案例分析，直观展示了方法在生成角色一致性和深度思考上的效果。

### 8. 不足与局限
- **依赖教师模型**：推理能力蒸馏效果受限于所使用的教师模型（Qwen2-32B）本身的能力。
- **角色属性的颗粒度**：角色身份激活模块基于自动提取的核心要素，对于极其复杂或微妙的角色，可能难以捕捉所有细粒度特质。
- **风格分类的简化**：RSO目前仅定义了二元化的场景（逻辑 vs. 生动）和风格，而现实对话常是混合模态，缺乏动态融合机制。
- **资源限制下的验证**：仅在8B参数规模的模型上做了验证，其在更大参数量模型上的表现潜力和可扩展性有待探索。
- **缺乏错误条**：论文未报告多次实验的统计显著性（如标准差），由于训练成本高昂，结果可复现性难以从数据上精确衡量。

（完）
