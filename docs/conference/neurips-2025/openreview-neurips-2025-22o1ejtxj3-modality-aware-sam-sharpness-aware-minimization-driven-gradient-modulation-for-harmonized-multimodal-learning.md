---
title: "Modality-Aware SAM: Sharpness-Aware-Minimization Driven Gradient Modulation for Harmonized Multimodal Learning"
title_zh: 模态感知SAM：基于锐度感知最小化的梯度调制实现和谐多模态学习
authors: "Hossein R. Nowdeh, Jie Ji, Xiaolong Ma, Fatemeh Afghah"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=22O1ejTxj3"
tags: ["query:affective-ai"]
score: 8.0
evidence: 通过锐度感知最小化和梯度调制平衡多模态学习
tldr: 多模态学习中主导模态常掩盖其他模态，损害泛化。本文提出模型无关的M-SAM框架，通过Shapley贡献识别主导模态，调节损失景观，并基于调制梯度更新，以平衡各模态影响力。实验覆盖多种场景与融合方式，显示该方法能有效缓解模态不平衡，增强整体鲁棒性。它为多模态和谐学习提供了一个通用即插即用方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-22o1ejtxj3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 634, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22o1ejtxj3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1399, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22o1ejtxj3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1414, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22o1ejtxj3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1332, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22o1ejtxj3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1334, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22o1ejtxj3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1402, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-22o1ejtxj3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 288, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-22o1ejtxj3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-22o1ejtxj3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 486, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-22o1ejtxj3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1399, \"height\": 290, \"label\": \"Table\"}]"
motivation: 多模态学习中主导模态会抑制其他模态，导致泛化能力下降。
method: 提出M-SAM，三步交替：识别主导模态、分解损失景观、调制梯度更新。
result: 在多种模态和融合设置下验证，M-SAM有效提升多模态学习鲁棒性。
conclusion: 模态感知的锐度最小化是解决模态不平衡的有效方法。
---

## Abstract
In multimodal learning, dominant modalities often overshadow others, limiting generalization. We propose Modality-Aware Sharpness-Aware Minimization (M-SAM), a model-agnostic framework that applies to many modalities and supports early and late fusion scenarios. In every iteration, M-SAM in three steps optimizes learning. \textbf{First, it identifies the dominant modality} based on modalities' contribution in the accuracy using Shapley. \textbf{Second, it decomposes the loss landscape}, or in another language, it modulates the loss to prioritize the robustness of the model in favor of the dominant modality, and \textbf{third, M-SAM updates the weights} by backpropagation of modulated gradients. This ensures robust learning for the dominant modality while enhancing contributions from others, allowing the model to explore and exploit complementary features that strengthen overall performance. Extensive experiments on four diverse datasets show that M-SAM outperforms the latest state-of-the-art optimization and gradient manipulation methods and significantly balances and improves multimodal learning. The code will be released.

---

## 论文详细总结（自动生成）

# 论文深度分析：《Modality-Aware SAM: Sharpness-Aware-Minimization Driven Gradient Modulation for Harmonized Multimodal Learning》

## 1. 核心问题与研究背景
- **多模态学习中的模态不平衡 (Modality Imbalance)**  
  多模态模型在训练时，某一“主导模态”常会因收敛速度更快、信息更易提取等原因，压制其他模态的学习，导致联合训练的性能不升反降，泛化能力受损。
- **现有方法的局限**  
  已有梯度调制方法（如 OGM‑GE、AGM 等）虽尝试平衡各模态贡献，却容易陷入尖锐极小值 (sharp minima)，加剧过拟合，未能从根本上改善损失景观的平坦性。  
- **本文动机**  
  通过优化器层面的改进，引导模型找到更平坦的极小值，使主导模态对其它模态的梯度扰动更具鲁棒性，同时为非主导模态保留足够的探索空间，最终实现多模态学习的和谐收敛。

## 2. 方法论：Modality‑Aware SAM (M‑SAM)
### 2.1 核心思想
- 将 **Sharpness‑Aware Minimization (SAM)** 扩展到多模态场景，并对主导模态定向施以锐度感知最小化，其余模态按普通损失更新。  
- 通过 **Shapley 值** 动态评估每个模态对当前准确率的贡献，识别主导模态，并在每个 mini‑batch 内自适应调节损失景观的分解。  

### 2.2 关键技术与算法流程
- **模态贡献分解**  
  利用 Shapley 值计算每个模态的贡献权重 `ν_m`，满足 `Σ ν_m = 1`，进而将总损失 `L` 分解为各模态损失之和：`L = Σ ν_m L`。  
- **主导模态识别**  
  每轮迭代中，选择 `ν_m` 最大的模态作为主导模态 `m_0`。  
- **损失景观调制与参数更新**  
  仅对主导模态的损失执行 SAM 的扰动最大化：  
  `ε = ρ · sign(∇L_{m_0})`, 计算扰动后的梯度 `∇L_{m_0}(θ + ε)`。  
  最终参数更新规则为：  
  `θ = θ − η( ∇L_{m_0}(θ + ε) + Σ_{m≠m_0} ∇L_m(θ) + λθ )`  
  其余模态仅采用当前点的梯度，不进行额外扰动。  
- **伪代码流程 (Algorithm 1)**  
  1. 采样 mini‑batch  
  2. 用 Shapley 值分解损失，获得主导模态 `m_d`  
  3. 计算主导模态损失 `L_d` 与非主导损失 `L_s`  
  4. 反向传播获得 `∇L_d` 与 `∇L_s`  
  5. 计算仅针对 `L_d` 的 SAM 扰动 `ε_d`  
  6. 更新参数：`θ ← θ − η (∇L_d(θ + ε_d) + ∇L_s(θ) + λθ)`  

### 2.3 收敛性分析
- 在 K‑smooth 和梯度有界的假设下，证明了 M‑SAM 的平均梯度收敛速度为 `O(log T/ √T)`，与传统 SGD 和 SAM 相当，且动态切换主导模态不影响收敛稳定性。

## 3. 实验设计
### 3.1 数据集
- **AV‑MNIST**：音频‑视觉双模态数字识别 (70k 样本)  
- **CREMA‑D**：语音情感识别，音频‑视觉双模态 (7,442 样本)  
- **UR‑Funny**：幽默检测，音频‑视觉‑文本三模态 (16,514 样本)  
- **AVE**：音视频事件定位 (4,143 样本)  

### 3.2 融合策略
- **早期融合 (Early Fusion)**：使用 MAXOUT 网络直接融合多模态特征。  
- **后期融合 (Late Fusion)**：各模态编码器保持独立，最后合并决策。  

### 3.3 基准方法
- **基础对比**：Joint‑Train (联合训练基线)  
- **优化/梯度调制方法**：MSES, MSLR, OGM‑GE, AGM, MM‑Pareto, CGGM, Recon‑Boost, SAM  
- 评估指标包括单模态精度 (`Acc_a, Acc_v, Acc_t`) 和多模态整体精度 (`Acc_mm`)，以及归一化过拟合缺口 τ。

### 3.4 实验设置
- 编码器：AV‑MNIST 和 CREMA‑D 使用 ResNet18；UR‑Funny 使用 Transformer。  
- 优化器：SGD (动量 0.9, 权重衰减 1e‑4)，初始学习率 1e‑3，每 70 轮衰减 0.1。  
- SAM 邻域半径 ρ 作为超参数。

## 4. 资源与算力
论文 **未明确说明** GPU 型号、数量、单次训练时长等具体硬件资源。仅提及使用 SGD 训练和标准学习率调度。从实验规模（四个数据集、两种融合、多种对比方法）推断，所需算力中等，但无确切数据可供量化。

## 5. 实验数量与充分性
- **实验组数** 丰富：覆盖 4 个数据集 × 2 种融合策略，共约 8 组主要实验，每组对比 10 种方法。  
- **额外分析**：  
  - 损失景观可视化（t‑SNE 投影）  
  - 训练过程曲线（单模态 / 多模态精度、过拟合缺口 τ）  
  - 相对提升幅度热力图 (relative improvement over Joint‑Train)  
- **消融与变体**：文中直接将 M‑SAM 与去掉模态感知的 vanilla SAM 对比，本质上构成消融实验。  
- **公平性**：所有方法使用相同骨干网络与数据预处理，尽可能确保对比客观。  
综上，实验设计较为全面，能支撑核心结论。

## 6. 主要结论与发现
- **性能提升显著**：M‑SAM 在所有数据集和融合方式下，均取得最优或次优的整体多模态精度，平均领先最接近的竞争者 (如 Recon‑Boost、CGGM) 约 1‑2 个百分点。  
- **平坦极小值效应**：损失景观视觉化和过拟合缺口曲线表明，M‑SAM 收敛到更平坦、泛化性更强的极小值区域，大幅缩小训练‑验证精度差。  
- **模态平衡机制生效**：M‑SAM 在提高主导模态稳定性的同时，非主导模态精度未发生退化，甚至在某些设置下有所提升，有效避免了“零和博弈”。  
- **优化器级通用性**：方法不依赖特定架构或融合方式，可即插即用于各类多模态模型。

## 7. 优点亮点
- **首个将 SAM 引入多模态学习** 并成功定向应用于主导模态，填补了优化器层面处理模态不平衡的空白。  
- **动态模态感知**：利用 Shapley 值实时识别主导模态，避免固定权重带来的不灵活。  
- **理论与实验结合**：提供收敛分析，并用丰富的实验（损失景观、过拟合缺口、多数据集）证明效果。  
- **方法简洁、独立于模型架构**，易于复现和集成。

## 8. 不足与局限
- **计算开销未评估**：M‑SAM 需额外计算 Shapley 值（需前向传播多个模态子集）和两次反向传播（一次扰动梯度，一次实际更新），论文未讨论由此增加的训练时间。  
- **高模态数下可扩展性**：Shapley 值计算复杂度随模态数指数增长，论文实验最多仅 3 模态，大模态数场景下的可行性未验证。  
- **超参数敏感度**：SAM 的邻域半径 ρ 和 Shapley 计算频率可能影响性能，但未详细报告调参实验。  
- **理论假设较强**：收敛性证明基于 K‑smooth 和梯度有界等理想假设，实际复杂模型中未必成立。  
- **缺少对采样噪声的研究**：主导模态识别依赖 mini‑batch 统计，小批次下可能存在噪声，影响稳定性，未深入讨论。  
- **未提供代码**：论文承诺接受后开源，当前尚无法直接复现（但方法流程描述清晰）。  

（完）
