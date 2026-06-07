---
title: "Evolving Minds: Logic-Informed Inference from Temporal Action Patterns"
title_zh: Evolving Minds：从时序动作模式进行逻辑信息推断
authors: "Chao Yang, Shuting Cui, Yang Yang, Shuang Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=QRms4lx0Fp"
tags: ["query:affective-ai"]
score: 9.0
evidence: 从动作模式推理人类心理状态，直接实现情感计算中的检测任务
tldr: 针对人类动作时序不规则且心理状态不可观测的挑战，提出逻辑信息引导的时间点过程框架，结合摊销变分EM，将逻辑规则作为先验引导强度函数，从而捕捉动作与心理事件的互动。引入离散时间更新过程近似后验，减少对大数据依赖。实验表明该框架在意图和欲望推理上准确高效，为构建情感具备的协作AI提供了新颖的神经符号方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1779, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 896, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1772, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1770, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1761, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qrms4lx0fp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 394, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1786, \"height\": 634, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1816, \"height\": 648, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 485, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 875, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 485, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1170, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1178, \"height\": 971, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1811, \"height\": 834, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1345, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1250, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1527, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1437, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1197, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1293, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1088, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1634, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1729, \"height\": 430, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1757, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1564, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qrms4lx0fp/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1792, \"height\": 202, \"label\": \"Table\"}]"
motivation: 理解意图、欲望等人类心理状态对自然AI协作至关重要，但状态不可观测且数据稀缺。
method: 结合逻辑先验的时间点过程与摊销变分EM，用离散时间更新过程处理推断不可解问题。
result: 在心理状态推理任务上优于基线，能以较少数据捕捉动作-心理事件交互。
conclusion: 为情感AI提供了一种神经符号结合的推理框架，可检测用户意图和欲望。
---

## Abstract
Understanding human mental states—such as intentions and desires—is crucial for natural AI-human collaboration. However, this is challenging because human actions occur irregularly over time, and the underlying mental states that drive these actions are unobserved. To tackle this, we propose a novel framework that combines a logic-informed temporal point process (TPP) with amortized variational Expectation-Maximization (EM). Our key innovation is integrating logic rules as priors to guide the TPP’s intensity function, allowing the model to capture the interplay between actions and mental events while reducing dependence on large datasets. To handle the intractability of mental state inference, we introduce a discrete-time renewal process to approximate the posterior. By jointly optimizing model parameters, logic rules, and inference networks, our approach infers entire mental event sequences and adaptively predicts future actions. Experiments on both synthetic and real-world datasets show that our method outperforms existing approaches in accurately inferring mental states and predicting actions, demonstrating its effectiveness in modeling human cognitive processes.

---

## 论文详细总结（自动生成）

# 论文总结：Evolving Minds: Logic-Informed Inference from Temporal Action Patterns

## 1. 核心问题与整体含义
- **研究动机**：在人机协作（如医疗、教育、机器人）中，AI 需理解人类潜在的**意图与欲望**等心理状态（mental states），才能提供及时、情境感知的辅助。但人类动作在时间上不规则，且驱动动作的心理状态不可观测，传统方法难以建模动作与心理事件之间的动态交互。
- **核心挑战**：
  - 动作与心理事件的发生时间**不规则**，时间间隔蕴含关于目标转移的上下文线索。
  - 心理状态**动态变化且相互依赖**，过去动作影响意图形成，意图引导未来行为，需要同时推断整个心理事件序列的时间与类型。
- **整体含义**：本文旨在联合解决**心理状态推理**与**未来动作预测**，通过将可解释的逻辑规则作为先验融入时序点过程，减小对大规模数据的依赖，提升模型在少量数据下的泛化性与可解释性。

## 2. 方法论
### 核心思想
将**逻辑信息引导的时序点过程（TPP）**与**摊销变分 EM** 结合，用逻辑规则作为先验指导强度函数，建模动作与心理事件的耦合生成过程；用离散时间更新过程（DT-RP）近似后验，实现高效推断与未来动作预测。

### 关键技术细节
- **解码器（Decoder）——逻辑信息引导的 TPP pθ(a, m)**
  - 统一动作类型与心理事件类型为布尔变量，通过 Horn 逻辑规则定义事件间的时序依赖（如 Before, After, Equal）。
  - 强度函数设计：`λx(t|H(t)) = μx + Σ wf φf(H(t))`，其中 φf 为满足规则体的历史事件组合的指数衰减加权计数，衰减因子 βf 可学。
  - 逻辑规则集 F 可动态学习：初始可为预定义规则或空集，通过列生成算法（主问题优化连续参数，子问题生成新规则）扩充与精炼。
- **编码器（Encoder）——摊销变分后验 qφ(m|a)**
  - 基于**离散时间更新过程（DT‑RP）** 建模，将时间轴离散化成网格。
  - 神经风险函数设计：利用交叉注意力从动作序列提取上下文，结合类型相关的发射网络和自回归更新的心理历史，输出每个网格的风险概率 hx(k)。
  - 风险函数可高效采样与计算似然，熵项具有闭式解，便于 E 步优化。
- **学习过程（摊销变分 EM）**
  - **E 步**：冻结解码器参数 θ，优化编码器 φ，最大化 ELBO；梯度通过 REINFORCE 估计，熵利用闭式解。
  - **M 步**：冻结编码器 φ，采样心理事件，优化连续参数（规则权重、基率）并更新离散规则集（列生成）。
- **预测与回溯机制**
  - 根据观察动作推断心理状态 m，然后从 pθ 采样候选动作。
  - 在候选动作时间与上次事件之间检查是否有心理事件发生，若有，则重新采样动作，确保时间一致性。

### 关键公式/算法流程（文字说明）
- 联合对数似然：`log pθ(a, m) = Σ log λ(事件发生时刻) - ∫ Σ λx(τ) dτ`。
- ELBO：`L(θ,φ; a) = E_{qφ}[log pθ(a,m)] - E_{qφ}[log qφ(m|a)]`。
- E 步更新 φ 时使用 REINFORCE 梯度估计，M 步通过采样计算期望似然并交替主问题与子问题。

## 3. 实验设计
### 数据集
- **合成数据**：
  - Syn Data‑1：1 种心理谓词，2 种动作谓词，3 条规则，序列平均 18.60 个动作。
  - Syn Data‑2：2 种心理谓词，2 种动作谓词，4 条规则，序列平均 13.25 个动作。
- **真实数据**：
  - **Hand‑Me‑That**（人机协作任务，503 条序列）
  - **Car‑Following**（跟车行为，2000 条序列）
  - **MultiTHUMOS**（篮球视频，2000 条序列）
  - **EPIC‑Kitchen‑100**（厨房动作，131 条序列）
- **训练/验证/测试划分**：80%/10%/10%（按序列数量）。
- **评估指标**：事件类型预测错误率（ER%）和时间预测平均绝对误差（MAE）。

### Benchmark 与对比方法
三类基线共 12 个：
- **神经 TPP**：RMTPP、THP、PromptTPP、HYPRO。
- **逻辑规则模型**：TELLER、CLNN、STLR。
- **生成模型**：AVAE、GNTPP、VEPP、STVAE。
- **本文方法**：Ours*（含规则学习与回溯机制）。

实验设置公平，所有方法均在相同数据划分下比较，并汇报标准差。

## 4. 资源与算力
- **训练环境**：Ubuntu 20.04.3 LTS，Intel Xeon Gold 6248R CPU @ 3.00GHz，227 GB 内存。
- **未提及 GPU 型号、数量或训练时长**。文中仅说明实验在 CPU 上运行，未提供算力消耗的量化数据。

## 5. 实验数量与充分性
实验设计包含：
- **合成数据**：心理事件推断可视化、规则学习准确性、单步/多步动作预测、消融实验、可扩展性实验（样本量、规则复杂度）。
- **真实数据**：四套数据集上的预测对比、可扩展性实验（不同样本量）、消融实验（先验知识和回溯模块）、注意力权重可视化、规则发现示例。
- **消融分析**：对比四种设置（有无先验、有无回溯）在合成与真实数据上的效果。
- **参数敏感性**：时间网格分辨率、最大回溯轮数的影响。

实验**覆盖充分，客观全面**，既有合成数据验证内部机制，又有多种真实场景验证实际性能；对比基线丰富，消融、扩展性、参数分析系统性强。但部分真实数据集的规模偏小（如 EPIC-Kitchen 仅 131 条），可能影响结论普适性。

## 6. 主要结论与发现
- 所提方法在合成与真实数据集上的**心理状态推理和动作预测**均优于现有神经 TPP、逻辑模型和生成模型。
- 逻辑先验有效**降低数据依赖**，在小样本下仍表现良好，且可发现具有实际意义的可解释规则。
- 回溯机制能**提升预测的时间一致性**，减少级联误差。
- 模型在**长时域多步预测**中表现稳健，兼具可解释性与预测精度。

## 7. 优点
- **神经符号融合**：将逻辑规则直接融入 TPP 强度函数，提升了可解释性与数据效率。
- **完整推断框架**：同时处理心理事件序列的推断、可学习规则发现和未来动作预测。
- **回溯机制**：确保预测动作与推断的意图在时间上一致，减轻误差传播。
- **模块化设计**：DT-RP 编码器与逻辑解码器分离，便于 E‑M 交替优化与规则动态更新。
- **实验丰富**：覆盖合成与多领域真实数据，系统消融与可扩展性分析，对比基线较全。

## 8. 不足与局限
- **离散化引入噪声**：时间网格分辨率是敏感超参，过粗会丢失心理事件，过细增加计算负担。
- **规则学习依赖模板**：虽然支持从零学习，但多数真实实验仍依赖手工定义的规则模板，可能引入偏差。
- **计算开销**：列生成子问题搜索规则空间可能在大规模规则时效率较低，未提供与 GPU 加速的对比。
- **心理事件真值缺失**：真实数据无心理状态标注，推断结果仅通过下游预测间接评估，缺乏直接验证。
- **数据集规模有限**：EPIC-Kitchen 序列数较少，较大场景下结论鲁棒性待进一步验证。

（完）
