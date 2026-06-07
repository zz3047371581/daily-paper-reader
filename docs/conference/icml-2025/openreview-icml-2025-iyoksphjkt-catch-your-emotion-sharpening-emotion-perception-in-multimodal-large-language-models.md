---
title: "Catch Your Emotion: Sharpening Emotion Perception in Multimodal Large Language Models"
title_zh: 抓住你的情绪：增强多模态大语言模型的情感感知
authors: "Yiyang Fang, Jian Liang, Wenke Huang, He Li, Kehua Su, Mang Ye"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=IYOksPHJKT"
tags: ["query:affective-ai"]
score: 10.0
evidence: 提升多模态大语言模型的情感感知，情感LLM的核心主题
tldr: 针对多模态大语言模型在情感推理中难以区分相似情感和受冗余视觉信息干扰的问题，提出在推理阶段增强情感捕捉的方法，无需微调即可提升情感识别准确率。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-iyoksphjkt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 822, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iyoksphjkt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1589, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iyoksphjkt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 828, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iyoksphjkt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1758, \"height\": 1117, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iyoksphjkt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 733, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iyoksphjkt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1767, \"height\": 640, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-iyoksphjkt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1652, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iyoksphjkt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iyoksphjkt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 843, \"height\": 254, \"label\": \"Table\"}]"
motivation: MLLMs在情感推理中容易混淆相似情绪，且被无关视觉信息分散注意力。
method: 提出推理阶段的情感增强策略，区分相似情感并过滤冗余视觉线索。
result: 方法有效提升了多模态大语言模型的情感理解能力。
conclusion: 为构建情感智能的LLM提供了高效的可扩展方案。
---

## Abstract
Multimodal large language models (MLLMs) have achieved impressive progress in tasks such as visual question answering and visual understanding, but they still face significant challenges in emotional reasoning. Current methods to enhance emotional understanding typically rely on fine-tuning or manual annotations, which are resource-intensive and limit scalability. In this work, we focus on improving the ability of MLLMs to capture emotions during the inference phase. Specifically, MLLMs encounter two main issues: they struggle to distinguish between semantically similar emotions, leading to misclassification, and they are overwhelmed by redundant or irrelevant visual information, which distracts from key emotional cues. To address these, we propose Sharpening Emotion Perception in MLLMs (SEPM), which incorporates a Confidence-Guided Coarse-to-Fine Inference framework to refine emotion classification by guiding the model through simpler tasks. Additionally, SEPM employs Focus-on-Emotion Visual Augmentation to reduce visual redundancy by directing the attention of models to relevant emotional cues in images. Experimental results demonstrate that SEPM significantly improves MLLM performance on emotion-related tasks, providing a resource-efficient and scalable solution for emotion recognition.

---

## 论文详细总结（自动生成）

# 论文总结：Catch Your Emotion: Sharpening Emotion Perception in Multimodal Large Language Models

## 1. 核心问题与研究动机
- 多模态大语言模型（MLLMs）在视觉问答、视觉理解等任务上表现优异，但在**情感推理**上仍存在明显短板，难以准确捕捉和解读复杂情感。
- 现有提升情感理解能力的方法主要依赖**微调**或**人工标注**，资源消耗大、扩展性受限。
- 本工作关注**推理阶段**的优化，旨在无需额外训练或标注的条件下增强 MLLMs 的情感识别能力。
- 推理阶段面临两大关键挑战：
  - **语义相似情感易混淆**：模型难以区分如 “amusement（愉悦）” 与 “excitement（兴奋）” 等近似情绪。
  - **视觉信息冗余**：图像中大量与情感无关的区域会分散模型注意力，干扰关键情感线索的提取。

## 2. 方法论：SEPM
提出 **Sharpening Emotion Perception in MLLMs (SEPM)**，无需训练，由两个主要组件构成：

### 2.1 Confidence-Guided Coarse-to-Fine Inference (CCI)
- **粗粒度阶段**：将全部情感类别预分为正面（PEC）与负面（NEC），让模型先回答“A. Positive  B. Negative”，简化任务，获得粗分类结果 \(\hat{E}\)。
- **置信度评估**：利用粗粒度阶段输出的 logits 计算选项概率分布，通过方差公式 \(C = [(p_A - \mu)^2 + (p_B - \mu)^2]/2\) 评估置信度。若置信度低于阈值 \(\alpha\)，则认为粗分类不可靠，细粒度阶段保留所有类别并加入模糊性描述以增强提示；否则只保留对应正/负面情感类别选项。
- **细粒度阶段**：根据粗分类结果与置信度调整后的细粒度查询 \(Q_f\)，进行最终情绪类别预测 \(E\)。

### 2.2 Focus-on-Emotion Visual Augmentation
- **Focus-on-Emotion Prompt (FoE)**：在文本询问中加入 “Please focus on emotion.” 显式引导模型关注情感信息。
- **视觉 token 重要性估计**：利用第一阶段的注意力图 \(A\)，提取 FoE 文本 token 与视觉 token 之间的关联矩阵 \(P\)，计算每个视觉 token 的平均注意力分数 \(\bar{P}[j]\) 作为重要性指标。
- **视觉 token 增强 (VTA)**：根据重要性指标，按设定丢弃比例 \(\beta\) 剔除冗余视觉 token（最低得分者），保留关键情感相关 token，形成新的视觉 token 集 \(V'\)，输入第二阶段推理。

整体流程（算法1）为：
1. 粗粒度推理 → 2. 置信度评估 → 3. 构建细粒度查询 → 4. 基于 FoE 注意力图估计视觉 token 重要性 → 5. 丢弃低相关视觉 token → 6. 细粒度推理输出最终情感类别。

## 3. 实验设计
### 3.1 数据集
- **Emotion6**（6类）、**EmoSet**（8类）、**WebEmo**（7类和25类）、**Abstract**（8类），覆盖不同场景和类别数。

### 3.2 基准方法
- **Zero-shot**（直接分类）
- **Zero-shot-CoT**（加入“Let's think step by step”的链式思考提示）
- **SparseVLM**（基于任务相关性的视觉 token 稀疏化方法）

### 3.3 模型架构
- LLaVA-7b 和 VILA-8b，均使用预训练检查点，无额外微调。

### 3.4 评估指标
- 答案准确率（ACC）。

### 3.5 对比的丢弃策略
- 随机丢弃、基于查询整体相关性丢弃、基于 FoE 情感相关性丢弃（本方法）。

## 4. 资源与算力
- 所有实验使用 **8 块 NVIDIA 4090 GPU**（每块 24GB 显存）。文中未提及训练，方法无需训练，**仅执行推理**，故无训练时间汇报。

## 5. 实验数量与充分性
- 在 4 个数据集、2 种模型架构上进行了对比实验（表1）。
- 进行了不同丢弃策略的对比（表2）。
- 完成**消融实验**（表3），测试 CCI、FP、VTA 各组件贡献。
- 进行了**超参数敏感性分析**（\(\alpha\) 和 \(\beta\)，图3）。
- 包含视觉 token 丢弃可视化（图4）、置信度估计合理性验证（图5）、各情绪类别精度可视化（图6）。
- 实验设计较为全面，包含与多个 baseline 的公平对比、组件消融和参数分析，客观性和充分性较好。

## 6. 主要结论与发现
- SEPM 在多个情感数据集上**显著优于**所有对比的零样本和训练无关方法，提升可达 17.19 个百分点（WebEmo 7类）。
- 情感任务相比一般任务存在更多冗余视觉信息，选择性丢弃冗余 token 有助于突出关键情感线索（RQ1）。
- 基于情感相关性选择丢弃 visual token 比随机丢弃或基于整体查询丢弃更有效（RQ2）。
- 利用 logits 概率方差作为置信度指标是可靠的，能有效过滤粗粒度阶段不可靠推理（RQ3）。
- 不同文本提示会引起 MLLMs 对不同情感类别的偏好差异（RQ4）。

## 7. 优点
- **训练无关**：无需微调或额外标注，大幅降低资源消耗，扩展性强。
- **新颖的两阶段推理**：由粗到细结合置信度引导，有效缓解语义相似情感混淆。
- **专注情感的视觉增强**：通过 FoE prompt 与注意力机制精准剔除冗余视觉 token，提升情感信号提取效率。
- **实验全面且定量详尽**，多数据集、多模型、多基线、消融与可视化分析，验证方法有效性与合理性。

## 8. 不足与局限
- 当前方法主要针对**图像情感分类**，未涉及其他情感模态（如语音、文本），应用场景相对单一。
- 丢弃视觉 token 的比例需手工设定，通用性受数据集和任务影响，未必能自适应最优。
- 模型对文本提示存在偏好，**类别间的精度提升不均衡**，可能在某些类别上产生负面效果。
- 未探讨模型**认知偏差**可能带来的公平性问题，也未评估对复杂多模态场景（如视频、对话）的适用性。
- 实验中未报告统计显著性检验，性能差异的可靠性有待进一步验证。

（完）
