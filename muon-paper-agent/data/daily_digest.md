# Daily Muon Paper Digest

## Top Highlights

1. A Quadratic Lens on Muon's Polar Update: Benefits, Pitfalls, and the Role of Newton-Schulz
Authors: Egor Shulgin, Sam Laing, Antonio Orvieto, Peter Richtárik
Link: http://arxiv.org/abs/2610.30280v1
Category: Muon Core
Paper type: Theory
Relevance score: 20.0
Abstract: Muon updates matrix-valued parameters along approximately orthogonalized directions and often trains large language models faster than AdamW, yet it remains unclear when and why orthogonalization helps. We study PolarGD, the orthogonalized update at the core of Muon, on matrix quadratics, where optimizers can be analyzed in closed form, and compare update directions under line search to remove the effect of learning-rate tuning. Orthogonalization pays off when the gradient is far from low rank and its largest singular directions see high curvature. PolarGD reaches the minimizer in one step whenever the rows of the error are orthogonal with equal norms, for any Hessian, whereas gradient descent needs all Hessian eigenvalues to be equal; and unlike sign descent, PolarGD is unaffected by rotations of the problem. Over many steps, PolarGD acts as gradient descent preconditioned by the current iterate, so its speed is governed by the conditioning of the iterate rather than of the Hessian. This explains fast regimes as well as a slow one, caused by tiny singular values of the iterate, in which PolarGD is much slower than gradient descent. Finally, the few Newton-Schulz iterations used in Muon treat these tiny singular values as gradient descent does, so fewer iterations can converge faster than exact orthogonalization; in a transformer trained with Muon, about a quarter of the singular values of the attention matrices fall in this regime.

2. FlashBoB: I/O-Efficient Exact Backward-over-Backward for Softmax Attention
Authors: Anthony Givans, Michael Crawshaw, Mingrui Liu
Link: http://arxiv.org/abs/2609.24089v2
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 8.5
Abstract: Transformer models built on the attention mechanism have become a central building block in modern deep learning, yet softmax attention remains a major bottleneck for long-context workloads. While FlashAttention makes the forward and first backward passes I/O-efficient, it does not support backward-over-backward (BoB), which enables exact differentiation through the backward pass for applications such as second-order optimization, test-time training, gradient-based memory, and meta-learning. Existing BoB implementations either materialize large intermediate tensors or exhaust GPU memory at long sequence lengths. We present FlashBoB, an exact, I/O-efficient algorithm for BoB in softmax attention that keeps computation within on-chip tiles and avoids all $N \times N$ intermediate tensors, where $N$ is the sequence length. The key insight is a hierarchical affine structure in the softmax double backward: two row-wise scalars determine all outputs through affine transformations. This yields a two-pass schedule with bounded on-chip static random-access memory (SRAM) usage and minimal off-chip high-bandwidth memory (HBM) traffic. FlashBoB achieves $Θ(N^2 d^2/M)$ HBM traffic ($d$ is the head dimension and $M$ is the memory size) and, within the standard FlashAttention-style score-recomputation model, matches the inherited large-cache lower bound for exact forward attention. Empirically, it scales exact attention BoB to $N=262\text{K}$ on a single A100 80GB GPU, where prior PyTorch exact baselines fail by $N=16\text{K}$, and is up to $6.3\times$ faster than FlashBack. These results make exact second-order attention practical at long-context sequence lengths where prior implementations cannot run efficiently.

3. IQuest-Q1: Advancing Foundation Capabilities for Agentic CLI Systems
Authors: A. Jian Yang, An Huang, Bo Dan, Chen Mu, Chengran Yang, Chuan Shi
Link: http://arxiv.org/abs/2610.30949v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 9.0
Abstract: We present IQuest-Q1, a sparse Mixture-of-Experts (MoE) agentic foundation model with 320B total parameters (15B activated). IQuest-Q1 is developed through a three-stage process: (1) stable and efficient pre-training, combining Stable SplitNorm, Muon, and muP with a two-stage curriculum whose second stage increases the coding-data mixture, preserving a wide stability margin between safe and optimal learning rates; (2) fine-grained mid-training, expanding the data mixture across domains and formats and progressively extending the context; and (3) multi-scaffold with multi-version post-training, combining SFT, domain-specialized RL, and MOPD across various scaffolds to integrate complementary training signals and strengthen agentic coding capabilities. Furthermore, model merging combines different experts and checkpoints from different stages while mitigating conflicts among their parameter updates. The resulting IQuest-Q1 demonstrates capabilities in both coding and general tasks. We release IQuest-Q1 as an open-source model to support community research and development.

4. Muting Tokens: Exploring Token Sparsification for Efficient Audio Transformers
Authors: Shreya Sajid, Fabrizio Julian Piva, Hiram Rayo Torres Rodriguez, Elif Ceren Gok Yildirim, Murat Onur Yildirim, Joaquin Vanschoren
Link: http://arxiv.org/abs/2610.31235v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 7.5
Abstract: Transformer-based models have shown strong performance across diverse tasks, but their reliance on self-attention mechanisms often leads to high computational costs. Token sparsification, which reduces the number of tokens processed in transformer layers, offers a promising solution to maintain performance while improving efficiency. However, although widely studied in the vision and language domains, token sparsification remains underexplored in audio, with existing work often limited to a single method, model size, or dataset. This work presents a comprehensive evaluation of token sparsification techniques for audio transformers. We assess a range of token pruning and merging strategies across multiple datasets and model sizes, under both post-training and fine-tuning settings. Furthermore, we introduce a novel sparsification approach that combines attention scores with spectral cues derived from the frequency content of token embeddings. Our experiments show that frequency-aware approaches, particularly those based on spectral flatness and low-frequency energy, consistently outperform attention-only methods. We also find that sparsification based on spectrogram patch intensity is especially effective for longer audio inputs. These results highlight the value of incorporating frequency-domain and input-specific information into sparsification strategies to enhance performance in audio tasks.

5. Squaring-the-Sphere: Distortion-Free and Seamless Panorama Generation via CubeAtlas
Authors: Xuhui Zuo, Chenjie Cao, Tengfei Wang, Junta Wu, Yisu Zhang, Chunchao Guo
Link: http://arxiv.org/abs/2610.31565v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 7.0
Abstract: Generating 360-degree panoramas requires both local perspective fidelity and global spherical continuity. Existing representations face a trade-off: equirectangular projection (ERP) enables seamless panorama modeling but suffers from severe distortion and a domain gap to pre-trained image generators, whereas cubemaps preserve perspective geometry but often produce inconsistent faces and visible seams. We present Squaring-the-Sphere, a panoramic image generation framework built on a novel representation CubeAtlas, which unfolds all cubemap faces into a single compact canvas. By arranging orientation-aligned, rotated polar regions alongside the equatorial faces, this representation preserves the perspective geometry of cubemaps while organizing the cross-face relationships required for seamless panorama assembly. It further enables a pretrained diffusion transformer to model the complete panorama jointly in a single pass, without altering the backbone architecture or positional encoding. While CubeAtlas has a token count comparable to ERP, its structured layout makes many dense attention interactions unnecessary. We therefore introduce a layout-aware sparse attention mask that preserves the interactions required for panorama continuity while removing geometrically irrelevant token pairs. As a result, CubeAtlas achieves better quality than ERP modeling with lower attention computation. Furthermore, we introduce a training-free super-resolution technique and a fusion scheme that enhance fine details in distortion-free perspective space before achieving the final ERP panorama. Experiments on various benchmarks demonstrate that our method improves geometric fidelity, cross-view consistency, and high-resolution visual quality over previous methods.

## Additional Papers

6. OpenAttention: One Percent Is Enough with Tail Proxies | Not Relevant | Experiment | Score: 6.5 | http://arxiv.org/abs/2610.30951v1
7. SpectralCanary: Embarrassingly Simple Low-Frequency Traces for T2I Dataset-Use Auditing | Not Relevant | Experiment | Score: 6.0 | http://arxiv.org/abs/2610.31659v1
8. Reliable AI-Assisted Decisions via Selective Auditing | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2610.31662v1
9. BeNice! Closing Looping's Inference-Memory Gap via KV-Sharing | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2610.31633v1
10. Questioning Instrumental Convergence in RLVR: Checkpoint Evidence from OLMo-3 | Not Relevant | Theory + Experiment | Score: 5.5 | http://arxiv.org/abs/2610.31624v1
