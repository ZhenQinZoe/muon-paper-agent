# Daily Muon Paper Digest

## Top Highlights

1. Monarch-Muon: Structure-Aware Muon for Fast and Memory-Efficient Pretraining
Authors: Alexander Miasnikov, Ruslan Kabirov, Gleb Molodtsov, Dmitrii Vlashchuk, Vladimir Aletov, Nail Bashirov
Link: http://arxiv.org/abs/2610.17429v1
Category: Muon Core
Paper type: Experiment
Relevance score: 18.0
Abstract: Training large language models is constrained by both wall-clock time and memory footprint, and recent matrix-aware optimizers sharpen this tradeoff: Muon can improve optimization but its dense polar update remains expensive. We propose Monarch-Muon, a structured matrix-aware optimizer for weights parameterized by Monarch factors. The resulting structure reduces weights, gradients, and optimizer state, and exposes small independent update subproblems in place of a single dense orthogonalization; we formalize this through a blockwise trust-region interpretation. In quality runs, Monarch-Muon improves over Monarch-AdamW at fixed structure: 3.06 vs. 3.09 in the dense 257M model and 2.68 vs. 2.77 in the 1B MoE model; the two-block MoE variant also matches dense AdamW while using 15% fewer active and 25.4% fewer total parameters. In 6.89B-parameter systems measurements, Monarch-Muon reduces peak memory from 68.9 to 52.9 GB, Muon optimizer state from 14.60 to 6.77 GB, and the Muon optimizer step from 1288 to 304 ms.

2. From Parallel to Sequential: Small-Batch Noise Restores Simplicity Bias of Muon
Authors: Tom Jacobs, Rebekka Burkholz
Link: http://arxiv.org/abs/2610.16868v1
Category: Muon Core
Paper type: Experiment
Relevance score: 18.0
Abstract: Simplicity bias, which can arise from sequential feature learning during training, has been proposed as a general explanation for the success of deep learning. An important driver of this phenomenon is saddle-to-saddle behavior, in which the gradient flow trajectory remains close to a sequence of saddle manifolds while learning one feature at a time. However, Muon, a state-of-the-art optimizer based on spectral descent, does not exhibit such dynamics in the full-batch setting and instead learns features in parallel. How is it then that Muon is so successful in deep learning settings? We show that stochastic gradient noise fundamentally changes this behavior: small-batch noise restores sequential feature learning, providing a mechanism for simplicity bias that is absent from full-batch Muon. We explain this transition through stochastic smoothing of the spectral descent operator underlying Muon. When gradients are small relative to the noise scale, the expected spectral update becomes approximately proportional to the actual gradient, which restores gradient-flow-like dynamics. We formalize this mechanism for deep linear models by deriving the effective continuous dynamics of noisy spectral descent. Experiments on low-rank matrix reconstruction, vision transformers, and large language models (LLMs) support these findings.

3. Taming Softmax at the Limits of Muon: A Unified Approach through Hilbert Geometry
Authors: Aditya Somasundaram, Charles Guille-Escuret, Alexander Moreno, Zhengzhong Liu, Eric Xing
Link: http://arxiv.org/abs/2610.17588v1
Category: Muon Core
Paper type: Theory
Relevance score: 16.5
Abstract: Muon controls weight updates through the RMS movement of a linear layer's output. This implicitly treats the linear output as a proxy for the full module, including the nonlinearity that follows. This proxy can be misleading for softmax, where the RMS shift in activations does not faithfully measure the change in the output distribution. We propose Hilbert distance as a natural metric for bounding changes in these output distributions. Hilbert distance bounds changes in cross-entropy loss and limits probability redistribution. For softmax, it takes the form of the variation seminorm of the preactivation perturbation, allowing probability constraints to be expressed as parameter constraints. Formulating the steepest descent problem with a Hilbert distance constraint brings two recently proposed methods under a unified mathematical framework. For the LM head, solving a row-wise approximation to the resulting diameter-constrained problem leads us to RowNorm \citep{pethick2025trainingdeeplearningmodels}. For scaled dot-product attention, the same principle yields the first-order query--key steepest descent problem underlying Compositional Muon \citep{keigwin2026compositional}. These connections motivate using Hilbert distance as a guiding principle for optimizer design in softmax modules.

4. Clean: Second-order LLM Training at Linear Memory Cost via Nystr{ö}m Sketching
Authors: Beheshteh T. Rakhshan, Sahar Rajabi, Maziar Sargordi, Shikai Fang, Guillaume Rabusseau, Sirisha Rambhatla
Link: http://arxiv.org/abs/2610.04204v3
Category: Muon-Adjacent Theory
Paper type: Theory
Relevance score: 13.5
Abstract: Training large language models (LLMs) entails a fundamental trade-off: memory-efficient optimizers such as Adam discard cross-parameter curvature, whereas full-curvature methods such as SOAP can accelerate convergence at prohibitive memory costs. We introduce Clean, a memory-efficient and full-curvature optimizer designed to resolve this bottleneck. Clean leverages the randomized Nystrom method to accurately approximate the left and right preconditioners in SOAP, and to reduce the optimizer's memory complexity from quadratic to linear in terms of model dimensions. We subsequently reintegrate the off-subspace components to capture curvature information beyond the low-rank approximation, preserving rich curvature at minimal memory cost. We further propose Q-Clean, a low-precision variant that aggressively compresses optimizer states. Q-Clean reduces optimizer memory consumption by over 50% compared to Muon when pre-training a LLaMA-1.3B architecture, all while maintaining strong and competitive predictive performance. Notably, Clean operates with a smaller optimizer-state footprint than standard AdamW while reaching AdamW's final performance 26% faster in wall-clock time. Furthermore, our methods uniquely enable the pre-training of a 13B-parameter model on a single 80GB GPU, providing a scalable, efficient, and accessible approach to large-scale model optimization.

5. The Best Optimizer Depends on Batch Size
Authors: Xingyu Dang, Kaiyue Wen, Sadhika Malladi
Link: http://arxiv.org/abs/2610.08975v2
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 13.0
Abstract: A plethora of new adaptive optimizers are designed to efficiently estimate and use minibatch gradient statistics to shape parameter updates, but they are typically benchmarked at a single batch size. Hyperparameter scaling rules promise to preserve performance as batch size and gradient noise change, suggesting that the best optimizer at one batch size should remain the best at another. We challenge this approach to developing and evaluating optimizers by showing: (1) no principled scaling rule for Muon works consistently across training settings, and (2) the best optimizer for language model pretraining changes with batch size even after extensive hyperparameter tuning. To understand these failures, we analyze a noisy quadratic model and show that the batch-size scaling rule that preserves performance is direction-dependent, shifting from square-root to linear as a direction's curvature-to-noise ratio rises. We further prove that gradient noise drives a bias-variance tradeoff in preconditioning that can reverse optimizer rankings across batch sizes, even under optimal learning rate and momentum tuning. Consistent with this, when we increase the batch size $16\times$ partway through language model pretraining, keeping small-batch updates in only the sharpest $0.001\%$ of directions removes up to $59.5\%$ of the resulting loss gap over the next $8\%$ of training, while a random subspace of the same size barely helps. Taken together, our results show that principled optimizer design must account for batch size and empirical benchmarking should be performed across batch sizes.

## Additional Papers

6. A Refresh Interval Does Not Fully Specify a Refresh Schedule: Learning-Rate-Dependent Placement in Kronecker-Preconditioned Language Model Training | Muon-Adjacent Experiments | Experiment | Score: 10.0 | http://arxiv.org/abs/2610.18695v1
7. Which Optimizer Leaks Most? Optimizer Implicit Bias as a Training-Data Privacy Controller | Muon-Adjacent Experiments | Experiment | Score: 9.0 | http://arxiv.org/abs/2610.18294v1
8. NBCLT: Parameter-Agnostic Norm-Ball Clipped Local Training | Muon-Adjacent Theory+Experiments | Theory + Experiment | Score: 9.0 | http://arxiv.org/abs/2610.17913v1
9. Neural Dimensional Analysis: Foundations of Dimensionless and Scale-Consistent Computation | Muon Core | Theory + Experiment | Score: 8.0 | http://arxiv.org/abs/2610.17969v1
10. Rate-Splitting Multiple Access for RIS-Enabled Full-Duplex Communications with User Relaying | Not Relevant | Experiment | Score: 8.5 | http://arxiv.org/abs/2610.18578v1
