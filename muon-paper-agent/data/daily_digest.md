# Daily Muon Paper Digest

## Top Highlights

1. NABLA: A Noise-Adaptive Blockwise Left-Right Preconditioning Algorithm for Stochastic Optimization
Authors: Yanlin Li, Ganzhao Yuan
Link: http://arxiv.org/abs/2611.32781v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 7.5
Abstract: We propose NABLA, a noise-adaptive blockwise left-right preconditioning algorithm for mini-batch stochastic nonconvex optimization. NABLA combines an exponential moving average of stochastic gradients with block-diagonal row and column preconditioners constructed from matrix-valued second-moment statistics. Unlike conventional matrix-preconditioned methods that use fixed decay parameters, NABLA adjusts the second-moment averaging coefficient through a closed-loop feedback rule determined by the cumulative stochastic-gradient energy and its running average. The first-moment coefficient remains fixed, allowing the trajectory-dependent adaptation to act directly on the structured preconditioners. The resulting method is horizon-free, requires no prior knowledge of the noise level, and automatically adjusts the memory of its second-moment estimators to the observed optimization dynamics. Under standard lower boundedness, smoothness, unbiasedness, bounded-variance, and spectral-boundedness assumptions, we establish uniform stability and variation bounds for the time-varying block preconditioners and control their interaction with momentum estimation and parameter updates. These results yield the noise-adaptive stationarity guarantee $\widetilde{\mathcal{O}}(T^{-1/2}+σ^{1/2}T^{-1/4})$, which automatically reduces to the nearly deterministic $\widetilde{\mathcal{O}}(T^{-1/2})$ rate when the stochastic-gradient noise vanishes. NABLA therefore provides a principled approach to combining closed-loop trajectory feedback with memory-efficient structured matrix preconditioning.

2. Scaling Laws of Ensemble Uncertainty in Language Models
Authors: Siamak Ravanbakhsh, David Nitchi, Khang Ngo
Link: http://arxiv.org/abs/2611.32801v1
Category: Muon-Adjacent Theory
Paper type: Theory
Relevance score: 7.0
Abstract: Many use cases for large language models (LLMs)---from AI safety to exploration and human interaction---can benefit from epistemic uncertainty estimates. We argue that existing Bayesian Deep Learning solutions, which are often restricted to a fixed model family, fail to capture the full epistemic uncertainty at practical LLM scales. This is because the error due to the bounded capacity of the model family remains invisible to disagreement among models supported by the prior. We relate this error to the well-known power-law scaling of LLM loss with model size. We then show that a second power law quantifies the shrinking disagreement within ensembles as model size increases. Its slower decay relative to the capacity law above suggests that ensembles capture a growing share of epistemic uncertainty and become more competitive as an axis for scaling, compared to a single larger model. Finally, a third power law quantifies the loss of ensemble diversity as members share a larger fraction of training before branching, and therefore identifies a further limitation, beyond the capacity error, for LoRA ensembles and optimization-based or second-order methods that approximate uncertainty around a single training solution. At a high level, these findings suggest diverse ensembles can be a promising axis, both for scaling and uncertainty quantification at larger scales.

3. How to build and train your recurrent-depth model: A fixed-point perspective
Authors: Thomas Pethick
Link: http://arxiv.org/abs/2611.31513v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 11.5
Abstract: Recurrent-depth models are trained with truncated backpropagation, yet it remains unclear why this works. We show that input injection, commonly used in recurrent-depth models, is exactly Halpern iteration, and that a slowly vanishing stepsize provably converges with a backpropagation window polylogarithmic in the depth. The guarantees require a Lipschitz operator, which for SwiGLU leads to a weight constraint in both row and spectral norm, while only a row norm constraint for gates. Based on these constraints, we develop an optimizer tailored to each parameter group, Sparrow, which provides a drop-in replacement of Muon/MuonH with no overhead, that speeds up training even beyond recurrent models.

4. MetaFORGE: A Meta-Learning Framework for Harness Optimization in Automated Code Generation for Parallel Computing
Authors: Scott Piersall, Yang Gao, Shenyang Liu, Liqiang Wang
Link: http://arxiv.org/abs/2611.33119v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 7.0
Abstract: Large language models (LLMs) can generate parallel programs, but their correctness and performance depend strongly on the instructions that guide generation. We present \textsc{MetaFORGE}, an execution-grounded meta-learning framework that iteratively optimizes persistent natural-language skill specifications for MPI C code generation. \textsc{MetaFORGE} combines correctness testing, compiler diagnostics, static-analysis findings, runtime measurements, and rank-level load-imbalance profiles into a scalar reward that drives textual-gradient refinement, while an external memory distills and retrieves reward-supported optimization knowledge across runs. Across six MPI tasks and three workload sizes, \textsc{MetaFORGE} improves static-analysis quality, runtime, and load balance relative to zero-shot generation and generally exceeds the evaluated \textsc{TextGrad} iterative baseline. A model-matched refinement ablation shows that the MetaFORGE advantage persists when its refinement model is reduced to \texttt{gpt-4o}. An expanded retrieval ablation across all 18 task--workload configurations shows consistent runtime benefit and broad static-analysis and load-balance benefit from retrieved context. Leakage-controlled held-out and zero-update experiments further provide evidence that optimization knowledge persists in both the transferred skill and external memory under the evaluated protocol.

5. ObsBridge: Observation-Grounded Conditioning for Ego Trajectory Prediction
Authors: Zhenhao Wang, Shaofeng Liang, Jiemin Wu, Sijia Chen, Keni Shi, Nan Li
Link: http://arxiv.org/abs/2611.32447v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 6.5
Abstract: Pedestrian forecasting from ego-view observations is challenging because occlusion, limited visibility, and tracking errors corrupt observed motion histories. Such errors are particularly consequential for autonomous robot navigation. Existing paradigms typically either impute noisy history positions before forecasting or jointly train an auxiliary history reconstruction branch. However, predictors trained on clean histories may be sensitive to residual errors in recovered histories at deployment. Meanwhile, auxiliary reconstruction still computes inter-agent interactions over raw, corrupted coordinates. We investigate conditioning future prediction on both recovered historical states and raw observation evidence, with progressive training to accommodate imperfect recovery. Building on this insight, we propose ObsBridge, a flow-based trajectory forecasting framework with observation-grounded historical bridging. Specifically, ObsBridge first employs a frozen estimator to recover historical motion from agent-relative and ego-relative positions, image-plane locations, and visibility states. During training, we introduce an agent-wise curriculum that gradually replaces clean teacher histories with complete estimated histories before context encoding. This progressively exposes the predictor to estimated histories during training. Furthermore, we design a residual geometry adapter to fuse the encoded motion with original observation evidence. We aggregate the resulting representations through social attention to condition the flow-based trajectory generator. Extensive experiments across multiple benchmarks demonstrate that ObsBridge outperforms state-of-the-art methods. On EgoTraj-TBD, it reduces minADE@20 by 6.5\% and minFDE@20 by 8.7\%. The code will be provided at https://github.com/shawnliang420/ObsBridge.

## Additional Papers

6. QoS-Constrained Sum-Rate Maximization in RIS-Assisted Pinching-Antenna NOMA Systems | Not Relevant | Theory + Experiment | Score: 6.0 | http://arxiv.org/abs/2611.32849v1
7. Self-Orthogonal Minimal Codes from n-to-1 Mappings | Not Relevant | Theory | Score: 6.0 | http://arxiv.org/abs/2611.32192v1
8. A Unified Control Framework for Gradient Inversion Defense in Federated Learning | Not Relevant | Theory + Experiment | Score: 6.0 | http://arxiv.org/abs/2611.32174v1
9. Auditing the Judge: Human-Derived Bias Discovery, Quantification, and Mitigation in LLM Judges | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2611.33065v1
10. U-Statistics-Powered LLM Reasoning | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2611.33064v1
