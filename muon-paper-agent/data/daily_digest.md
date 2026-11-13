# Daily Muon Paper Digest

## Top Highlights

1. BiMuon: A Geometry-Aware Stochastic Bilevel Optimization Approach
Authors: Zhen Qin, Zhiyao Zhang, Yingbin Liang, Jia Liu
Link: http://arxiv.org/abs/2611.10188v2
Category: Muon Core
Paper type: Experiment
Relevance score: 25.5
Abstract: Stochastic bilevel optimization provides a general framework for many machine learning applications, such as hyperparameter learning, data reweighting, language model alignment, and actor-critic reinforcement learning. However, most existing bilevel optimization methods treat matrix-valued gradients as flattened vectors and perform optimization in the resulting vectorized space, ignoring the matrix structures common in modern neural networks. Moreover, the lower-level (LL) problem curvature can induce significant spectral imbalance in the upper-level (UL) geometry. Such limitations of existing bilevel optimization methods motivate us to develop BiMuon, a geometry-aware stochastic bilevel optimization method that integrates implicit hypergradient estimation in bilevel optimization with Muon-style orthogonalized updates at the UL. To our knowledge, BiMuon is the first stochastic BLO method with Muon-style orthogonalized matrix updates and an $O(ε^{-4})$ iteration-complexity guarantee, matching the best-known rates achieved by Muon-type methods based on matrix parameterizations. To improve computational and parallel efficiency for models with multiple matrix parameters, we further study BiMuon for blockwise diagonal matrix approximation and derive a relative stepsize allocation rule based on UL progress and blockwise LL sensitivity. We evaluate BiMuon on representation learning and blockwise bilevel optimization, providing empirical support for our methods.

2. Factored One-sided Adam-Moment for Practical and Scalable SOAP
Authors: Jaemyung Yu, Byeongho Heo, Sangdoo Yun, Dongyoon Han
Link: http://arxiv.org/abs/2611.16905v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 13.0
Abstract: Second-order optimizers (e.g., Shampoo, SOAP) have emerged as compelling alternatives to Adam/AdamW and promise faster per-step convergence than AdamW in transformer training. However, they still remain costly in practice, and even SOAP still pays substantial optimizer-state memory and eigendecomposition overhead. We ask whether the benefits of SOAP can be retained at nearly the efficiency of AdamW. In this paper, we answer yes with a lightweight SOAP variant, Factored One-sided Adam-Moment (FOAM). The path to practical impact is twofold: first, FOAM employs input-only preconditioning, dropping the output-side Kronecker factor to reduce memory and remove one eigendecomposition. The Kronecker structure of the Hessian shows that this is exact for a diagonal output-side curvature and nearly lossless for a near-diagonal one, as we observe empirically. Second, FOAM replaces SOAP's dense rotated second moment with a factored Adam-moment estimator based on row-by-column statistics. Under the K-FAC Fisher assumption with a diagonal output curvature, this estimator exactly recovers SOAP's dense second moment, and we measure only a 15-20% K-FAC violation, with negligible effect on the update. Our empirical results support the claim that FOAM matches strong SOAP and Muon baselines in validation loss across scales of large language model (LLM) pre-training, uses half of SOAP's optimizer state, runs at Muon-class wall-clock time, and retains robustness across a three-fold learning-rate range. The results hold from 124M to 760M parameters, demonstrating that SOAP's gains need not require SOAP's cost. Code: https://github.com/naver-ai/foam

3. SS-HSDP: Efficient and Flexible Sharded Data Parallelism via Runtime-Update Decoupling
Authors: Chendong Xiang, Pengle Zhang, Jinliang Li, Zichen Liang, Jintao Zhang, Fan Bao
Link: http://arxiv.org/abs/2611.16467v1
Category: Muon-Adjacent Experiments
Paper type: Experiment
Relevance score: 11.0
Abstract: Sharded data parallelism enables memory-efficient training of large models. While efficient training kernels favor packed, kernel-specific data layouts, optimizers may require variant data structures as optimization units. Existing sharded data-parallel frameworks couple these two choices, limiting runtime efficiency and optimization flexibility. To address this, we present \textbf{\our}, a training framework that separates runtime parameters from update parameters, allowing computation layouts and optimization units to be organized independently. Through shared data views and hierarchical sharding, \our supports this separation while avoiding redundant data movement. This design supports a broad range of optimizers, including matrix-based methods such as Muon, and performance optimizations such as fully zero-copy execution. Experiments on video and language model workloads with MXFP8 training show that \our achieves higher Model FLOPs Utilization (MFU) than FSDP2, veScale-FSDP, and Megatron-FSDP. At 128 GPUs, MFU improves by up to 21.7\% over the fastest evaluated baseline, with comparable or lower peak memory usage.

4. Infrastructure for Verifiable AI: Where Proof Costs Go and How Hardware Can Help
Authors: Yihan Xia, Wenxin Xu, Taotao Wang
Link: http://arxiv.org/abs/2611.17042v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 6.5
Abstract: Users of artificial intelligence services, including those powered by large language models and other transformer-based models, need assurance that inference and training follow the declared computation without exposing private models or data. Zero-knowledge proofs can provide this assurance, but proof generation remains expensive. Hardware acceleration research often reports gains for individual cryptographic operations, leaving their effect on the full cost of proving neural-network workloads, particularly large transformer models, unclear. We introduce a four-layer framework linking verifiable AI workloads, proof systems, cryptographic kernels and hardware platforms, use it to review the literature, and add original measurements of six provers and seven kernels to identify which costs matter in practice. Our measurements show that the dominant cost changes with the proof system and input length. In low-rank fine-tuning, the cost of opening commitments to fixed model weights remains nearly constant across input lengths from 64 to 2048, while the work associated with intermediate values grows. A 13-billion-parameter fine-tuning configuration exceeds the capacity of a 40-gigabyte graphics processor but completes on an 80-gigabyte device, showing why capacity must be assessed alongside execution time. Our kernel profiling further identifies instruction issue and synchronization limits that a bandwidth-only model misses. We use these findings to assess graphics processors, reconfigurable logic, custom chips and existing artificial intelligence accelerators. The resulting research agenda connects proof-friendly numeric formats, reuse of fixed-weight commitments, heterogeneous execution and shared benchmarks to the measured bottlenecks. Effective acceleration requires selecting hardware and proof-system optimizations around the cost profile of the target workload.

5. TokenStream: Multi-Subject Personalized Video Generation with Token-wise LoRA and Guided Attention
Authors: Hung Nguyen, Quang Qui-Vinh Nguyen, Khoi Nguyen
Link: http://arxiv.org/abs/2611.16897v1
Category: Muon-Adjacent Experiments
Paper type: Experiment
Relevance score: 6.5
Abstract: We introduce TokenStream, an optimization-based framework that composes independently learned subject identities in text-to-video generation without a reference-video training dataset or joint optimization of each new subject combination. Learning from a single reference image makes subject appearance difficult to separate from static-image bias, while merging independently trained adapters can mix identities. Token-wise LoRA (ToRA) restricts low-rank updates to the cross-attention value projections of subject-associated text tokens, providing a separate adaptation path for each subject. A T2V-guided stream copies queries and keys from the frozen base model during early denoising to reuse its layout and motion priors while retaining personalized values. We also introduce Multi-DB, a 30-subject, 122-prompt benchmark with appearance-free prompts and varied interactions. On Multi-DB at 1.3B, TokenStream improves identity preservation from 0.422 for DreamBooth to 0.467 and textual alignment from 0.652 to 0.688.

## Additional Papers

6. BlinkMimic: Training a Humanoid Motion Tracker in Minutes on a Single GPU | Not Relevant | Experiment | Score: 9.0 | http://arxiv.org/abs/2611.16422v1
7. TTB: Test-time Baking for Efficient Rendering of Decoder-only View Synthesis Models | Not Relevant | Experiment | Score: 7.0 | http://arxiv.org/abs/2611.17331v1
8. Studies on Sign Language Retrieval in Low-Resource Dictionary Settings | Not Relevant | Experiment | Score: 6.5 | http://arxiv.org/abs/2611.16621v1
9. MALNISI-Infused Graph Construction and Weighted Contrastive Loss based GAT for Unsupervised Representation Learning in HSI | Not Relevant | Theory + Experiment | Score: 6.0 | http://arxiv.org/abs/2611.17199v1
10. Starscream: Reimagining LLM Sharding on AMD Instinct GPUs with GPU Partitioning | Not Relevant | Unclear | Score: 6.0 | http://arxiv.org/abs/2611.15951v1
