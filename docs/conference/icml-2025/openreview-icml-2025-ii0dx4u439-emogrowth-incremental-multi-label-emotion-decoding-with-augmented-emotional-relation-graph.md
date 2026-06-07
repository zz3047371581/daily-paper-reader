---
title: "EmoGrowth: Incremental Multi-label Emotion Decoding with Augmented Emotional Relation Graph"
title_zh: EmoGrowth：基于增强情感关系图的增量式多标签情绪解码
authors: "Kaicheng Fu, Changde Du, Jie Peng, Kunpeng Wang, Shuangchen Zhao, Xiaoyu Chen, Huiguang He"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Ii0DX4U439"
tags: ["query:affective-ai"]
score: 9.0
evidence: 引入基于增强情感关系图的多标签细粒度增量情绪解码
tldr: 针对情绪识别中新类别持续出现且多情绪共存的挑战，提出EmoGrowth模型和增强情感语义学习框架，通过增强情感关系图生成可靠软标签，结合情感维度知识蒸馏，实现多标签细粒度增量情绪解码，有效应对过去与未来部分标签缺失问题，为开放世界情感计算提供高效解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ii0dx4u439/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 824, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ii0dx4u439/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1551, \"height\": 851, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ii0dx4u439/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 866, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ii0dx4u439/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1566, \"height\": 1162, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ii0dx4u439/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1248, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ii0dx4u439/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 835, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ii0dx4u439/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 761, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ii0dx4u439/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1550, \"height\": 1513, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1765, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 126, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1707, \"height\": 1417, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1498, \"height\": 2310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1766, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ii0dx4u439/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1763, \"height\": 517, \"label\": \"Table\"}]"
motivation: 现实应用中新情绪不断出现且多情绪共存，现有系统难以增量学习并识别多并发情绪。
method: 提出增强情感语义学习框架，包含增强情感关系图生成软标签和情感维度知识蒸馏。
result: 模型能够增量学习新情绪类别，同时保持对多个并发情绪的识别能力。
conclusion: 该方法为开放世界中细粒度多标签情绪识别提供了有效途径，提升了情感计算系统的适应性。
---

## Abstract
Emotion recognition systems face significant challenges in real-world applications, where novel emotion categories continually emerge and multiple emotions often co-occur. This paper introduces multi-label fine-grained class incremental emotion decoding, which aims to develop models capable of incrementally learning new emotion categories while maintaining the ability to recognize multiple concurrent emotions. We propose an Augmented Emotional Semantics Learning (AESL) framework to address two critical challenges: past- and future-missing partial label problems. AESL incorporates an augmented Emotional Relation Graph (ERG) for reliable soft label generation and affective dimension-based knowledge distillation for future-aware feature learning. We evaluate our approach on three datasets spanning brain activity and multimedia domains, demonstrating its effectiveness in decoding up to 28 fine-grained emotion categories. Results show that AESL significantly outperforms existing methods while effectively mitigating catastrophic forgetting. Our code is available at https://github.com/ChangdeDu/EmoGrowth.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义
- 现实情绪识别面临两大挑战：新型情绪类别不断出现，且同一刺激常同时引发多种情绪（多标签）。
- 当前研究多数局限于单标签类增量学习，难以处理 **多标签细粒度类增量情绪解码** 这一新范式。
- 核心难点在于**过去缺失的部分标签**（训练新任务时旧情绪类别无法获得真实标签）与**未来缺失的部分标签**（训练旧任务时新情绪类别标签未知），导致灾难性遗忘加剧。
- 本文提出 **增强情感语义学习框架 (AESL)**，在不存储历史样本的前提下，增量学习新情绪类别并持续识别多标签情绪。

### 方法论
AESL 由四个紧密耦合的模块构成，对应两类部分标签问题的解决：

1. **增强情感关系图（AEG-D）—— 应对过去标签缺失**
   - 在每个增量任务中，构建并扩充情感关系图 \(G_b = (V_b, E_b)\)，其邻接矩阵 \(A_b\) 需整合新旧类别的共现关系。
   - 当新任务到来时，先用旧模型对新数据生成软标签 \(S\)，然后通过**基于图的标签消歧 (GLD)**：利用样本间的高斯核相似性矩阵 \(P\) 进行标签传播，得到精炼的软标签矩阵 \(\hat{S} = F^*\)。
   - 基于 \(\hat{S}\) 和新任务真实标签，利用贝叶斯规则计算新旧类别间的转移概率，从而构建完整的增广邻接矩阵 \(A_b\)。

2. **情感语义学习与语义引导特征解耦**
   - 使用 **图同构网络 (GIN)** 作为编码器，从增广关系图中学习情感标签的嵌入 \(E_b\)。
   - 解码器采用成对重建损失 \(\mathcal{L}_{le}\) 维持图拓扑结构。
   - **语义引导特征解耦**：对每个样本的深层特征 \(z\)，为每个情感标签计算重要性向量 \(\alpha_k\)，通过哈达玛积获得语义特定的特征 \(\mathbf{o}_k\)，最终由对应分类器预测各标签出现的置信度。

3. **基于情感维度的关系知识蒸馏 —— 应对未来标签缺失**
   - 利用情感维度空间（如 Valence-Arousal）作为补充域知识，建立“教师-学生”蒸馏框架。
   - 计算模型特征 \(z\) 的表示相似矩阵 (RSM) \(M^b\)、旧模型 RSM \(M^{b-1}\) 以及情感维度特征 \(\tau\) 的 RSM \(M^{aff}\)。
   - 蒸馏损失 \(\mathcal{L}_{kd}\) 由新旧模型间的相似性保持损失 \(\mathcal{L}_{kd}^{model}\) 和模型与情感维度的对齐损失 \(\mathcal{L}_{kd}^{aff}\) 组合而成，使用 arctanh 重参数化以稳定训练。

4. **最终目标函数**
   \[
   \mathcal{L} = \mathcal{L}_{ce} + \lambda_1 \mathcal{L}_{kd}^{model} + \lambda_2 \mathcal{L}_{kd}^{aff} + \lambda_3 \mathcal{L}_{le}
   \]
   其中 \(\mathcal{L}_{ce}\) 为二值交叉熵，训练时使用的混合标签 \(\tilde{y} = [\hat{s}^T, y^T]^T\) 同时覆盖旧类软标签和新类真实标签。

### 实验设计
- **数据集**
  - **Brain27**：fMRI 脑活动数据，5 名被试者观看 2196 个视频，提取 2880 维 ROI 池化特征，27 类情绪，14 个情感维度。
  - **Video27**：与 Brain27 对应的视频数据集，VGG19 提取 1000 维特征，27 类情绪。
  - **Audio28**：1841 段音乐，ResNet-18 提取 MFCC 后的 512 维特征，28 类情绪，11 个情感维度。
- **增量协议**：对于 Brain27 和 Video27 使用 B0‑I9、B0‑I3、B15‑I3、B15‑I2；对于 Audio28 使用 B0‑I7、B0‑I4、B16‑I3、B16‑I2（B 表示基础类数，I 表示每阶段新增类数）。
- **对比方法**：Finetune、EWC、LwF、ER、RS 等单标签类增量方法，以及 AGCN、PRS、OCDM、KRT‑R 等多标签类增量方法，同时设置 Upper‑bound（全量数据联合训练）作为性能上界。
- **评价指标**：mAP、maF1、miF1，并汇报各任务最终准确率 (Last Acc) 和所有任务平均准确率 (Avg. Acc)。

### 资源与算力
- 论文明确说明所有实验均在**一块 NVIDIA TITAN GPU** 上完成。
- 其他训练细节（如总训练时长或 GPU 内存占用）未详细披露，但给出了优化器设置（Adam，β₁=0.9, β₂=0.9999，权重衰减 0.005 或 0，学习率 10⁻⁴ 或 10⁻³ 等）。

### 实验数量与充分性
- **主实验**：3 个数据集 × 4 种增量协议 = 12 组主要对比实验，每组比较 10 种方法（含 Upper‑bound），报告 Avg. Acc 和 Last Acc 三种指标。
- **统计检验**：采用 Friedman 检验和 Nemenyi 事后检验（基于 7 个数据集/被试的平均最终 mAP），严格评估方法间相对排序的显著性。
- **消融实验**：在 Audio28 的 B0‑I7 协议下设置 8 组消融模型，分别去除或替换 ESL、LD、RKD 等关键组件，验证每个模块的贡献。
- **可视化分析**：对情感嵌入进行 t‑SNE 可视化，展示增广情感关系图与 Oracle 关系图的对比及皮尔逊相关系数。
- **超参数敏感性**：分析 λ₂（情感维度蒸馏权重）与 λ₃（图重构损失权重）对性能的影响。
- 实验设计全面、对比公平，兼顾定量、统计与定性分析，具有较高充分性。

### 主要结论与发现
- AESL 在三个不同模态的数据集上均显著优于现有类增量方法（包括 SLCIL 和 MLCIL），有效缓解了灾难性遗忘。
- 情感关系图的增广与标签消歧对于处理过去缺失标签至关重要；而基于情感维度的关系知识蒸馏则成功应对未来缺失标签问题。
- 语义引导特征解耦与图自动编码器学习到的情感嵌入保留了有意义的语义拓扑（如积极/消极情绪的可视化聚类）。
- 重播式（rehearsal‑based）方法在 MLCIL 中表现不佳，因其保存的多为当前任务标签，加剧了部分标签问题。

### 优点
- **创新性强**：首次提出多标签细粒度类增量情绪解码任务，并构建一套完整、理论上自洽的解决方案。
- **方法设计缜密**：AESL 同时解决两类部分标签问题，且各模块（AEG‑D、情感语义学习、关系蒸馏）协同工作，互为补充。
- **实验扎实**：覆盖三种模态、多被试、多种增量协议，对比方法丰富，并辅以消融实验、统计检验和可视化。
- **无需存储历史样本**，避免了数据隐私和内存负担，更贴近实际开放世界场景。

### 不足与局限
- **应用范围受限**：仅考虑情绪类别的增量，未涉及跨被试/跨域（domain incremental）的持续学习场景。
- **任务顺序固定**：实验按照字母顺序固定类别出现顺序，未探讨不同类别顺序对增量学习的影响。
- **计算资源未详述**：虽提及 GPU 型号，但缺少单次训练时长、峰值显存等细节，复现的算力预算不够明确。
- **情感维度依赖**：需要预定义情感维度的标注，这可能在某些数据集中难以获得，限制了方法在无维度标注场景下的直接应用。
- **超参数敏感性**：λ₂ 和 λ₃ 对性能影响较大（特别是 λ₂ 过大或过小都会损害性能），实际部署时可能需要谨慎调整。

（完）
