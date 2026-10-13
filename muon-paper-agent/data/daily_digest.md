# Daily Muon Paper Digest

No strong matches today. Showing the best available 10 candidates.

## Top Highlights

1. RATED: Reliability-Aware AI Agent Tool Retrieval via Execution Dynamics
Authors: Weiliang Chen, Song Liao
Link: http://arxiv.org/abs/2610.13889v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: As AI agents increasingly rely on external tools, accurate retrieval is essential for reliable behavior. Existing methods optimize semantic relevance but largely ignore tool availability during execution. To address this gap, we propose RATED (Reliability-Aware Tool Retrieval via Execution Dynamics), a retrieval framework that combines robust semantic matching with dynamic reliability adaptation. RATED employs a frozen dual-encoder with contrastive fine-tuning for semantic matching, and a lightweight contextual bandit module that re-ranks candidates based on real-time execution feedback. This design enables rapid adaptation to runtime tool failures without expensive model retraining. We introduce EcoAgent, a benchmark of 5,172 real-world tools and over 210,000 query-tool pairs for offline retrieval and dynamic reliability evaluation. Experimental results demonstrate that RATED achieves a 52.2% relative MRR improvement over the ToolLLM API retriever on real-world queries, and reduces fault selection rate from 86.2% to 2.9% under severe API outage scenarios with a 30% failure rate, while incurring negligible latency overhead of less than 1 ms over encode-only inference. The code and dataset are available at https://github.com/Elliotes/EcoAgent.

2. Event-based Action Recognition by Pre-Training on Multi-Frame Representations
Authors: Emma Norrby, Tomas Wilkinson, Per Nyblom, David Gustafsson
Link: http://arxiv.org/abs/2610.13856v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 4.0
Abstract: Action recognition is a crucial task in domains like robotics, patient monitoring, or surveillance. Recently, event-based action recognition has attracted much attention due to the event camera's ability to capture fast motions and its improved privacy over conventional vision cameras. While frame-based event representations work well for short event sequences, their discriminative ability declines sharply with longer and more complex event sequences. In this work, we introduce a multi-frame representation that greatly improves recognition performance over its single-frame counterpart. We adopt a masked auto-encoding framework to pre-train a Vision Transformer using a sparsity-aware masking algorithm and token selection mechanism to improve downstream performance and control computational complexity. We also introduce multiple mask tokens for the decoder with a position-aware attention mechanism, leading to further improved performance. Our proposed method shows impressive performance for challenging long-duration and complex event sequences, yielding state-of-the-art performance on THU-EACT-50 CHL and DailyDVS-200.

3. Partially Informed Stochastic Optimization via Zeroth-Order Residual Tracking
Authors: El Mahdi Chayti, Alireza Mirrokni, Martin Jaggi
Link: http://arxiv.org/abs/2610.13871v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 3.5
Abstract: Many optimization problems provide direct access to only part of the gradient, while the remaining component must be inferred from function evaluations. This structure arises in performative prediction, performative reinforcement learning, and bilevel optimization with a black-box lower level. We introduce Partially Informed Stochastic Optimization (PISO), which combines the available gradient component with a running estimate of the residual. By centring each zeroth-order observation on this estimate, PISO makes the variance due to random probing depend on the tracking error rather than the residual's magnitude. This yields a randomized sketch iteration with an explicit contraction mechanism and a principled interpretation of momentum. For smooth nonconvex objectives, we establish convergence guarantees that depend on the residual's variation and initial magnitude, without requiring a uniform bound on the unavailable gradient component. With independently sampled function evaluations and Gaussian or spherical probes, PISO attains leading function-evaluation complexities of \(O(d^{2}\varepsilon^{-6})\) under Lipschitz gradients and \(O(d^{2}\varepsilon^{-5})\) under an additional Lipschitz-Hessian assumption. These rates require only one probe direction, two function samples, and one known-component sample per update. The analysis also quantifies how batching trades observations for fewer deployments. Across five settings, PISO variants improve on the tested baselines with comparable oracle access in three, reach a comparable solution faster in bilevel routing, and perform best among methods without response-model derivatives in performative reinforcement learning.

4. Images Talk Back: Guiding MMDiTs by Suppressing Image-to-Text Feedback
Authors: Yucheng Yang, Xiaoxiao Sun, Shusheng Yang, Jiakang Chen, Serena Yeung-Levy
Link: http://arxiv.org/abs/2610.13941v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 2.0
Abstract: Multimodal diffusion transformers (MMDiTs) allow the evolving image to update internal text representations through joint attention. These representations then guide subsequent image updates, raising a question: does this feedback help correct deviations from the prompt, or preserve them? We find that image-to-text (I2T) feedback can preserve the objects and attributes already represented in the evolving image, including errors. Transplanting I2T messages can rescue failures or disrupt successes. At matched intervention strengths, suppressing the influence of I2T feedback improves generation, whereas opposite controls degrade it. These findings motivate Semantic Feedback Guidance (SFG), which suppresses the influence of I2T feedback by guiding away from an auxiliary branch that strengthens this feedback and weakens text-to-image conditioning. The in-place variant, iSFG, directly suppresses I2T feedback and strengthens text-to-image conditioning, requiring no extra model evaluations. Temporal interventions motivate running the SFG branch during the first 20% of image sampling steps, requiring about $1.2\times$ the base NFE without classifier-free guidance (CFG). Experiments across three image-generation backbones show gains in alignment and preference-model scores. On FLUX, adding SFG to CFG raises GenEval from $0.6661$ to $0.7479$; on SD3.5M, iSFG adds $+1.33$ HPSv2.1 over CFG at zero extra NFE. The control also transfers to text-to-video and image-to-video generation, improving VBench scores. Code is available at https://github.com/yyc1215lll-creator/SFG.

5. Goal-Oriented Bundle Management and Flow Control for Deep-Space Communications via Reinforcement Learning
Authors: Sajjad Baghaeea, Aimin Lib, Shanmugarajan Balasubramanian, Elif Uysal
Link: http://arxiv.org/abs/2610.13923v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 2.0
Abstract: Deep-space communications operate under intermittent connectivity, long propagation delays, and relay storage constraints. In such networks, the Bundle Protocol enables store-carry-forward communication, requiring relay nodes to manage limited storage and scarce contact opportunities. Relay-side scheduling and dropping decisions are inherently goal-oriented: transmission resources should be allocated to bundles most valuable to downstream mission objectives. Conventional schedulers, such as FIFO, do not explicitly optimize task utility and may provide unfair service across heterogeneous planetary sources. This paper presents a closed-loop modeling and learning framework for relay-side bundle and flow management in a contact-driven deep-space network, where lunar and Martian updates are forwarded through a shared-buffer relay to Earth. We quantify destination-side information freshness using excess age $Δ_i^e(t)=[Δ_i(t)-d_i(t)]^+$, where $Δ_i(t)$ denotes the Age of Information of source $i$ and $d_i(t)$ is a source-dependent delay baseline. Based on this metric, we define a goal-oriented loss that supports source-dependent nonlinear penalties, allowing prioritization according to mission relevance. We formulate relay control as a constrained semi-Markov decision process (CSMDP) and solve it using masked Lagrangian Proximal Policy Optimization (PPO). Feasibility-aware action masking restricts transmissions to bundles that can complete within the remaining contact window. DTNSim simulations indicate improved age-based utility and inter-flow fairness compared with baseline schedulers. The proposed framework jointly optimizes relay-side bundle scheduling, dropping, and flow control under contact-driven dynamics with explicit fairness considerations across heterogeneous sources.

## Additional Papers

6. RSI-Anything: Unlocking Recursive Self-Improvement with World Models | Not Relevant | Experiment | Score: 2.0 | http://arxiv.org/abs/2610.13912v1
7. Task Context Shapes Component Roles in Language Models | Not Relevant | Unclear | Score: 2.0 | http://arxiv.org/abs/2610.13895v1
8. How Social Reinforcement Shapes Word-of-Mouth: A Conviction-Based Model for Marketing Diffusion and Network Targeting | Not Relevant | Experiment | Score: 2.0 | http://arxiv.org/abs/2610.13890v1
9. Prediction Is Not a Sufficient Memory State | Not Relevant | Theory + Experiment | Score: 2.0 | http://arxiv.org/abs/2610.13881v1
10. Decision-Focused Learning for Cyber-Physical Risk-Aware Power Grid Operations | Not Relevant | Experiment | Score: 2.0 | http://arxiv.org/abs/2610.13853v1
