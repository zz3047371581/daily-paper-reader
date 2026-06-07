---
title: "Diffuse Everything: Multimodal Diffusion Models on Arbitrary State Spaces"
title_zh: 扩散一切：任意状态空间上的多模态扩散模型
authors: "Kevin Rojas, Yuchen Zhu, Sichen Zhu, Felix X-F. Ye, Molei Tao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AjbiIcRt6q"
tags: ["query:affective-ai"]
score: 4.0
evidence: 提出多模态扩散模型框架，实现跨模态联合生成
tldr: 现有方法依赖外部预处理协议统一多模态数据，本文提出在任意状态空间上构建多模态扩散模型的框架，原生实现多模态数据的联合生成。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1598, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1343, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 372, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 371, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 372, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 789, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1579, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1583, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1578, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 361, \"height\": 2104, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 364, \"height\": 2104, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 362, \"height\": 2112, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 363, \"height\": 2104, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 364, \"height\": 2097, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajbiicrt6q/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 362, \"height\": 2111, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 744, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1640, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1627, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1050, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 479, \"height\": 624, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 769, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1240, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1487, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1470, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajbiicrt6q/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1468, \"height\": 362, \"label\": \"Table\"}]"
motivation: 现有方法需高精度编解码器预处理，限制多模态扩散模型应用。
method: 提出在任意状态空间上构建多模态扩散模型，无需外部令牌化器。
result: 实现了多模态数据的原生联合生成。
conclusion: 为多模态生成提供了更灵活的方法。
---

## Abstract
Diffusion models have demonstrated remarkable performance in generating unimodal data across various tasks, including image, video, and text generation. On the contrary, the joint generation of multimodal data through diffusion models is still in the early stages of exploration. Existing approaches heavily rely on external preprocessing protocols, such as tokenizers and variational autoencoders, to harmonize varied data representations into a unified, unimodal format. This process heavily demands the high accuracy of encoders and decoders, which can be problematic for applications with limited data. To lift this restriction, we propose a novel framework for building multimodal diffusion models on arbitrary state spaces, enabling native generation of coupled data across different modalities. By introducing an innovative decoupled noise schedule for each modality, we enable both unconditional and modality-conditioned generation within a single model simultaneously. We empirically validate our approach for text-image generation and mixed-type tabular data synthesis, demonstrating that it achieves competitive performance. Code is available at https://github.com/KevinRojas1499/Diffuse-Everything.

---

## 论文详细总结（自动生成）

好的，以下是根据论文《Diffuse Everything: Multimodal Diffusion Models on Arbitrary State Spaces》生成的详细中文总结。

---

## 1. 核心问题与研究动机

*   **背景：** 扩散模型在图像、视频、文本等**单模态生成**中表现卓越，但多模态数据的**联合生成**仍处于探索早期。
*   **现有方法的局限：** 当前多模态扩散模型（如UniDiffuser、OmniFlow、Chameleon等）极度依赖外部预处理协议（如Tokenizer、VAE、VQVAE、CLIP对齐），将不同模态的数据统一转换为一种**单一表示格式**（全连续或全离散），再送入模型。
*   **痛点：** 这种“统一表示后又解码”的流程要求**极高性能的编码器-解码器对**。一方面，解码器精度不足会引入伪影；另一方面，在数据稀缺的应用中，训练如此高性能的编解码器十分困难。此外，这类方法定制性强，难以灵活扩展至**任意模态组合**。
*   **核心问题：** 能否设计一个原则性框架，让多模态数据**在其原生空间中**进行联合建模，从而摆脱对统一表示和强大外部编解码器的依赖？

## 2. 方法论

### 2.1 核心思想与统一框架

*   **理论基础：** 将扩散模型提升到**去噪马尔可夫模型 (Denoising Markov Models)** 的高度，不同状态空间（连续欧氏空间、离散有限空间、黎曼流形）上的扩散过程本质上是同一类马尔可夫过程，具有统一的生成元 (Generator) 和广义分数匹配目标 (Generalized Explicit Score Matching, GESM)。
*   **多模态扩展：** 直接将多个独立状态空间上的、具有各自独立时间变量的正向扩散过程进行**笛卡尔积**，构建联合正向过程。数据中的每个模态分别按自己的“时钟”独立加噪。
*   **解耦时间变量：** 为每个模态引入独立的、**解耦的噪声调度**。各模态可以在不同的“噪声水平”下运作，这种异步加噪的设计是实现单模型同时支持无条件/条件生成的关键。
*   **统一学习目标：** 从去噪马尔可夫模型的广义分数匹配出发，作者**严谨地证明**：在多模态联合正向过程下，学习联合边际分布的分数函数，其训练损失**等价于各个模态各自的条件分数匹配损失之和**。这意味着学习者只需对每个模态做一次普通的单模态条件分数匹配，即可完成多模态联合训练，实操极为简洁。

### 2.2 关键技术：连续-离散多模态扩散

论文重点实例化了一种兼具连续性与离散性的多模态扩散模型：

*   **正向过程：**
    *   连续模态（如图像）采用带漂移的**Ornstein-Uhlenbeck过程**：\(dX_t = f(X_t,t)dt + g(t)dB_t\)。
    *   离散模态（如文本）采用**连续的马尔可夫链 (CTMC)**，例如带掩码的离散扩散：\(Y_s \sim \text{CTMC}(Q_s)\)，其中 \(Q_s\) 主要指向一个特殊的[MASK]状态。
*   **训练目标：** 根据上述等价定理，联合训练的损失函数为“连续模态的显式分数匹配损失 + 离散模态的分数熵损失”的加权和。借助离散扩散的特性（如掩码扩散），分数熵损失可进一步简化为交叉熵。
*   **生成过程（反向过程）：** 基于学习到的联合分数，设计了一个在“双时间”系统下的反向过程。通过选择不同的**时间参数化方案**，即可从同一模型中实现多种生成方式：
    *   **无条件下联合生成：** 令两个时间变量同时从 \(T\) 单调递减到 \(0\)。
    *   **有条件生成：** 始终保持条件模态时间变量为 \(0\)（即已经处于干净数据状态），仅对被生成模态执行反向时间推进。

### 2.3 噪声引导 (Noisy Guidance)

*   **创新引导机制：** 受“自引导 (Autoguidance)”思想启发，论文提出**噪声引导**。传统无分类器引导 (CFG) 使用无条件分数作为指导者，噪声引导则改用**被部分加噪的条件**作为指导者。公式为：\(\omega s_\theta(x_t, y_s, t, s) + (1-\omega) s_\theta(x_t, y_{\sigma}, t, \sigma)\)，其中 \(\sigma > s\)。
*   **优势：** 此方法不仅在标准条件生成（给定清晰条件）中可用，甚至在**无监督的联合生成过程**中（条件本身也在从噪声中恢复）也能适应性地动态施加引导，具有更广泛的适用性。实验表明，选择一个噪声程度介于清晰和完全噪声之间的条件进行引导，能有效提升生成质量（如降低FID）。

## 3. 实验设计

实验验证了两大场景，均采用连续-离散扩散实现。

### 3.1 文本-图像联合生成

*   **数据集：** 训练使用**SAM-LLaVA数据集**（为分割一切模型生成的图片配上LLaVA自动描述的文本）。评估使用**MS-COCO**数据集，计算FID-30K指标。
*   **模型架构：** 设计了一个结合MMDiT（多模态扩散Transformer）与DiT的主干网络，图像和文本分别以原生形式输入，通过交叉注意力进行深层交互。
*   **基准对比：** 与两类模型对比。第一类是纯文本-图像模型（如DALL-E 2, Imagen, Stable Diffusion, PixArt-α, MMDiT-improved）；第二类是多模态生成/理解模型（如Show-o, Transfusion, Chameleon, Versatile Diffusion等）。
*   **训练策略：** 采用**多阶段训练**：第一阶段侧重文本-图像对齐；第二阶段冻结联合嵌入，专门训练文本预测；第三阶段联合微调解码器。

### 3.2 混合类型表格数据合成

*   **数据集：** 使用UCI机器学习库中的6个真实世界表格基准：**Adult, Default, Shoppers, Magic, Beijing, News**。前四个为分类任务，后两个为回归任务。
*   **模型架构：** 基于DiT构建的轻量级网络，对数值特征和分类特征分别做简单嵌入后直接拼接（早融合），送入Transformer块。
*   **评估指标：** 遵循标准协议，评估合成数据的**Trend（列间相关性）**、**MLE（机器学习效用）**、**Shape（列分布相似度）**、**α-Precision（合成数据的保真度）**和**β-Recall（合成数据的覆盖度）**。
*   **基准对比：** 与GOGGLE, STaSy, CoDi, TabDDPM, TAB SYN等多种最新的表格数据生成模型进行对比。

## 4. 资源与算力

*   **本文没有明确提及**具体的GPU型号、数量或训练总时长。论文侧重于提出方法和验证其效率，通过模型**参数量**的显著降低来间接体现资源节省。例如，文本-图像模型核心部分约481M参数，无需数B参数的外部文本/视觉编码器；表格数据模型仅有约64K参数，比其他方法小100-200倍。

## 5. 实验数量与充分性

*   **实验数量充足：** 涵盖了两个差异巨大的应用领域（视觉-语言生成、结构化表格数据合成），并在一个黎曼流形（SO(3)）的玩具示例上验证了框架的通用性。
*   **评估全面客观：**
    *   **文本-图像任务：** 对比了多达十余种包含工业级规模的基线模型，从FID这一核心指标进行衡量。同时定性地展示了联合生成、文生图、图生文的非精选样本。
    *   **表格数据任务：** 在6个涵盖分类/回归不同特征规模的数据集上，比较了5种基线方法，并使用了**5种从不同维度衡量数据质量的指标**。为确保鲁棒性，所有实验**重复20次**并报告了标准差。
    *   **消融与机制验证：** 设计了噪声引导程度的消融实验（图4），验证了不同噪声水平对生成质量的影响。
*   **公平性：** 对比时明确区分了“需要外部强大编码器”的模型与自身的方法，并特别强调了在**不借助预训练编码器、参数极低**条件下的性能，对比基准清晰、立场客观。

## 6. 主要结论与发现

1.  **框架普适性：** 成功提出并验证了一个能在**任意状态空间**（连续、离散、黎曼流形）上构建多模态扩散模型的通用框架，无需将数据强制转化为统一格式。
2.  **理论简洁性：** 给出了优雅的理论证明：多模态联合训练的学习目标自然地分解为各模态单条件损失之和，为实践提供了坚实基础。
3.  **功能集成性：** 通过**解耦时间变量**和**噪声引导**机制，单一模型即可原生支持无条件联合生成、有条件和无条件下的单模态生成，实现了“any-to-any”的灵活生成。
4.  **性能与效率：** 在两个任务上均取得了有竞争力的性能。最突出的是，在参数规模**显著低于**依赖外部编码器的基线模型的情况下（尤其是表格数据任务，参数量仅为其它方法的几十分之一到几百分之一），性能仍能保持领先或次优。

## 7. 优点

*   **原生多模态：** 彻底抛弃了VAE、Tokenizer等可能导致信息损失和伪影的中间表示，直接在原始数据空间建模，是最根本的亮点。
*   **坚实的理论基础：** 从去噪马尔可夫模型的统一视角出发，给出了严谨的定理证明（如GESM优化性质、损失的等价性等），为工程的简洁性提供了理论担保。
*   **优雅的“双时间”设计：** 解耦的时间变量不仅统一了各种生成任务，还催生了更通用的“噪声引导”方法，有效提升了生成质量，构思巧妙。
*   **极高的参数效率：** 尤其是在表格数据上，64K参数即可超越比它大两个数量级的复杂模型，证明了减少冗余组件（如编解码器）并采用早融合策略的巨大优势。
*   **可扩展性强：** 框架不局限于特定模态，附录中展示的黎曼流形-离散模态结合案例，预示着其在蛋白质设计、分子构象等复杂结构化数据上的应用潜力。

## 8. 不足与局限

*   **性能天花板：** 在文本-图像生成这样高度复杂的任务上，虽然结果有竞争力，但FID指标与当前最顶级的、使用了海量数据和超大规模模型的工业系统（如DALL-E 3, Transfusion）仍有差距。这是放弃强预训练编码器必然面临的挑战。
*   **训练策略复杂：** 文本-图像生成任务需要精细的多阶段训练，这增加了方法的应用门槛，且不同模态间的平衡可能更依赖于经验。
*   **未利用预训练信息：** 作者承认，目前完全从零开始训练，没有探索如何将现有的、强大的单模态预训练模型（如CLIP文本编码器）作为初始化来加速多模态训练，这是未来工作的重要方向。
*   **下游任务评估缺失：** 文本-图像生成的评估仅停留在FID和CLIP相似度，缺少如图像描述标准任务（CIDEr, SPICE等）、视觉问答等更深入的理解或交互任务上的评估。
*   **生成规模限制：** 表格数据的实验均基于传统UCI小规模数据集，未在现代大规模工业级表格数据上验证。在文本-图像生成中，也未见对更高分辨率（如1024x1024）的直接探索。

（完）
