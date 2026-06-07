---
title: Enhancing CLIP Robustness via Cross-Modality Alignment
title_zh: 通过跨模态对齐增强CLIP的鲁棒性
authors: "Xingyu Zhu, Beier Zhu, Shuo Wang, Kesen Zhao, Hanwang Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=t77EZLjvd5"
tags: ["query:affective-ai"]
score: 9.0
evidence: 提出基于最优传输的跨模态对齐方法，增强CLIP对抗鲁棒性。
tldr: CLIP因文本-图像特征错位而容易受到对抗攻击。本文提出COLA，一个基于最优传输的跨模态对齐框架，通过恢复全局和局部对齐来增强鲁棒性。实验表明COLA显著提升了CLIP的对抗鲁棒性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-t77ezljvd5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t77ezljvd5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t77ezljvd5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 346, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-t77ezljvd5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1478, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t77ezljvd5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t77ezljvd5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 580, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t77ezljvd5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1414, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t77ezljvd5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t77ezljvd5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t77ezljvd5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t77ezljvd5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 559, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t77ezljvd5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1381, \"height\": 204, \"label\": \"Table\"}]"
motivation: CLIP特征错位导致对抗鲁棒性不足。
method: 提出基于最优传输的跨模态对齐COLA框架。
result: 显著提高CLIP在对抗攻击下的分类鲁棒性。
conclusion: COLA通过显式对齐有效缓解对抗攻击风险。
---

## Abstract
Vision-language models (VLMs) such as CLIP demonstrate strong generalization in zero-shot classification but remain highly vulnerable to adversarial perturbations. Existing methods primarily focus on adversarial fine-tuning or prompt optimization, they often overlook the gaps in CLIP’s encoded features, which is shown as the text and image features lie far apart from each other. This misalignment is significantly amplified under adversarial perturbations, leading to severe degradation in classification performance. To address this problem, we propose **C**r**O**ss-moda**L**ity **A**lignment, dubbed **COLA**, an optimal transport-based framework that explicitly addresses adversarial misalignment by restoring both global image-text alignment and local structural consistency in the feature space. (1) COLA first projects adversarial image embeddings onto a subspace spanned by class text features, effectively filtering out non-semantic distortions while preserving discriminative information.  (2) It then models images and texts as discrete distributions over multiple augmented views and refines their alignment via OT, with the subspace projection seamlessly integrated into the cost computation. This design ensures stable cross-modal alignment even under adversarial conditions. COLA is training-free and compatible with existing fine-tuned models.

Extensive evaluations across 14 zero-shot classification benchmarks demonstrate the effectiveness of COLA, especially with an average improvement of 6.7% on ImageNet and its variants under PGD adversarial attacks, while maintaining high accuracy on clean samples.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的详细中文总结。

### 1. 论文的核心问题与整体含义

*   **研究问题**：以CLIP为代表的视觉-语言模型在零样本分类中表现出色，但对由细微、不可感知的对抗性扰动极其脆弱，导致分类准确率几乎崩溃。
*   **根本原因**：论文指出，核心问题在于CLIP内部的**跨模态特征错位**。模型通过全局匹配的方式进行训练，导致图像和文本的嵌入特征在向量空间中分布为两个分离的集群。对抗攻击会显著放大这种错位，不仅破坏全局对齐，还会扰乱图像特征内部的局部结构一致性。
*   **整体含义**：现有防御方法（如对抗训练、提示优化）往往忽视了这个根本性的对齐问题。因此，该论文旨在提出一个无需训练、即插即用的框架，通过显式地恢复并增强图像与文本特征之间的跨模态对齐，来提升CLIP的对抗鲁棒性，这对自动驾驶、医疗诊断等高风险应用至关重要。

### 2. 论文提出的方法论

论文提出了一个名为 **COLA** 的框架，其核心思想是通过一个统一的**最优传输**框架，在特征和语义两个层面解决对抗扰动带来的错位问题。

*   **全局特征对齐：子空间投影**
    *   **核心思想**：利用干净的文本特征构成的子空间，作为恢复被对抗扰动污染的图像特征的可靠代理。
    *   **技术细节**：
        1.  将所有类别的文本嵌入向量排列成矩阵 **Z**。
        2.  对 **Z** 进行奇异值分解（SVD），提取前 `C` 个主成分向量 **U_C**，形成一个文本诱导的子空间 **U**。
        3.  将每个被攻击后的图像特征 ˆx 投影到该子空间上：**Π(ˆx) = U_C U_C^⊤ ˆx**。
        4.  理论上证明，此投影可以有效过滤掉与语义无关的正交扰动噪声，从而恢复干净图像特征间的余弦相似度。

*   **局部结构对齐：分布级匹配**
    *   **核心思想**：不将图像或文本视为单一向量，而是通过数据增强，将它们建模为包含多个视图的离散概率分布，精细地对齐局部语义。
    *   **技术细节**：
        1.  **图像分布 P(x)**：对一张对抗图像进行 `N` 次数据增强（如随机裁剪、翻转），得到 `N` 个视图，并用其预测熵作为重要性权重 `a_n`。预测越确定（熵越低），权重越高。
        2.  **文本分布 Q_y(z)**：对一个类别名，使用大语言模型（LLM）生成 `M` 个细粒度描述，同样计算其重要性权重 `b_m`。
        3.  **最优传输距离**：通过求解一个最优传输问题，找到将图像分布P“搬运”到文本分布Q的最小成本（即Wasserstein距离）。运输成本矩阵 **C_Π** 的元素由 1减去投影后的图像特征与文本特征之间的余弦相似度`(1 - cos(Π(ˆx_n), z_{m}^{y}))` 来计算。
        4.  最终分类结果为运输成本最小的那个类别：`ŷ = argmin_{y} d_{OT}(P(x), Q_y(z); C_Π^y)`。
        5.  理论上证明，与使用原始被攻击特征的成本矩阵相比，该投影后的成本矩阵能使分类器获得更大的决策边界，从而具有更强的泛化能力。

### 3. 实验设计

*   **数据集与场景**：论文在**14个零样本分类基准**上进行了广泛评估，覆盖了多个领域：
    *   **通用/场景/纹理**：ImageNet、Caltech101、SUN397、DTD。
    *   **卫星图像**：EuroSAT。
    *   **细粒度分类**：Oxford Pets、Stanford Cars、Flowers、Food101、Aircraft。
    *   **分布偏移下的鲁棒性**：ImageNet的5个变体，包括ImageNet-V2、ImageNet-Sketch、ImageNet-A、ImageNet-R。
*   **对比方法（Benchmark）**：COLA与多类方法进行了比较。
    *   **测试时防御**：Anti-Adversary、Hedge Defense (HD)、Test-Time Transformation Ensembling (TTE)、Test-Time Counterattacks (TTC)。
    *   **基于微调的防御**：TeCoA、PMG、FARE（这些方法需要在TinyImageNet上对视觉编码器进行对抗性微调）。
*   **攻击设定**：主要使用 PGD 和 C&W 攻击，默认攻击预算 `ϵ_a = 1/255`，并测试了更大攻击预算（`ϵ_a = 4/255`）下的性能。还评估了对AutoAttack的鲁棒性。

### 4. 资源与算力

*   论文明确说明，所有实验均在**单张NVIDIA 3090 GPU**上进行。
*   在ImageNet数据集上，使用CLIP ViT-B/32模型和128的批处理大小时，COLA的评估时间为**28分钟**，相比之下，测试时防御方法TTC需要40分钟。这表明COLA在推理效率上有显著优势，因为它无需进行TTC所依赖的昂贵迭代优化。

### 5. 实验数量与充分性

实验设计非常充分、客观且公平。
*   **主要结果组数**：至少包含4组大型实验。
    1.  在14个数据集上，对比多种基线方法的干净与对抗鲁棒性（如表1、2）。
    2.  在多种对抗微调模型（TeCoA, PMG, FARE）上验证COLA的即插即用能力（如表3、4）。
    3.  在不同CLIP视觉骨干网络（ViT-B/16, ViT-L/14）上验证通用性（如表5）。
    4.  在更大对抗攻击预算下进行压力测试（如表6）。外加AutoAttack测试（如表9）。
*   **消融实验组数**：包含4组关键消融研究。
    1.  验证投影成本矩阵C_Π的有效性（如表7）。
    2.  研究图像和文本增强数量对性能的影响（如图2）。
    3.  研究投影矩阵主成分数量C的影响（如图3）。
    4.  可视化分析投影前后特征相似度分布的变化（如图4）。
*   **充分性与公平性**：实验覆盖了泛化、鲁棒性、效率、模型兼容性等多个维度。对比方法既有测试时防御，也有需要训练的强基线，部分比较通过在同一微调模型上添加不同后处理模块来确保公平。消融研究系统地验证了方法中每个核心组件的贡献。

### 6. 论文的主要结论与发现

*   COLA能**显著提升**CLIP模型在各种对抗攻击下的零样本分类鲁棒性，在PGD攻击下，ImageNet及其变体的平均准确率提升**6.7%**。
*   COLA在提升鲁棒性的同时，能**很好地保持甚至略微提升干净样本的准确率**。
*   COLA作为一个**即插即用**的模块，可直接应用于不同的CLIP变体和对抗微调模型，无需任何重新训练，展现了极强的通用性和实用性。
*   其效率优于需要迭代优化的测试时防御方法（如TTC）。

### 7. 优点

*   **训练无关**：方法完全在测试时运作，无需进行耗时的对抗训练或提示微调，极大降低了计算成本。
*   **问题洞察深刻**：准确地将对抗脆弱性归因于“跨模态错位”，并提供了两种互补的解决策略（全局恢复+局部精细匹配）。
*   **理论支撑坚实**：为子空间投影和最优传输的应用提供了理论证明，保证其能减少相似度失真并扩大分类边界。
*   **模块化与通用性**：可无缝集成到多种现有的CLIP模型和基于微调的防御方法上，表现出一致的性能增益。
*   **实验扎实**：在多个维度上进行了详尽的评估，包括多种数据集、攻击类型、攻击强度和模型架构，并包含了丰富的消融研究和可视化分析。

### 8. 不足与局限

*   **依赖文本子空间质量**：方法假设干净文本特征构成的子空间是纯净的，但该子空间可能编码了数据集特有的偏见，导致在未知的语言或视觉领域的泛化能力受限。
*   **继承VLM偏见**：作为一个测试时增强方法，COLA无法根本性地移除预训练VLM（如CLIP）本身固有的社会偏见。
*   **潜在的自适应攻击风险**：论文提到，更强的防御可能催生专门针对该对齐机制的自适应攻击，这是未来需要研究的方向。
*   **推理速度的开销**：虽然比迭代方法快，但相比于标准CLIP的前向传播，COLA涉及SVD分解和最优传输求解，仍然引入了额外的推理延迟。

（完）
