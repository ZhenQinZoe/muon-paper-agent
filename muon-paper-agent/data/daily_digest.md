# Daily Muon Paper Digest

## Top Highlights

1. Randomized Momentum Transport with Cheap Predictors
Authors: El Mahdi Chayti, Martin Jaggi
Link: http://arxiv.org/abs/2610.13789v1
Category: Muon-Adjacent Theory
Paper type: Theory
Relevance score: 12.5
Abstract: Momentum methods such as STORM and second-order momentum track the gradient by adding a transport correction to momentum, at the cost of an extra oracle call per iteration. We introduce randomized momentum transport, which evaluates the correction with probability $q$ and otherwise uses a cheap prediction, with importance weighting that preserves the conditional mean and adds $(q^{-1}-1)$ times the prediction loss to the variance. Under transport-bias, second-moment, and residual-control assumptions, linear minimization oracle (LMO) updates, including normalized, sign, and exact spectral (Muon) directions, retain an $O(T^{-1/3})$ stationarity bound for each fixed $q>0$ with a single-gradient initialization. For unnormalized STORM, some $q<1$ lowers the leading coefficient of our sufficient gradient budget if and only if the gradient-difference noise modulus exceeds the smoothness constant, by at most about $10\%$. An online diagonal predictor admits a regret-to-convergence guarantee. At approximately equal oracle cost, querying a quarter of the corrections lowers the final training loss by $18$ to $43\%$ on MNIST1D and raises the test accuracy of Hessian-vector transport on CIFAR-10 by $1.5$ points.

2. Geometry-Aware Multi-Objective Optimization: Norm-Constrained Oracles with Entropic Weight Updates
Authors: El Mahdi Chayti, Alireza Mirrokni, Martin Jaggi
Link: http://arxiv.org/abs/2610.13773v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 6.0
Abstract: Multiple-gradient descent is typically formulated in Euclidean geometry, whereas matrix-aware optimizers use directions induced by other norms. We analyze a single-loop multi-objective method combining a norm-constrained linear minimization oracle with entropic updates of task weights. For any finite-dimensional norm pair, we establish an $O(T^{-1/2})$ ergodic stationarity rate in the deterministic setting, deriving the required trajectory gradient bound from smoothness and lower-boundedness in the unregularized case. With stochastic gradients and a bounded-gradient assumption, one persistent blended-gradient momentum buffer yields an $O(T^{-1/4})$ rate whose leading term has no explicit dependence on the number of tasks. We also establish static regret for the inner weighting objective on arbitrary bounded gradient sequences and, with entropy regularization and a weight floor, iteration-wise inner-gap control after burn-in while retaining ergodic stationarity, conditional on a trajectory gradient bound. The optimal blended gradient can be nonunique in spectral and sign geometries, motivating a selection-independent inner gap. Our analysis extends the spectral construction studied by concurrent MOON to general norms. Experiments compare the method with existing multi-task optimizers and examine its oracle, weighting, and momentum choices.

3. AudioTETRIS: Token Elimination via Transitional Importance Signals for Efficient Audio LLMs
Authors: Shreya Sajid, Anna Vettoruzzo, Joaquin Vanschoren
Link: http://arxiv.org/abs/2610.13600v1
Category: Not Relevant
Paper type: Theory
Relevance score: 8.0
Abstract: Large Audio Language Models (LALMs) achieve strong performance on speech-text tasks, but standard audio encoders produce hundreds of tokens for even short audio clips. Because self-attention scales quadratically in sequence length, this inflates inference-time compute substantially. Current training-free token compression methods prune or merge tokens based solely on coarse attention or feature similarity. However, treating audio tokens as generic, isotropic features smooths over spectral transitions, destroying fine-grained phonetic transitions essential for decoding speech. In contrast, speech signals exhibit highly structured temporal patterns where information density peaks at acoustic transitions. We propose AudioTETRIS, a training-free, two-stage framework that uses the audio encoder's representation geometry as an acoustic prior for token importance before applying attention-based compression. Instead of discarding encoder structure after the encoding stage, AudioTETRIS propagates this prior directly into the LLM decoder to compute a per-token fused score. This score drives progressive top-$k$ token selection across decoder layers without requiring additional training or auxiliary models. Evaluated on Qwen2-Audio-7B, Phi-4-Multimodal, and Audio Flamingo 3, AudioTETRIS retains near-uncompressed performance on several speech tasks using only 25% of audio tokens, matches or surpasses full-token accuracy at moderate compression rates, and consistently outperforms existing training-free baselines.

4. Can Failed Trajectories Reveal Where Agents Go Wrong? Agentic Failure Attribution Without Step-Level Labels
Authors: Do Nguyen-Thanh, Junlin Fang, Bing Li, Zhen Fang, Sean Du
Link: http://arxiv.org/abs/2610.13105v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 6.5
Abstract: Failure attribution for LLM agents aims to identify decisive steps responsible for task failure, which is critical for debugging and improving agentic systems. Existing methods rely on costly LLM prompting, step-level error annotations, or verified successful trajectories that lack failure signals for assistance. In this paper, we study failure attribution from step-unlabeled failure trajectories, where each trajectory is known to have failed but its decisive step is unknown. We propose SOAP (Spectral scOring with Attention-guided Propagation), an effective framework requiring neither step-level training labels nor a separate success-only reference set. SOAP first constructs a spectral reference space from LLM representations and assigns each step a base error score according to its projection behavior. Importantly, later steps may exhibit stronger failure signals because they inherit an earlier mistake, causing independent scorers to favor downstream consequences over the decisive error. To address this downstream contamination, SOAP derives soft step dependencies from attention patterns and propagates downstream error evidence toward its likely upstream sources. Extensive experiments show that SOAP consistently improves attribution performance over competitive baselines.

5. Multi-Stream Attention Residuals
Authors: Xiaohan Qin, Xiangdong Zhang, Tuo Dai, Sunan Zou, Huaijin Wu, Yebin Yang
Link: http://arxiv.org/abs/2610.13630v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 5.5
Abstract: Attention Residuals (AttnRes) enables content-dependent retrieval over network depth, which can be viewed as single-stream softmax attention along the depth axis. Inspired by the success of multi-head attention along the sequence axis, we introduce Multi-Stream Attention Residuals (MSAR), an extension of AttnRes that generalizes this mechanism to multi-head depth attention, yielding substantial performance gains with minimal additional overhead. MSAR draws stream diversity from sequence context through multi-scale causal convolutions, allowing different heads to retrieve historical representations through distinct contextual views while preserving the integrity of the hidden representation. The retrieved streams are combined through lightweight adaptive mixing to generate the single-stream layer input. By retaining single-stream sources and expanding them on demand, MSAR supports multi-stream computation without requiring persistent multi-stream storage or communication. Across all 12 downstream benchmarks at the 18B and 28B MoE scales, MSAR consistently outperforms prior residual variants, including standard residual connections, manifold-constrained Hyper-Connections (mHC), and AttnRes. Scaling-law experiments yield an iso-loss compute speedup of $1.58\times$ over the standard residual baseline, compared with $1.35\times$ for AttnRes and $1.30\times$ for mHC. These results make MSAR a promising residual architecture for large-scale pre-training.

## Additional Papers

6. Data-Adaptive Mahalanobis Metric Learning for Cross-Head Attention in Transformers | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2610.13261v1
7. GuidedNav: Shaping Vision-Language Navigation Representations through Pre-action Attention and Spatial Guidance | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2610.13122v1
8. PANDA: Prior-guided Attentional Dual-path Architecture | Not Relevant | Experiment | Score: 4.5 | http://arxiv.org/abs/2610.13635v1
9. Chronos Policy: Learning Robot Policies on Physical Time | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.13929v1
10. Revisiting Tabular Deep Regression: Objectives and the Limits of Global Early Stopping | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.13909v1
