---
title: Object-centric binding in Contrastive Language-Image Pretraining
title_zh: 对比语言-图像预训练中的以对象为中心的绑定
authors: "Rim Assouel, Pietro Astolfi, Florian Bordes, Michal Drozdzal, Adriana Romero-Soriano"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dsUK4Xql8Z"
tags: ["query:affective-ai"]
score: 8.0
evidence: 通过场景图整合以对象为中心的绑定至CLIP预训练，提升组合场景理解
tldr: 针对CLIP模型在复杂场景中无法理解对象间关系的问题，本文提出一种对象绑定模块，将从文本描述中导出的场景图与槽结构化视觉表示相连接，将组合性归纳偏置注入对比预训练。实验表明该方法在多个组合理解基准上显著超越基线，无需精细设计的难负样本增强，为视觉语言预训练中的结构化对齐提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1354, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 989, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1435, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1409, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 1309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 1603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1450, \"height\": 1317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 627, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 628, \"height\": 838, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1219, \"height\": 754, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1221, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1218, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1221, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1434, \"height\": 1310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1453, \"height\": 1326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dsuk4xql8z/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1449, \"height\": 1314, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1461, \"height\": 727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 724, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1464, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1406, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 820, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1460, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1461, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 532, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dsuk4xql8z/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1147, \"height\": 801, \"label\": \"Table\"}]"
motivation: 现有CLIP模型在复杂多对象场景理解中存在局限，难以捕捉空间关系和组合结构。
method: 提出一种绑定模块，将文本描述的场景图与槽状视觉表示相连接，无需难负样本增强即可在预训练中注入结构归纳偏置。
result: 在组合性理解基准上，本方法显著优于标准CLIP，展现了更强的对象-关系对齐能力。
conclusion: 通过对象绑定引入组合性先验提升了VLMs的场景理解能力，为视觉语言对齐提供了新的结构化方案。
---

## Abstract
Recent advances in vision language models (VLM) have been driven by contrastive models such as CLIP, which learn to associate visual information with their corresponding text descriptions. However, these models have limitations in understanding complex compositional scenes involving multiple objects and their spatial relationships. To address these challenges, we propose a novel approach that diverges from commonly used strategies that rely on the design of finegrained hard-negative augmentations. Instead, our work focuses on integrating inductive biases into the pretraining of CLIP-like models to improve their compositional understanding. To that end, we introduce a binding module that connects a scene graph, derived from a text description, with a slot-structured image representation, facilitating a structured similarity assessment between the two modalities. We also leverage relationships as text-conditioned visual constraints, thereby capturing the intricate interactions between objects and their contextual relationships more effectively. Our resulting model not only enhances the performance of CLIP-based models in multi-object compositional understanding but also paves the way towards more accurate and sample-efficient image-text matching of complex scenes.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- 当前视觉 - 语言模型（如 CLIP）在理解包含多个对象及其空间关系的复杂场景时存在严重局限，常表现出“词袋”行为：能识别独立对象却难以正确绑定属性（如“红苹果和蓝香蕉” vs “蓝苹果和红香蕉”）以及判别空间关系（如“猫在垫子左边” vs “猫在垫子右边”）。
- 现有改进多依赖精细设计的**硬负样本增强**来提升组合理解，但这类方法并未从根本上解决表征层面的**对象绑定问题**（segregation, representation, composition），泛化性有限。
- 作者提出应将**以对象为中心的归纳偏置**引入 CLIP 预训练，通过结构化场景图与槽状视觉表示的显式对齐，在不依赖大量硬负样本的情况下显著提升模型的组合性场景理解能力。

## 2. 方法论

### 2.1 总体框架
模型称为 **OC‑CLIP**（Object‑Centric CLIP），其流程为：
1. 用 LLM 解析文本描述，生成场景图（节点：对象短语，边：关系三元组）。
2. 图像经 ViT 编码为补丁特征；文本节点和关系分别经过（可更小容量的）文本编码器得到嵌入。
3. **绑定模块**将文本节点作为查询，与图像补丁进行竞争性交叉注意力，产生与对象对应的**视觉槽**（visual slots）。
4. 用**结构化相似度评分**将视觉槽与场景图对齐，引入对象‑槽匹配和关系约束。

### 2.2 绑定模块（Binding Module）
- 采用**逆交叉注意力**（inverted cross‑attention）：查询为场景图节点特征 \( Q = W_q N \)，键、值为图像补丁 \( K, V = W_k \bar{x}, W_v \bar{x} \)。
- 在查询维度做 softmax，促使不同查询竞争解释图像不同区域。
- 添加一组**默认查询** \( Q_{\text{default}} \) 以吸收不在文本中描述的视觉信息，增加训练稳定性。
- 输出视觉槽 \( S \) 及丢弃的默认槽。

### 2.3 结构化相似度评分
全局图像 - 场景图相似度由两部分加权组成：
\[
S(x, G) = \frac{\alpha \sum_{i} \cos(N_i, S_i) + \beta \sum_{i} f_\phi(r_i, S_{s_i}, S_{o_i})}{\alpha M + \beta P}
\]
- **对象评分**：纹理节点与对应视觉槽的余弦相似度之和。
- **关系评分** \( f_\phi \)：以关系嵌入 \( r \)、主体槽 \( S_s \)、客体槽 \( S_o \) 为输入，经两个 MLP 投影后通过余弦相似性计算，保持了有向性。
- \( \alpha, \beta \) 为可学习参数。

### 2.4 训练损失
- **图像‑文本对比损失** \( \mathcal{L}_{\text{itc}} \)：最大化配对图像与场景图的相似度，最小化与批内其他对的相似度。
- **局部图对比损失** \( \mathcal{L}_{\text{rel}} \)：对关系的正样本、交换主体/客体顺序的样本、随机替换主客体的样本进行对比，防止关系评分网络退化。

## 3. 实验设计

### 3.1 合成数据控制实验
- 使用 PUG 3D 环境构建封闭集合对象，包含 5 种背景、20 种动物、4 种纹理，可枚举所有属性绑定和空间关系组合。
- 在训练时控制**可见对象对比例**（30%–70%）和**硬负样本比例**（0%–70%），评估在未见组合、未见对象对上的属性绑定与空间关系识别能力。
- 对比方法：基于预训练 OpenCLIP 微调的 CLIP 基线 与 OC‑CLIP。

### 3.2 域内组合理解评估
- **训练数据**：COCO Captions、Visual Genome、GQA 的聚合数据。
- **测试基准**：
  - 属性绑定：SugarCrepe（swap‑attribute、swap‑object、replace‑relation 等）和 ARO‑A。
  - 关系理解：COCO‑spatial、GQA‑spatial（WhatsUp 基准）、ARO‑Relation。
- **对比基线**：
  - 域内微调：OpenCLIP‑FT、BLIP、XVLM。
  - 硬负样本方法：NegCLIP、CE‑CLIP、CC‑CLIP、CLIP‑SVLC、MosaiCLIP。
  - 密集再标注方法：DAC‑LLM、DAC‑SAM。
- **模型变体**：OC‑CLIP 使用 OpenCLIP ViT‑B‑16 或 DINOv2 ViT‑B‑14 作为视觉骨干，绑定模块从头训练。

### 3.3 从零训练与规模扩展
- 数据集：CC3M、CC12M 及其合并集（15M），均使用 LLM 解析生成场景图。
- 评估：零样本 ImageNet 分类、ELEVATER 套件、SugarCrepe swap 分裂、Winoground。
- 对比基线：同样结构从头训练的 OpenCLIP、NegCLIP、IL‑CLIP。
- 模型设定：ViT‑B‑16 视觉骨干，文本编码器缩小为 256 维、6 层、上下文长度 20。

### 3.4 消融与分析
- 对竞争性交叉注意力、局部图对比损失、注意力层数、默认令牌数等进行消融。
- 解析方法对比（spaCy、T5 场景图解析器、LLaMA3），分析不同解析器对下游组合性能的影响。
- 视觉层选择（从第几层插入绑定模块）的灵敏度测试。
- 评分维度 \( d_{\text{obj}}, d_{\text{rel}} \) 的鲁棒性分析。

## 4. 资源与算力

- **训练资源**：CC3M/CC12M 实验使用 `4×8 V100 GPUs`，每 GPU 本地 batch size 128。
- **计算开销对比**：OC‑CLIP（B‑16）总 GFLOPs 约为同配置 CLIP 的 **2.2 倍**，文本编码器更小，开销主要来自绑定模块的交叉注意力。当视觉骨干增大到 ViT‑L 时，额外开销比例下降到 **1.3 倍**，说明绑定模块的计算量相对固定。
- **解析成本**：使用 LLaMA3‑8B 通过 vLLM 并行处理 COCO (~500k 描述) 耗时约 3.5 小时（10 实例，128 块）；CC12M 用本地 Ollama 片式处理耗时约 3 天，文中指出可通过更多 GPU 加速。

## 5. 实验数量与充分性

- 实验设计较为完备：包含合成环境控制变量分析、两个实际域内训练设置、三种数据规模的从零训练、多维度的组合性基准、丰富的对比基线以及消融实验。
- 定量结果多次报告均值 ± 标准差（如 3 个随机种子），增强统计可靠性。
- 覆盖属性绑定、空间关系两大关键组合能力，测试集涵盖易受词袋干扰的困难拆分（SugarCrepe）。
- 对比公平，对相同骨干、相同训练数据、相同超参数的 CLIP 基线进行直接对比。
- 仍缺少与 400M 以上超大规模 CLIP 的全面对比，但作者在结论中明确此为未来工作方向，不损害核心贡献的完整性。

## 6. 主要结论与发现

- OC‑CLIP 在不依赖任何硬负样本增强的情况下，显著优于使用大量硬负样本微调的 OpenCLIP，且样本效率更高：同样训练数据量下，属性绑定准确率从 81% 提升至 97%。
- 在真实场景组合性基准上，OC‑CLIP 相较于域内微调的 OpenCLIP 在 SugarCrepe swap‑attribute 上提升 **+16.5%**，在 COCO‑spatial 上提升 **+44.1%**（从随机水平到 89.7%），在 GQA‑spatial 上提升 **+43.6%**（至 92.7%）。
- 即使对比大规模密集再标注方法（DAC），OC‑CLIP 仍在 swap‑attribute 和 swap‑object 上保持明显优势。
- 在从零训练的设置下，OC‑CLIP 在零样本 ImageNet 分类（+12.8%）和零样本组合性理解上都优于相同数据规模的 OpenCLIP，证明了对象中心归纳偏置的普适性与缩放潜力。
- 消融验证了竞争性交叉注意力和局部关系对比损失对最终性能至关重要。

## 7. 优点

- **结构化归纳偏置**：将对象中心学习中的槽注意力机制与视觉语言对比预训练相结合，从表征层面解决绑定问题，而非仅靠数据增强。
- **无需硬负样本**：摆脱了对精细设计难负样本的依赖，方法更本质、更样本高效。
- **骨干灵活性**：可兼容不同预训练视觉编码器（OpenCLIP、DINOv2），绑定模块可与 CLIP 风格架构无缝集成。
- **极强的关系理解提升**：在空间关系基准上从接近随机水平大幅提升至 90% 左右，表明模型真正学会了结构化关系推理。
- **实验全面**：合成实验、域内微调、从零训练以及大量消融和解析器对比，支撑核心主张。
- **计算效率可随模型尺度改善**：绑定模块开销固定，随着视觉骨干增大，相对开销显著降低，有利于大规模训练。

## 8. 不足与局限

- **依赖外部解析器**：方法需要由 LLM 生成场景图，解析质量和覆盖度会影响下游性能，计算开销（尤其是大规模数据）不可忽略。
- **域内微调时丧失零样本泛化能力**：绑定模块从头训练，CLIP 原有的通用对齐空间被重塑，模型只在训练集词汇范围内有效。作者通过线性探测证明视觉主干未严重退化，但多模态零样本能力受限。
- **训练规模有限**：从零训练实验仅到 15M 图像，未在 400M 级别上与主流 CLIP 进行比较，离实际部署尚有距离。
- **模型容量探究不足**：实验主要集中在 ViT‑B 尺度，未展示在 ViT‑L 或更大模型的缩放效果。
- **场景图结构限制**：当前仅在二值关系上建模，对更复杂、多元关系的支持未涉及。

（完）
