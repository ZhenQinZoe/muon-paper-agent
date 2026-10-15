# Daily Muon Paper Digest

## Top Highlights

1. From Spectral to Frobenius: When Muon Loses Its Spectral Implicit Bias
Authors: Yongtao Wu, Mahdi Mansouri, Zhenyu Zhu
Link: http://arxiv.org/abs/2610.20112v1
Category: Muon Core
Paper type: Theory + Experiment
Relevance score: 20.5
Abstract: Prior work on implicit bias shows that gradient descent selects the Frobenius max-margin direction on linearly separable problems, whereas Fan et al. (2025) established spectral max-margin behavior for spectral-norm steepest descent methods, including idealized Muon with exact orthogonalization. In practice, however, Muon approximates orthogonalization using finite Newton-Schulz iterations and a positive stabilization constant. We prove that these implementation choices cause Muon to select the Frobenius rather than the spectral max-margin direction in linear classification with separable data. We also establish this behavior for both exponential moving average and Nesterov-style momentum. The key technical ingredient is a summable perturbation argument showing that the resulting parameter trajectories remain at bounded distance from those of gradient descent. We then disentangle the roles of Newton-Schulz iteration count, the stabilization constant, and the Newton-Schulz polynomial, revealing distinct asymptotic behaviors, including directions that achieve neither Frobenius nor spectral max-margin. Finally, we show that Muon can recover its spectral max-margin bias with Newton-Schulz iterations growing logarithmically over training.

2. Memory-Efficient Subspace Optimization with Residual Correction: From Momentum SGD to Muon
Authors: Sifan Yang, Hongyi Tao, Dingzhi Yu, Haomin Bai, Wei Jiang, Silin Gao
Link: http://arxiv.org/abs/2610.19844v1
Category: Muon Core
Paper type: Theory + Experiment
Relevance score: 18.0
Abstract: Memory-efficient subspace optimization has emerged as a practical approach to reducing the memory cost of LLM training while preserving optimization performance. Previous algorithms typically rely on the leading singular subspace of stochastic gradients, yet the gradient noise may dominate the subspace in later training stages and can prevent convergence. To overcome this limitation, we adopt a residual correction framework, which maintains the optimizer states in the subspace and adds the orthogonal residual gradient to the parameter update. We first integrate this scheme into momentum SGD to develop SMRC, which attains an $O(T^{-1/4})$ convergence rate for a fixed orthonormal basis, matching that of full-space momentum SGD. Our analysis introduces a subspace virtual iterate to resolve the coupling between the momentum and the residual correction. Furthermore, we extend SMRC to a multi-stage variant which periodically recomputes bases to track the evolving dominant subspace and retains the same rate. Since each basis refresh breaks the consistency of the virtual iterates, we devise a boundary correction approach that aligns them across stages. Beyond momentum SGD, we incorporate our framework into Muon and propose PMRC, which applies the matrix sign to the projected momentum. Through a weighted momentum tracking analysis that accounts for the residual gradient, we establish an $O(T^{-1/4})$ convergence rate for PMRC, which matches the rate of full-space Muon. We also design a multi-stage PMRC with periodically refreshed bases, which maintains a convergence rate of the same order. Extensive experimental results confirm the effectiveness and efficiency of our algorithms.

3. Long-Horizon RL Needs Muon
Authors: Kai Ruan, Jinghao Lin, Tao Chen, Ziqi Zhou, Qianshan Wei, Zihe Huang
Link: http://arxiv.org/abs/2610.20256v1
Category: Muon Core
Paper type: Unclear
Relevance score: 13.0
Abstract: Long-horizon agents must coordinate reasoning, tool use, and environment feedback over extended interactions. Learning from sparse outcome rewards requires weighting trajectories of different lengths and updating the policy while rollouts are still being collected. We examine a single-rollout asynchronous recipe combining Muon, token-averaged loss, truncated importance sampling, and auxiliary length and tool-error penalties. Single-rollout sampling allows asynchronous learning without waiting for multiple trajectories for the same issue. We study optimizer choices and recipe components for repository-level issue resolution across two model families. The evaluated training runs show higher training success with the full recipe than with the baselines.

4. How Inner Optimizers Shape Replica Scaling
Authors: Eugene Belilovsky, Stefan Horoi, Edouard Oyallon, Benjamin Thérien
Link: http://arxiv.org/abs/2610.19064v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 13.0
Abstract: Training large language models (LLMs) across geographically distributed and poorly interconnected compute pools or data centers has become a topic of significant interest. This has led to increased study of local optimization methods such as DiLoco for LLMs, especially those that use local (or inner) adaptive or preconditioned optimizers, which are critical for high-performance LLM training. However, a central challenge remains: it is well known that increasing the number of model replicas (replica scaling) while fixing the total training budget leads to monotonically decreasing performance. Existing work has empirically demonstrated that the choice of inner optimizer (Muon v.s. AdamW) can significantly improve this trend, but offers only limited explanation of the performance difference. In this work, we consider a range of inner-optimizers and identify two important factors that impact replica scaling: (1) the covariance structure of the pseudo-gradients and (2) the impact of batch size on the pseudogradient's noise scale. Based on these insights, we theoretically and empirically demonstrate that whitening-based pre-conditioning is a powerful inner-optimizer desideratum. Our empirical evaluation extends the results to reveal that whitening-based inner-optimizers achieve strong replica scaling (for 8-96 replicas), with performance relative to DP improving as parameters and data are scaled.

5. StructZO: Structured Zeroth-Order Optimization for Memory-Efficient LLM Fine-Tuning
Authors: Xuanlin Yang, Jia Li, Zhouchen Lin
Link: http://arxiv.org/abs/2610.16451v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 8.0
Abstract: Fine-tuning large language models at scale is increasingly limited by the memory cost of backpropagation. Zeroth-Order (ZO) optimizers reduce this burden by relying only on forward function evaluations, but they still exhibit a substantial performance gap to first-order (FO) optimizers such as Adam. We argue that this gap does not arise solely from the absence of explicit gradients: FO fine-tuning also benefits from informative low-rank optimization geometry, large-scale signal aggregation, and well-conditioned update directions. Motivated by this, we introduce StructZO, a structured Zeroth-Order optimization framework for memory-efficient LLM fine-tuning. StructZO performs large-query ZO estimation within an activation-induced informative subspace and applies spectral control to the resulting reduced-space update before mapping it back to the original parameters. This lets ZO aggregate useful directional signals in a compact, geometry-aware space while avoiding the activation and optimizer-state memory costs of backpropagation. We show theoretically that, when the induced subspace captures concentrated optimization-relevant directions, StructZO reduces the effective ZO estimation dimension from $mn$ to $mr$, with the remaining projection error governed by the spectral tail of the activation Gram matrix. Empirically, across OPT-series and Llama3.1-8B on diverse downstreamtasks, StructZO improves over the strongest existing ZO baselines by up to $8.7%$ relative on average and up to $26.9%$ relative on individual tasks, while remaining within $1.5%$ of FO-Adam on average. These results suggest that structured and spectrally controlled ZO updates can substantially narrow the gap between ZO and FO optimization.

## Additional Papers

6. Continual pretraining Prostate MRI ViT Encoder for task alignment | Muon-Adjacent Theory+Experiments | Theory + Experiment | Score: 6.5 | http://arxiv.org/abs/2610.20217v1
7. From Mixing to Tearing: Graph Decomposition in Decentralized Optimization via Message Passing | Not Relevant | Theory + Experiment | Score: 9.0 | http://arxiv.org/abs/2610.03709v2
8. ACR-Net: Mitigating Semantic Dominance via Contrastive Acoustic-Semantic Decoupling | Not Relevant | Experiment | Score: 8.0 | http://arxiv.org/abs/2610.20114v1
9. Can Learning to Answer Spatial Questions Improve Novel-View Generation? | Not Relevant | Theory + Experiment | Score: 7.0 | http://arxiv.org/abs/2610.20610v1
10. GeoThinker-$F$: Endogenous Predictive World Representations for Fast Spatial Intelligence | Not Relevant | Experiment | Score: 7.0 | http://arxiv.org/abs/2610.20592v1
