---
title: Improving Task-Specific Multimodal Sentiment Analysis with General MLLMs via Prompting
title_zh: 通过提示利用通用多模态大语言模型改进任务特定多模态情感分析
authors: "Haoyu Zhang, Yinan Zhang, Chaolong Ying, Xiaoying Tang, Tianshu Yu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PBy1Ew1ihV"
tags: ["query:affective-ai"]
score: 10.0
evidence: 提出MLLM引导的多模态情感学习框架，改进任务特定MSA模型。
tldr: 多模态情感分析（MSA）利用多模态大语言模型（MLLM）成本高昂且提升有限。本文提出MMSLF，一种教师-学生框架，通过提示引导MLLM知识蒸馏到任务特定MSA模型，避免直接使用MLLM推理。实验表明该方法能高效利用MLLM知识提升MSA性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pby1ew1ihv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 555, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pby1ew1ihv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1243, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pby1ew1ihv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1169, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pby1ew1ihv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 883, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pby1ew1ihv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1254, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pby1ew1ihv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1265, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pby1ew1ihv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 805, \"height\": 210, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 587, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 620, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1453, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1453, \"height\": 705, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1456, \"height\": 714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1456, \"height\": 680, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1459, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1450, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1427, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1453, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1456, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1454, \"height\": 551, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1452, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1453, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pby1ew1ihv/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1458, \"height\": 1121, \"label\": \"Table\"}]"
motivation: 直接应用MLLM到MSA成本高且提升有限。
method: 提出MMSLF教师-学生框架，利用MLLM提示引导MSA模型。
result: 在多个MSA数据集上提升任务特定模型性能。
conclusion: MMSLF高效利用MLLM知识增强MSA。
---

## Abstract
Multimodal Sentiment Analysis (MSA) aims to predict sentiment from diverse data types, such as video, audio, and language. Recent progress in Multimodal Large Language Models (MLLMs) have demonstrated impressive performance across various tasks. However, in MSA, the increase in computational costs does not always correspond to a significant improvement in performance, raising concerns about the cost-effectiveness of applying MLLMs to MSA. This paper introduces the MLLM-Guided Multimodal Sentiment Learning Framework (MMSLF). It improves the performance of task-specific MSA models by leveraging the generalized knowledge of MLLMs through a teacher-student framework, rather than directly using MLLMs for sentiment prediction. First, the proposed teacher built upon a powerful MLLM (e.g., GPT-4o-mini), guides the student model to align multimodal representations through MLLM-generated context-aware prompts. Then, knowledge distillation enables the student to mimic the teacher’s predictions, thus allowing it to predict sentiment independently without relying on the context-aware prompts. Extensive experiments on the SIMS, MOSI, and MOSEI datasets demonstrate that our framework enables task-specific models to achieve state-of-the-art performance across most metrics. This also provides new insights into the application of general MLLMs for improving MSA.

---

## 论文详细总结（自动生成）

# 论文总结：通过提示利用通用多模态大语言模型改进任务特定多模态情感分析

## 1. 研究动机与背景
- **核心问题**：多模态情感分析（MSA）需融合视频、音频、文本等多种信息预测情感。近年来多模态大语言模型（MLLMs）在各类任务中表现突出，但直接用于 MSA 面临成本高、性能提升有限的问题——其参数量（数十亿级）与任务特定模型（几百万至几千万参数）相比，计算开销巨大，但对 MSA 性能的增益并不总是显著，存在成本效益瓶颈。
- **研究整体含义**：探索如何利用通用 MLLMs 的广义知识来辅助训练任务特定的小型 MSA 模型，而非直接依赖 MLLMs 进行推理，以在保持低计算成本的同时提升情感分析效果。

## 2. 方法论：MLLM-Guided Multimodal Sentiment Learning Framework (MMSLF)
- **核心思想**：采用**教师-学生框架**，教师网络内嵌 MLLM（如 GPT-4o-mini）生成上下文感知提示，为学生模型提供增强监督，知识蒸馏后学生可独立推理。
- **关键技术细节**：
  - **输入与嵌入**：多模态序列 \(X^m\)（语言 L、视频 V、音频 A）经线性嵌入层映射到统一维度 \(d\)，得到 \(S^m\)。
  - **提示嵌入**：MLLM 生成的提示 \(X^P\) 通过预训练 BERT 和额外 Transformer 编码器提取特征 \(S^P\)，维度与 \(S^L\) 一致。
  - **条件注意力（Conditional Attention）**：教师模型中，将 \(S^\alpha\) 作为 Query，\(S^\beta\) 作为 Key/Value 计算原始注意力图 \(W^{\alpha,\beta}\)，同时利用提示特征 \(S^P\) 计算偏移注意力图 \(\Delta\)（以 \(S^P\) 为 Query）。融合后得到条件注意力权重 \(W_{\text{con}} = \text{softmax}(W^{\alpha,\beta} \cdot \Delta)\)，再经多头注意力和前馈网络得到对齐特征 \(H^{\text{Teacher}}_{\beta\to\alpha}\)。学生对齐模块不使用提示，直接学习模态间关系。
  - **融合与预测**：将对齐后的语言、视频、音频特征同学习到的回归标记一起输入 Transformer 编码器，通过回归标记得到预测情感分数 \(\hat{y}\)。
  - **学习目标**：
    - **教师阶段**：仅用回归损失 \(L_{\text{regr}}^{\text{Teacher}}\)（MAE）。
    - **学生阶段（教师参数冻结）**：
      - 注意力迁移损失：\(L_{\text{attn}}^{\text{Student}} = \frac{1}{N}\sum |W_i - W_i^{\text{con}} |\)
      - 融合表示匹配损失：\(L_{\text{fusion}}^{\text{Student}} = \frac{1}{N}\sum |H'^{\text{fusion}}_i - H_i^{\text{fusion}}|\)
      - 回归损失：\(L_{\text{regr}}^{\text{Student}}\)（与教师公式相同）
      - 总损失：\(L_{\text{overall}}^{\text{Student}} = L_{\text{regr}}^{\text{Student}} + \alpha L_{\text{attn}}^{\text{Student}} + \beta L_{\text{fusion}}^{\text{Student}}\)，\(\alpha, \beta\) 为超参数。

## 3. 实验设计
- **数据集**：
  - **SIMS**：中文情感数据集（1368训练/456验证/457测试），标签区间 [-1,1]。
  - **MOSI**：英文情感数据集（1284/229/686），标签区间 [-3,3]。
  - **MOSEI**：英文大规模情感数据集（16326/1871/4659），标签区间 [-3,3]。
- **评估基准**：MAE（平均绝对误差）、相关性（Corr）、Acc-2（正/负分类准确率）、F1 分数；MOSI 和 MOSEI 同时报告“负/非负”和“负/正”两种分类指标。
- **对比方法**：
  - 任务特定模型：TFN、LMF、MuLT、MISA、Self-MM、TETFN、ALMT、DLF、DeepMLF 等。
  - 大语言/多模态模型：Video-LLaMA2、GPT-4V、GPT-4o-mini、Gemini-2.0-Flash（分别采用分类/回归提示评估相应指标）。

## 4. 资源与算力
- 实现平台：PyTorch 2.1.1、CUDA 12.1。
- 计算设备：AMD EPYC 7513 CPU，**NVIDIA Tesla A40 GPU**（单卡）。
- 训练时长：教师推理需额外调用 MLLM API（如 GPT-4o-mini 或 Gemini-2.0-Flash）生成提示，占主要时间，但实验未完整报告总 GPU 训练小时或 API 调用成本；单次推理时间学-生模型约为 6.39 秒（SIMS 数据集）。
- 论文未详细说明总 GPU 算力消耗或 API 调用次数，但提供了模型参数量和 FLOPs 对比。

## 5. 实验数量与充分性
- **主要实验**：在 3 个数据集上全面对比十余种 SOTA 方法，每个实验均运行 5 个随机种子并报告均值±标准差。
- **消融实验**：
  - 移除教师模型中的 MLLM 提示（w/o prompt）。
  - 移除学生模型的教师指导（w/o guid. of teacher）。
  - 学生模型中分别移除注意力迁移损失和融合匹配损失。
- **额外实验**：
  - 不同 MLLM（GPT-4o-mini vs. Gemini-2.0-Flash）生成的提示效果对比。
  - 提示中语言/视觉/音频线索的分类准确性分析。
  - 提示采样策略影响（固定 vs. 随机抽样）。
  - 提示模板敏感性测试（不同 prompt 变体）。
  - 学生模型参数规模变化（0.49M~4.05M）。
  - 损失权重（\(\alpha, \beta\)）超参数搜索。
  - 特征提取器影响（替换为 RoBERTa、Data2Vec）。
  - 泛化性测试（将教师-学生框架应用于 ALMT）。
  - 效率-性能权衡分析（参数量、GFLOPs、推理时间）。
- **充分性与公平性**：实验设计完整，对比基线包含同期最新工作，指标多样，显著性检验（p 值）有所提供，整体较为客观公平。

## 6. 主要结论与发现
- **知识蒸馏有效性**：教师模型可以在 MLLM 提示下显著提升性能，即使学生模型在推理时不借助提示，仍能接近或超越教师，并在大多数指标上达到当时领先水平。
- **成本效益**：学生模型参数量小（0.82M），推理快，较 MLLM 直接推理成本大幅降低，证明通过知识蒸馏利用 MLLM 知识是高效路径。
- **提示质量重要性**：GPT-4o-mini 虽不支持音频分析，但其语言和视觉提示质量优于支持音频的 Gemini-2.0-Flash，导致更高的蒸馏效果；提示准确性直接影响教师和学生性能。
- **模型架构鲁棒性**：方法可泛化到其他任务特定模型（如 ALMT）上，但需注意原模型设计对蒸馏框架的适配性。
- **局限性**：传统特征提取器限制了性能上限；教师模型在小数据集上过拟合严重；学生训练过程受随机种子影响较大，训练不稳定。

## 7. 优点
- **创新性强**：首次提出利用 MLLM 提示作为教师引导条件注意力，将通用知识蒸馏到小型 MSA 模型，为非推理方式运用大模型提供了新范式。
- **设计简洁高效**：条件注意力机制直观，教师-学生结构清晰，无需学生依赖外部大模型，实际部署轻量。
- **实验扎实全面**：多数据集、多指标、丰富消融及鲁棒性分析，结果可信。
- **成本分析详细**：提供参数量、FLOPs、推理时间对比，突出实际应用价值。

## 8.不足与局限
- **特征提取器陈旧**：仍使用 OpenFace、Librosa 等经典工具，可能限制模型性能进一步提升。
- **过拟合风险**：教师模型在小规模数据集（如 MOSI、SIMS）上容易严重过拟合，可能影响蒸馏质量。
- **训练稳定性**：学生模型表现随随机种子变化较大，尤其在注意力对齐过程中收敛波动明显。
- **MLLM 依赖与开销**：教师训练仍需调用商业 MLLM API，虽只有一次，但生成成本和处理时间在实际应用中可能仍是障碍。
- **跨语言泛化性**：主要在中英文数据集上验证，对其他语言和文化背景的普适性未经测试。
- **多模态限制**：GPT-4o-mini 不支持音频分析，仅依赖视觉和语言提示，音频模态信息未被充分利用。

（完）
