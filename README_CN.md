# Awesome RSI 论文

[English](README.md) | 简体中文

**递归自我改进（Recursive Self-Improvement，RSI）**及相关自进化 AI 系统的精选阅读列表。

## 目录

- [综述与路线图](#rsi-surveys)
- [有界自我优化与经验积累](#rsi-bounded-refinement)
- [自训练与自生成反馈](#rsi-self-training)
- [自博弈与自动课程](#rsi-self-play)
- [代理设计与递归代码改进](#rsi-agent-improvement)
- [自动化研究与算法发现](#rsi-automated-research)
- [评测与安全](#rsi-evaluation-safety)
- [代码仓库与资源](#rsi-resources)

<a id="rsi-surveys"></a>
## 📚 综述与路线图

用于理解 RSI 研究全貌的综合综述。

- [自进化 AI 代理综述](https://arxiv.org/abs/2508.07407)<sup>†</sup> - 围绕系统输入、代理系统、环境和优化器组织自进化代理研究，并专门讨论评测与安全问题。

<a id="rsi-bounded-refinement"></a>
## 🔁 有界自我优化与经验积累

在不改变基础模型权重的情况下，通过推理时反馈或持久经验改善行为的系统。

- [Self-Refine](https://arxiv.org/abs/2303.17651) - 让同一个 LLM 同时充当生成器、批评器和改写器，在无需额外训练的测试时反馈循环中迭代优化答案。
- [Reflexion](https://arxiv.org/abs/2303.11366) - 将任务反馈转化为语言反思并写入情景记忆，以改进代理后续尝试的决策。
- [Voyager](https://arxiv.org/abs/2305.16291) - 结合自动课程、持续扩展的可执行技能库和环境反馈驱动的迭代提示，实现具身终身学习。

<a id="rsi-self-training"></a>
## 🧠 自训练与自生成反馈

将模型生成的推理、指令、奖励、提示或更新指令转化为持久能力变化的方法。

- [STaR](https://arxiv.org/abs/2203.14465) - 反复生成推理过程、筛选答案正确的轨迹并据此微调，从而自举模型的推理能力。
- [Self-Instruct](https://arxiv.org/abs/2212.10560) - 自行生成和筛选指令数据，以极少的人工标注提升模型的指令遵循能力。
- [Promptbreeder](https://arxiv.org/abs/2309.16797) - 同时进化任务提示与负责改进它们的变异提示，构成自指式提示优化循环。
- [Self-Rewarding Language Models](https://arxiv.org/abs/2401.10020) - 在迭代偏好优化中让语言模型自身担任评判者，使指令遵循能力和奖励质量共同提升。
- [SEAL](https://arxiv.org/abs/2506.10943) - 让模型生成自己的训练数据与更新指令，并用更新后的下游表现强化有效的持久自编辑。
- [Co-RL](https://arxiv.org/abs/2608.17253)<sup>†</sup> - 利用多样且参数解耦的同伴模型提供奖励，在无标签条件下学习推理，同时缓解相关错误引发的训练坍缩。
- [RecurSE](https://arxiv.org/abs/2608.24231)<sup>†</sup> - 协同进化可训练的规则评判器及其同步策略副本检查器，并监测奖励有效性以在退化前停止有界自我改进。

<a id="rsi-self-play"></a>
## 🎮 自博弈与自动课程

在学习者能力边界附近自动生成问题，并以求解进展作为改进信号的系统。

- [Absolute Zero Reasoner（AZR）](https://arxiv.org/abs/2505.03335)<sup>†</sup> - 由单一模型提出并解决可验证的代码推理任务，在无外部数据条件下共同进化课程与推理能力。
- [R-Zero](https://arxiv.org/abs/2508.05004)<sup>†</sup> - 分别优化挑战者与求解者模型，使两者从零任务和零标签开始协同进化出针对性的推理课程。
- [SOAR](https://arxiv.org/abs/2601.18778)<sup>†</sup> - 采用非对称自博弈与双层元强化学习，奖励能够生成踏脚石问题并帮助学生突破初始不可解任务的教师。
- [J-Zero](https://arxiv.org/abs/2608.26582)<sup>†</sup> - 从零数据协同进化挑战者、求解者和评判者，并利用答案生成方式所确定的偏好顺序适配不可验证领域中的评估。

<a id="rsi-agent-improvement"></a>
## 🛠️ 代理设计与递归代码改进

优化提示、工作流、脚手架、代理逻辑、评估器或负责后续改进之实现代码的系统。

- [STOP](https://arxiv.org/abs/2310.02304) - 将由语言模型驱动的代码改进器应用于它自己的脚手架程序，从而得到实证表现更强的程序优化器。
- [Meta Agent Search](https://arxiv.org/abs/2408.08435) - 让元代理基于持续扩展的档案编写更强的代理设计，搜索范围涵盖提示、工具与工作流。
- [Gödel Agent](https://arxiv.org/abs/2410.04444) - 在高层目标引导下递归重写自身代理逻辑，而不依赖固定的人工设计优化流程。
- [Darwin Gödel Machine（DGM）](https://arxiv.org/abs/2505.22954) - 进化由编程代理组成的分支档案，让代理修改自身代码并在编程基准上实证验证改进。
- [Red Queen Gödel Machine（RQGM）](https://arxiv.org/abs/2606.26294)<sup>†</sup> - 在受控的非平稳效用下协同进化代理与评估器，将自我改进扩展到固定基准之外。

<a id="rsi-automated-research"></a>
## 🔬 自动化研究与算法发现

闭合更多研究环节，并能为 AI 本身或其计算基础设施带来改进的系统。

- [The AI Scientist](https://arxiv.org/abs/2408.06292) - 在迭代式科学发现循环中自动完成创意生成、代码实现、实验执行、论文写作与模拟评审。
- [AlphaEvolve](https://arxiv.org/abs/2506.13131) - 结合 LLM 代码生成、自动评估器和进化搜索来发现并优化算法，其中包括用于 AI 训练的组件。

<a id="rsi-evaluation-safety"></a>
## 🛡️ 评测与安全

衡量 AI 研发能力并分析自我改进循环中尤为重要的失效模式。

- [极端风险模型评测](https://arxiv.org/abs/2305.15324) - 区分危险能力评测与对齐评测，用于识别和治理可能造成严重后果的模型行为。
- [RE-Bench](https://arxiv.org/abs/2411.15114) - 在真实、开放式的机器学习研发工程任务上，将前沿代理与人类专家进行比较。
- [自改进代理脆弱性](https://arxiv.org/abs/2608.18066)<sup>†</sup> - 揭示基于记忆的自我改进会放大评测方差和任务顺序效应，因此主张采用多次运行与随机任务顺序进行压力测试。
- [AI4AI-Bench](https://arxiv.org/abs/2608.20318)<sup>†</sup> - 在固定隐藏评估器和受控算力下，测试代理能否重写十个冻结研究仓库中的训练算法。

<a id="rsi-resources"></a>
## 🗂️ 代码仓库与资源

用于持续追踪或复现该领域的动态文献地图、实现代码与评测环境。

- [Awesome Self-Evolving Agents](https://github.com/ANative-Lab/Awesome-Self-Evolving-Agents) - 自进化代理综述的配套仓库，按照被优化的系统组件对论文进行分类。
- [DGM 代码](https://github.com/jennyzzt/dgm) - Darwin Gödel Machine 的官方实现与实验产物。
- [RE-Bench 环境](https://github.com/METR/ai-rd-tasks) - RE-Bench 使用的开源 AI 研发任务环境、参考资料与评测基础设施。

## 贡献

欢迎补充建议。请将论文加入具体的类别，并使用 `[核心方法名称](论文链接) - 改进对象、改进机制和反馈信号。` 的格式。
