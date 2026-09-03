# Awesome RSI Papers

[English](README.md) | [简体中文](README_CN.md)

A reading list on **recursive self-improvement (RSI)** and closely related self-evolving AI systems.

## Contents

- [Surveys and Roadmaps](#rsi-surveys)
- [Bounded Self-Refinement and Experience](#rsi-bounded-refinement)
- [Self-Training and Self-Generated Feedback](#rsi-self-training)
- [Self-Play and Automated Curricula](#rsi-self-play)
- [Agent Design and Recursive Code Improvement](#rsi-agent-improvement)
- [Automated Research and Algorithm Discovery](#rsi-automated-research)
- [Evaluation and Safety](#rsi-evaluation-safety)
- [Repositories and Resources](#rsi-resources)

<a id="rsi-surveys"></a>
## 📚 Surveys and Roadmaps

An overview for understanding the RSI landscape.

- [Self-Evolving AI Agents Survey](https://arxiv.org/abs/2508.07407)<sup>†</sup> - Organizes self-evolving agents around system inputs, agent systems, environments, and optimizers, with dedicated coverage of evaluation and safety.

<a id="rsi-bounded-refinement"></a>
## 🔁 Bounded Self-Refinement and Experience

Systems that improve behavior through inference-time feedback or persistent experience without changing the base model's weights.

- [Self-Refine](https://arxiv.org/abs/2303.17651) - Uses one LLM as generator, critic, and refiner in an iterative test-time feedback loop without additional training.
- [Reflexion](https://arxiv.org/abs/2303.11366) - Converts task feedback into verbal reflections stored in episodic memory to improve an agent's later attempts.
- [Voyager](https://arxiv.org/abs/2305.16291) - Combines an automatic curriculum, a growing executable skill library, and environment-grounded iterative prompting for lifelong embodied learning.

<a id="rsi-self-training"></a>
## 🧠 Self-Training and Self-Generated Feedback

Methods that turn model-generated reasoning, instructions, rewards, prompts, or update directives into lasting capability changes.

- [STaR](https://arxiv.org/abs/2203.14465) - Bootstraps reasoning by repeatedly generating rationales, filtering for successful answers, and fine-tuning on the retained traces.
- [Self-Instruct](https://arxiv.org/abs/2212.10560) - Generates and filters its own instruction data to improve instruction following with minimal human annotation.
- [Promptbreeder](https://arxiv.org/abs/2309.16797) - Evolves both task prompts and the mutation prompts that improve them, creating a self-referential prompt-optimization loop.
- [Self-Rewarding Language Models](https://arxiv.org/abs/2401.10020) - Uses the language model itself as a judge during iterative preference optimization so both instruction following and reward quality can improve.
- [SEAL](https://arxiv.org/abs/2506.10943) - Lets a model generate its own training data and update directives, using downstream performance to reinforce effective persistent self-edits.
- [Co-RL](https://arxiv.org/abs/2608.17253)<sup>†</sup> - Uses rewards from diverse, parameter-decoupled peer models to learn reasoning without labels while reducing correlated-error collapse.
- [RecurSE](https://arxiv.org/abs/2608.24231)<sup>†</sup> - Co-evolves a trainable rubric judge and synchronized policy-copy checker while monitoring reward validity to stop bounded self-improvement before it degrades.

<a id="rsi-self-play"></a>
## 🎮 Self-Play and Automated Curricula

Systems that generate problems near the learner's frontier and use solving progress as the improvement signal.

- [Absolute Zero Reasoner (AZR)](https://arxiv.org/abs/2505.03335)<sup>†</sup> - A single model proposes and solves verifiable code-reasoning tasks, evolving its curriculum and reasoning ability without external data.
- [R-Zero](https://arxiv.org/abs/2508.05004)<sup>†</sup> - Separately optimizes Challenger and Solver models that co-evolve a targeted reasoning curriculum from zero pre-existing tasks or labels.
- [SOAR](https://arxiv.org/abs/2601.18778)<sup>†</sup> - Uses asymmetric self-play and bilevel meta-RL to reward a teacher for producing stepping-stone problems that improve a student on initially unsolved tasks.
- [J-Zero](https://arxiv.org/abs/2608.26582)<sup>†</sup> - Co-evolves Challenger, Solver, and Judge models from zero data, using production-derived preference orderings to adapt evaluation even in unverifiable domains.

<a id="rsi-agent-improvement"></a>
## 🛠️ Agent Design and Recursive Code Improvement

Systems that optimize prompts, workflows, scaffolds, agent logic, evaluators, or the implementation responsible for future improvements.

- [STOP](https://arxiv.org/abs/2310.02304) - Applies a language-model-infused code improver to its own scaffolding program, yielding an empirically better program optimizer.
- [Meta Agent Search](https://arxiv.org/abs/2408.08435) - Maintains an archive while a meta-agent programs increasingly capable agent designs across prompts, tools, and workflows.
- [Gödel Agent](https://arxiv.org/abs/2410.04444) - Recursively rewrites its own agent logic under high-level objectives instead of relying on a fixed human-designed optimization routine.
- [Darwin Gödel Machine (DGM)](https://arxiv.org/abs/2505.22954) - Evolves a branching archive of coding agents that modify their own code and empirically validate improvements on coding benchmarks.
- [Red Queen Gödel Machine (RQGM)](https://arxiv.org/abs/2606.26294)<sup>†</sup> - Co-evolves agents and evaluators under controlled non-stationary utilities, extending self-improvement beyond fixed benchmarks.

<a id="rsi-automated-research"></a>
## 🔬 Automated Research and Algorithm Discovery

Systems that close larger portions of the research loop and can contribute improvements to AI or its computational substrate.

- [The AI Scientist](https://arxiv.org/abs/2408.06292) - Automates idea generation, implementation, experimentation, paper writing, and simulated review in an iterative scientific discovery loop.
- [AlphaEvolve](https://arxiv.org/abs/2506.13131) - Combines LLM-generated code, automated evaluators, and evolutionary search to discover and optimize algorithms, including components used in AI training.

<a id="rsi-evaluation-safety"></a>
## 🛡️ Evaluation and Safety

Work on measuring AI R&D capability and understanding failure modes that become especially important inside self-improvement loops.

- [Extreme-Risk Model Evaluations](https://arxiv.org/abs/2305.15324) - Distinguishes dangerous-capability and alignment evaluations for identifying and governing high-consequence model behavior.
- [RE-Bench](https://arxiv.org/abs/2411.15114) - Measures frontier agents against human experts on realistic, open-ended machine-learning research-engineering tasks.
- [Self-Improving Agent Fragility](https://arxiv.org/abs/2608.18066)<sup>†</sup> - Shows that memory-based improvement can amplify evaluation variance and task-order effects, motivating multi-run and shuffled-order stress tests.
- [AI4AI-Bench](https://arxiv.org/abs/2608.20318)<sup>†</sup> - Tests whether agents can rewrite training algorithms across ten frozen research repositories under fixed hidden evaluators and controlled compute.

<a id="rsi-resources"></a>
## 🗂️ Repositories and Resources

Living literature maps, implementations, and evaluation environments useful for following or reproducing the field.

- [Awesome Self-Evolving Agents](https://github.com/ANative-Lab/Awesome-Self-Evolving-Agents) - Companion repository to the self-evolving-agent survey, with papers grouped by the component being optimized.
- [DGM Code](https://github.com/jennyzzt/dgm) - Official implementation and experiment artifacts for the Darwin Gödel Machine.
- [RE-Bench Environments](https://github.com/METR/ai-rd-tasks) - Open-source AI R&D task environments, reference material, and evaluation infrastructure used by RE-Bench.

## Contributing

Suggestions are welcome. Please add each paper to the most specific category using the format `[Core method name](paper URL) - One concise sentence describing the improvement target, mechanism, and feedback signal.`
