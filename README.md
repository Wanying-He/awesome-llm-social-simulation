# Awesome LLM Social Simulation

> A curated and annotated reading list for LLM-based social simulation research.  
> Last updated: February 2026

---

## Tag Legend

| Tag | Meaning |
|-----|---------|
| `[survey]` | Review / survey paper |
| `[position]` | Position / perspective paper |
| `[critique]` | Critical analysis of the field |
| `[platform]` | Full simulation platform / framework |
| `[application]` | Domain-specific application paper |
| `[benchmark]` | Evaluation benchmark or dataset |
| `[arch]` | Agent architecture / cognitive design |
| `[10k+]` | Simulation at 10,000+ agent scale |
| `[1k+]` | Simulation at 1,000–10,000 agent scale |
| `[<100]` | Small-scale simulation |
| `[validated]` | Validated against real-world empirical data |
| `[open-source]` | Code publicly available |
| `[🔥 new]` | Published or significantly updated Dec 2025–present |

---

## 📚 Surveys & Position Papers

### General Surveys

- **[2025.01] A Survey on LLM-based Multi-Agent Systems: Workflow, Infrastructure, and Challenges** `[survey]`  
  [[Paper](https://arxiv.org/abs/2501.06322)]

- **[2024.12] From Individual to Society: A Survey on Social Simulation Driven by LLM-based Agents** `[survey]`  
  Mou et al. [[Paper](https://arxiv.org/abs/2412.03563)]  
  > The most comprehensive survey of the field as of late 2024. Proposes the canonical 3-tier taxonomy: **Individual Simulation → Scenario Simulation → Society Simulation**. Essential orientation reading. Covers agent architecture, construction methods, and evaluation across all three tiers.

- **[2024.12] A Survey on LLM-based Multi-Agent System: Recent Advances and New Frontiers** `[survey]`  
  [[Paper](https://arxiv.org/abs/2412.17481)]  
  > Broader MAS survey that covers simulation as one application domain alongside software engineering, games, etc.

- **[2024.04] A Survey on the Memory Mechanism of LLM-based Agents** `[survey]`  
  [[Paper](https://arxiv.org/abs/2404.13501)]  
  > Foundational reading for understanding how agents maintain state across long simulations.

- **[2024.02] Large Language Model based Multi-Agents: A Survey of Progress and Challenges** `[survey]`  
  [[Paper](https://arxiv.org/abs/2402.01680)]

- **[2024] Large Language Models Empowered Agent-based Modeling and Simulation: A Survey and Perspectives** `[survey]`  
  Gao, Lan, Li et al. (Tsinghua FIB)  
  > The survey most directly tied to the computational social science angle. Focuses on ABM methodology.

- **[2024] Cognitive Architectures for Language Agents** `[survey]`  
  Sumers, Yao, Narasimhan, Griffiths. *Transactions on Machine Learning Research*  
  > Classic reference for understanding single-agent cognitive design: memory, planning, and action.

### Position Papers & Perspectives

- **[2025.07] Integrating LLM in Agent-Based Social Simulation: Opportunities and Challenges** `[survey]` `[critique]`  
  Taillandier et al. Submitted to *JASSS*. [[Paper](https://arxiv.org/abs/2507.19364)]  
  > Critical perspective from the classical ABM community. Key argument: LLMs may create *illusions* of behavioral fidelity through pattern matching without genuine understanding. Distinguishes contexts where LLMs add clear value (interactive simulations, serious games) from where they are problematic (explanatory/predictive modeling). Advocates hybrid LLM + rule-based approaches (GAMA, NetLogo).

- **[2025.06] LLM-based Social Simulations Require a Boundary** `[position]` `[critique]`  
  Wu, Peng, Ito, Xiao. [[Paper](https://arxiv.org/abs/2506.19806)]  
  > Argues for principled scope limitations on what LLM simulations can claim to model.

- **[2025.04] LLM Social Simulations Are a Promising Research Method** `[position]`  
  Anthis et al. [[Paper](https://arxiv.org/abs/2504.02234)]  
  > Optimistic counterpart to the critique papers. Identifies five tractable challenges for the field. Introduces the key concept of **"alienness"** — LLMs superficially match human behavior but operate with non-humanlike mechanisms. Argues sims are already usable for pilot/exploratory research. Well-cited, ICML 2025.

- **[2025.04] Do Large Language Models Solve the Problems of Agent-Based Modeling? A Critical Review** `[critique]`  
  [[Paper](https://arxiv.org/abs/2504.03274)]  
  > Systematic review of 35 generative ABM papers categorizing their validation practices. Finds most validation is either subjective (expert judgment, often the authors themselves) or circular (LLM-judges validating LLM behavior). Important reference for the Social Sim Eval project.

- **[2025.02] Simulate Anything: A Generalized Social Simulation Framework Driven by LLM Agents Based on a Large-scale Real-World User Pool** `[position]`  
  Wang et al. [[OpenReview](https://openreview.net/forum?id=YEhLMBNLNp)]

- **[2023.09] Generative Agent-Based Modeling: Unveiling Social System Dynamics through Coupling Mechanistic Models with Generative AI** `[position]`  
  Ghaffarzadegan et al. [[Paper](https://arxiv.org/abs/2309.11456)]

- **[2023] Large Language Models as Simulated Economic Agents: What Can We Learn from Homo Silicus?** `[position]`  
  Horton. NBER Working Paper.  
  > Foundational framing paper for using LLMs as economic simulation proxies. Coined the "homo silicus" concept.

### Validation-Focused Critical Work

- **[2026.01] Validation is the Central Challenge for Generative Social Simulation** `[critique]` `[survey]` `[🔥 new]`  
  *Artificial Intelligence Review* (Epub Nov 2025). [[Paper](https://link.springer.com/article/10.1007/s10462-025-11412-6)] [[PubMed](https://pubmed.ncbi.nlm.nih.gov/41268053/)]  
  > Published in a major AI journal — will likely become the canonical validation critique. Central finding: LLMs may **exacerbate** rather than alleviate ABM's longstanding validation problems due to black-box structure, cultural biases, and stochastic outputs. Proposes three-part yardstick: (1) purpose alignment, (2) external grounding, (3) robustness. Essential reading for any eval-focused work.

- **[2025.12] Towards Operational Validation of LLM-Agent Social Simulations** `[application]` `[validated]` `[🔥 new]`  
  [[Paper](https://arxiv.org/abs/2508.21740)] (updated Dec 31, 2025)  
  > One of very few papers that actually does rigorous validation. Simulates a Voat-like forum using the YSocial digital-twin platform with 30 independent replications and quantitative comparison to matched empirical data. Finds operational validity is achievable with calibration — but identifies architectural choices (stateless dialogue, simplified feedback rules) that cause divergence.

---

## 🏗️ Platforms & Frameworks

### General-Purpose Social Simulation Platforms

| Framework | Paper | Affiliation | Date | Scale | Key Novelty | Code |
|-----------|-------|-------------|------|-------|-------------|------|
| **AIvilization v0** | [[Paper](https://arxiv.org/abs/2602.10429)] | Multi-inst. | 2026.02 🔥 | 10k+ | Publicly deployed. Hierarchical branch-thinking planner + dual-process memory (fast execution traces / slow semantic consolidation) + human-in-the-loop steering | — |
| **GMASS** | [[Paper](https://arxiv.org/abs/2510.06225)] | 浙大 | 2025.10 | — | Generalized multi-agent social simulation framework | — |
| **SALLMA** | Becattini et al., IEEE SATrends 2025 | — | 2025 | — | Software architecture for LLM-based MAS | — |
| **YuLan-OneSim** | [[Paper](https://arxiv.org/abs/2505.07581)] | RUC YuLan | 2025.05 | — | "Next generation" platform from RUC team | [[Code](https://github.com/RUC-GSAI/YuLan-OneSim)] |
| **ProSim** | [[Paper](https://arxiv.org/abs/2505.15857)] | — | 2025.05 | — | Simulates prosocial behavior and social contagion under institutional interventions | [[Code](https://github.com/halsayxi/ProSim/)] |
| **SocioVerse** | [[Paper](https://arxiv.org/abs/2504.10157)] | Fudan DISC | 2025.04 | 10M users pool | World model grounded in 10M real user profiles; fine-grained demographic calibration | [[Code](https://github.com/FudanDISC/SocioVerse)] |
| **AgentSociety** | [[Paper](https://arxiv.org/abs/2502.08691)] | Tsinghua FIB | 2025.02 | 10k+ | 5M+ interactions. Agents with emotions/needs/motivations. Tested on polarization, UBI, disasters | [[Code](https://github.com/tsinghua-fib-lab/AgentSociety)] |
| **GenSim** | [[Paper](https://arxiv.org/abs/2410.04360)] | Tsinghua + NTU | 2024.10 | — | General platform with modular scenario builder | [[Code](https://github.com/TangJiakai/GenSim)] |
| **AgentTorch** | [[Paper](https://arxiv.org/abs/2409.10568)] | MIT | 2024.09 | — | Differentiable ABM; gradient-based optimization of agent populations | [[Code](http://github.com/AgentTorch/AgentTorch)] |
| **AgentScope** | [[Paper](https://arxiv.org/abs/2407.17789)] | Alibaba | 2024.07 | 10k+ | Very large-scale multi-agent infra; focuses on efficiency | [[Code](https://github.com/agentscope-ai/agentscope)] |
| **Concordia** (DeepMind) | [[Paper](https://arxiv.org/abs/2312.03664)] | Google DeepMind | 2023.12 | — | GM-style narrative environment | [[Code](https://github.com/google-deepmind/concordia)] |
| **SOTOPIA** | [[Paper](https://arxiv.org/abs/2310.11667)] | CMU | 2023.10 | — | Interactive evaluation of social intelligence | [[Code](https://www.sotopia.world/)] |
| **MetaAgents** | [[Paper](https://arxiv.org/abs/2310.06500)] | — | 2023.10 | — | Task-oriented coordination via collaborative generative agents | — |
| **AgentVerse** | [[Paper](https://arxiv.org/abs/2308.10848)] | OpenBMB | 2023.08 | — | Multi-agent collaboration + emergent behavior | [[Code](https://github.com/OpenBMB/AgentVerse/)] |
| **Smallville** (Generative Agents) | [[Paper](https://arxiv.org/abs/2304.03442)] | Stanford | 2023.04 | 25 agents | **The foundational paper**. Memory stream + reflection + planning architecture | [[Code](https://github.com/joonspk-research/generative_agents)] |
| **CAMEL** | [[Paper](https://arxiv.org/abs/2303.17760)] | KAUST | 2023.03 | — | Role-playing communicative agents; large open-source ecosystem | [[Code](https://github.com/camel-ai/camel)] |
| **GAMA Platform** | [[Code](https://github.com/gama-platform/gama.experimental)] | IRD/Sorbonne | ongoing | — | Classical ABM platform with new LLM plugin (MCP integration) | [[Code](https://github.com/gama-platform/gama.experimental)] |

> **Note:** PKU-Wuhan 北武院社会模拟器 — to be added once paper is located.

### Hybrid Frameworks

- **[2025.10] Integrating LLM and Diffusion-Based Agents for Social Simulation** `[platform]`  
  [[Paper](https://arxiv.org/abs/2510.16366)] [[Code](https://github.com/lixinyi22/Social-Simulation-for-Information-Diffusion.git)]  
  > Hybrid approach combining generative LLM agents with diffusion-based mechanistic agents.

### Social Network Simulators

| Framework | Paper | Affiliation | Date | Scale | Key Novelty | Code |
|-----------|-------|-------------|------|-------|-------------|------|
| **DynamiX** | [[Paper](https://arxiv.org/abs/2507.19929)] | — | 2025.12 🔥 | — | **Addresses dynamic social relationship evolution**, not just static scale-up. Dynamic hierarchy module for core agent selection at each timestep. Opinion leader modeling. | — |
| **GA-S³** | [[Paper](https://arxiv.org/abs/2506.03532)] | HUST | 2025.06 | — | Group agents for social network simulation | [[Code](https://github.com/AI4SS/GAS-3)] |
| **LLM-AIDSim** | [[Paper](https://www.researchgate.net/publication/387719929)] | — | 2025.01 | — | Influence diffusion simulation in social networks | — |
| **OASIS** | [[Paper](https://arxiv.org/abs/2411.11581)] | CAMEL-AI | 2024.11 | 1M agents | Million-agent social interaction simulation | [[Code](https://github.com/camel-ai/oasis)] |
| **Y Social** | [[Paper](https://arxiv.org/abs/2408.00818)] | Pisa | 2024.08 | — | LLM-powered social media digital twin | [[Code](https://ysocialtwin.github.io/)] |
| **S³** | [[Paper](https://arxiv.org/abs/2307.14984)] | Tsinghua FIB | 2023.07 | — | Foundational social network simulator; simulates emotion, attitude, interaction behaviors | — |
| **TWON** | [[Paper](https://www.twon-project.eu/)] | EU Project | 2023 | — | Twin of Online Social Networks; EU-funded | [[Zenodo](https://zenodo.org/records/15577602)] |

---

## 🧪 Evaluations & Benchmarks

### Benchmarks

- **[2025.12] SoMe: A Realistic Benchmark for LLM-based Social Media Agents** `[benchmark]` `[🔥 new]`  
  [[Paper](https://arxiv.org/abs/2512.14720)]  
  > 8 agentic social media tasks. 154 trending topic events from Nov–Jan 2024/25. Measures multi-round information acquisition, event analysis, and social media reasoning.

- **[2025.10] SimBench: Benchmarking the Ability of LLMs to Simulate Human Behaviors** `[benchmark]`  
  [[Paper](https://arxiv.org/abs/2510.17516)] [[Data](https://huggingface.co/datasets/pitehu/SimBench)] [[Code](https://github.com/pitehu/SimBench_release/)]  
  > The most dedicated benchmark for human behavior simulation ability. Important reference for eval projects.

- **[2024.11] Generative Agent Simulations of 1,000 People** `[benchmark]` `[validated]` `[1k+]`  
  Park et al. (Stanford). [[Paper](https://arxiv.org/abs/2411.10109)]  
  > Landmark validation study. Agents grounded in qualitative interviews of 1,052 real individuals replicate General Social Survey responses at **85% accuracy** (comparable to human test-retest reliability). The gold standard for individual-level behavioral fidelity.

### Evaluation Papers

- **[2025.10] Synthetic Social Data: Trials and Tribulations** `[critique]`  
  [[Paper](https://arxiv.org/abs/2510.19952)]

- **[2025.10] HugAgent: Evaluating LLMs in Simulating Human-Like Individual Reasoning on Open-Ended Tasks** `[benchmark]`  
  [[Paper](https://arxiv.org/abs/2510.15144)]

- **[2024.12] Sense and Sensitivity: Evaluating the Simulation of Social Dynamics via LLMs** `[benchmark]`  
  [[Paper](https://arxiv.org/abs/2412.05093)]

- **[2024.10] Is This the Real Life? Is This Just Fantasy? The Misleading Success of Simulating Social Interactions with LLMs** `[critique]`  
  Zhou et al. *EMNLP 2024*. [[Paper](https://arxiv.org/abs/2403.05020)]  
  > One of the earliest pointed critiques of the field. Key warning: positive results in LLM social simulations are often artifacts of evaluation design rather than genuine behavioral fidelity.

- **[2024.05] Evaluating LLM Agents for Simulating Humanoid Behavior** `[benchmark]`  
  Chen, Yao, Wang et al. [[Paper](https://par.nsf.gov/servlets/purl/10544265)]

- **[2024.02] Can LLM Agents Simulate Human Trust Behaviors?** `[benchmark]`  
  Xie, Chen, Li, Bibi, Guohao Li et al. [[Paper](https://arxiv.org/abs/2402.04559)]  
  > Tests LLMs in trust games. Finds they can partially replicate trust behaviors but diverge in systematic ways.

- **[2022] Neural Theory-of-Mind? On the Limits of Social Intelligence in Large LMs** `[critique]`  
  Sap, Le Bras, Fried, Choi. *EMNLP 2022*. [[Paper](https://aclanthology.org/2022.emnlp-main.248/)]  
  > Foundational critique of LLM social reasoning abilities at the individual agent level. Still relevant for grounding expectations.

---

## 📡 Domain Applications

### Opinion Dynamics & Misinformation

- **[2025.05] FUSE: The Stepwise Deception — Simulating the Evolution from True News to Fake News with LLM Agents** `[application]` `[misinformation]`  
  [[Paper](https://arxiv.org/abs/2410.19064v2)] [[Code](https://anonymous.4open.science/r/FUSE-7022/README.md)]

- **[2025.01] SITGNet: Social Influence Text Generation for Opinion Guidance** `[application]` `[opinion dynamics]` `[🔥 new]`  
  Zhang, Yu, Peng et al. *Int. J. Machine Learning & Cybernetics*, 2026. [[Paper](https://link.springer.com/article/10.1007/s13042-025-02816-5)]  
  > Focuses on *proactive* opinion guidance rather than passive simulation. Relevant to LLM Ads track.

- **[2024.12] From Skepticism to Acceptance: Simulating Attitude Dynamics Toward Fake News** `[application]` `[opinion dynamics]`  
  Liu, Song, Chen, Yan (RUC). [[Paper](https://arxiv.org/abs/2403.09498)] [[Code](https://github.com/LiuYuHan31/FPS)]

- **[2024.10] LLM-Driven Multi-Agent Simulation for News Diffusion Under Different Network Structures** `[application]` `[social network]`  
  [[Paper](https://arxiv.org/abs/2410.13909)]

- **[2023.11] Simulating Opinion Dynamics with Networks of LLM-based Agents** `[application]` `[opinion dynamics]`  
  Chuang, Goyal, Harlalka et al. *NAACL Findings 2024*. [[Paper](https://arxiv.org/abs/2311.09618)] [[Code](https://github.com/yunshiuan/llm-agent-opinion-dynamics)]  
  > One of the cleaner empirical papers on opinion dynamics. Tests bounded confidence models with LLM agents.

### Finance & Economics

- **[2025.02] TwinMarket: A Scalable Behavioral and Social Simulation for Financial Markets** `[platform]` `[application]` `[finance]`  
  [[Paper](https://arxiv.org/abs/2502.01506)] [[Code](http://tobyyang7.github.io/TwinMarket)]  
  > The main financial market simulation paper in the group's reading list.

- **[2024.10] SRAP-Agent: Simulating and Optimizing Scarce Resource Allocation Policy** `[application]` `[policy]`  
  [[Paper](https://arxiv.org/abs/2410.14152)] [[Code](https://github.com/jijiarui-cather/SRAPAgent_Framework)]

- **[2024.07] StockAgent: LLM-based Stock Trading in Simulated Real-World Environments** `[application]` `[finance]`  
  [[Paper](https://arxiv.org/abs/2407.18957)] [[Code](https://github.com/MingyuJ666/Stockagent)]

- **[2024.06] Simulating Financial Market via LLM-based Agents** `[application]` `[finance]`  
  [[Paper](https://arxiv.org/abs/2406.19966)]

- **[2023.10] EconAgent: LLM-Empowered Agents for Simulating Macroeconomic Activities** `[application]` `[finance]`  
  Li, Gao et al. *ACL 2024*. [[Paper](https://arxiv.org/abs/2310.10436)] [[Code](https://github.com/tsinghua-fib-lab/ACL24-EconAgent)]

- **[2023] Large Language Models as Simulated Economic Agents: Homo Silicus** `[position]` `[finance]`  
  Horton (NBER).

### Political & Governance

- **[2024.11] Donald Trumps in the Virtual Polls: Predicting Public Opinions Using LLMs** `[application]` `[political]`  
  [[Paper](https://arxiv.org/abs/2411.01582)]

- **[2024.06] Simulating the U.S. Senate: Legislative Behavior and Bipartisanship** `[application]` `[political]`  
  [[Paper](https://arxiv.org/abs/2406.18702)]

- **[2024.02] Unveiling the Truth and Facilitating Change: Agent-based Large-scale Social Movement Simulation** `[application]` `[political]`  
  Mou, Wei, Huang (Fudan DISC). [[Paper](https://arxiv.org/abs/2402.16333)] [[Code](https://github.com/xymou/social_simulation)]

### Epidemics & Public Health

- **[2025.03] VacSim: Simulating Vaccine Hesitancy to Inform Public Health Policy** `[application]` `[epidemics]` `[validated]`  
  [[Paper](https://arxiv.org/abs/2503.09639)]  
  > One of the more honest papers — does not overclaim. Explicitly evaluates promises and limitations of LLM agents for policy simulation. Introduces "attitude modulation" and "simulation warmup."

- **[2025.01] LLM-AIDSim: LLM-Enhanced Agent-Based Influence Diffusion Simulation** `[application]` `[epidemics]`  
  [[Paper](https://www.researchgate.net/publication/387719929)]

- **[2024.03] COMOKIT v2: Multi-scale Epidemic Control Policy Simulation** `[platform]` `[epidemics]`  
  Taillandier et al. [[Paper](https://www.researchgate.net/publication/379188265)] [[Code](https://github.com/COMOKIT/COMOKIT-Model)]  
  > Classical ABM approach (GAMA platform), not LLM-based — useful baseline comparison.

- **[2023.07] Epidemic Modeling with Generative Agents** `[application]` `[epidemics]`  
  Williams et al. [[Paper](https://arxiv.org/abs/2307.04986)] [[Code](https://github.com/bear96/GABM-Epidemic)]

### User Modeling & Recommendation

- **[2024.05] Lusifer: LLM-based User Simulated Feedback Environment for Recommender Systems** `[application]` `[user modeling]`  
  [[Paper](https://arxiv.org/abs/2405.13362)] [[Code](https://github.com/danialebrat/Lusifer)]

- **[2023.06] RecAgent: User Behavior Simulation with LLM-based Agents** `[application]` `[user modeling]`  
  Wang et al. (RUC). [[Paper](https://arxiv.org/abs/2306.02552)]

### Urban

- **[2025.10] SimCity: Multi-Agent Urban Development Simulation with Rich Interactions** `[application]` `[urban]`  
  [[Paper](https://arxiv.org/abs/2510.01297)]

### War & Geopolitics

- **[2023.11] WarAgent: LLM-based Multi-Agent Simulation of World Wars** `[application]` `[geopolitics]`  
  Hua, Fan, Li et al. [[Paper](https://arxiv.org/abs/2311.17227)] [[Code](https://github.com/agiresearch/WarAgent)]

---

## 🧠 Agent Architecture & Emergence

### Foundational Architecture

- **[2024.11] Generative Agent Simulations of 1,000 People** — Park et al. (Stanford). [[Paper](https://arxiv.org/abs/2411.10109)]  
  > The follow-up to Smallville, validating interview-grounded agent personas at scale. See also: Benchmarks section.

- **[2024.02] Affordable Generative Agents** — Yu, Zhang et al. [[Paper](https://arxiv.org/abs/2402.02053)]  
  > Efficient alternative to full Smallville-style architecture.

- **[2024] Cognitive Architectures for Language Agents** — Sumers et al. *TMLR*  
  > The best survey of agent cognitive design patterns.

- **[2023.04] Generative Agents (Smallville)** — Park et al. (Stanford). [[Paper](https://arxiv.org/abs/2304.03442)]  
  > *The* paper that started the modern field. Memory stream + reflection + planning in a 25-agent sandbox. See framework table above.

- **[2022] Neural Theory-of-Mind? On the Limits of Social Intelligence in Large LMs** — Sap et al. *EMNLP 2022*.  
  > Sets the baseline for what single-agent social cognition LLMs can and cannot do.

### Emergence & Collective Behavior

- **[2025.08] Simulating Generative Social Agents via Theory-Informed Workflow Design** `[arch]`  
  [[Paper](https://arxiv.org/abs/2508.08726)]  
  > Applies structured social science theory to agent workflow design rather than ad-hoc prompting.

- **[2025] Simulating Prosocial Behavior with Multi-Agent LLMs: Evidence for Policy Decisions** `[arch]` `[application]`  
  Sreedhar, Cai, Chilton et al. *IUI 2025*.

- **[2024.11] Project Sid: Many-agent Simulations Toward AI Civilization** `[platform]` `[10k+]`  
  Altera.al [[Paper](https://arxiv.org/abs/2411.00114)]  
  > Commercial research showing large-scale LLM agent society with civilization-level dynamics.

- **[2024.09] Can Agents Spontaneously Form a Society? Introducing a Novel Architecture for Generative Multi-Agents to Elicit Social Emergence** `[arch]`  
  Zhang, Yin, Jiang, Su. [[Paper](https://arxiv.org/abs/2409.06750)]

- **[2024.06] Artificial Leviathan: Social Evolution of LLM Agents through Hobbesian Social Contract Theory** `[arch]`  
  Dai et al. [[Paper](https://arxiv.org/abs/2406.14373)]

- **[2024.04] Cooperate or Collapse: Emergence of Sustainability Behaviors in a Society of LLM Agents** `[arch]`  
  Piatti et al. [[Paper](https://arxiv.org/abs/2404.16698)]

- **[2024.03] Social Norm Emergence in Generative Agent Societies** — Ren et al. *IJCAI 2024*. [[Paper](https://arxiv.org/abs/2403.08251)]

- **[2024.03] AgentGroupChat: Interactive Group Chat Simulacra for Emergent Behavior** `[arch]`  
  Gu et al. [[Paper](https://arxiv.org/abs/2403.13433)] [[Code](https://github.com/MikeGu721/AgentGroup)]

- **[2023.10] CompeteAI: Understanding Competition Dynamics of LLM-based Agents** `[arch]`  
  Zhao et al. *ICML 2024*. [[Paper](https://arxiv.org/abs/2310.17512)]

### Communication & Language Technology

- **[2025.05] EcoLANG: Efficient Agent Communication Language Induction for Social Simulation** `[arch]` `[technology]`  
  [[Paper](https://arxiv.org/abs/2505.06904)] — Zhongyu Wei (Fudan DISC)  
  > Proposes inducing efficient inter-agent communication protocols rather than relying on natural language for all agent communication. Relevant for scaling simulations cost-effectively.

### Alignment × Social Simulation

- **[2024] Training Socially Aligned Language Models on Simulated Social Interactions** `[application]` `[alignment]`  
  Liu, Yang, Zhang et al. *ICLR 2024*. [[Paper](https://openreview.net/forum?id=NddKiWtdUm)]  
  > Feedback loop: use social simulation to generate training data for better-aligned LLMs.

### Games & Social Simulation

- **[2024.01] CivRealm: A Learning and Reasoning Odyssey in Civilization for Decision-Making Agents** `[platform]` `[games]`  
  [[Paper](https://arxiv.org/abs/2401.10568)] [[Code](https://github.com/bigai-ai/civrealm)] — BIGAI

- **[2023.10] LLM-based Agent Society Investigation: Collaboration and Confrontation in Avalon** `[games]`  
  Lan et al. [[Paper](https://arxiv.org/abs/2310.14985)]

- **[2023.09] Exploring LLMs for Communication Games: Empirical Study on Werewolf** `[games]`  
  [[Paper](https://arxiv.org/abs/2309.04658)]

---

## 📖 Pre-LLM Social Science ABM Foundations

- Squazzoni, Jager, Edmonds (2014). Social Simulation in the Social Sciences: A Brief Overview. *SSCR*.

- Epstein (2012). *Generative Social Science: Studies in Agent-Based Computational Modeling*. Princeton UP.  
  > The canonical theoretical grounding for ABM as a social science methodology.

- Hegselmann & Krause (2002, 2005). Opinion dynamics with bounded confidence.  
  > Classical opinion dynamics model; compare LLM-based opinion dynamics against this baseline.

- Bonabeau (2002). Agent-based modeling: Methods and techniques for simulating human systems. *PNAS*.

- Macy & Willer (2002). From Factors to Actors: Computational Sociology and ABM. *Annual Review of Sociology*.

- Axelrod (1997). Advancing the Art of Simulation in the Social Sciences. *Simulating Social Phenomena*.

- Schelling (1971). Dynamic Models of Segregation. *Journal of Mathematical Sociology*.  
  > Founding work on emergent segregation from local preference rules.

---

## 👥 Research Groups

| Group | PI(s) | Affiliation | Notable Works |
|-------|--------|-------------|---------------|
| **Tsinghua FIB Lab** | Yong Li | Tsinghua University | AgentSociety, EconAgent, S³|
| **Fudan DISC** | Zhongyu Wei | Fudan University | SocioVerse, FUSE, EcoLANG, Social Movement Sim |
| **RUC YuLan Team** | Ji-Rong Wen, Rui Yan, Xu Chen | Renmin University | YuLan-OneSim, RecAgent, Fake News dynamics |
| **KAUST CAMEL Team** | Guohao Li | KAUST | CAMEL, OASIS, Trust behaviors |
| **Stanford HAI** | Joon Sung Park | Stanford University | Generative Agents (Smallville), 1,000 People |
| **CMU** | Maarten Sap, others | CMU | SOTOPIA, Theory-of-Mind work |
| **BIGAI** | — | Beijing Institute for General AI | CivRealm |
| **IRD/Sorbonne (GAMA)** | Patrick Taillandier | IRD France | GAMA Platform, COMOKIT, JASSS critique survey |
| **Altera.al** | — | — | Project Sid |

---

## 🔧 Infrastructure

- **AgentScope** — Alibaba's large-scale multi-agent infra. [[Paper](https://arxiv.org/abs/2407.17789)] [[Code](https://github.com/agentscope-ai/agentscope)]
- **AutoGen** — Wu et al., Microsoft. [[Paper](https://arxiv.org/abs/2308.08155)]
- **GAMA Platform** — Classical spatial ABM platform with LLM MCP plugin. [[Code](https://github.com/gama-platform/gama)]
- **AgentTorch** — Differentiable ABM for gradient-based population optimization. [[Code](http://github.com/AgentTorch/AgentTorch)]
- **YSocial** — Social media digital twin platform. [[Paper](https://arxiv.org/abs/2408.00818)] [[Code](https://ysocialtwin.github.io/)]

---

## 📌 Curated Starting Points by Reading Goal

**"I need to understand the field landscape"**  
→ Start with arxiv:2412.03563 (survey), then arxiv:2304.03442 (Smallville), then arxiv:2502.08691 (AgentSociety)

**"I want to find research gaps for an eval project"**  
→ Read arxiv:2504.02234 (Promising Method), then arxiv:2504.03274 (Do LLMs Solve ABM?), then the Springer validation critique (2026), then arxiv:2508.21740 (Operational Validation)

**"I want to understand the critique perspective"**  
→ arxiv:2403.05020 (Misleading Success), arxiv:2507.19364 (JASSS critique), arxiv:2506.19806 (Requires a Boundary)

**"I want to study the architecture of a specific system"**  
→ AgentSociety (arxiv:2502.08691) for large-scale society; AIvilization (arxiv:2602.10429) for long-horizon agents; OASIS for social networks; TwinMarket for finance

**"I want to understand validation methodology"**  
→ arxiv:2411.10109 (1,000 People, best practice), arxiv:2508.21740 (Operational Validation), Springer 2026 review

---

*Maintained by Attey. PRs welcome.*
