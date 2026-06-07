---
title: "AutoToM: Scaling Model-based Mental Inference via Automated Agent Modeling"
title_zh: AutoToM：通过自动化智能体建模扩展基于模型的心智推理
authors: "Zhining Zhang, Chuanyang Jin, Mung Yao Jia, Shunchi Zhang, Tianmin Shu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=oeZZusZheP"
tags: ["query:affective-ai"]
score: 9.0
evidence: 结合贝叶斯逆向规划的自动化智能体建模用于心智理论，提升社交智能
tldr: 当前心智推理方法或依赖易出错的LLM提示，或使用僵化的手工模型。AutoToM提出自动化智能体建模方法，结合LLM后端与贝叶斯逆向规划，通过不确定性引导迭代优化，实现可扩展且鲁棒的心智推断。实验证明其跨领域泛化能力，推动了社交智能体发展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1303, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1362, \"height\": 1174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1290, \"height\": 625, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1379, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 576, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 571, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1363, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1338, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1359, \"height\": 1065, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oezzuszhep/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1370, \"height\": 704, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 585, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 951, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1219, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 950, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1384, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1261, \"height\": 588, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 549, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 775, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1005, \"height\": 551, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1305, \"height\": 588, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1326, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1310, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1327, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-oezzuszhep/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1532, \"height\": 666, \"label\": \"Table\"}]"
motivation: 现有ToM方法泛化性差且易出错。
method: 利用贝叶斯逆向规划和LLM自动构建并迭代优化智能体模型。
result: 在多个领域实现鲁棒且可解释的心智推理。
conclusion: 为构建具有社会智能的AI agent提供了新途径。
---

## Abstract
Theory of Mind (ToM), the ability to understand people's minds based on their behavior, is key to developing socially intelligent agents. Current approaches to ToM reasoning either rely on prompting Large Language Models (LLMs), which are prone to systematic errors, or use handcrafted, rigid agent models for model-based inference, which are more robust but fail to generalize across domains. In this work, we introduce *AutoToM*, an automated agent modeling method for scalable, robust, and interpretable mental inference. Given a ToM problem, *AutoToM* first proposes an initial agent model and then performs automated Bayesian inverse planning based on this model, leveraging an LLM backend. Guided by inference uncertainty, it iteratively refines the model by introducing additional mental variables and/or incorporating more timesteps in the context. Across five diverse benchmarks, *AutoToM* outperforms existing ToM methods and even large reasoning models. Additionally, we show that *AutoToM* can produce human‐like confidence estimates and enable online mental inference for embodied decision-making.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究背景**：心智理论（Theory of Mind, ToM）——根据行为理解他人内心状态（如信念、目标）的能力——是构建具有社会智能的AI的关键。当前主流方法面临两难困境。
*   **现有方法缺陷**：
    *   **基于LLM的提示工程**（如视角转换）：灵活性高，但在复杂场景下易产生系统性错误，稳健性不足。
    *   **基于手工模型的贝叶斯逆规划（BIP）**：稳健且可解释，但依赖领域专家手工指定代理模型（所含心理变量、因果结构），泛化能力极差，无法扩展至开放领域。
*   **核心问题**：如何构建一个**统一、自动化、可扩展且稳健**的机器心智推理框架，使其能在任意上下文中、对任意数量的代理、进行任意深度的递归推理，而无需人工干预模型构建。
*   **整体含义**：AutoToM 旨在通过**自动发现代理模型**并执行**自动贝叶斯逆规划**，弥合灵活性与稳健性之间的鸿沟，提供一种跨领域的通用ToM解决方案。

### 2. 方法论：核心思想与关键技术
AutoToM 由两大核心组件构成一个自迭代循环，其形式化基础是统一的模型化ToM公式。

*   **核心思想**：为给定的ToM问题自动构建一个最合适的概率代理模型（贝叶斯网络），并在该模型上执行贝叶斯逆规划来推断目标心理变量。通过“推断不确定性”引导模型结构迭代优化，最终以高置信度回答问题。
*   **关键技术细节**：
    *   **1. 自动贝叶斯逆规划 (Automated BIP)**：在给定代理模型 \(M\) 的情况下进行推理。
        *   **假设采样**：利用LLM为模型中的隐心理变量（如信念、目标、观察）生成一小批高质量假设，并通过局部条件概率筛选掉低概率假设以避免爆炸式增长。
        *   **贝叶斯推理**：使用LLM估算模型中的每个局部条件概率（如 \(P(a_t | b_t, g)\)），然后通过边际化计算目标变量的后验分布 \(P(q | X^{ts:t})\)。这完全不依赖手工变量表示，且天生支持高阶递归推理（I-POMDP）。
    *   **2. 自动代理模型发现 (Automated Model Discovery)**：迭代构建和改进模型 \(M\)。
        *   **信息提取**：从上下文中提取可观测变量 \(X^{1:t}\)（状态、动作、言语）并按时间线组织。
        *   **初始模型提出**：基于查询，提出一个仅含最少必要心理变量的简单模型，并从最后一个时间步开始推理。
        *   **模型调整**：根据模型效用 \(U(M, q) = R(M, q) - C(M)\) 进行迭代优化，其中奖励 \(R\) 是推理结果的负熵（鼓励低不确定性），成本 \(C\) 与模型包含的隐变量数量成正比（鼓励简约）。
            *   **变量调整**：当推理不确定时，按顺序尝试引入新的隐变量（如先引入“信念”，再引入“目标”，见表4），并接受能最大化效用增长的修改。
            *   **时间步调整**：若在当前时间窗口内变量调整无法显著提升效用，则向前扩展一个时间步 \(ts-1\)，纳入更多历史信息。
        *   整个循环持续至模型效用超过阈值或无更优模型为止。

### 3. 实验设计
*   **测试数据集/场景**：
    *   **ToM基准测试**：覆盖5个不同难度和类型的基准——**ToMi**（多代理，一阶/二阶信念），**BigToM**（开放场景，信念/行动），**MMToM-QA**（长上下文，多模态，信念/目标），**MuMA-ToM**（多代理社交目标，高阶推理），**Hi-ToM**（高阶递归信念，最多4阶）。
    *   **认知心理学实验**：复现并评估在经典认知研究（Baker et al. 2009, 2017）中的在线目标推断、欲望推断和信念推断任务上，模型置信度估计与人类判断的相关性。
    *   **具身辅助任务**：在“Online Watch-And-Help (O-WAH)”基准中，作为助手代理利用AutoToM进行在线目标推断以规划帮助动作，评估任务完成加速比。
*   **对比方法**：
    *   **基础LLM**：Llama 3.1 70B，GPT-4o，Gemini 2.0 Flash/Pro。
    *   **ToM提示增强LLM**：SymbolicToM，SimToM。
    *   **大型推理模型**：DeepSeek-R1，Gemini 2.0 Flash Thinking，o3-mini-high。
    *   **基于模型的ToM方法**：BIP-ALM，LIMP。
*   **评估指标**：准确率（QA benchmarks），Pearson相关系数（认知实验），任务加速比（具身辅助）。

### 4. 资源与算力
*   论文本身未提及任何模型训练过程，因此无需使用GPU进行训练。所有计算均基于对LLM的API调用（如GPT-4o，Gemini等），文中报告了**Token消耗量**和**推理时间**作为计算效率指标。例如在最具挑战的MMToM-QA基准上，AutoToM平均每个问题消耗8000 tokens，耗时8.5秒，与大型推理模型相比有计算成本上的竞争力。但未给出进行完整实验所需的总体API成本或时间估算。

### 5. 实验数量与充分性
实验设计全面且充分，兼顾内部有效性和外部泛化性。
*   **主实验**：在5个差异显著的ToM基准上，与3大类共11种基线方法进行全面对比。并分析了在不同问题类型、上下文长度、代理数量和递归深度下的性能，证明了AutoToM的鲁棒性。
*   **消融研究**：设计了5个消融变体（无假设约减、强制用POMDP、无变量调整、只看最后时间步、看所有时间步），验证了各核心组件的必要性和效率权衡。
*   **稳健性分析**：替换不同的LLM后端（Qwen3-235B，DeepSeek-V3，Gemini-2.5 Flash），在MMToM-QA上进行了敏感度测试；通过多次运行（不同随机种子）验证了结果的统计可靠性。
*   **应用拓展实验**：从QA延伸到认知建模（与人类数据对比）和具身决策，验证了方法的通用价值。所有对比均在同一信息输入和设定下进行，保证了公平性。

### 6. 主要结论与发现
*   **性能优越**：AutoToM在所有5个基准上的综合表现**显著优于**所有对比方法，包括大型推理模型（如o3-mini-high），且大幅超越了其自身的LLM后端（GPT-4o）。
*   **鲁棒且可扩展**：面对更长上下文、更多代理、更高阶递归等复杂条件时，AutoToM的性能波动远小于大型推理模型，表现出更强的可扩展性。
*   **认知合理性**：AutoToM产生的置信度估计与人类判断高度相关（如欲望推断中r=0.88），远优于GPT-4o和o3-mini-high，能复现人类心智推理模式。
*   **实际应用价值**：在具身辅助任务中，利用AutoToM进行在线目标推断，能使帮助者比随机基线和GPT-4o基线分别带来**21.4%和20.9%**的任务完成加速。
*   **可解释与可调试**：其模型结构为推理过程提供了可解释的“白箱”，甚至可结合人类反馈纠正模型错误，提升准确率。

### 7. 优点
*   **首创性**：首次实现了**完全自动化的代理模型发现**，无需任何手工模型指定即可进行基于模型的心智推理，解决了该范式泛化性的根本难题。
*   **方法融合**：巧妙地将LLM的灵活生成与贝叶斯推理的严格概率框架结合，利用LLM作为“世界模型”和“概率估计器”，替代了过去僵化的人工实现。
*   **自适应效率**：通过效用函数驱动迭代，实现了“按需建模”，在保证推理精度的同时最小化模型复杂度，避免了欠/过度建模。
*   **全面的实证检验**：不仅覆盖了多维度NLP基准，还拓展至认知科学和机器人学任务，多角度验证了框架的鲁棒性、仿人性和实用性。
*   **强可解释性**：输出是一个显式的概率图模型，推理过程和错误来源清晰可追溯，并展示了对人工反馈的兼容性。

### 8. 不足与局限
*   **多模态处理限制**：当前需借助独立的前置模块将视觉等多模态信息融合为文本，再由AutoToM处理，未实现端到端原生多模态推理。
*   **模型调整的稳健性**：自动模型发现过程有时可能无法准确识别哪些心理变量是相关的，导致构建的模型不够充分，从而回答错误。
*   **效率与成本的权衡**：虽然相较于部分大型推理模型有优势，但迭代搜索模型的过程仍需多次LLM调用，在需要极低延迟的实时交互场景可能受限。
*   **领域范围**：尽管测试领域已多样化，但仍局限在特定基准和任务，其在完全开放、无结构的真实世界社交互动中的泛化性有待进一步检验。
*   **依赖于LLM能力**：作为其核心计算后端的LLM本身存在的偏见或局限，会传导至AutoToM的概率估计和假设生成中，文中未深入探讨这种风险。

（完）
