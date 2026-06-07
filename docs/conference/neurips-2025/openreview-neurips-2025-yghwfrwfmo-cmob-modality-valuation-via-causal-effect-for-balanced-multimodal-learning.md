---
title: "CMoB: Modality Valuation via Causal Effect for Balanced Multimodal Learning"
title_zh: CMoB：基于因果效应的模态估值以实现平衡的多模态学习
authors: "Jun Wang, Fuyuan CAO, ZhixinXue, Xingwang Zhao, Jiye Liang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ygHWfrwFmO"
tags: ["query:affective-ai"]
score: 7.0
evidence: 提出因果感知的模态估值方法，实现平衡的多模态学习。
tldr: 模态不平衡问题困扰多模态学习。本文提出CMoB，一种因果感知的模态估值方法，基于香农信息熵动态评估每个样本的模态重要性，实现平衡训练。实验证明该方法能有效平衡模态贡献，提升学习效果。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yghwfrwfmo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yghwfrwfmo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1146, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yghwfrwfmo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yghwfrwfmo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1421, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yghwfrwfmo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1148, \"height\": 908, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yghwfrwfmo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 673, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yghwfrwfmo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 893, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yghwfrwfmo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 613, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yghwfrwfmo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 761, \"height\": 263, \"label\": \"Table\"}]"
motivation: 多模态学习中模态贡献不平衡且样本间存在动态变化。
method: 提出基于因果效应的模态估值方法CMoB。
result: 实现模态平衡学习，提升整体性能。
conclusion: CMoB通过样本级动态估值平衡模态训练。
---

## Abstract
Existing early and late fusion frameworks in multimodal learning are confronted with the fundamental challenge of modality imbalance, wherein disparities in representational capacities induce inter-modal competition during training. Current research methodologies primarily rely on modality-level contribution assessments to measure gaps in representational capabilities and enhance poorly learned modalities, overlooking the dynamic variations of modality contributions across individual samples. To address this, we propose a Causal-aware Modality valuation approach for Balanced multimodal learning (CMoB). We define a benefit function based on Shannon's theory of informational uncertainty to evaluate the changes in the importance of samples across different stages of multimodal training. Inspired by human cognitive science, we propose a causal-aware modality contribution quantification method from a causal perspective to capture fine-grained changes in modality contribution degrees within samples. In the iterative training of multimodal learning, we develop targeted modal enhancement strategies that dynamically select and optimize modalities based on real-time evaluation of their contribution variations across training samples. Our method enhances the discriminative ability of key modalities and the learning capacity of weak modalities while achieving fine-grained balance in multimodal learning. Extensive experiments on benchmark multimodal datasets and multimodal frameworks demonstrate the superiority of our CMoB approach for balanced multimodal learning.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **核心问题：多模态学习中的模态不平衡**
    *   在多模态联合训练中，深度神经网络倾向于优先学习与目标任务相关性高、易于学习的“强势模态”，从而抑制其他“弱势模态”的优化，导致弱势模态的性能远低于其性能上限。
    *   这种现象被称为“模态不平衡”或“模态坍塌”，其根源在于神经网络的“贪婪”特性，导致了模态间的竞争。这使得模型无法充分融合所有模态的互补信息，甚至可能出现多模态性能不如单模态的情况。

*   **现有方法的局限**
    *   当前主流的解决思路主要是在**模态级别**评估各模态的贡献度，并针对性增强弱势模态。
    *   这种方法忽略了模态贡献度在**样本级别**上的动态变化。在现实数据中，同一个模态在不同样本中的信息量和数据质量是波动的（如TED演讲中，观众依赖音频，但遇到不熟悉的语言时会转向依赖字幕），仅从模态级别评估无法反映数据的真实特性。

*   **本文的核心思想**
    *   受人类多模态认知机制（尤其是因果推断能力）的启发，提出从**样本级别**和**因果学习**的视角重新审视多模态学习过程。
    *   通过衡量样本内各模态的**因果效应**，量化其贡献度，并据此动态优化弱势模态，从而以一种精细化的方式解决模态不平衡问题，提升多模态学习的性能与可解释性。

### 2. 方法论

*   **核心思想**
    *   本方法受到人类认知科学的启发：当单一模态信息不足时，大脑会利用信息熵动态整合其他模态以辅助理解。这个过程具有“基于因果关系的模态贡献估值”和“样本级别的粒度调整”两大特征。
    *   论文提出的CMoB方法旨在模拟这一过程，通过评估样本中每个模态的因果效应来量化其贡献，并针对性地增强贡献低的模态。

*   **关键技术细节与算法流程**
    *   **样本利益函数（Benefit Function）**
        1.  **理论基础**：基于香农信息论，认为增加模态会带来更多信息，降低模型预测的不确定性，从而提高预测置信度。
        2.  **函数定义**：对于一个样本，如果多模态模型的预测正确，并且加入新模态后的预测置信度高于加入前，则该样本的利益值定义为输入的模态数量 `|M|`；否则为0。
    *   **因果感知的模态贡献量化方法（Causal-aware Modality Contribution Quantification, CQM）**
        1.  **核心概念**：引入因果推断中的“干预”（`do`操作）和个体因果效应（ITE）概念。将含所有模态的样本作为对照组，将移除某特定模态后的样本作为实验组。
        2.  **ITE计算**：某模态 `j` 在样本 `i` 中的ITE等于对照组与实验组通过利益函数计算出的差值。公式为：`ITE(xji) = B(ˆF(S(xi))) - B(ˆF(S(xi)|do(ti = xji)))`。
        3.  **模态贡献度表示**：模态 `j` 的最终贡献度 `Φ(xji)` 等于其ITE加上该模态单独对输出的影响。公式为：`Φ(xji) = ITE(xji) + B(ˆF(xji))`。当 `Φ(xji) ≤ 1` 时，该模态被认为是“弱势模态”。
    *   **动态模态优化策略（Dynamic Modality Optimization Strategy, RE）**
        1.  **优化目标**：在训练迭代中，针对贡献度低的弱势模态样本进行选择性增强。
        2.  **优化方法**：为防过拟合，不简单地增加数据，而是采用自适应掩码。对弱势模态的局部特征进行掩码（音频用Time Masking，视频用Spatial Masking），迫使模型利用跨模态上下文依赖进行推理，提升鲁棒性和模态间语义连贯性。
        3.  **阶段化训练**：在训练前半段，仅对弱势模态应用掩码；在后半段，也对其它模态应用一个强度较弱的掩码，以实现定向的模态重平衡。

### 3. 实验设计

*   **数据集**：在5个公开的多模态基准数据集上验证，覆盖了不同模态组合：
    *   **CREMA-D**：音视频双模态，用于情感识别。
    *   **Kinetic Sounds**：音视频双模态，用于动作识别。
    *   **UCF-101**：RGB和光流双模态，用于动作识别。
    *   **CMU-MOSEI**：音频、视频、文本三模态，用于情感分析。
    *   **NVGesture**：RGB、深度、光流三模态，用于手势识别。

*   **基准方法**：与多种方法进行了比较，包括：
    *   **传统融合方法**：特征拼接（Concat）、预测求和（Sum）、预测加权（Weight）。
    *   **专门的模态平衡方法**：MMCosine， AGM， OGM， GBlending， PMR， MMCooperation， Relearning， MLA， MMPareto等。

*   **评估指标**：使用了准确率（ACC）和F1分数。

### 4. 资源与算力

*   **硬件资源**：文中明确提到所有实验在 **2 块 NVIDIA DGX A100** GPU上进行。
*   **训练时长**：论文未明确提及训练的总时长或单个Epoch的耗时。
*   **其他细节**：使用了SGD优化器，动量为0.9，学习率为1e-3。模型架构根据不同数据集采用了ResNet-18或Transformer等。

### 5. 实验数量与充分性

*   **实验数量**：
    *   **主实验**：在5个不同规模、不同模态数的数据集上进行了全面的对比实验（Table 1）。
    *   **鲁棒性分析**：通过在CREMA-D数据集的音频模态中注入高斯白噪声，模拟“信息稀缺模态”的极端场景，对比分析了各种方法的性能（Figure 2, Figure 5）。
    *   **消融实验**：在2个数据集上验证了所提出的两个核心模块（CQM和RE）的有效性（Table 2）。
    *   **可视化分析**：
        *   **模态差距分析**：通过t-SNE可视化，比较了CMoB与其他强基线方法在CREMA-D数据集上导致的模态差距（Figure 3）。
        *   **特征关注区域分析**：使用Grad-CAM可视化了模型在训练不同阶段关注的关键区域，对比了CMoB与基线方法（Figure 4）。
    *   **补充实验**：在更大的VGGSound数据集和具有5个模态的Caltech101-20数据集上进行了额外验证（Table 3, Table 4）。

*   **充分性与公平性**：
    *   **充分性**：实验设计层次清晰，覆盖了多个数据集、模态数（2和3）、对抗性场景、内部模块验证和可解释性分析，证据链较为完整。
    *   **公平性**：主实验遵循了该领域研究（如OGM-GE, PMR）的通用设置和基线方法，并报告了标准差（`±`），确保了对比的公平性和结果的可信度。

### 6. 主要结论与发现

*   **有效性**：提出的CMoB方法在所有5个基准数据集上均取得了当前最优（SOTA）或极具竞争力的性能，证明了其在平衡多模态学习方面的有效性。
*   **泛化能力**：CMoB能够处理超过两个模态的数据集（如CMU-MOSEI和NVGesture），表现出比仅适用于双模态的方法（如OGM, PMR）更强的泛化能力。
*   **鲁棒性**：在模态信息极度稀缺的极端场景下，CMoB仍能保持相对最好的性能，提升了模型对弱模态的判别能力。
*   **机制验证**：消融实验证实了CQM和RE模块的必要性。可视化分析表明，CMoB增大了模态差距，并使模型能更稳定地关注与任务最相关的特征区域，从而学到更具判别性的表征。

### 7. 优点
*   **视角新颖**：从样本级别的因果效应出发，而非传统的模态级别梯度或损失，为解决模态不平衡问题提供了更精细和可解释的视角。
*   **双模块设计**：CQM模块负责精细化估值，RE模块负责定向增强，二者协同工作，逻辑清晰。
*   **防止过拟合**：在增强弱势模态时采用掩码策略，而非简单的过采样，能有效避免过拟合，是一种巧妙的设计。
*   **广泛的实验验证**：实验覆盖了多种模态组合、不同规模的数据集、极端场景，并通过消融和可视化对方法的内在机理进行了深入剖析，论证充分扎实。

### 8. 不足与局限

*   **计算开销**：方法需要在每个样本上计算个体因果效应，这可能引入额外的计算开销。论文未讨论该方法的计算效率或与基线方法的训练时间对比。
*   **利益函数的敏感性**：利益函数依赖于模型的预测正确率和置信度排序，在训练初期模型尚不稳定时，其估值可能不准，如何平滑其影响文中未深入探讨。
*   **超参数敏感性**：动态优化策略中引入了如α（掩码强度）和阶段划分（E/2）等超参数，论文未系统讨论这些超参数的敏感性。
*   **对特定噪声的依赖**：虽然在CREMA-D的音频中加入高斯噪声验证了鲁棒性，但现实中的模态信息缺失形式（如数据损坏、信息冲突）更复杂，方法是否普遍适用尚待验证。
*   **应用范围**：该方法应用于分类和预测任务，其在需要细粒度跨模态对齐的任务（如视觉问答、图文检索）上的适用性未知。

（完）
