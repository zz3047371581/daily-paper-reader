---
title: "Unveiling the Cognitive Compass: Theory-of-Mind–Guided Multimodal Emotion Reasoning"
title_zh: 揭示认知罗盘：基于心智理论的多模态情感推理
authors: "Meng Luo, Bobo Li, Shanqing Xu, Shize Zhang, Qiuchan Chen, Menglu Han, Wenhao Chen, Yanxiang Huang, Hao Fei, Mong-Li Lee, Wynne Hsu"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=8VSrk2CaBr"
tags: ["query:affective-ai"]
score: 10.0
evidence: 基于心智理论指导的多模态大模型情感推理方法
tldr: 针对多模态大模型深层情感理解不足的问题，本文提出心智理论引导的情感推理框架。通过构建层级化基准HitEmotion和心智状态追踪链，并利用强化学习以过程监督训练模型，显著提升了MLLM的情绪理解能力。该方法为赋予AI真正的情感智能提供了认知启发的新范式。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 现有多模态大模型缺乏深层情感理解，未显式建模心智状态。
method: 引入心智理论，构建层级基准和推理链，并用过程监督强化学习优化。
result: 在多个情感推理任务上，心智引导的MLLM表现优于传统方法。
conclusion: 心智理论引导显著增强了MLLM的情感推理深度与可信度。
---

## Abstract
Despite rapid progress in multimodal large language models (MLLMs), their capability for deep emotional understanding remains limited. We argue that genuine affective intelligence requires explicit modeling of Theory of Mind (ToM), the cognitive substrate from which emotions arise. To this end, we introduce HitEmotion, a ToM-grounded hierarchical benchmark that diagnoses capability breakpoints across increasing levels of cognitive depth. Second, we propose a ToM-guided reasoning chain that tracks mental states and calibrates cross-modal evidence to achieve faithful emotional reasoning. We further introduce TMPO, a reinforcement learning method that uses intermediate mental states as process-level supervision to guide and strengthen model reasoning. Extensive experiments show that HitEmotion exposes deep emotional reasoning deficits in state-of-the-art models, especially on cognitively demanding tasks. In evaluation, the ToM-guided reasoning chain and TMPO improve end-task accuracy and yield more faithful, more coherent rationales. In conclusion, our work provides the research community with a practical toolkit for evaluating and enhancing the cognition-based emotional understanding capabilities of MLLMs.

---

## 论文详细总结（自动生成）

# 论文深度解读：基于心智理论的多模态情感推理

## 1. 论文的核心问题与整体含义
- **研究动机**：当前多模态大语言模型（MLLMs）虽然在感知与常规推理上进展迅速，但深层情感理解能力依然薄弱。模型倾向于表层特征匹配，无法真实“感受”或“推断”情绪背后的心智状态。
- **整体含义**：作者认为，实现真正的情感智能必须显式建模**心智理论（Theory of Mind, ToM）**——情绪产生的认知根基。论文通过构建认知层级的评测基准、设计心智状态追踪推理链，以及引入过程监督强化学习，为MLLM赋予以认知为驱动的可信情感推理能力，开辟了一条从“行为模仿”到“心智理解”的新范式。

## 2. 论文提出的方法论
整套方法论由三个核心部分构成，形成“评测—推理—优化”闭环。

### 2.1 层级化基准 HitEmotion
- **核心思想**：将情感理解分解为逐级递增的认知深度，诊断不同模型的能力断点。
- **关键设计**：
  - 构建多层级任务，从浅层情绪识别到深层心智推断（如愿望、信念、意图等）。
  - 每个层级对应不同的ToM心智成分，实现对缺陷的细粒度定位。

### 2.2 心智理论引导的推理链
- **核心思想**：在推理过程中显式追踪心智状态，并校准跨模态证据，从而生成忠实、连贯的情感推理。
- **流程说明**（文字描述）：
  - **心智状态追踪**：模型先推断角色当前的**信念、愿望、意图**等中间心智变量。
  - **跨模态证据校准**：结合视觉、语言等多模态线索，验证并修正心智状态。
  - **情绪推理输出**：基于校准后的心智状态链，最终推断情绪并生成可解释的推理路径。
- **效果**：将黑箱情绪判断转化为可审查的心智推理过程。

### 2.3 过程监督强化学习 TMPO
- **核心思想**：不只看最终答案，而是利用中间心智状态作为**过程级监督信号**，通过强化学习优化整个推理链。
- **算法流程**（文字描述）：
  - **奖励设计**：不仅奖励最终情绪标签正确，还奖励心智状态推断的准确性与一致性。
  - **策略优化**：使用强化学习（可能是PPO等）更新模型参数，最大化过程奖励。
  - **训练目标**：使模型自发地生成更准确的心智推理步骤，而非仅拟合最终答案。
- **优势**：强化学习的过程监督弥补了仅用最终标签训练的不足，增强推理的忠实度和鲁棒性。

## 3. 实验设计
- **数据集 / 场景**：
  - 基于自建的 **HitEmotion 基准** 进行诊断与评测，该基准包含多个认知深度的子任务。
  - 涉及多模态输入（视觉+文本），模拟真实情感推理场景。
- **对比方法**：
  - 与现有先进 MLLM（未在摘要中列举具体模型名）在相同基准下对比，尤其关注深层认知任务的性能。
  - 对比项目：端到端准确率、推理过程的忠实度与连贯性。
- **评测维度**：
  - **能力断点暴露**：揭示现有模型在不同认知层级上的性能骤降点。
  - **增强效果评测**：分别验证 ToM 引导推理链与 TMPO 训练带来的准确率提升与推理质量改善。

## 4. 资源与算力
- **文中提供情况**：摘要文本未提及使用的GPU型号、数量、训练时长等具体算力信息。
- **推断**：考虑到涉及多模态大模型训练和强化学习，预期需要中等以上算力，但细节需查阅全文。

## 5. 实验数量与充分性
- **实验数量描述**：摘要仅用“Extensive experiments”（广泛实验）概括，未给出确切实验组数。
- **充分性评价**：
  - 从设计逻辑看，实验覆盖了**诊断性实验**（HitEmotion暴露缺陷）、**组件消融**（推理链与TMPO各自贡献）以及**性能对比**，结构较完整。
  - 若全文包含消融研究、不同模型规模测试、跨领域迁移等，则实验会非常充分。但仅凭摘要无法完全判断统计显著性与偏差控制。

## 6. 论文的主要结论与发现
- **发现一**：HitEmotion 基准成功揭示出当前一流模型在深层情感推理上的明显缺陷，尤其在需要高阶心智推理的任务上表现断崖式下跌。
- **发现二**：引入 ToM 引导推理链后，模型不仅能提升最终情绪判断准确率，还能生成更忠实、逻辑更连贯的推理解释。
- **发现三**：用中间心智状态作为过程监督的强化学习 TMPO 可进一步强化推理链，使情感推理从“猜答案”进化为“懂心理”。
- **总体结论**：显式建模心智理论是赋予 MLLM 真正情感智能的关键路径，所提框架为社区提供了评估与增强认知情感理解的有效武器。

## 7. 优点
- **认知深度突破**：首次将心智理论显式、系统性地融入多模态情感推理，瞄准“为什么会有情绪”的深层问题。
- **方法闭环完整**：从诊断基准（HitEmotion）到推理机制（心智链）再到训练算法（TMPO），形成一套可操作的解决方案。
- **过程监督创新**：利用中间心智状态作为过程级奖励，相比只看最终答案的传统监督，显著提升推理忠实度与可解释性。
- **实用工具包视角**：为研究社区提供可直接复用的评测与增强手段，不止于模型本身。

## 8. 不足与局限
- **实验细节缺失**：摘要未提供数据集规模、对比模型列表、统计显著性检验等，难以评估结论的稳健性。
- **算力与可复现性**：未说明资源消耗和训练细节，完全复现存在门槛。
- **心智标注依赖**：HitEmotion 及训练中的心智状态标签可能需要大量专业标注，限制了方法的快速扩张至其他领域。
- **泛化性待验证**：目前聚焦于情感推理，扩展至其他需要心智推理的任务（如社交互动、谈判）的效果未知。
- **偏差风险**：若训练数据中的心智状态推断存在文化或情境偏差，可能导致模型产生有偏的心智归因。

（完）
