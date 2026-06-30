---
title: "MMOC: Multi-Model Online Collaboration Framework for Enhancing EEG Emotion Recognition"
title_zh: MMOC：强化EEG情感识别的多模型在线协作框架
authors: "Hanqi Wang, Lang Qian, Jingyu Zhang, Kun Yang, Liang Song"
date: 2025-09-17
pdf: "https://openreview.net/pdf?id=NN0ab41ifX"
tags: ["query:affective-ai"]
score: 10.0
evidence: 基于EEG的多模型在线协作情感识别，处理脑电信号流
tldr: 该论文针对EEG情感识别中高被试间变异性和分布漂移问题，提出自监督多模型在线协作框架MMOC，通过路由机制为每个流式样本激活最合适的模型，提升了在线场景下的识别性能。
source: ICLR-2026-Rejected-Public
selection_source: conference_retrieval
motivation: EEG情感识别面临被试间差异大，现有离线迁移学习无法适应在线流式数据。
method: 自监督学习框架，多模型池，路由机制在线选择最佳模型。
result: 有效应对流式EEG样本，提升情感识别准确性。
conclusion: 在线多模型协作能增强脑机接口中的情感识别鲁棒性。
---

## Abstract
Electroencephalography (EEG)-based emotion recognition is critical for developing adaptive brain-computer interfaces, yet remains challenged by high inter-subject variability and consequent distribution drifts. While self-supervised learning offers a promising alternative to supervised approaches by leveraging unlabeled data, current methods often use offline transfer learning with calibration, which is insufficient for streaming EEG samples in online scenarios. To overcome this limitation, we introduce MMOC, a novel self-supervised framework with Multi-Model Online Collaboration (MMOC). For handling the varying input samples in the stream, MMOC proposes to activate the most suitable model from a candidate pool using a routing mechanism. This routing decision is guided by a hybrid reconstruction–contrastive performance, which comprehensively captures distribution drifts at both structural and semantic levels. Furthermore, each model is equipped with an online parameter update mechanism with model specialization and mutual assistance. This mechanism not only enhances inter-model differentiation and specialization but also facilitates collaborative adaptation among models via pseudo-label sharing, thereby improving robustness against evolving data distributions. Extensive experiments on SEED and Dreamer datasets demonstrate that MMOC outperforms the state-of-the-art works with 86.39\% $\pm$ 5.41 on SEED, and 69.37\% $\pm$ 6.13 (arousal) and 70.33\% $\pm$ 6.78 (valence) on Dreamer. This result confirms its strong resistance to the inter-subject variability problem. Our work offers a practical solution for handling real-world EEG emotion recognition.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究背景**：基于脑电图（EEG）的情感识别对开发自适应脑机接口至关重要，但其面临高被试间变异性和由此引发的分布漂移问题。
- **现有方法局限**：当前流行自监督学习利用无标签数据，但主要采用离线迁移学习加校准的方式，无法应对流式 EEG 样本在线场景下的持续变化。
- **整体含义**：论文提出 MMOC（多模型在线协作框架），旨在以在线方式动态应对流式数据中的分布漂移，提升 EEG 情感识别的鲁棒性和实用化水平。

### 2. 方法论
- **核心思想**：构建一个多模型候选池，通过路由机制为每一个流式样本在线激活最合适的模型，从而实现“按需分工”。
- **路由决策依据**：基于混合重构-对比性能（hybrid reconstruction–contrastive performance），从结构（重构损失）和语义（对比损失）两个层面全面捕捉分布漂移，作为模型选择的信号。
- **模型更新机制**：每个被激活的模型具有在线参数更新能力，同时引入**模型专业化**和**互助**策略。模型间通过伪标签共享实现协作适应，一方面增强模型间的差异化和专业性，另一方面促进模型协同抵御数据分布演化。

### 3. 实验设计
- **数据集**：
  - **SEED** 数据集：用于离线及在线情感识别评测。
  - **Dreamer** 数据集：同时考察唤醒度（arousal）和效价（valence）维度。
- **Benchmark 与对比方法**：论文将 MMOC 与现有最先进（state-of-the-art）方法进行对比（文中未列出具体对比方法名称，但明确其在两个数据集上均达到最优）。
- **评估指标**：分类准确率（均值±标准差）。

### 4. 资源与算力
- 提供的摘要和元数据中**未提及**所用 GPU 型号、数量、训练时长或具体算力消耗信息。因此，无法从现有材料推断其计算资源需求。

### 5. 实验数量与充分性
- 文中提及至少包含：
  - SEED 数据集实验；
  - Dreamer 数据集上两个维度（arousal, valence）的实验；
  - 与多个现有方法的对比；
  - 在线流式场景下的性能评测。
- 摘要中未说明是否进行了消融实验（如移除路由机制、移除专业化更新等），但元数据结果和讨论暗示可能包含此类分析。基于提供的信息，实验覆盖了两个主流多被试情绪数据集，对比基线明确，结果以均值和标准差呈现，具有一定的客观性和公平性。

### 6. 主要结论与发现
- MMOC 在 SEED 上达到 86.39% ± 5.41 的准确率，在 Dreamer 唤醒度上达到 69.37% ± 6.13，效价上达到 70.33% ± 6.78，全面超越现有工作。
- 结果证实了该框架对高被试间变异性和在线分布漂移具有强大的抵抗力，为真实世界的 EEG 情感识别提供了切实可行的解决方案。

### 7. 优点（亮点）
- **在线适应能力**：区别于离线迁移学习，MMOC 直接在流式环境中工作，更贴近实际应用。
- **混合性能信号**：通过重构与对比双路信号指导模型路由，可敏锐检测分布变化。
- **协作进化机制**：模型专业化结合伪标签互助，既保证了多样性又增强了整体鲁棒性。
- **性能表现突出**：在两个主流基准上取得领先结果。

### 8. 不足与局限
- **算力与效率未知**：未披露在线推理时的计算延迟、内存占用或训练开销，实际部署可行性需进一步验证。
- **技术细节待考证**：摘要未给出具体公式、算法流程细节，路由阈值、模型池大小、更新频率等超参数的影响未明确。
- **实验局限性**：
  - 仅在两个数据集上验证，泛化能力未被更广泛的任务或模态检验。
  - 未说明是否与基于在线学习或元学习的现有专门方法直接对比。
  - 可能缺少更复杂的流式漂移模式（如概念漂移类型细分）的分析。
  - 被试间变异性虽被强调，但未知实验是否为留一被试（leave-one-subject-out）跨被试协议，若为被试依赖协议则结论可能高估实用性。
- **应用限制**：实际在线 EEG 系统中常伴有噪声、通道缺失等问题，MMOC 对这些因素的鲁棒性未探讨。

（完）
