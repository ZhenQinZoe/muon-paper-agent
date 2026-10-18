# Daily Muon Paper Digest

No strong matches today. Showing the best available 10 candidates.

## Top Highlights

1. A hidden Markov model for unsupervised EEG-based tracking of auditory attention to a single voice
Authors: Tianyi Li, Simon Geirnaert, Davina Van den Broek, Elien Bellon, Bert De Smedt, Alexander Bertrand
Link: http://arxiv.org/abs/2610.21691v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 4.5
Abstract: Objective: Absolute auditory attention decoding (aAAD) aims to track how strongly a listener attends to a single speech source using electroencephalography (EEG). Unlike selective auditory attention decoding, aAAD lacks a competing speech reference, making reliable attention tracking challenging. Approach: We propose a fully unsupervised aAAD pipeline combining neural envelope tracking (NET) with hidden Markov model (HMM)-based temporal inference. Using EEG signals and the target speech envelope, the framework estimates a continuous attention trajectory without explicit attention-state labels. We evaluate the approach using EEG recordings from 30 adults, investigate the impact of analysis window length, and compare HMM post-processing with moving-average (MA) smoothing and alternative EEG features. Main results: With 1-s analysis windows, non-causal HMM post-processing improves the area under the receiver operating characteristic curve (AUC) for all 30 participants, increasing mean AUC from 0.547 for raw NET to 0.832. A 5-s window achieves the highest mean AUC of 0.858. Compared with non-causal MA smoothing, the HMM achieves higher AUC across the examined smoothing scales. Individual switch detection times are comparable, while the HMM generally achieves lower group-level detection times. NET also outperforms alpha power and spectral entropy as an observation feature in the unsupervised HMM framework. Significance: The proposed framework provides a label-free approach for estimating temporal fluctuations in auditory attention, demonstrating the utility of probabilistic temporal inference for continuous attention tracking in single-speaker listening scenarios.

2. Librarian Agents: Training LLMs to Curate Long-Context Workspaces that Anticipate Future Queries
Authors: Anikait Singh, Teresa Zhang, Yoonho Lee, Roshen Sanjay Nair, Aviral Kumar, Chelsea Finn
Link: http://arxiv.org/abs/2610.22273v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: Reasoning over long document contexts remains a challenge for large language models (LLMs). Standard retrieval methods are inherently reactive, bottlenecking agents with complex, cross-document reasoning at inference time, while precomputed structures like knowledge graphs often fall short because they rely on rigid heuristics. Instead, can we allow agents to perform anticipatory directed curation: learning to proactively reorganize unstructured corpora prior to inference to efficiently serve diverse future queries. We build on a key asymmetry in modern agentic harnesses (e.g., Claude Code): while LLM agents are adept at navigating existing filesystems to solve an immediate task, they are rarely trained to construct reusable workspaces for future use. To instantiate this capability, we introduce Librarian Agents, a framework in which a builder agent transforms raw documents into a hierarchical filesystem of synthetic files and reference links, which forms a workspace tailored for a downstream answering agent. We formulate workspace construction as a Markov decision process and optimize the builder policy via reinforcement learning to directly maximize downstream answering accuracy. Empirically, Librarian Agents outperforms the strongest retrieval and precomputation baselines by 33 percentage points on BrowseComp-Plus, amortizes upfront construction costs across repeated queries, and generalizes zero-shot to unseen domains on BRIGHT with a 31-point average accuracy improvement.

3. X-RIC: An Agentic RAN-Intelligent Controller Benchmark for Enhancing Reinforcement Learning
Authors: Adhwaa Al-Chaab, Ayman Younis, Dario Pompili
Link: http://arxiv.org/abs/2610.22269v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: The O-RAN ALLIANCE introduces architectural flexibility through disaggregation and AI-driven control. While the RAN Intelligent Controller (RIC) enables centralized optimization, current AI approaches lack reasoning capabilities and explainability. We propose eXplainable RIC (X-RIC), a novel framework integrating agentic AI into O-RAN architectures. X-RIC combines reactive Reinforcement Learning (RL) with strategic agentic reasoning through: (i) automated Behavioral Cloning (BC) using domain heuristics for sample-efficient training, (ii) a Telecom Language Model (TLM), a transformer-based reasoning module providing contextual abstraction and interpretability, and (iii) closed-loop co-adaptation within the Near-RT RIC control loop enabling continuous policy refinement. To ensure deployment readiness, we introduce BARX (Benchmarking Agentic Reasoning for RAN), a domain-specific evaluation framework assessing agentic control across latency, compliance, and determinism metrics. We validate X-RIC on SLA-aware network slicing in simulation and O-RAN-compliant testbed deployments. X-RIC achieves 89% operational cost reduction while maintaining SLA compliance, converging 75% faster with 50% fewer training steps and 46% lower variance.

4. SCOPE: Semantic Bounded Credit Optimization for Prompt Engineering in Text-to-image Generation
Authors: Yufei Jiao, Jinfa Huang, Zeyue Xue, Tianyu Xie, Yuexiao Ma, Rongrong Ji
Link: http://arxiv.org/abs/2610.22264v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 4.0
Abstract: Reinforcement learning (RL) enables language models to improve text-to-image (T2I) generation by rewriting prompts for a frozen image generator. Existing methods typically apply a single signal derived from the image to individual subword tokens, although objects, counts, attributes, and relations form coherent semantic spans. We propose SCOPE, an objective based on Group Relative Policy Optimization (GRPO) that aligns update weighting with this structure. The rewriter jointly generates an enhanced prompt and its semantic partition. SCOPE pools shifts in policy log probabilities within each span to derive a shared coefficient for its token losses while retaining a single advantage for each completion. It requires neither separate span rewards nor additional image renders. Across Qwen-Image, SD3, and FLUX.1-dev, SCOPE achieves average relative gains over vanilla GRPO of 9.48% on GeneVal and 7.62% on T2I-CompBench. Ablation studies show that both semantic boundaries and pooling within spans contribute to these gains, supporting semantic structure as a practical inductive bias for prompt engineering with RL.

5. Not X, but When: Diagnosing a Mandarin LLM Writing Tic through Contextual Appropriateness
Authors: Yihang Peng, Yi Jing, Dewen Liu, Weihan Meng, Ying Liu
Link: http://arxiv.org/abs/2610.22249v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 4.0
Abstract: Recurring expressions in model-written text are often treated as signatures of machine authorship, yet most of them serve legitimate functions. Whether such an expression is a tic depends on whether the model knows when it is called for. This judgment of appropriateness, central to communicative competence, remains largely unexamined for language models. We study it through the Mandarin corrective construction bushi X, ershi Y ("not X, but Y"). Drawing on Gricean pragmatics and corrective negation, we introduce a decision tree that classifies uses as substantive, optional, or defective by testing whether the context makes X a live alternative and whether rejecting X is informative. Five commercial models use the construction 2.5 to 9.2 times as densely as a human reference. Of 307 annotated uses, only 1.30% are defective while 52.8% are optional, that is, correct but unneeded, so models fall short in appropriateness far more often than in correctness. Several reward models favor the construction even over quality-matched variants, an LLM judge favors it even where the context does not license it, and both supervised fine-tuning and preference optimization tend to raise its frequency in open-weight models. We hope this work encourages the development of models attentive to the appropriateness of their expressions.

## Additional Papers

6. Disagreement-Guided Weak-to-Strong Routing | Not Relevant | Unclear | Score: 4.0 | http://arxiv.org/abs/2610.22245v1
7. Skill-Decoupled On-Policy Expert Distillation for Unified Vision-Language Models | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.22217v1
8. Hy-Memory-30B-A3B: Attributed Reinforcement Learning for Long-Term Memory Writing | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.22196v1
9. EVA-Cap: Optimizing Audiovisual Video Captioning via Event-Centric Alignment | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.22186v1
10. Motion- and Gravity-Aware Feedforward 3D Reconstruction | Not Relevant | Theory + Experiment | Score: 4.0 | http://arxiv.org/abs/2610.22177v1
