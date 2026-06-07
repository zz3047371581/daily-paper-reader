---
title: A Multimodal BiMamba Network with Test-Time Adaptation for Emotion Recognition Based on Physiological Signals
title_zh: 基于多模态双向 Mamba 网络与测试时自适应的生理信号情绪识别
authors: "Ziyu Jia, Tingyu Du, Zhengyu Tian, Hongkai Li, Yong Zhang, Chenyu Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3vLp3J7540"
tags: ["query:affective-ai"]
score: 10.0
evidence: 利用测试时自适应的多模态生理信号情绪识别
tldr: 多模态生理信号情绪识别在心理健康和人机交互中具有重要作用，但如何有效建模信号内部长程依赖和跨模态关联，以及应对模态缺失，仍是难题。本文提出基于双向 Mamba 和测试时自适应的 BiM-TTA 框架：双向 Mamba 捕捉模态内与模态间的时序依赖，测试时自适应模块在推理时动态补齐缺失信息。实验表明，该方法在情绪识别准确性和鲁棒性上均优于现有方法，为生理信号情绪识别提供了新解法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 878, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1309, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1200, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1218, \"height\": 873, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1088, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 998, \"height\": 1026, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3vlp3j7540/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1020, \"height\": 256, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 865, \"height\": 589, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1397, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1398, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1074, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 457, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3vlp3j7540/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1366, \"height\": 226, \"label\": \"Table\"}]"
motivation: 多模态生理情绪识别中，模态内长程依赖和模态间相关性建模不足，且模态缺失导致性能下降。
method: 设计双向 Mamba 网络捕获多模态生理信号的时序依赖，并引入测试时自适应机制处理缺失模态。
result: 在 DEAP 和 MAHNOB-HCI 等数据集上，BiM-TTA 即使在模态缺失时也取得了领先的识别精度。
conclusion: 该工作为鲁棒的多模态情绪识别提供了新范式，测试时自适应策略可推广至其他多模态任务。
---

## Abstract
Emotion recognition based on physiological signals plays a vital role in psychological health and human–computer interaction, particularly with the substantial advances in multimodal emotion recognition techniques. However, two key challenges remain unresolved: 1) how to effectively model the intra-modal long-range dependencies and inter-modal correlations in multimodal physiological emotion signals, and 2) how to address the performance limitations resulting from missing multimodal data. In this paper, we propose a multimodal bidirectional Mamba (BiMamba) network with test-time adaptation (TTA) for emotion recognition named BiM-TTA. Specifically, BiM-TTA consists of a multimodal BiMamba network and a multimodal TTA. The former includes intra-modal and inter-modal BiMamba modules, which model long-range dependencies along the time dimension and capture cross-modal correlations along the channel dimension, respectively. The latter (TTA) mitigates the amplified distribution shifts caused by missing multimodal data through two-level entropy-based sample filtering and mutual information sharing across modalities. By addressing these challenges, BiM-TTA achieves state-of-the-art results on two multimodal emotion datasets.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景**：基于生理信号的多模态情绪识别在心理健康诊断、人机交互等领域具有重要应用价值。相比面部表情或语音，脑电（EEG）、眼电（EOG）、心电（ECG）等信号能更客观地反映真实情感状态。
- **核心挑战**：
  1. **模态内长程依赖与模态间相关性建模不足**：现有 CNN 擅长局部特征，Transformer 注意力缺乏显式的时间滤波能力，二者均难以在捕获情绪波动的关键节点基础上构建实用的长程依赖；同时，现有的跨模态融合多停留在成对交互，难以捕捉高阶关联。
  2. **多模态数据缺失导致性能急剧下降**：在真实采集场景中，出汗、姿势变化等原因常造成传感器接触不良，导致部分模态信号缺失，这会放大训练与测试之间的分布偏移，使预训练模型性能严重退化。
- **本文目标**：提出一种名为 **BiM‑TTA** 的框架，在训练阶段利用双向 Mamba（BiMamba）骨干网络同时建模模态内长程依赖和模态间相关性，在测试阶段通过测试时自适应（TTA）缓解数据缺失带来的分布偏移。

### 2. 方法论：核心思想、关键技术细节与算法流程

BiM‑TTA 由**多模态 BiMamba 网络**和**多模态 TTA** 两部分构成，整体结构见图1。

#### 2.1 多模态 BiMamba 网络

- **模态内 BiMamba 模块**
  - 每个模态先通过一个轻量初始编码器 `InitEncoder_i` 提取浅层特征 `h_i`。
  - 引入**门控机制** `g_i = σ(W_gi h_i + b_gi)`，用 SiLU 激活，自适应地增强情绪相关特征、抑制噪声。
  - 使用双向状态空间模型（SSM）分别沿时间维度进行前向和反向建模：
    - `h→_i = g_i ⊗ SSM→(σ(Conv1D→(W_hi h_i + b_hi)))`
    - `h←_i = g_i ⊗ SSM←(σ(Conv1D←(Rev_t(W_hi h_i + b_hi))))`
  - 通过线性投影与残差连接融合双向特征，得到模态内输出 `u_i`。

- **模态间 BiMamba 模块**
  - 将各模态的 `u_i` 沿通道维拼接，并交换时间维与通道维，得到统一的多模态特征矩阵 `m`。
  - 再次送入 BiMamba 结构，沿**通道维**进行前向/反向状态建模，使不同模态之间存在交互：前向过程中模态 1,…,i‑1 的隐藏状态辅助构建第 i 模态的特征表示，反向过程则利用模态 M,…,i+1 进行补充。

- **辅助任务**
  - 对每个模态的 `u_i` 额外连接一个分类器，输出单模态预测概率 `p(ŷ_i|x_i)`，计算交叉熵损失 `L_i`，与主任务损失 `L_task` 加权求和作为训练总损失：
    `L_train = L_task + Σ α_i L_i`，从而平衡各模态训练进度、防止过拟合。

#### 2.2 多模态测试时自适应（TTA）

针对多模态数据缺失造成的分布偏移，TTA 分两步进行：

- **两级熵样本过滤**
  - **多模态熵** `Ent(x)` 反映模型预测的确定性（低熵 → 分布接近源域，适合微调）。
  - **单模态熵** `Ent(x_i)` 体现样本对多模态信息的依赖程度（高单模态熵 → 多模态信息更丰富，更值得用于微调）。
  - 保留满足 **低多模态熵** 且 **高单模态熵** 的样本集合 `S(x)`。
  - 采用**渐进扩展策略**：初始阈值较严格，随着迭代次数逐步放宽，从弱分布偏移样本平滑过渡到强偏移样本。

- **跨模态互信息共享**
  - 利用多模态预测概率和互补概率（其他模态的平均预测）指导单模态预测：
    `p'(ŷ_i|x_i) = ( Σ_{j≠i} p(ŷ_j|x_j) ) / (M-1)`。
  - 通过最小化 KL 散度，将单模态预测 `p(ŷ_i|x_i)` 拉向 `(p'(ŷ_i|x_i) + p(ŷ|x)) / 2`，即同时参考互补多模态信息与最终多模态预测，从而对齐不同模态的信息。
  - 损失函数 `L_test` 由熵加权项与互信息项组合，仅更新少量参数（第一层卷积、第一层全连接层及所有 BN 层），其余参数冻结，计算开销极低。

算法1（附录A.3）给出了迭代过滤‑更新‑排除样本的完整流程。

### 3. 实验设计

- **数据集**：
  - **DEAP**：32 名被试，每名 40 个试次，记录 EEG（32 导）、EOG、EMG 等外周生理信号；唤醒度（arousal）和效价（valence）二分类（阈值 5）。
  - **MAHNOB‑HCI**：27 名被试（3 名数据缺失），每名 20 试次，记录 EEG（32 导）、ECG、GSR 等；同样进行二分类。
- **评估设置**：
  - 试次级 10 折交叉验证；将每个试次切割为 4 秒的非重叠段。
  - **无缺失数据**：使用全部模态。
  - **有缺失数据**：在测试集上随机掩蔽 0.2、0.4、0.6、0.8 比例的数据模拟不同缺失程度。
- **对比方法**：
  - **情绪识别模型**：SVM, EEGNet, ACRNN, HetEmotionNet, TSception, LGGNet, EEG‑Deformer, MambaFormer, SST, VSGT。
  - **TTA 方法**：No Adapt（无适应基线）、Tent、EATA、READ、2LTTA。

### 4. 资源与算力

- **硬件**：所有实验在 NVIDIA RTX A4000（16 GB）单卡 GPU 上完成。
- **训练时间**：单次训练（30 个 epoch）约需 60 分钟。
- **模型效率**：BiM‑TTA 仅含约 22.4k 参数，单次推理时间约 0.47 秒，FLOPs 1.18M，GPU 内存占用 2.29 MB，远低于 LGGNet（721k 参数）和 EEG‑Deformer（915k 参数），在保持高性能的同时实现了极低的计算开销。

### 5. 实验数量与充分性

- 共进行了 **两大组实验**（无缺失与有缺失），每组涵盖 10‑20 个基线。
- 在 DEAP 与 MAHNOB‑HCI 上分别报告了效价和唤醒度的准确率。
- 进行了丰富的**消融实验**：
  - 移除整个 BiMamba 骨干或整个 TTA 模块，观察性能变化；
  - 细粒度对比模态内 BiMamba 与 Mamba、Transformer、LSTM；
  - 模态间 BiMamba 与注意力融合、MLP 融合；
  - TTA 的两级过滤与单级过滤、互信息损失的增减。
- 提供了**可视化分析**：Grad‑CAM 展示模态内长程依赖与模态间相关性（如 EOG 运动伪影对 EEG 的干扰）；t‑SNE 显示 TTA 对分布偏移的缓解。
- 进行了**超参数研究**：α_i, λ, μ_i, 迭代数, β 等 5 个关键参数的影响，以及 TTA 迭代过程中的性能变化。
- 综上，实验设计严谨、覆盖全面，对比与消融充分，结果具有统计学可信度。

### 6. 主要结论与发现

- BiM‑TTA 在无缺失数据时，在两个数据集上均超越所有对比的情绪识别模型，准确率最高（DEAP 效价 0.673，唤醒度 0.641；MAHNOB‑HCI 效价 0.650，唤醒度 0.635）。
- 在有缺失数据时，BiM‑TTA 在所有缺失比例下带来的平均提升显著优于 Tent、EATA、READ、2LTTA 等 TTA 方法，尤其在 DEAP 唤醒度上平均提升 1.309%，展示出极强的鲁棒性。
- 模态内 BiMamba 有效捕捉了长程时序依赖，模态间 BiMamba 能捕获跨通道高阶关联；TTA 的两级熵过滤与互信息共享成功缓解了缺失放大带来的分布偏移，且参数高效。

### 7. 优点

- **架构创新**：首次将双向 Mamba 引入多模态生理信号情绪识别，同时解决模态内长程依赖和模态间高阶融合问题。
- **实用性强**：在推理阶段通过 TTA 无需重新训练即可适配缺失模态场景，且只微调极少数参数，延迟和内存消耗极低，适合部署。
- **性能领先**：在标准公开数据集上全面达到 SOTA，并在严重缺失条件下仍保持明显优势。
- **实验充分**：多层次消融、可视化、超参数分析、效率对比，论证扎实。
- **可复现性强**：论文提供了伪代码、详细超参数表以及匿名代码仓库。

### 8. 不足与局限

- **实时在线场景未评估**：虽然在单样本推理上效率很高，但尚未在真正的可穿戴设备或实时系统中测试延迟与功耗。
- **任务泛化性待验证**：仅在情绪识别任务上测试，对睡眠分期、运动想象等其他生理信号分析任务的适用性尚不明确（作者已计划扩展）。
- **缺失模拟与真实场景的差异**：缺失由随机掩蔽模拟，真实场景中的缺失通常是非随机、成段连续的，模型对这类缺失的鲁棒性有待进一步检验。
- **超参数灵敏度**：虽然多个超参数在较大范围内表现稳定，但个别参数（如迭代次数、β）仍需根据领域经验设定，可能在不同数据集上需要额外调参。
- **假设依赖性**：方法假设测试数据可以小批量迭代访问并更新模型参数，在完全单样本或严格无状态的环境中可能受限。

（完）
