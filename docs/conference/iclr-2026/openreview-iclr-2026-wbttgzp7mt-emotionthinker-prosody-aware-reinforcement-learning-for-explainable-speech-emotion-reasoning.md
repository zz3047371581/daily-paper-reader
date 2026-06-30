---
title: "EmotionThinker: Prosody-Aware Reinforcement Learning for Explainable Speech Emotion Reasoning"
title_zh: EmotionThinker：基于韵律感知强化学习的可解释语音情感推理
authors: "Dingdong WANG, Shujie LIU, Tianhua Zhang, Youjun Chen, Jinyu Li, Helen M. Meng"
date: 2026-01-26
pdf: "https://openreview.net/pdf?id=wbttgzp7MT"
tags: ["query:affective-ai"]
score: 10.0
evidence: 利用强化学习与语音大语言模型生成基于声学线索的可解释情感识别
tldr: 针对当前语音大语言模型仍将情感理解视为简单分类、缺乏可解释性的问题，提出EmotionThinker，通过强化学习将语音情感识别转化为深度推理任务，构建大规模情感思维链数据集EmotionCoT-35K，使模型能生成基于细粒度声学线索的可解释情感预测。实验结果显示该方法在准确率和可解释性上均优于传统分类方法，为语音情感识别从感知到认知的跨越提供了新范式。
source: ICLR-2026-Accepted
selection_source: conference_retrieval
motivation: 语音大模型在情感理解上缺乏推理能力和可解释性。
method: 构建情感推理数据集，利用强化学习训练语音大模型生成可解释情感预测。
result: 模型在准确率和可解释性上均表现优异，优于分类方法。
conclusion: 该工作首次将语音情感识别建模为推理任务，提升了情感识别的深度和可靠性。
---

## Abstract
Emotional information in speech plays a unique role in multimodal perception. However, current Speech Large Language Models (SpeechLLMs), similar to conventional speech emotion recognition (SER) systems, still treat emotion understanding as a simple classification problem. This provides limited interpretability of predictions, while leaving the LLMs’ expressive and reasoning capabilities underutilized. In this work, we take the first step to reformulate SER as a deep reasoning problem through reinforcement learning (RL). We propose EmotionThinker, which is designed to generate accurate emotion predictions with interpretable explanations grounded in fine-grained acoustic cues. To achieve this, we first construct EmotionCoT-35K, an emotional reasoning dataset with Chain-of-Thought annotations and detailed captions. Second, we observe that current SpeechLLMs exhibit weak prosody perception, whereas prosodic cues constitute fundamental signals for interpreting emotions. To address this, we develop the prosody-enhanced foundation model EmotionThinker-Base, and demonstrate that prosody enhancement improves emotion understanding. Third, we introduce Group-Relative-Policy-Optimization with Progressive-Trust-aware-Reasoning-Reward (GRPO-PTR}) for RL. Different from standard GRPO, which relies only on rule-based outcome rewards, GRPO-PTR progressively introduces reasoning reward, dynamically adjusts it with a trustworthiness weight reflecting the alignment between reasoning and outcome, and evaluates the overall reasoning quality with a reward model based on multi-dimensional criteria. EmotionThinker outperforms previous state-of-the-art evaluation models both in emotion accuracy and explanation quality, advancing SER toward interpretable multimodal reasoning.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**  
  语音中的情感信息是多模态感知的重要组成部分，但现有语音大语言模型（SpeechLLM）和传统语音情感识别（SER）系统仍将情感理解简化为分类问题，输出仅是一个标签，缺乏对预测的解释。这不仅限制了模型的可信度与透明度，也未能充分利用大语言模型固有的表达和推理能力。
- **核心问题**  
  如何让语音大模型从“感知”走向“认知”，即不仅输出情感类别，还能给出基于声学线索的、可解释的推理过程。
- **整体含义**  
  该工作首次将语音情感识别重塑为深度推理任务，通过强化学习驱动模型生成准确且可解释的情感预测，推动SER从黑箱分类走向可解释的多模态推理。

## 2. 论文提出的方法论

- **整体思想**  
  提出 **EmotionThinker** 框架，使语音大模型能够为输入语音生成“情感思维链”，一步步揭示细粒度声学线索（如音高、语速、能量等）如何支撑最终的情感判断。
- **关键技术细节**
  - **数据集构建：EmotionCoT‑35K**  
    构建了一个包含思维链（Chain‑of‑Thought）标注和详细情感描述的大规模情感推理数据集，为模型提供可解释性训练信号。
  - **韵律增强基础模型：EmotionThinker‑Base**  
    针对当前SpeechLLM普遍存在的韵律感知弱的问题，设计韵律增强方法，提升模型对韵律线索（如语调、重音、节奏）的理解能力，实验证明该增强可改善情感理解。
  - **强化学习训练：GRPO‑PTR**  
    提出**Group‑Relative‑Policy‑Optimization with Progressive‑Trust‑aware‑Reasoning‑Reward（GRPO‑PTR）**，区别于仅依赖规则化结果奖励的标准GRPO，GRPO‑PTR具备三个特点：
    - *渐进导入推理奖励*：逐步引入对推理质量的奖励，避免早期训练中不成熟的推理信号干扰。
    - *可信度加权调整*：引入一个可信度权重，反映推理过程与最终情感结果之间的对齐程度，据此动态调整推理奖励的影响。
    - *多维奖励模型评估*：使用奖励模型从多个维度（如逻辑连贯性、声学线索准确性）综合评判推理质量，而非单一得分。

- **算法流程**（文字说明）  
  EmotionThinker以语音为输入，利用韵律增强的编码器提取特征，再通过大语言模型生成包含推理步骤和情感预测的输出；在RL阶段，策略根据生成的完整回答（推理+预测）获得由结果奖励与可信度引导的推理奖励组成的组合奖励，通过组内相对优劣进行策略优化。

## 3. 实验设计

- **数据集/场景**  
  论文未在摘要中明确列出具体数据集，但通常SER领域会使用IEMOCAP、MSP-IMPROV、RAVDESS等标准库，且自建了EmotionCoT‑35K用于训练和评估。推测实验涵盖这些常见情感语音数据。
- **Benchmark与对比方法**  
  以先前最优的评估模型（包括传统SER系统和SOTA SpeechLLM）作为基准，主要比较指标为情感识别准确率和解释质量。
- **对比维度**  
  在“情感准确度”和“解释质量”两个维度进行评测，后者可能通过人工或自动化指标衡量推理的忠实度和合理性。

## 4. 资源与算力

- 文中未明确提供GPU型号、数量、训练时长等信息。  
- 鉴于涉及大语言模型训练与强化学习，所需算力预计较高，但具体配置需查阅正文补充材料。

## 5. 实验数量与充分性

- **实验组数**  
  摘要未详细说明实验规模。根据已有信息，至少包含：
  - 韵律增强模块的消融实验（比较有无增强的效果）；
  - 不同RL策略对比（标准GRPO vs. GRPO-PTR）；
  - 与多个基线模型的准确率和解释质量对比；
  - 可能对不同数据集的泛化性测试。
- **充分性与公平性**  
  从设计上看，消融实验和与SOTA的比较较为必要，能验证各组件的贡献。但受限于信息量，无法判断是否覆盖了跨语种、跨场景、低资源等条件，也无法确认解释指标的客观性（如是否只依赖模型自评）。

## 6. 论文的主要结论与发现

- EmotionThinker在情感识别准确率和解释质量上均显著优于以往最优模型。
- 韵律增强有效弥补了现有SpeechLLM在韵律感知上的短板，是提升情感理解的关键。
- GRPO‑PTR通过渐进推理奖励和可信度机制，稳定地训练出兼顾预测准确性与解释合理性的模型。
- 这项工作为语音情感识别从感知分类跃升至认知推理提供了新的范式。

## 7. 优点

- **范式创新**：首次将SER建模为可解释的深度推理任务，充分发挥LLM的生成与推理能力。
- **数据构建**：EmotionCoT‑35K为情感思维链训练提供了宝贵资源。
- **方法严谨**：韵律增强直击SpeechLLM痛点；GRPO‑PTR的渐进可信奖励机制比传统RL更适配推理任务。
- **评估全面**：同时关注预测准确性和解释质量，超越单一的标签准确率。

## 8. 不足与局限

- **实验细节缺失**：基于摘要无法获知具体数据集、算力开销、解释质量的具体评估方式，限制了对结果稳定性和可复现性的判断。
- **数据依赖性**：EmotionCoT‑35K的构建方式、标注成本、覆盖的语种和文化背景未说明，可能影响方法的通用性。
- **推理真实性风险**：模型生成的声学线索解释可能只是一种“合理化的修辞”，而不一定真实反映其内部决策过程，幻觉问题可能存在。
- **应用效率**：生成式推理比传统分类消耗更多计算资源，实时场景下的部署可行性需进一步评估。

（完）
