# Daily Muon Paper Digest

## Top Highlights

1. Last-Iterate Stationarity of Muon with Finitely Many Newton-Schulz Iterations
Authors: Ping Li, Vincent Y. F. Tan
Link: http://arxiv.org/abs/2610.34158v2
Category: Muon Core
Paper type: Theory + Experiment
Relevance score: 18.0
Abstract: Muon has demonstrated strong empirical performance in large-scale language-model training, motivating a deeper theoretical understanding of its practical implementation. Unlike the idealized polar-factor update, practical Muon employs a fixed number of quintic Newton-Schulz iterations. Existing analyses primarily establish average- or best-iterate stationarity guarantees, while last-iterate convergence remains less understood. In this work, we investigate last-iterate gradient convergence of practical finite-step Muon on smooth, lower-bounded nonconvex objectives. In the deterministic setting, we show that Muon without input stabilization can exhibit cyclic behavior even on a smooth convex quadratic. In contrast, with positive stabilization, we establish last-iterate gradient convergence and square-summability of gradients for any fixed momentum coefficient below one and a sufficiently small constant learning rate. In the stochastic setting, we first demonstrate that persistent bounded, unbiased noise can prevent convergence under fixed learning rates and momentum, even with positive stabilization. We then establish almost-sure and mean-square last-iterate gradient convergence under bounded-variance stochastic gradients by combining diminishing learning rates with increasing momentum. Finally, we construct a smooth counterexample demonstrating that neither convergence theorem implies a pointwise polynomial convergence rate. Nevertheless, we establish density-one convergence rates, guaranteeing polynomial gradient decay for all but an asymptotically vanishing fraction of iterations.

2. Pretraining Data Scale Reverses the Muon-AdamW Fine-Tuning Gap
Authors: Catherine Li, Jingchu Gai, Andrej Risteski, Jacob Mitchell Springer, Aditi Raghunathan
Link: http://arxiv.org/abs/2611.03633v2
Category: Muon Core
Paper type: Experiment
Relevance score: 15.0
Abstract: Muon has recently emerged as a promising optimizer for pretraining large language models, offering a speedup over AdamW in minimizing pretraining loss. However, it remains unclear whether Muon's advantage persists after fine-tuning. In this paper, we study the downstream behavior of Muon and AdamW and uncover a surprising trend: beyond a sufficiently large pretraining data budget, AdamW outperforms Muon after fine-tuning. Moreover, as model size increases, AdamW overtakes Muon at progressively smaller pretraining token-parameter ratios. To explain this reversal, we view fine-tuning as a perturbation of the outputs and introduce the margin-to-spread ratio, which measures how far the correct logit lies above the wrong ones relative to how widely the wrong logits are spread. In language models, Muon has the larger margin-to-spread ratio at small data budgets and AdamW at large ones, mirroring the fine-tuning trend. In a linear associative memory, we prove that after one update the margin-to-spread ratio of gradient descent gains on that of Muon as the data budget grows, and simulations show that this trend persists after extended training.

3. A low-rank decoder bottleneck bounds reliability in foundation-model perturbation prediction
Authors: Zheyu Zhang, Yuanhao Huang, Fan Feng, Jie Liu
Link: http://arxiv.org/abs/2611.05849v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 6.5
Abstract: Foundation-model predictors of perturbation response are evaluated primarily by aggregate accuracy. Using their predictions to prioritize experiments requires assessing each prediction's reliability. We audit the state-transition (ST) decoder used in STATE across three encoders (SE-600M, scGPT, and Tahoe-x1) and four cell lines under CRISPRi. The decoder's first attention layer has a low-rank output. Projecting this output onto 4-32 fixed directions estimated from training activations preserves mean per-perturbation Pearson delta correlation (PDC). This low-rank attention bottleneck bounds the decoder's reliability by distance to training responses: PDC declines as the cosine distance from a perturbation's observed response to its nearest training response increases. We propose predicted-NN-distance, the cosine distance from a predicted response to its nearest training response, as a per-prediction confidence score. The score has a mean absolute Spearman correlation of 0.81 with PDC, close to the 0.88 obtained with the observed response. Thresholds calibrated on this score transfer across encoders and cell lines, and the score remains predictive of PDC for drug perturbations.

4. Adaptive Multi Mode: Budget-Aware Routing of Optimizers By Online Landscape Probes
Authors: Benjamin Jacob Bodner
Link: http://arxiv.org/abs/2611.06879v1
Category: Muon-Adjacent Experiments
Paper type: Experiment
Relevance score: 5.5
Abstract: The best classical optimizer for a continuous black-box problem depends on its budget and landscape. Existing routers decide from the dimension and budget, past improvement or features fitted to one benchmark, and few test an optimizer's implicit assumptions online. AMM (Adaptive Multi Mode) routes a known budget among quasi-Newton, trust-region, coordinate, multistart and evolution-strategy optimization engines with online probes of curvature, plateaus, separability, kinks, basins and fractal structure. Each probe has a default, a dimension-by-budget validity range and a cost charged to the budget. In its pre-registered development loop on bbob, 32 of 36 predictions held over the last 16 confirmations. AMM was then tested once on held-out bbob instances 101-110 (D=2-40, 10*D-1000*D) against up to seven competitors. It has the highest target share in 382 of 600 function-dimension-budget cells (236 outright, 146 tied) and, by a descriptive posterior rule, is credibly behind in 35, mostly at 10*D and 30*D. At every budget it also leads the controls built from its own engines (the best engine alone, the best engine per dimension and budget, and a greedy schedule), narrowly at 10*D and 30*D, and nevergrad's NgIohTuned. In pre-registered runs its lead over IPOP-CMA-ES holds under affine and box transformations, on box-constrained bbob and, pooled, on rotated f2-f4, but rotating the separable f3 and f4 removes most of the lead there. On held-out MA-BBOB its final share at 2000*D is level with IPOP-CMA-ES's and its anytime area lower. We published AMM as an open-source Python package (pip install amm-optimizer; https://github.com/BjBodner/amm-optimizer).

5. PARGAR: Pilot-Aware Graph Attention for Sparse-Pilot Neural OFDM Receivers
Authors: Sajedeh Norouzi, Mostafa Rahmani Ghourtani, Eric Samikwa, Torsten Braun
Link: http://arxiv.org/abs/2611.06432v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 8.5
Abstract: Reliable channel estimation and symbol detection in 5G New Radio (NR), as well as emerging 6G radio systems, rely on demodulation reference signals (DMRS). The density and placement of these pilots on the orthogonal frequency-division multiplexing (OFDM) time--frequency resource grid affect both receiver reliability and spectral efficiency. Sparse DMRS layouts increase the time--frequency distance between pilot observations and data resource elements (REs), which can make pilot information harder to exploit with purely local processing. This paper proposes \textbf{PARGAR (Pilot-Aware Graph Attention Receiver)}, a graph-attention neural receiver that represents the OFDM resource grid as a graph for bit detection. The graph combines local time--frequency edges with pilot-anchor links from data REs to selected pilot REs, and we further study a channel-scaled pilot-anchor rule based on approximate coherence time and coherence bandwidth. Using Sionna-generated OFDM simulations, we evaluate \textsc{PARGAR} against DeepRx, a convolutional neural network (CNN)-based receiver, across dense, two-symbol sparse, and single-symbol sparse DMRS layouts under channel-mismatch scenarios. Under the considered SISO uncoded setup, channel-scaled \textsc{PARGAR} explicitly injects pilot-aware inductive bias and yields lower BER in selected sparse-pilot scenarios while remaining competitive under dense pilots.

## Additional Papers

6. CAPE-JEPA - Cross-modal Adversarial Probabilistic Embedding JEPA | Not Relevant | Unclear | Score: 7.5 | http://arxiv.org/abs/2611.06247v1
7. Learning Pseudo-Riemannian Manifolds for Heterophilic Graphs via Graph Signature | Not Relevant | Experiment | Score: 6.5 | http://arxiv.org/abs/2611.06265v1
8. cuRoboV2-Fast: Fast Torque-Limited Collision-Free Motion Planning | Not Relevant | Unclear | Score: 5.5 | http://arxiv.org/abs/2611.06913v1
9. SpecCompact: Accelerating LLM Agent Context Compaction with Slot-Parallel Semantic Speculative Verification | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2611.06876v1
10. Visual Token Routing: Learning to keep tokens that matter | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2611.06854v1
