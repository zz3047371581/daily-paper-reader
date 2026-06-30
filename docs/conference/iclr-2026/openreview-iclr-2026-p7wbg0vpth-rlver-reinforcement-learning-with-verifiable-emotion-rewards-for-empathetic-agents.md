---
title: "RLVER: Reinforcement Learning with Verifiable Emotion Rewards for Empathetic Agents"
title_zh: RLVER：基于可验证情感奖励的强化学习训练移情智能体
authors: "Peisong Wang, Ruotian Ma, Bang Zhang, Xingyu Chen, Zhiwei He, Kang Luo, Qingsong Lv, Qingxuan Jiang, Zheng Xie, Shanyi Wang, CIXING LI, Yuan Li, Fanghua Ye, Jian Li, Yifan Yang, Jia Li, Zhaopeng Tu, Xiaolong Li"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=P7wBg0vPTh"
tags: ["query:affective-ai"]
score: 10.0
evidence: 端到端强化学习框架，利用仿真用户的验证情感奖励培养LLM的共情能力
tldr: 大语言模型在逻辑推理方面表现优异，但其情感智能仍落后。本文提出RLVER框架，首次将可验证情感奖励的强化学习应用于对话领域：通过自洽的仿真用户产生对话情感分数作为奖励，引导LLM内化高阶移情能力。实验证明该方法能显著提升模型的共情回应质量，为构建高情商对话智能体提供了全新训练范式。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 大语言模型认知能力强但情感智能不足，强化学习应用于对话情感能力未被探索。
method: 提出RLVER框架，利用自洽情感模拟用户进行对话交互并产生确定性情感分数作为奖励信号，指导LLM训练。
result: 在移情对话任务中，LLM的高级移情能力显著提升，超越了现有方法。
conclusion: 首次将可验证奖励强化学习应用于情感对话，开辟提升LLM情感智能的新途径。
---

## Abstract
Large language models (LLMs) excel at logical and algorithmic reasoning, yet their emotional intelligence (EQ) still lags far behind their cognitive prowess.  While reinforcement learning from verifiable rewards (RLVR) has advanced in other domains, its application to dialogue—especially for emotional intelligence—remains underexplored. In this work, we introduce RLVER, the first end-to-end reinforcement learning framework that leverages verifiable emotion rewards from simulated users to cultivate higher-order empathetic abilities in LLMs. Within this framework, self-consistent affective simulated users engage in dialogue rollouts and produce deterministic emotion scores during conversations, serving as reward signals to guide the LLM's learning. Fine-tuning publicly available Qwen2.5-7B-Instruct model with PPO boosts its Sentient-Benchmark score from 13.3 to 79.2 while largely preserving mathematical and coding competence.  Extensive experiments reveal that: (i) RLVER consistently improves multiple dialogue capabilities; (ii) Thinking and non-thinking models show distinct trends—thinking models excel in empathy and insight, while non-thinking models favor action; (iii) GRPO often yields stable gains, while PPO can push certain capabilities to a higher ceiling; (iv) More challenging environments are not always better—moderate ones can yield stronger outcomes. Our results show that RLVER is a practical route toward emotionally intelligent and broadly capable language agents.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大语言模型（LLMs）在逻辑推理与算法任务上表现卓越，但其情感智能（EQ）远远滞后于认知能力。现有研究虽然已开始探索利用强化学习提升 LLM 的能力，但在对话领域——尤其是情感对话中——利用**可验证奖励的强化学习（RLVR）** 仍属空白。
- **整体含义**：本文首次将可验证的情感奖励引入端到端强化学习框架，通过构造一个能够给出确定性情感评分的仿真用户，使 LLM 能够在对话交互中直接内化高阶移情能力，为构建具备高情商且综合能力不退化的大语言模型提供了一条实用的技术路线。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：提出 **RLVER（Reinforcement Learning with Verifiable Emotion Rewards）** 框架，让 LLM 通过与一个**自洽的情感仿真用户**进行多轮对话展开（dialogue rollouts），由该仿真用户产出**可验证的、确定性的情感分数**作为奖励信号，从而优化模型产生移情回应的策略。
- **关键技术细节**：
  - **自洽情感仿真用户**：该仿真用户能够模拟人类的情绪反应，并在对话过程中生成一致且可复现的情感评分，确保奖励的可验证性。
  - **奖励信号**：以对话过程中的情感分数（例如来自 Sentient-Benchmark 的评分）作为强化学习的奖励，直接反映移情质量。
  - **训练算法**：采用 **PPO（Proximal Policy Optimization）** 对公开可用的 Qwen2.5-7B-Instruct 进行微调；同时实验中也对比了 **GRPO**（未详细说明，可能是另一种策略梯度方法）。
- **算法流程（文字描述）**：
  1. 给定一个需要情感回应的对话上下文，LLM 生成回复。
  2. 仿真用户读取该回复并与之交互，持续展开多轮对话，并根据预定义的情感评估标准给出一个情感分数。
  3. 将该分数作为回报，利用 PPO 更新 LLM 策略，使其在未来相似上下文中生成更高情感评分的回复。
  4. 同时保持对原有数学和代码能力的泛化约束，避免灾难性遗忘。

### 3. 实验设计：使用了哪些数据集/场景，benchmark 是什么，对比了哪些方法

- **数据集/场景**：并未在元数据中给出具体数据集名称，但提到了 **Sentient-Benchmark**，很可能是一个评估移情对话能力的基准测试。场景为开放式情感对话，要求模型表现出共情、洞察力或行动建议。
- **Benchmark**：以 Sentient-Benchmark 的评分作为主要评价指标，该分数量化了模型移情回应的质量。同时也会考察数学与编码能力的变化（如 GSM8K、HumanEval 等常用 benchmark 的分数隐含提及保持能力）。
- **对比方法**：虽然未列出具体 baseline，但从摘要可以推测对比了：
  - 原始 Qwen2.5-7B-Instruct 模型；
  - 可能包含其他不对情感进行优化的基线（如仅经过指令调优的模型）；
  - 不同强化学习变体：PPO 与 GRPO 的效果对比；
  - 不同难度的训练环境（moderate vs. challenging environments）。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力

- 元数据**未明确提及** GPU 型号、数量、训练时长等具体算力信息。仅知所用基础模型为 Qwen2.5-7B-Instruct，属于 7B 参数规模，通常在多张 A100 或同等 GPU 上即可完成 PPO 微调，但此处无法给出确切数字。

### 5. 实验数量与充分性：大概做了多少组实验，是否充分、客观、公平

- 据摘要和元信息推断，实验至少涵盖以下维度：
  - **两种策略优化算法**：PPO 和 GRPO 的对比；
  - **思维与非思维模型**的区分（thinking vs. non-thinking models），并观察其在 empathy、insight、action 等不同能力维度上的表现差异；
  - **环境难度消融**：对比中等难度与高难度训练环境下的效果；
  - **能力保持验证**：确认情感强化学习后数学和编程能力不会严重退化。
- 这些实验设计从算法选择、模型变体、环境设计等角度提供了多组对比，具有一定的充分性。由于情感奖励是确定性的，评估相对客观；所有模型均基于同一基座，公平性较好。但对比的基线方法种类未详细描述，可能会影响全面性判断。

### 6. 论文的主要结论与发现

- **RLVER 有效性**：经过 RLVER 微调后，Qwen2.5-7B-Instruct 在 Sentient-Benchmark 上的得分从 **13.3 大幅提升至 79.2**，同时数学和编码能力基本保留。
- **多维度能力提升**：RLVER 能稳定提升多种对话能力，且不同模型类型表现出不同优势：
  - **思维模型（thinking models）** 在共情和洞察力方面更胜一筹；
  - **非思维模型（non-thinking models）** 则更倾向于提供行动建议。
- **算法差异**：GRPO 通常能带来更稳定的增益，而 PPO 在特定能力上有可能达到更高的天花板。
- **环境难度影响**：更具挑战性的训练环境并不总是更好，中等难度的环境反而能产生更强的最终表现。
- **整体启示**：该框架为打造高情商且能力全面的语言智能体提供了可行途径。

### 7. 优点：方法或实验设计上有哪些亮点

- **首次探索**：首次将可验证奖励的强化学习应用于对话情感领域，填补了 RLVR 在该方向的空白。
- **可验证奖励设计**：利用自洽仿真用户给出确定性情感分数，避免了奖励模型训练不稳定的问题，使强化学习信号更清晰可靠。
- **保持通用能力**：在显著提升情商的同时，并未牺牲模型原本的数学和编码能力，避免了灾难性遗忘。
- **细致的能力分析**：区分了 thinking/non-thinking model 的行为差异，并考察了不同算法和环境难度的影响，提供了有价值的实践指导。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **仿真用户与真实人类的差距**：情感奖励由模拟用户给出，可能与真实人类的复杂情感评价存在偏差，迁移到真实对话场景时性能可能下降。
- **评价方式相对单一**：目前主要依赖 Sentient-Benchmark 这一自动化指标，缺乏人类评估或与真实用户交互的验证。
- **基座模型限制**：仅在 Qwen2.5-7B 一个模型上进行了验证，其他模型家族或更大参数量下的效果未知。
- **安全与伦理**：通过强化学习夸大情感回应可能带来操控性对话的风险，论文未提及此类安全控制机制。
- **缺少算力与成本讨论**：无具体算力消耗数据，限制了他人对复现成本的判断。

（完）
