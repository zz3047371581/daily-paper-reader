---
title: "OpenOmni: Advancing Open-Source Omnimodal Large Language Models with Progressive Multimodal Alignment and Real-time Emotional Speech Synthesis"
title_zh: OpenOmni：通过渐进多模态对齐与实时情感语音合成推进开源全模态大语言模型
authors: "Run Luo, Ting-En Lin, Haonan Zhang, Yuchuan Wu, Xiong Liu, Yongbin Li, Longze Chen, Jiaming Li, Lei Zhang, Xiaobo Xia, Hamid Alinejad-Rokny, Fei Huang, Min Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=4iehXI36QG"
tags: ["query:affective-ai"]
score: 9.0
evidence: 实时情感语音合成与全模态对齐，用于开源大语言模型
tldr: 针对开源全模态模型数据集稀缺和实时情感语音合成难题，提出OpenOmni两阶段训练框架。通过渐进式多模态对齐和语音生成，构建了同时理解图文语音并合成情感语音的开源全模态大语言模型，在多项评测中达到领先水平，推动了情感交互AI的发展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1397, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 665, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1340, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 563, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1181, \"height\": 668, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1035, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1475, \"height\": 428, \"label\": \"Table\"}]"
motivation: 开源全模态模型缺乏高质量数据集，实时情感语音合成不足。
method: 提出两阶段训练框架：多模态对齐和语音生成，融合情感合成。
result: OpenOmni在图文语音理解和情感语音生成上取得顶尖性能。
conclusion: 为开源社区提供了强大的全模态情感交互模型。
---

## Abstract
Recent advancements in omnimodal learning have significantly improved understanding and generation across images, text, and speech, yet these developments remain predominantly confined to proprietary models. The lack of high-quality omnimodal datasets and the challenges of real-time emotional speech synthesis have notably hindered progress in open-source research. To address these limitations, we introduce OpenOmni, a two-stage training framework that integrates omnimodal alignment and speech generation to develop a state-of-the-art omnimodal large language model. In the alignment phase, a pretrained speech model undergoes further training on image-text tasks, enabling (near) zero-shot generalization from vision to speech, outperforming models trained on tri-modal datasets. In the speech generation phase, a lightweight decoder is trained on speech tasks with direct preference optimization, which enables real-time emotional speech synthesis with high fidelity. Extensive experiments demonstrate that OpenOmni surpasses state-of-the-art models across omnimodal, vision-language, and speech-language benchmarks. It achieves a 4-point absolute improvement on OmniBench over the leading open-source model VITA, despite using 5$\times$ fewer training examples and a smaller model size (7B vs. 7$\times$8B). Besides, OpenOmni achieves real-time speech generation with less than 1 second latency at non-autoregressive mode, reducing inference time by 5$\times$ compared to autoregressive methods, and improves emotion classification accuracy by 7.7\%. The codebase is available at https://github.com/RainBowLuoCS/OpenOmni.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究背景**：全模态学习（Omnimodal Learning）在图像、文本和语音的理解与生成方面取得了显著进步，但主要局限于闭源商业模型（如GPT-4o）。
- **核心问题**：开源全模态大语言模型（OLLMs）面临三大根本性挑战，制约了其实际应用：
    1.  **数据稀缺**：高质量的真三模态（图像-语音-文本）数据集极其稀缺且昂贵，导致跨模态对齐效果差。
    2.  **高推理延迟**：现有模型多采用自回归（AR）架构或级联外部TTS模块，推理速度慢，无法实现实时交互。
    3.  **情感表达缺失**：生成的语音语调平淡、机械，缺乏基于对话上下文的情感一致性，无法进行自然且有感染力的交互。
- **整体含义**：论文提出**OpenOmni**，一个完全开源的两阶段训练框架，旨在以较低的数据和计算成本，解决上述挑战，构建能同时理解图文语音并生成实时、富有情感表现力语音的全模态助手。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：**渐进式多模态对齐**与**文本引导的语音生成**。
    - **渐进式对齐**：以文本为枢纽，将全模态对齐分解为“语音-文本”和“图像-文本”两个连续的阶段，避免直接依赖稀缺的三模态数据，实现从视觉到语音的（近）零样本泛化。
    - **语音生成**：集成轻量级语音解码器，支持非自回归生成以实现实时响应，并利用直接偏好优化（DPO）实现情感一致的语音合成。
- **关键技术细节**：
    1.  **语音-文本对齐**：使用语音编码器 \( h_s \) 提取语音特征 \( x_s \)，通过语言模型目标 \( \mathcal{L}_{s-t} = -\sum \log p_\phi(x_t | h_s(x_s)) \) 进行预训练。
    2.  **图像-文本对齐**：使用图像编码器 \( h_v \) 提取视觉特征 \( x_v \)，分两阶段进行：
        - **预训练**：使用目标 \( \mathcal{L}_{v-t} = -\sum \log p_\theta(x_t | h_v(x_v)) \) 对齐视觉模块与大语言模型（LLM）。
        - **指令微调**：使用 \( \mathcal{L}_{Iv-t} = -\sum \log p_\theta(x_{t,a} | h_v(x_v), f_{LLM}(x_{t,q})) \) 进行微调。论文指出，此时模型能隐式地将视觉-文本对齐能力泛化到语音指令上 (\( f_{LLM}(x_{t,q}) \approx f_{LLM}(h_s(x_{s,q})) \) )。
    3.  **文本引导的语音生成**：
        - **语音解码器**：一个包含混合专家（MoE）层和少量Transformer层的轻量级解码器。它接收LLM的输出隐状态，通过文本引导模块（TGM）融合后，生成离散语音单元序列。
        - **实时生成**：采用联结时序分类（CTC）损失 \( \mathcal{L}_{CTC} = -\log \sum_{A \in \Delta(x_{u,a})} \prod p_\psi(x_{u,a}^i | o) \) 进行非自回归（NAR）训练，实现并行解码。
        - **情感优化**：提出CTC-DPO算法 \( \mathcal{L}_{CTC-DPO} = -\mathbb{E}[\log \sigma(\beta \log \frac{\pi^*(y_w|x)}{\pi_{ref}(y_w|x)} - \beta \log \frac{\pi^*(y_l|x)}{\pi_{ref}(y_l|x)})] \)，使用情感一致/中性语音对作为偏好数据，微调策略模型 \( \pi^* \)，使其生成情感自知的语音。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法
- **数据集**：
    - **对齐阶段**：WeNetSpeech， LibriSpeech， AIShell-4 等共8000小时双语语音数据；LLaVA-Pretrain-595K 和 MMEvol 图文数据集。
    - **语音生成阶段**：自建 **O2S-300K** 数据集（8000小时双语合成语音）。
    - **情感优化阶段**：自建 **EO2S-9K** 数据集（基于Plutchik情感模型的9类情感偏好对数据）。
- **Benchmarks**:
    - **全模态理解**：OmniBench， AV-Odyssey Bench。
    - **视觉-语言**：MMBench-EN/CN， MMStar， HallusionBench， MathVista， MMMU 等8个基准。
    - **语音-语言**：AIShell-2， Librispeech（评估词错误率 WER）。
    - **情感语音合成**：EO2S-9K 测试集（用 Emotion2Vec 分类准确率评估）。
- **对比方法**：
    - **全模态模型**：AnyGPT， Video-SALMONN， UnifiedIO-2， Baichuan-Omni， **VITA**， EMOVA 等。
    - **视觉-语言模型**：GPT-4o/mini， MiniCPM-V2.5， Qwen2-VL， Cambrain-1， MMEvol 等。
    - **语音-语言模型**：SpeechT5， SALMONN， Mini-Omni， Freeze-Omni， Qwen2-Audio。

### 4. 资源与算力
- **硬件配置**：所有实验均在 **8 × NVIDIA A100-80G** GPU 上完成。
- **训练时长/成本**：训练分五个子阶段，总计约664 GPU小时。
    - 语音-文本对齐: 40小时。
    - 图像-文本预训练: 80小时。
    - 图像-文本指令微调: 500小时。
    - 语音解码器训练: 36小时。
    - 情感DPO训练: 8小时。

### 5. 实验数量与充分性
- **实验数量**：进行了约5组主要实验，包括全模态、视觉-语言、语音-语言理解任务评估，情感语音生成评估，以及多组消融实验。
- **实验充分性与公平性**：实验设计**充分且公平**。
    - **覆盖广度大**：评测覆盖了三大模态的十多个主流基准，与大量闭源/开源模型进行了全面对比。
    - **结论可靠**：消融实验涵盖了TGM模块、解码器层数与专家数、LLM冻结策略、对齐顺序与联合训练策略等多个维度，为论文主张提供了坚实证据。
    - **对比公平**：强调了与领先模型VITA在训练数据量（1.6M vs. 5M）和模型参数量（7B vs. 7×8B）更少的情况下进行对比，凸显了方法的高效性。

### 6. 论文的主要结论与发现
- **高效的全模态对齐**：OpenOmni仅用图文和语音-文本双模态数据，实现了（近）零样本的全模态泛化，在全模态基准OmniBench上以37.40分超越使用三模态数据训练的VITA（33.45分）。
- **顶尖的多模态性能**：在视觉-语言和语音-语言基准上，OpenOmni性能均达到或超越领先的开源模型。
- **实时语音生成**：设计的轻量级NAR语音解码器实现了低于1秒的生成延迟，推理速度是自回归方法的5倍。
- **情感语音合成**：CTC-DPO算法显著提升了情感语音的表现力和自洽性，情感分类准确率相对提升7.7%。
- **训练策略高效**：渐进式多阶段训练相比联合训练能大幅降低显存占用（40GB vs 90GB），且获得具有竞争力的结果，验证了其在低资源场景下的实用性和高效性。

### 7. 优点
- **问题导向清晰**：精准识别并解决了开源全模态模型面临的三个核心挑战（数据、延迟、情感）。
- **方法论创新**：提出的“以文本为枢纽的渐进式对齐”和“CTC-DPO情感语音优化”思路新颖且有效，显著降低了对稀缺三模态数据的依赖。
- **架构高效**：轻量级NAR语音解码器设计在保证生成质量的同时实现了实时性，工程价值高。
- **实验论证扎实**：全面的基准测试、与强基线的公平对比以及详尽的消融实验，强有力地支撑了所有核心论点。
- **完全开源**：承诺完全开源，并提供详细的实验设计与复现细节，对社区研究和创新具有重要推动作用。

### 8. 不足与局限
- **语言支持有限**：实验和模型主要集中于中英双语，未在更多语言上进行训练或验证，多语言泛化能力有待考证。
- **情感类别受限**：情感语音合成基于固定的9类Plutchik模型，对于更复杂、微妙或混合情感的生成能力未作探讨。
- **生成鲁棒性**：非自回归（NAR）模式虽快但质量略低于自回归模式，模型的抗噪性（如对错误LLM输出的容忍度）主要通过TGM缓解，在极端情况下的表现可能受限。
- **客观指标局限**：情感语音的评估依赖Emotion2Vec的分类准确率，对语音自然度、表现力等主观体验的评估不足，缺乏人类评估。
- **实验规模**：未进行多次随机种子实验以报告误差范围，实验统计显著性方面存在不足。

（完）
