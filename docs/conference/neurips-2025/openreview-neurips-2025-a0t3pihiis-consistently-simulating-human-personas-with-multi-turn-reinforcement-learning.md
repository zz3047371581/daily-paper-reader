---
title: Consistently Simulating Human Personas with Multi-Turn Reinforcement Learning
title_zh: 通过多轮强化学习一致地模拟人类角色
authors: "Marwa Abdulhai, Ryan Cheng, Donovan Clay, Tim Althoff, Sergey Levine, Natasha Jaques"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=A0T3piHiis"
tags: ["query:affective-ai"]
score: 6.0
evidence: 在治疗、教育、角色扮演中模拟人类角色；通过多轮强化学习提高LLM对话中角色一致性
tldr: 针对LLM在模拟人类用户时经常偏离指定角色的问题，本文提出三种自动评估指标（提示与行一致性、行与行一致性、问答一致性）来衡量角色漂移，并利用这些指标作为奖励信号进行多轮强化学习微调。实验表明，该方法能有效提升对话中角色行为的一致性，为构建可靠的交互式AI代理提供了评估和优化框架。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-a0t3pihiis/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1423, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a0t3pihiis/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1424, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a0t3pihiis/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a0t3pihiis/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a0t3pihiis/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1395, \"height\": 346, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1179, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 890, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1551, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 551, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 771, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1300, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1544, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1295, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a0t3pihiis/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 930, \"height\": 466, \"label\": \"Table\"}]"
motivation: 现有LLM在模拟人类角色时常常偏离设定，表现出不一致的言行，影响交互式应用的可靠性。
method: 提出三种自动角色一致性指标，并以此为奖励信号进行多轮强化学习微调。
result: 微调后模型在三个指标上取得一致提升，并经人类标注验证了有效性。
conclusion: 该方法为AI代理的角色一致性提供了统一评估和优化框架，在治疗、教育等领域具有应用价值。
---

## Abstract
Large Language Models (LLMs) are increasingly used to simulate human users in interactive settings such as therapy, education, and social role-play. While these simulations enable scalable training and evaluation of AI agents, off-the-shelf LLMs often drift from their assigned personas, contradict earlier statements, or abandon role-appropriate behavior. We introduce a unified framework for evaluating and improving persona consistency in LLM-generated dialogue. We define three automatic metrics—prompt-to-line consistency, line-to-line consistency, and Q\&A consistency—that capture different types of persona drift and validate each against human annotations. Using these metrics as reward signals, we apply multi-turn reinforcement learning to fine-tune LLMs for three user roles: a patient, a student, and a social chat partner. Our method reduces inconsistency by over 55%, resulting in more coherent, faithful, and trustworthy simulated users.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义
大型语言模型（LLM）被广泛用于模拟人类用户，以支持治疗、教育和社交角色扮演等交互式场景的 AI 代理训练与评估。然而，现成的 LLM 在多轮对话中常出现**角色漂移**：即偏离初始设定，前后陈述矛盾，或放弃与角色相符的行为。这不仅降低模拟的真实性，还可能对下游系统（如心理健康支持、教育辅导）造成误导，干扰策略学习并扭曲实验结果。因此，本文旨在**系统性地评估和提升 LLM 模拟用户的角色一致性**，使模拟更可靠、更可信。

### 2. 方法论
论文提出一个统一框架，包括三个核心环节：数据集生成、一致性自动评分、多轮强化学习微调。

- **角色设定与对话生成**  
  定义三个任务场景：开放域闲聊（基于 PersonaChat 风格）、教育（学生-教师）和心理健康（患者-治疗师）。每个场景中，一个 LLM 充当**用户模拟器（Usim）**，另一个充当**任务代理（Task Agent）**，并依据详细背景提示（persona）生成多轮对话。

- **三种一致性自动指标**  
  使用 LLM-as-a-Judge（如 Meta-Llama-3.1-70B-Instruct）计算以下指标，作为奖励信号：
  1. **提示-行一致性（Prompt-to-Line）**：衡量每条回复与初始背景提示的一致性。
  2. **行-行一致性（Line-to-Line）**：检测同一说话者在对话历史中是否自相矛盾。
  3. **问答一致性（Q&A）**：通过生成诊断性问题，比较从对话中推断的答案与从背景提示直接得到的答案，评估信念稳定性。

- **奖励引导的强化学习**  
  以**提示-行一致性**为主要奖励信号，采用 PPO（Proximal Policy Optimization）对用户模拟器模型进行多轮对话微调。每轮对话的状态包含历史上下文，动作是新的回复，奖励由 LLM Judge 根据一致性指标实时给出。训练使用 OpenRLHF 框架，支持对话级别的奖励和 rollout，无需人工反馈，实现可扩展的优化。

### 3. 实验设计
- **任务与数据**
  - **开放对话**：使用 100 个人工合成 persona（来自 Li et al.），生成 200 个对话，长度分别为 10、20、40、60 轮。
  - **教育**：学生 persona 来自 27 种学习风格（如叙事型、动觉型等），教师指导特定主题，对话设置同上。
  - **心理健康**：从临床标准（DSM‑5、认知疗法等）综合生成 100 种患者 persona，表示焦虑、抑郁、冒名顶替综合征等，由治疗师代理进行对话。
- **对比方法**
  - 基准模型：Meta-Llama-8B-Instruct
  - 监督微调（SFT）
  - 离线强化学习：Kahneman-Tversky Optimization (KTO)
  - 在线 RL：PPO（本文方法）
- **评估指标**
  - 三种自动一致性指标，以及人类一致性评分（李克特量表 1–6，转换为二分类）
  - 人机一致性：Fleiss’ Kappa、百分比一致性
  - 下游对话质量补充测评：AlpacaEval‑2、FED 风格精细评估

### 4. 资源与算力
- 训练使用 8 个 NVIDIA H100 GPU 集群，部分实验使用 H200 GPU。
- 数据集生成（对话生成和评分）约耗时 2‑3 天（每个场景 2 个 GPU）。
- SFT 训练约 30 分钟，KTO 约 5 小时，PPO 约 10 小时。
- PPO 训练需至少 2 个 H200 运行 reward model（Llama‑3.1‑70B‑Instruct vLLM 服务器）和 1‑2 个 H200 或 3 个 H100 运行 actor、critic 和 student 模型。

### 5. 实验数量与充分性
- 每个任务（3 个任务）× 3 个基础模型（Llama‑8B、Gemma‑2B、Mistral‑7B）生成约 **800 个对话/任务**，总计约 **39K 条对话语句**。
- 人类评估涉及 **75 个选择题**，覆盖三种任务和所有模型，由 30 名评审员标注。
- 微调后，对 10 个新 persona 生成 40 个不同长度的对话进行评估。
- 补充实验：分析对话长度延长（10‑60 轮）下的一致性趋势，以及 PPO 后长对话的稳定性。
- 还进行了 AlpacaEval‑2 和 FED 风格的自动质量评估，验证微调未损害通用指令跟随能力。
- 总体而言，实验规模较大，涵盖多任务、多模型、多方法对比，且有严格的人类验证和消融分析，比较充分、客观。

### 6. 主要结论与发现
- **自动指标与人类判断高度一致**：LLM‑as‑a‑Judge 的评分与人类评分的 Fleiss’ Kappa 平均 0.40，优于人类间 Kappa（0.06‑0.26）；提示-行一致性的一致性最高。
- **基线 LLM 存在显著不一致**：尤其在长对话和情感模糊的心理健康场景中，提示-行和问答一致性下降明显；Mistral‑7B 整体表现最优，Llama‑8B 一致性较低但语言更丰富。
- **多轮 RL 显著提升一致性**：PPO 微调后，提示-行一致性提升 **+58.5%**（开放对话）、**+20.6%**（教育）、**+37.6%**（心理健康），在扩展对话长度下也能维持高一致性。
- **PPO 优于 SFT 和 KTO**：PPO 在所有任务上获得最高一致性分数，且长对话稳定性最佳。

### 7. 优点
- **全面的一致性衡量体系**：三种指标覆盖局部与全局、语言与信念层面的角色漂移。
- **自动化、可扩展的奖励**：无人工标注，利用 LLM‑Judge 提供低成本、一致的训练信号。
- **多任务泛化**：在开放对话、教育、心理健康三个差异较大的领域验证，证明方法的通用性。
- **严格的人类对齐实验**：通过 Fleiss’ Kappa 和百分比一致性证明自动指标优于人类评审员间的信度。
- **结合多轮 PPO**：直接优化对话级奖励，解决长期角色稳定性问题。

### 8. 不足与局限
- **静态 persona 假设**：未模拟现实中角色的想法变化或情境适应；可能惩罚合理的态度转变。
- **仅优化提示-行一致性**：未联合使用三种指标，可能无法全面捕捉所有不一致类型。
- **人类评估规模有限**：30 名评审员，可能未完全覆盖人群多样性。
- **应用场景受限**：由于对话基于合成数据和固定背景，模型不应直接部署于临床或教育场景，需额外安全验证。
- **心理健康任务仍有不足**：即使在微调后, 该任务的情感细腻度、适应性和信息性指标仍较低, 留下改进空间。

（完）
