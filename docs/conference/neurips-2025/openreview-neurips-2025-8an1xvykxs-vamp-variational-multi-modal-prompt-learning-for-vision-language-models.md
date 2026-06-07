---
title: "VaMP: Variational Multi-Modal Prompt Learning for Vision-Language Models"
title_zh: VaMP：面向视觉-语言模型的变分多模态提示学习
authors: "Silin Cheng, Kai Han"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=8an1xVyKxS"
tags: ["query:affective-ai"]
score: 8.0
evidence: 结合不确定性的多模态提示学习，用于视觉-语言模型
tldr: 针对现有多模态提示学习方法依赖固定共享提示、无法捕捉实例级差异的问题，提出VaMP框架，通过变分推断生成实例特定的不确定性感知提示，在有限监督下显著提升了视觉-语言模型的下游任务适配性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-8an1xvykxs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 1140, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8an1xvykxs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 471, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1246, \"height\": 1306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 664, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1311, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 680, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 790, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 725, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 693, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 554, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 490, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1150, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1287, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8an1xvykxs/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1448, \"height\": 242, \"label\": \"Table\"}]"
motivation: 固定提示无法适应多样任务和域，且忽略模型不确定性。
method: 提出变分多模态提示学习VaMP，采样后验分布生成实例条件化提示。
result: VaMP在多个下游任务上优于固定提示，增强了泛化能力。
conclusion: 该方法为多模态提示学习引入不确定性建模，提升适应性和鲁棒性。
---

## Abstract
Vision-language models (VLMs), such as CLIP, have shown strong generalization under zero-shot settings, yet adapting them to downstream tasks with limited supervision remains a significant challenge. Existing multi-modal prompt learning methods typically rely on fixed, shared prompts and deterministic parameters, which limits their ability to capture instance-level variation or model uncertainty across diverse tasks and domains. To tackle this issue, we propose a novel Variational Multi-Modal Prompt Learning (VaMP) framework that enables sample-specific, uncertainty-aware prompt tuning in multi-modal representation learning. VaMP generates instance-conditioned prompts by sampling from a learned posterior distribution, allowing the model to personalize its behavior based on input content.
To further enhance the integration of local and global semantics, we introduce a class-aware prior derived from the instance representation and class prototype. Building upon these, we formulate prompt tuning as variational inference over latent prompt representations and train the entire framework end-to-end through reparameterized sampling. Experiments on few-shot and domain generalization benchmarks show that VaMP achieves state-of-the-art performance, highlighting the benefits of modeling both uncertainty and task structure in our method. Project page: https://visual-ai.github.io/vamp

---

## 论文详细总结（自动生成）

### 1. 核心问题与研究动机
- 现有视觉-语言模型（如 CLIP）在零样本下泛化能力强，但在有限监督（少样本）下适配下游任务仍具挑战。
- 当前多模态提示学习方法普遍采用**固定的、全局共享的提示**，且参数是确定性的，无法捕捉**实例级别的变化**或**建模不确定性**，限制了在多样化任务和域上的泛化能力。
- 已有的不确定性提示方法（如 Bayesian Prompt Learning）仅限文本模态、全局共享，且缺少类别结构先验，难以实现精细的跨模态对齐。
- 为此，论文提出 **VaMP (Variational Multi-Modal Prompt Learning)**，旨在实现**样本特定的、面向不确定性的多模态提示学习**。

### 2. 方法论
#### 2.1 整体框架：变分多模态提示学习
- 将多模态提示学习构建为**对潜在提示表示的变分推断**，采用重参数化采样端到端训练。
- 三个核心组件：
  1. **样本特定的多模态提示生成** (sample-specific multi-modal prompt generation)
  2. **变分提示适配** (variational prompt adaptation)
  3. **类别感知先验** (class-aware prior)

#### 2.2 关键技术细节
- **样本特定提示生成**：
  - 文本端提示不再是固定共享向量，而是根据**输入图像特征**动态生成。
  - 对于 CLIP 文本编码器第 i 层，使用轻量 MLP \(\Phi_i\) 将冻结的图像表示 \(f_x\) 映射为一组提示 token：\(z_i = \Phi_i(f_x)\)。
  - 生成的 \(z_i\) 与原有文本 token 拼接，注入多个中间 transformer 层（深度提示）。
  - 视觉端仍然采用可学习的、跨样本共享的视觉提示 token，但不建模为潜在变量。

- **变分提示适配**：
  - 将文本端提示 token \(z_i\) 视为潜在变量，通过变分推理建模不确定性。
  - 后验网络 \(\phi_i\) 输出高斯分布参数：\([\mu_i, \sigma_i] = \phi_i(f_x)\)，后验为 \(q_\phi(z_i|x) = \mathcal{N}(\mu_i, \mathrm{diag}(\sigma_i^2))\)。
  - 通过重参数化采样：\(z_i = \mu_i + \sigma_i \odot \epsilon\)，\(\epsilon \sim \mathcal{N}(0, I)\)。
  - 优化 ELBO：
    \[
    \mathcal{L}_{\text{ELBO}} = \sum_{i=J}^{J+H-1} \left[ \mathbb{E}_{q_\phi(z_i|x)}\log p(y|x,t,z_i) - \text{KL}(q_\phi(z_i|x) \| p_\psi(z_i|o_y)) \right]
    \]

- **类别感知先验**：
  - 取代标准高斯先验，使用类别原型 \(o_y\)（训练样本图像特征均值）通过先验网络 \(\psi_i\) 生成每层的高斯先验 \(p_\psi(z_i|o_y)\)。
  - 引导同一类别的潜在提示分布聚集，增强类别判别性和少样本泛化。
  - 测试时无标签，回退为标准高斯先验。

#### 2.3 推理流程
- 输入图像提取特征 \(f_x\)，通过后验网络得到分布。
- 从分布中采样 \(S=10\) 次，得到多组提示 token，分别送入文本编码器。
- 同时注入学习到的视觉提示 token。
- 将 \(S\) 次预测结果平均作为最终输出，提升鲁棒性。

### 3. 实验设计
#### 3.1 数据集与场景
- **Base-to-Novel Generalization**：11 个分类数据集（ImageNet, Caltech101, OxfordPets, StanfordCars, Flowers102, Food101, FGVCAircraft, SUN397, UCF101, DTD, EuroSAT），基类训练，基类+新类测试评估泛化性。
- **Cross-dataset Generalization**：用 ImageNet 训练，直接测试到上述 10 个目标数据集，评估跨数据集迁移能力。
- **Domain Generalization**：用 ImageNet 训练，测试到 4 类分布偏移变体（ImageNetV2, ImageNet-Sketch, ImageNet-A, ImageNet-R）。
- **额外扩展任务**：开放词汇分割（CAT-Seg 框架）、开放词汇动作识别（FROSTER 框架），展示通用性。

#### 3.2 基准方法对比
- 对比了大量现有提示学习方法：CLIP zero-shot, CoOp, CoCoOp, ProDA, KgCoOp, MaPLe, PromptSRC, TCP, MMA, 2SFS, SkipT, MMRL 等。
- 主实验在 16-shot 设置下，以 ViT-B/16 CLIP 为骨骼，采用 MaPLe 风格和 MMRL 风格两种注入层配置。

### 4. 资源与算力
- 文中指出所有实验均在**单张 NVIDIA V100 GPU** 上完成。
- VaMP 引入的额外参数极少（与 MMRL 结合后参数仅从 4.992M 增至 5.132M），推理时间增加微乎其微（\(S=10\) 时延迟仅增加 0.8ms/图，从 5.3ms 到 6.1ms），证实了参数与计算效率。

### 5. 实验数量与充分性
- 实验设置丰富，涵盖多种泛化任务和 11 个基准数据集，并提供详细的消融研究：
  - 评估三种主要泛化设置 + 两个扩展任务。
  - 消融实验分别验证样本特定生成、变分提示、类别感知先验的各自贡献（基于 MaPLe 和 MMRL 两种骨干）。
  - 分析针对关键超参数（插入深度 J/H、每层提示 token 长度 M）和效率（不同采样数量 S）的影响。
  - 还在其他 VLM 架构（EVA-CLIP, SigLIP, SigLIP2）上验证兼容性。
- 所有结果均报告三次重复实验的平均值，实验设计客观、公平，对比基线广泛且标准。

### 6. 主要结论与发现
- VaMP 在少量样本下显著提升视觉-语言模型的泛化能力，在 base-to-novel、跨数据集、域泛化三项任务上均达到**最先进的性能**。
- 变分建模与样本特定生成能够捕捉实例级变化和不确定性，超越固定共享提示。
- 类别感知先验加强了潜在空间的类内一致性和判别性，进一步提高新类性能。
- 方法具有**高参数效率**和**低计算开销**，可轻松迁移到其他 VLM 架构和下游任务（分割、动作识别）。
- 定性可视化显示不同层和不同样本的潜在分布呈现出可解释的层次化不确定性细化。

### 7. 优点
- **新颖的不确定性建模**：首次在多模态提示学习中结合逐层潜在变量和变分推断，实现样本特定的概率提示。
- **结构化先验设计**：类别感知先验利用原型信息规范化潜在空间，兼顾任务结构。
- **全面扎实的实验**：涵盖多种泛化设置、在 11 个数据集上对比 15 种方法，消融与扩展任务丰富。
- **效率与实用性**：额外开销极小，可轻松嵌入现有方法（MaPLe、MMRL），且兼容多种 VLM。
- **良好的可解释性**：通过后验分布可视化展示了层次化不确定性和类别分离。

### 8. 不足与局限
- **类别原型依赖**：类别感知先验需在训练阶段计算类别原型，**不适用于完全无标签场景**或动态变化类别。
- **任务范围尚有局限**：主要实验集中在分类任务，生成式或多模态推理任务（如图像描述、VQA）未测试，仅做了分割和动作识别扩展。
- **固定视觉端提示**：视觉提示仍为共享确定性参数，未建模不确定性，可能限制跨模态对齐的潜力。
- **推断样本数固定**：尽管验证了 \(S=10\) 的效率与效果，但未探索自适应采样或更高级的不确定性校正。
- **训练需有监督**：在 few-shot 设定下，仍需一定数量的带标样本，未探索无监督或少标签设置。

（完）
