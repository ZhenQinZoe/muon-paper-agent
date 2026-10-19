# Daily Muon Paper Digest

## Top Highlights

1. BMuon: Budgeting Muon's Spectral Geometry for Structured Compressibility
Authors: Rida Assalouh, Tom Jacobs, Rebekka Burkholz, Yani Ioannou, Umut Şimşekli
Link: http://arxiv.org/abs/2610.23571v1
Category: Muon Core
Paper type: Unclear
Relevance score: 16.0
Abstract: Muon has emerged as a strong optimizer for neural network training and admits an interpretation as steepest descent under a spectral-norm geometry. Yet we find that Muon-trained Transformers can degrade sharply when their MLP hidden channels are pruned after training. To reconcile Muon's optimization performance with structured compressibility, we introduce Budget Muon (BMuon), which modifies Muon's spectral geometry so that hidden channels across blocks compete for a shared allocation budget. The resulting oracle is exactly normalized steepest descent under a family of norms that interpolate between Muon's geometry and structured sparse geometries. Our principal sparsity control is an interpretable global channel-allocation budget, rather than a setting-dependent sparsity-penalty coefficient. For linear factorization models, we show that Muon admits minimum-cost exact representations with redundant hidden width, whereas under the BMuon oracle geometry and a sufficiently scarce budget, every minimum-cost representation is width-minimal. For practical training, we derive a minorization-maximization surrogate for the exact allocation problem. On ImageNet-1K with ViT-S/16, BMuon improves over Muon under gradual structured MLP pruning, and its learned allocations provide a more effective pruning criterion than weight magnitude. On a 1B-parameter LLaMA-style model trained on FineWeb, BMuon improves over Muon under post-training MLP channel pruning.

2. Bridging Compressed Communication and Local Steps via Spectral Method in Federated Learning
Authors: Dmitriy Bystrov, George Chirkov, Daniil Medyakov, Dmitry Bylinkin, Aleksandr Beznosikov
Link: http://arxiv.org/abs/2610.23434v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 10.5
Abstract: Federated Learning (FL) enables collaborative training of complex models across large-scale networks of edge devices while keeping data localized. However, data heterogeneity and high communication overhead remain fundamental bottlenecks. Recently, the spectral optimizer Muon has demonstrated remarkable advantages over Adam-like methods in centralized training. While recent efforts have attempted to transition Muon to FL, naive integrations into traditional architectures fail short. Crucially, existing approaches do not support the the communication compression and local steps --- the two foundational techniques of efficient FL. To address this limitation, we introduce a novel spectral FL method that utilizes both local updates and compression. We establish rigorous convergence guarantees under mild assumptions, notably eliminating the restrictive bounded heterogeneity condition. Empirical evaluation on standard image classification benchmarks validates the efficiency and robustness of our approach.

3. Towards Hyperparameter Transfer for Differentially Private Optimization
Authors: Tianze Wang, Zhiqi Bu, Linjun Zhang
Link: http://arxiv.org/abs/2610.22976v1
Category: Muon Core
Paper type: Theory + Experiment
Relevance score: 9.0
Abstract: Scaling laws and hyperparameter tuning remain central challenges in training large-scale models, particularly under differential privacy (DP), where optimization is further complicated by noise injection and per-sample gradient clipping. While Maximal Update Parametrization ($μ$P) allows for zero-shot hyperparameter transfer in standard training, we show that it fails under DP constraints due to the distinct spectral properties of high-dimensional noise versus low-rank gradients. In this work, we introduce DP-$μ$P, a theoretically grounded framework that extends $μ$P to the privacy-preserving setting. By analyzing the interaction between gradient clipping, noise injection, and feature learning, we derive a Signal-to-Noise Ratio (SNR) condition that governs layer-wise learning rate scaling. Combining this with our proposed spectral scaling formulation, we provide specific scaling rules for DP-SGD, DP-Adam, and DP-Muon optimizers. Empirically, we demonstrate that DP-$μ$P enables effective zero-shot transfer of learning rates across model widths on diverse architectures (MLP, ViT, GPT-2), matching or exceeding the performance of individually tuned baselines while significantly reducing computational costs.

4. How Finite-Rank Bottlenecks Shape the Low-Rank Adaptation Landscape
Authors: Long Nguyen-Chi, Quynh Nguyen, Thanh Nguyen-Cung, Binh T. Nguyen
Link: http://arxiv.org/abs/2610.23343v1
Category: Muon-Adjacent Theory
Paper type: Theory
Relevance score: 8.0
Abstract: Low-rank adaptation (LoRA) has become the standard method for parameter-efficient fine-tuning of large pretrained models, yet theoretical explanations for why low-rank updates suffice remain incomplete. Most existing analyses rely on the Neural Tangent Kernel (NTK) regime, which linearizes the network around the pretrained weights. In this work, we take a different approach that requires no linearization: our key observation is that, once the backbone is frozen, the loss sees each adapted weight matrix only through a finite-rank linear map induced by the frozen activations. Trace-norm regularization then forces the optimizer to pick a low-rank matrix among all matrices that produce the same observed output. This yields global minimizers whose ranks are controlled by the rank of this map, which we call the \emph{bottleneck rank}, rather than the sample size. For multi-head attention, we obtain tighter rank upper bounds by exploiting two additional invariances: row-wise softmax is insensitive to additive row constants in the score matrix, and value updates are observable only after attention weighting and frozen output projection. For the factorized LoRA objective with weight decay, we prove a complementary result on the nonconvex side: after an arbitrarily small generic positive semidefinite perturbation, every first-order stationary point is rank-deficient once the LoRA rank exceeds a threshold determined by the bottleneck rank. Finally, we show that global minimizers of the perturbed objective are near-optimal for the original trace-norm problem, and we provide uniform generalization bounds governed by the spectral structure of the frozen features.

5. Does On-Policy Distillation Need to Complete Every Rollout?
Authors: Zhengxin Zhang, Maosen Tang, Ning Wang, Changhao Li, Jingren Zhou, Bo Dai
Link: http://arxiv.org/abs/2610.21337v2
Category: Muon-Adjacent Theory
Paper type: Theory
Relevance score: 8.0
Abstract: On-policy distillation (OPD) effectively transfers capabilities from a teacher to a student through feedback on student-generated rollouts. However, generating complete student rollouts and computing teacher feedback for every token make OPD computationally expensive. We introduce Stochastic Truncated On-Policy Distillation (STOPD), which accelerates OPD by randomly truncating student rollouts and correcting the resulting sampling bias with blockwise inverse-probability weighting (IPW). At each training step, we sample a stopping position for each rollout before generation and let the student generate until that position or natural termination. We obtain teacher feedback on every generated token and use blockwise IPW to compensate for the lower probability of retaining later tokens while controlling the weights. We prove that this weighting preserves Vanilla OPD's gradient sum in expectation and derive one-step update-error bounds for SGD, Adam, and Muon. We evaluate STOPD across multiple teacher-student model pairs, task domains, and optimizers. STOPD reduces generated tokens by 25-48% while maintaining accuracy comparable to Vanilla OPD, achieving 1.3-2.2x training speedups.

## Additional Papers

6. The Ephemeral Cost of Switching Optimizers Across LLM Training Stages | Muon Core | Experiment | Score: 7.0 | http://arxiv.org/abs/2610.22650v1
7. CatchUp: Depth-Aware Re-Admission of Visual Tokens for Efficient Large Vision-Language Models | Muon-Adjacent Experiments | Experiment | Score: 5.5 | http://arxiv.org/abs/2610.23324v1
8. ToPA: Block-wise Toeplitz Adaptation for Expressive and Efficient Fine-Tuning | Muon-Adjacent Theory+Experiments | Theory + Experiment | Score: 5.5 | http://arxiv.org/abs/2610.22883v1
9. Ori: Drift-Aware Streaming $k$-PCA for Very Low-Rank LLM Training | Muon-Adjacent Experiments | Experiment | Score: 5.5 | http://arxiv.org/abs/2610.22794v1
10. Anisotropic Representation Dynamics in Transformers | Not Relevant | Theory + Experiment | Score: 6.0 | http://arxiv.org/abs/2610.23242v1
