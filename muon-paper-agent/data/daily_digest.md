# Daily Muon Paper Digest

## Top Highlights

1. DMuon-2: Scaling Matrix Optimizers in Data Parallelism with Topology-Aware Matrix Ownership and Communication
Authors: Starrick Liu, Ruizhi Chengze, Lufang Chen, Michael Zhao, Ran Yu, Xiaofan Li
Link: http://arxiv.org/abs/2611.07084v2
Category: Muon Core
Paper type: Unclear
Relevance score: 16.0
Abstract: Matrix optimizers such as Muon update whole weight matrices, which conflicts with the element- or row-wise sharding of data-parallel runtimes. Once parameters are sharded as well, matrix optimizers incur extra communication or repeated computation. We present DMuon, a matrix-granular optimizer runtime for PyTorch FSDP (ZeRO-2/3) and HSDP. DMuon assigns each matrix a unique owner, which performs the Newton--Schulz (NS) iteration and optimizer update on the full matrix, and balances the load across owners by computational cost. On HSDP, ownership is global across replicas, so the cluster keeps a single copy of gradients and optimizer state, and updated parameters are published across nodes as soon as they are ready, overlapping subsequent computation. This layout makes every collective sparse and variable in length, so DMuon schedules these collectives as their data becomes ready and routes them along the cluster's two-level network. On up to 256 H100 GPUs, across three dense LLMs and two VLA models, DMuon matches or exceeds the training throughput of PyTorch FSDP2 with AdamW, reaching 1.05$\times$ that of FSDP2 with AdamW at the median on 256 GPUs. The optimized parameter gathering and gradient reduction absorb the extra communication and computation a matrix optimizer requires. Against a gather-then-replicate Muon baseline, DMuon's throughput is 2.1 times as high at the median.

2. Multi-Mode Pinching-Antenna-Based OFDM Systems: A Robust Design Perspective
Authors: Hao Liang, Xidong Mu, Mingzhe Chen, Hyundong Shin, Michail Matthaiou
Link: http://arxiv.org/abs/2611.09591v1
Category: Muon-Adjacent Experiments
Paper type: Experiment
Relevance score: 7.0
Abstract: A robust transmission framework is proposed for a multi-mode pinching-antenna (MPA)-based orthogonal frequency-division multiplexing (OFDM) system under both channel state information (CSI) errors and PA positioning errors. A physical model is first developed based on the multi-mode coupled-mode equations (CMEs), which characterizes the frequency-dependent guided-mode propagation and the coupling among guided modes and PAs over the OFDM band. Based on this model, a worst-case sum-rate maximization problem is formulated to jointly optimize the baseband beamformer and the intended PA positions under CSI and PA positioning errors, subject to user quality-of-service (QoS) and transmit-power constraints. To solve the resulting non convex problem, the worst-case CSI is exactly obtained for any given PA positions by solving trust-region subproblems, while the PA positioning errors are handled by grid-based and second-order approximation-based scenario constructions. Then, an alternating optimization (AO) algorithm is developed, where the baseband beamformer and the intended PA positions are updated via the weighted minimum mean-square error (WMMSE) method and successive convex approximation (SCA), respectively. Both subproblems are solved efficiently by exploiting the Karush--Kuhn--Tucker (KKT) conditions. Numerical results show that the proposed robust design outperforms the non-robust and conventional robust benchmarks with the same multi-mode architecture in terms of both worst-case sum rate and QoS satisfaction. They also demonstrate that the proposed robust design satisfies the QoS requirements of all users more reliably than the baselines that consider either CSI errors or PA positioning errors.

3. Fixed-point acceleration on Neural Wasserstein manifolds
Authors: Vitalii Aksenov, Sebastian Gutierrez Hernandez
Link: http://arxiv.org/abs/2611.09723v1
Category: Muon-Adjacent Experiments
Paper type: Experiment
Relevance score: 5.5
Abstract: We propose a fixed-point acceleration method for optimization over probability measures, applicable to a variety of machine learning problems. We represent probability measures as pushforwards of a reference distribution through a neural network map and equip the parameter space with the induced pullback Wasserstein metric. This geometric structure allows natural gradient descent to be interpreted as a fixed-point iteration on a Riemannian manifold. We accelerate this iteration using Riemannian Anderson mixing method, which exploits historical residuals to capture approximate second-order information without forming Hessians. In the present parametric setting, the manifold is represented by Euclidean coordinates endowed with a point-dependent metric, simplifying retraction and vector transport. We evaluate the method on multimodal sampling, PDE-based inverse problems, aggregation dynamics, Bayesian logistic regression, and generative modeling. Across the tested tasks, Anderson mixing reduces the number of natural-gradient iterations and achieves competitive performance relative to SGD and Adam in terms of both loss-gradient evaluations and wall-clock time. These results suggest that fixed-point acceleration is an efficient tool for improving the computational efficiency of training on parametric Wasserstein methods.

4. Steerable Multi-Objective Group-Relative Preference Optimization with Jointly Trained Low-Rank Adapters
Authors: Constantinos Karouzos, Nikolaos Aletras
Link: http://arxiv.org/abs/2611.09634v1
Category: Muon-Adjacent Experiments
Paper type: Experiment
Relevance score: 5.5
Abstract: Language model deployment often requires different trade-offs between competing objectives as user preferences change, yet standard post-training methods typically produce a single policy for a fixed objective weighting. We introduce LambdaMix, a new parameter efficient method for learning a preference conditioned family of policies with group-relative online reinforcement learning. LambdaMix jointly trains one low-rank adapter per objective over a frozen base model. One preference vector selects the adapter mixture that generates responses and weights the separately normalized rewards used to update the adapters. A single training run supports changing preferences at inference without further optimization. We experiment with four models on helpfulness and harmlessness and on solving math problems while following instructions. We also evaluate the two largest models on rewriting comments to preserve wording while reducing clues about personal attributes. On the first two tasks, LambdaMix achieves higher hypervolume than all evaluated conditioned and policy merging baselines across all four models. LambdaMix uses fewer training completions and stores fewer adapter parameters than a set of GRPO specialist policies. With architecture and initialization fixed, varying adapter mixtures and objective weights together gives wider score ranges and higher coverage than varying either alone.

5. DeepRT-Cal: Learning to Calibrate Ray-Traced Twin Channel Statistics with Low-Fidelity Environmental Geometry
Authors: Shaoyi Liu, Jianhua Zhang, Li Yu, Yichen Cai, Tao Wu, Yuxiang Zhang
Link: http://arxiv.org/abs/2611.09079v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 5.5
Abstract: Sixth-generation (6G) wireless systems increasingly rely on digital twin channels (DTCs) to represent and interact with physical radio environments. Ray tracing (RT) is naturally suited to DTC construction because it provides deterministic and physically interpretable channel predictions. However, high-fidelity three-dimensional environment models are expensive to obtain, whereas geometric inaccuracies in low-fidelity models can alter the detected multipath components (MPCs) and consequently distort received-power and delay-domain twin channel statistics. Building on the DeepRT ray-tracing framework, this paper proposes DeepRT-Cal, a geometry-aware cross-fidelity calibration framework that predicts high-fidelity twin channel statistics from low-fidelity geometry and RT features.The network encodes global link descriptors, masked low-fidelity MPC tokens, propagation-corridor geometry, and link-centered environmental objects. During training, detailed geometry is introduced as privileged information with structured masking, while deployment requires only low-fidelity geometry and low-fidelity RT information. A link-conditioned cross-attention module retrieves the environmental context relevant to each Tx--Rx link. The prediction heads estimate high-fidelity twin channel statistics, including total received power, RMS delay spread, mean excess delay, and a normalized power-weighted power-delay profile (PDP). Outdoor evaluation shows that, in an non-line of sight (NLoS) region, the method reduces power MAE from 16.80 to 3.88 dB and RMS delay-spread MAE from 304.89 to 98.19 ns. In a LoS-dominated region, power prediction improves, while RMS delay-spread accuracy remains comparable to direct RT.

## Additional Papers

6. SSF-Net: A Spatial-Spectral Fusion Network for Accurate PDE Operator Learning | Not Relevant | Experiment | Score: 4.5 | http://arxiv.org/abs/2611.08912v1
7. On the Reliability of Majority-Vote Pseudo-Labels in Test-Time Reinforcement Learning | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2611.09872v1
8. BitDecoding-FP4: Native FP4 KV Cache Decoding via Algorithm-System Co-Design | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2611.09825v1
9. AR-Edit: Training-Free Autoregressive Video Editing without Inversion | Not Relevant | Unclear | Score: 4.0 | http://arxiv.org/abs/2611.09795v1
10. MemoryDojo: Benchmarking Poisoning Through LLM Agent Memory | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2611.09721v1
