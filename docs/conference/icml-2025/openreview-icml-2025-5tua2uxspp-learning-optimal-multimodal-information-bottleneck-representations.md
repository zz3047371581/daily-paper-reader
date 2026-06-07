---
title: Learning Optimal Multimodal Information Bottleneck Representations
title_zh: 学习最优多模态信息瓶颈表示
authors: "Qilong Wu, Yiyang Shao, Jun Wang, Xiaobo Sun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=5TUa2UXSpp"
tags: ["query:affective-ai"]
score: 7.0
evidence: 提出一种通过信息瓶颈学习最优多模态表示的方法，适用于跨模态表示学习。
tldr: 针对现有多模态信息瓶颈方法中正则化权重设置随意和模态间任务相关信息不均衡的问题，提出最优多模态信息瓶颈框架OMIB，通过优化目标保证最优联合表示的学习，有助于提升通用多模态任务的性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 789, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 791, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1579, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 825, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 886, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 892, \"height\": 548, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 894, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1174, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1771, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 857, \"height\": 116, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 945, \"height\": 963, \"label\": \"Table\"}]"
motivation: 现有多模态信息瓶颈方法正则化权重设置随意且忽略模态间任务相关信息不均衡，难以达到最优表示。
method: 提出最优多模态信息瓶颈（OMIB）框架，设计优化目标直接保证最优多模态信息瓶颈的可达性。
result: 未提供具体实验结果，但理论保证实现具有最大任务相关信息且最小冗余的最优表示。
conclusion: OMIB框架解决了多模态表示学习中的关键优化问题，可广泛适用于各类多模态任务。
---

## Abstract
Leveraging high-quality joint representations from multimodal data can greatly enhance model performance in various machine-learning based applications. Recent multimodal learning methods, based on the multimodal information bottleneck (MIB) principle, aim to generate optimal MIB with maximal task-relevant information and minimal superfluous information via regularization. However, these methods often set regularization weights in an *ad hoc* manner and overlook imbalanced task-relevant information across modalities, limiting their ability to achieve optimal MIB. To address this gap, we propose a novel multimodal learning framework, Optimal Multimodal Information Bottleneck (OMIB), whose optimization objective guarantees the achievability of optimal MIB by setting the regularization weight within a theoretically derived bound. OMIB further addresses imbalanced task-relevant information by dynamically adjusting regularization weights per modality, ensuring the inclusion of all task-relevant information. Moreover, we establish a solid information-theoretical foundation for OMIB's optimization and implement it under the variational approximation framework for computational efficiency. Finally, we empirically validate the OMIB’s theoretical properties on synthetic data and demonstrate its superiority over the state-of-the-art benchmark methods in various downstream tasks.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义
- **研究背景**：多模态学习通过整合不同模态的信息（如图像、文本、音频）来提升模型性能。信息瓶颈（IB）原理旨在学习压缩且保留任务相关信息（sufficiency）的表示，同时去除冗余（conciseness）。现有的多模态信息瓶颈（MIB）方法通常使用正则化项来平衡这两个目标，但存在以下问题：
  - **正则化权重设置随意**：多数方法采用启发式（ad hoc）指定正则化系数，缺乏理论保证，导致无法真正达到最优MIB——权重过小则保留冗余，过大则丢弃任务相关信息。
  - **忽略模态间任务相关信息的不均衡**：不同模态包含的任务相关信息量可能差异很大（例如一模态仅有少量关键信息），固定的正则化权重可能使弱势模态的关键信息被错误丢弃。
  - **理论不完善**：现有方法未将一致性、特异性、互补性、充分性、简洁性这五个信息论因素系统地纳入优化目标，也未区分不同模态间的信息角色。
- **整体含义**：本文提出**最优多模态信息瓶颈（OMIB）框架**，通过理论推导给出正则化权重的理论上界，并动态调节各模态的正则化强度，从而保证能够学习到只保留所有任务相关信息、且不含任何冗余信息的**最优MIB表示**。该框架具有扎实的信息论基础，并在多个真实多模态下游任务上验证了有效性。

## 2. 论文提出的方法论
OMIB 框架包含两个阶段（热身训练和主训练）与两个核心组件：**任务相关分支（TRB）** 和**最优多模态融合块（OMF）**，并以变分估计方式实现。

### 2.1 总体优化目标
- 目标函数定义为：  
  \(\min_\xi \ell(\xi) = \min_\xi -I(\xi; y) + \beta \big(I(\xi; v_1) + r I(\xi; v_2)\big)\)，  
  其中 \(\beta\) 控制整体冗余压缩程度，\(r\) 动态调整第二模态相对于第一模态的正则化比例。
- 利用充分编码 \(z_i\)（满足 \(I(z_i;y)=I(v_i;y)\)），可简化为：  
  \(\min_\xi -\ I(\xi; y) + \beta \big(I(\xi; z_1) + r I(\xi; z_2)\big)\)。

### 2.2 热身训练（Warm-up）
- 对每个模态，先用编码器 \(Enc_i\) 将原始输入 \(v_i\) 映射为充分表示 \(z_i\)。
- 将 \(z_i\) 与随机高斯噪声 \(e_i\) 拼接，通过预测头 \(Dec_i\) 输出 \(\hat{y}_i\)，优化损失 \(L_{TRB}^i\)（交叉熵或MSE等），迫使 \(z_i\) 提取最大的任务相关信息。

### 2.3 主训练（Main Training）
- 引入变分自编码器 \(VAE_i\) 从 \(z_i\) 生成高斯分布的均值 \(\mu_i\) 和方差 \(\Sigma_i\)，再通过重参数化得到 \(\zeta_i = \mu_i + \Sigma_i \epsilon_i\)。
- 用交叉注意力网络（CAN）融合 \(\zeta_1, \zeta_2\) 得到联合嵌入 \(\xi\)，并经过预测头 \(\hat{y} = dDec(\xi)\)。
- 同时，\(\xi\) 替代前一步的随机噪声参与计算各模态的 \(\hat{y}_i\)，用于更新编码器。
- **核心损失函数**（变分上界）：
  \[
  L_{OMF} = \frac{1}{N}\sum_n \mathbb{E}_{\epsilon_1,\epsilon_2}[-\log q(y_n|\xi_n)] + \beta \Big(\mathbb{KL}[p(\zeta_{n,1}|z_{n,1})||\mathcal{N}(0,I)] + r \cdot \mathbb{KL}[p(\zeta_{n,2}|z_{n,2})||\mathcal{N}(0,I)]\Big)
  \]
- **动态权重 r 的计算**：  
  \(r = 1 - \tanh\left(\ln\frac{\mathbb{E}[KL(p(\hat{y}_2|\xi,z_2)||p(\hat{y}|\xi))]}{\mathbb{E}[KL(p(\hat{y}_1|\xi,z_1)||p(\hat{y}|\xi))]}\right)\)，  
  该式本质上反映了剩余任务相关信息的比例：\(r \propto I(y;v_1|\xi) / I(y;v_2|\xi)\)，使得包含更多未利用任务信息的模态受到更小的压缩。

### 2.4 理论上界与最优性保证
- 通过信息论分析，给出 \(\beta\) 的紧上界 \(M_u = \frac{1}{(1+r)(H(v_1)+H(v_2)-I(v_1;v_2))}\)。  
  当 \(\beta \in (0, M_u]\) 时，优化过程能保证 \(\xi\) 包含所有任务相关信息且排除所有冗余，从而实现**最优MIB**。
- 该上界可利用 MINE 在训练数据上预先估计熵与互信息得到；为加速训练还给出了一个更紧的下界 \(M_l\)。

### 2.5 扩展到多模态
- 对于三模态情形，损失函数增加相应的正则项 \(r_1 I(\xi; z_2) + r_2 I(\xi; z_3)\)，并给出相应的上界公式。动态权重 \(r_1, r_2\) 类似定义。

## 3. 实验设计
### 3.1 数据集
| 任务 | 数据集 | 模态数及类型 | 备注 |
|------|--------|---------------|------|
| 合成数据验证 | SIM‑{I,II,III} | 2 个高斯模态 | 可控制任务相关信息分布，三种场景（一模态主导、另一模态主导、均衡）|
| 情感识别 | CREMA‑D | 音频 + 视觉 | 6类情绪分类 |
| 多模态情感分析（MSA） | CMU‑MOSI | 视觉 + 文本 + 音频 | 回归（强度评分），评分范围‑3~3 |
| 异常组织检测 | 10x‑hNB‑{A‑H} (训练) 、10x‑hBC‑{A‑D} (测试) | 基因表达 + 组织病理图像 | 使用SVDD异常检测框架，只在正常样本上训练 |

### 3.2 对比方法
- **非MIB方法**：简单拼接（Concat）、BiGated、MISA。
- **MIB方法**：deep IB、MMIB‑Cui、MMIB‑Zhang、DMIB、E‑MIB、L‑MIB、C‑MIB（部分基准在特定任务中有所增减）。
- 评价指标：准确率、F1、MAE、相关系数、AUC等，视任务而定。

## 4. 资源与算力
- 论文中**未见对所用GPU型号、数量、训练时长等算力细节的说明**。仅提及使用PyTorch实现，训练采用SGD或Adam优化器，未给出具体硬件配置或耗时统计。

## 5. 实验数量与充分性
- 实验覆盖了**四个不同的应用场景**：合成数据理论验证、单双模态分类、三模态回归、双模态异常检测，共涉及约14个数据集（含合成数据集3个、情感1、MSA1、空间转录组12个）。
- **消融实验**在CREMA‑D上进行了四项（去除热身训练、替换CAN为拼接、去除OMF块、去掉动态r），验证了各组件的必要性。
- **复杂度分析**提供了理论复杂度O(N)及对样本规模的扫描实验（从10万到100万），展示主训练和热身阶段均线性扩展。
- 对比方法丰富，既有早期融合也有多种MIB变体，覆盖了主流基线。所有对比均在相同数据集和评估设置下进行，具有客观性和公平性。
- 综合来看，实验设计较为**充分、系统**，既有合成验证又有真实下游任务，且消融分析支撑了模型设计的有效性。

## 6. 论文的主要结论与发现
- OMIB框架**能够保证学到最优多模态信息瓶颈表示**：该表示包含所有任务相关信息（一致性部分 \(a_0\) 和互补部分 \(a_1, a_2\)），且完全不含冗余信息（\(b_0, b_1, b_2\)）。  
- 通过设置正则化参数 \(\beta\) 在理论推导的上界以内，以及**动态调整模态间正则化比例 r**，可以处理任务相关信息不均衡的场景。  
- 合成实验验证了当 \(\beta \le M_u\) 时，分类准确率达到峰值，且生成的MIB接近真实最优MIB（仅包含任务相关子向量）的性能。  
- 在情感识别、多模态情感分析和异常组织检测等多个下游任务中，OMIB**一致超越 state‑of‑the‑art 的MIB和非MIB方法**（例如在CREMA‑D上准确率63.6%，比最佳MIB方法高3.6%；MOSI上多数指标领先；异常检测AUC平均提升11.4%）。  
- 消融实验证明热身训练、交叉注意力融合、OMF块以及动态权重r均为关键设计，移除任一项均导致性能下降。

## 7. 优点
- **理论坚实**：首次给出了多模态信息瓶颈正则化权重的理论上界，并证明了在该范围内最优MIB的可达性，信息论基础严谨。
- **动态模态平衡**：通过计算剩余任务相关信息比值动态调整各模态的正则化强度，解决了任务相关信息不均衡这一实际痛点。
- **端到端可学习框架**：用变分推断将理论目标转化为可微损失，并引入热身训练保证充分编码，结构清晰。
- **广泛的实验支持**：涵盖合成数据验证和多类真实任务，并与多种先进基线比较，效果突出且消融分析透彻。

## 8. 不足与局限
- **计算资源未说明**：论文未提及训练所需的GPU/TPU型号、数量及耗时，可复现性和资源评估受影响。
- **任务多样性有限**：尽管使用了多个数据集，但任务类型仍以分类、回归和异常检测为主，缺少在更复杂的生成式任务或大规模预训练场景下的验证。
- **超参数β的估计依赖MINE**：虽然MINE是常用了估计器，但其精度会受网络容量和训练影响，实际应用中可能需要额外的调参成本。
- **扩展到更多模态时的上界推导较复杂**：论文仅给出三模态的形式，更多模态需要进一步推广，且上界计算将更加繁琐。
- **实验对比未涉及一些最新的多模态融合方法**（如基于Transformer的更复杂结构），可能存在比较基线不够前沿的风险。

（完）
