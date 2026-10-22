# Daily Muon Paper Digest

## Top Highlights

1. Hybrid Momentum Methods for Optimizing Deep Learning Models
Authors: Haifeng Xu, Yijin Ren, Chenyu Zhou, Qi Deng, Dongdong Ge, Yinyu Ye
Link: http://arxiv.org/abs/2610.27674v2
Category: Muon-Adjacent Experiments
Paper type: Experiment
Relevance score: 16.0
Abstract: Momentum is central to stochastic optimization in deep learning, including the training of large language models. Classical momentum methods typically rely on a fast exponential moving average (EMA) scheme, which discounts past gradients on a fixed timescale and may underweight older gradients that remain informative. This creates a trade-off between retaining long-term history and adapting to recent changes. We introduce Hybrid Momentum (HyM), which combines a linearly weighted average of past gradients with a geometrically discounted fast momentum. The former assigns weights proportional to the gradients' iteration indices and retains a growing span of history, while the latter emphasizes recent gradients. This hybrid construction is modular and can be combined with adaptive preconditioning and other update transformations. In particular, we propose HyMUON, which applies Newton--Schulz orthogonalization to the hybrid direction. Illustrative examples and controlled experiments demonstrate the benefits of combining gradient information across these two timescales. Across image classification, machine translation, and language modeling, HyM and HyMUON match or improve upon strong baselines. HyMUON improves over Muon on IWSLT14, and in both the 100k- and 600k-step GPT-2 124M OpenWebText regimes. For LLaMA-1.3B pretraining on C4, HyMUON achieves a final validation loss of 2.777, compared with 2.903 for Muon.

2. Training-free Acceleration for Blind Compressed Image Restoration via Activation-Calibrated Singular Value Decomposition
Authors: Suhang Yao, Xin Li, Xijun Wang, Yufei Wang, Yeying Jin, Zhibo Chen
Link: http://arxiv.org/abs/2610.29959v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 7.0
Abstract: Transformer-based models achieve strong performance on blind compressed image restoration (CIR) under unknown compression settings, but their densely stacked projection operators make deployment costly. We study training-free acceleration for such models through an empirical, operator-level analysis. Specifically, we profile where computation is concentrated, characterize channel-wise activation distributions under compressed inputs, and examine the singular-value decay of representative projection weights. These measurements identify the recurring projections in the attention, feed-forward, convolutional, and prompt-conditioning pathways as effective low-rank replacement targets that preserve the original inference graph. They further establish truncated SVD (TSVD) as a principled training-free baseline for blind CIR and reveal why a uniform low-rank objective is mismatched to the channel-imbalanced feature distributions of compressed images. Accordingly, we formulate Activation-Calibrated Singular Value Decomposition (ASVD) for this restoration setting, deriving low-rank factors entirely offline from pretrained weights and lightweight activation statistics gathered from only a few compressed calibration images. By weighting the decomposition with channel-wise activation magnitudes, our ASVD assigns larger penalties to errors on more active channels, requiring neither retraining nor online calibration and leaving the restoration pipeline intact. When instantiated on PromptCIR at rank 64, ASVD consistently improves PSNR-B over TSVD across four standard benchmarks under identical parameter and MAC budgets. At this operating point, the factorized model cuts parameters by 59% (34.75M to 14.34M) and computation by 16.1% (258.79 to 217.16 GMACs for a 256 x 256 input), enabling acceleration without retraining.

3. Building SQL Equivalence Proofs from Query Rewrite Rules
Authors: Chunyu Chen, Xinyi Huang, Zhengjie Miao
Link: http://arxiv.org/abs/2610.30100v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 5.5
Abstract: Query rewriting and semantic evaluation of text-to-SQL systems both depend on deciding whether two SQL queries return the same result on every database satisfying the schema constraints. Decades of equivalence-preserving optimizer rules provide a natural basis for constructive proofs: two queries are equivalent when admitted rewrites transform them to a common logical expression. Building on this observation, \sys{} organizes query-rewriting knowledge as a standalone proof-producing system. It separates rule validation from proof discovery, explicitly aligns alternative query representations, and returns the resulting rewrite derivation. Across three corpus classes, EquiTrace proves 648/1,106 expected-equivalent text-to-SQL pairs (58.6%), 229/266 curated pairs (86.1%), and 97/240 LLM-generated rewrites whose results agree under benchmark execution (40.4%). On the query rewrite corpus, EquiTrace proves 97 pairs, compared with 35 for QED and 38 for SQLSolver. An analysis of 1,242 recorded proofs shows that coverage depends on a small number of transformations, while many frequently used rules are individually substitutable. The resulting derivations make each proof replayable and expose the specific transformations on which it depends.

4. How Does Orthogonalization Adapt to the Neural Network Hessian Structure? A Gradient Self Outer-Product Analysis at Initialization
Authors: Shenyang Deng, Garvit Goyal, Tianyu Pang, Shuhua Yu, Yaoqing Yang
Link: http://arxiv.org/abs/2610.28975v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 16.0
Abstract: Muon orthogonalizes a weight matrix's momentum before each step, and on neural networks this simple preconditioner beats AdamW in a wide range of tasks. Existing analyses explain Muon within general optimization frameworks or on a few specific models, and many of them view orthogonalization as a preconditioner. Since the Hessian is the optimal preconditioner under a quadratic approximation of the loss, these works leave a basic question open: what makes orthogonalization suited to the Hessian of a neural network? Prior work shows that the layer-wise Hessian of a neural network is row-block diagonally dominant, and Muon's implicit preconditioner, the Kronecker product $(\mathbf{V}\mathbf{V}^\top)^{1/2}\otimes\mathbf{I}$ with $\mathbf{V}$ the momentum, has the same row-block structure exactly when $\mathbf{V}\mathbf{V}^\top$ is diagonally dominant. Diagonal dominance of $\mathbf{V}\mathbf{V}^\top$ has been observed in language models, but why a neural network produces it has not been explained. This work provides a quantitative asymptotic theory for neural networks at initialization, and points out the intuition that the overparameterization of the weight matrices drives the diagonal dominance. We analyze $\mathbb{E}[\mathbf{G}\mathbf{G}^\top]$, which equals $\mathbb{E}[\mathbf{V}\mathbf{V}^\top]$ at initialization, in four canonical models: symmetric matrix factorization, deep linear networks, two-layer ReLU networks, and single-layer linear attention. In each case the diagonal entries outgrow the off-diagonal ones at explicit rates as the hidden dimensions grow; for the query, key and value weights of attention the off-diagonal vanishes altogether. Simulations of the four models and experiments on language models at initialization confirm the predicted scaling.

5. Speedrunning Relational Foundation Model Pretraining
Authors: Gabriel Wedson Mendonça de Souza Veloso, Luan Borges Teodoro Reis Sena, Denis Oliveira Correa, Francisco Galuppo Azevedo
Link: http://arxiv.org/abs/2610.28855v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 11.0
Abstract: Progress on foundation model pretraining is gated by who can afford a trial, and relational pretraining is no exception. Recipes are developed inside individual labs, reported under private protocols, and do not accumulate. Speedrun leaderboards remove that barrier by decentralizing the search rather than the training run. The problem is fixed, the stack is open, entries are ranked by wall-clock time to a quality target, and one GPU is enough to hold the record. We introduce modded-nanoRT, the first such leaderboard for Relational Transformers. Which database to hold out decides whether the benchmark can resolve improvements at all, so we fix it by calibration, ranking six candidates by how sharply a 45-minute learning curve separates improvement from seed noise. We open the leaderboard with typed trilinear attention, a relational operator that conditions attention scores and values on the foreign key traversed, together with Muon and SIGReg. The recipe reaches the target in 305.63 seconds on one NVIDIA H200, 8.11x faster than the reference implementation, and wins 13 of 15 pairs outside the development database. We will release the benchmark, its frozen artifacts, and the record runs. Our code is available at https://github.com/kunumi/nanoRT.

## Additional Papers

6. BrainCodes: A Lightweight EEG Foundation Model over Discrete Neural Codes | Not Relevant | Experiment | Score: 9.0 | http://arxiv.org/abs/2610.29320v1
7. NeuroCodec: EEG-Guided Latent-Domain Generative Model for High-Fidelity Target Speaker Extraction | Not Relevant | Experiment | Score: 7.5 | http://arxiv.org/abs/2610.29815v1
8. Worst-Case Finite-Horizon Analysis of Perturbed LQR via Performance Estimation Problem | Not Relevant | Theory | Score: 7.0 | http://arxiv.org/abs/2610.29910v1
9. BlazeVGGT: 13x Faster VGGT at 2,000 Frames via Camera Token without Training | Not Relevant | Theory + Experiment | Score: 6.5 | http://arxiv.org/abs/2610.29454v1
10. GaP-MoE : Explicit Expert Specialization in Mixture-of-Experts via Orthogonal Gradient Accumulation and Projection | Not Relevant | Experiment | Score: 6.0 | http://arxiv.org/abs/2610.29355v1
