# Daily Muon Paper Digest

No strong matches today. Showing the best available 10 candidates.

## Top Highlights

1. Humanoid Mobility via Attention-based Contacts
Authors: Junzhe He, Kehan Wen, Chong Zhang, Clemens Schwarke, Zewei Zhang, Kaixian Qu
Link: http://arxiv.org/abs/2610.31608v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 5.0
Abstract: Humanoid mobility over complex terrain requires accurate foot placement and coordinated whole-body motion capable of robust adaptation. Reinforcement learning (RL) policies trained without motion references generalize well across terrains, yet eliciting effective whole-body coordination through reward design and exploration alone remains challenging. In contrast, reference-based methods yield natural motions but struggle to adapt beyond the predefined trajectories in their training data. We introduce a learning framework that bridges these two approaches by using motion data strictly as a training prior. An explicit, self-supervised, attention-based contact planner predicts future body-environment contacts, while a contact-conditioned tracker translates these plans into coordinated whole-body motion. Together, they establish contact as an interface between sensory observations and control actions. This abstraction allows the policy to internalize the contact-aware structure of locomotion rather than directly replicating kinematics. Consequently, a single policy can exploit data-driven motion priors for natural whole-body coordination while retaining the flexibility to discover environment-dependent behaviors through reinforcement learning. Building on the learned contact planner and tracker, a subsequent fine-tuning stage bootstraps their acquired capabilities to explore environment variations beyond those covered by the original motion data. Operating entirely from onboard observations without any reference inputs at deployment, this framework enables versatile humanoid mobility in challenging environments.

2. Diffusion Language Models for Perplexity-Aware Black-Box Attacks
Authors: Ali Al-Lawati, Elsayed Eshra, Dongwon Lee, Suhang Wang
Link: http://arxiv.org/abs/2610.31558v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 5.0
Abstract: \emph{Continuous-space} attacks find prompts that trigger malicious behaviors, such as overthinking, in black-box LLMs by sampling or optimizing over a low-dimensional Gaussian latent space and decoding it to text through a \emph{random mapping} and nearest-token lookup. Because the random mapping is not learned from language, its prompts can be highly unnatural, and as such easily detectable through input guardrails, and the risk estimates they yield are not grounded in natural prompts. In this paper, we demonstrate that the same continuous latent-space framework can be coupled directly to a learned generative distribution over language, a continuous diffusion language model (dLLM), which removes the artificial random mapping while preserving the standard-Gaussian latent formulation and the downstream sampling or optimization procedure. We evaluate this approach under two settings: sampling-based estimation using \emph{RareTrap} and optimization-based search using \emph{ThinkTrap}. We find that character-level perplexity drops from $10^3$--$10^7$ to 3--5 in RareTrap and from 20--28 to 4.3--5.4 in ThinkTrap. We also find that model risk estimates can differ by an order of magnitude across the two mappings.

3. HiP3R: Hierarchical Pose Graphs for Long-Horizon 3D Reconstruction
Authors: Zunnan Xu, Shangchen Zhou, Yihang Luo, Chen Change Loy
Link: http://arxiv.org/abs/2610.31635v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.5
Abstract: Feed-forward models accurately estimate camera motion and 3D geometry from short video windows. However, computational and memory costs prevent direct inference on sequences containing thousands of frames. Long videos must therefore be processed as overlapping chunks. This division produces independent local reconstructions with inconsistent coordinate frames and duplicate estimates of shared cameras. Achieving global consistency requires propagating constraints from adjacent overlaps and distant revisits across the sequence. This requirement naturally motivates pose graph optimization. However, the choice of graph level creates a trade-off. Chunk-level graphs efficiently resolve scale drift and close large loops. Yet, their rigid transformations cannot correct internal errors or conflicting frame predictions. Conversely, frame-level optimization offers local flexibility, but scaling it globally is computationally expensive and can break metric scale. HiP3R resolves this trade-off using a hierarchical pose graph. HiP3R first optimizes a robust chunk-level $\mathrm{Sim}(3)$ graph to establish the global layout and scale. It then holds this layout fixed and estimates one shared $\mathrm{SE}(3)$ camera per frame, turning overlapping window predictions into a single trajectory. Experiments across multiple benchmarks demonstrate the effectiveness of HiP3R in improving camera trajectories and 3D reconstruction. Our method applies to both chunk-based and streaming backends without additional training or fine-tuning. The codes are available at https://kkakkkka.github.io/HiP3R.

4. SympFormer: Inertial Attention Blocks from Damped Hamiltonian Dynamics on Spaces of Probability Measures
Authors: Viktor Stein, Levin Maier, Wuchen Li, Gabriele Steidl
Link: http://arxiv.org/abs/2610.31600v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.5
Abstract: The attention mechanism underpins modern large language models, yet their dynamics remain only partially understood. Recent perspectives interpret attention blocks as interacting particle systems, whose mean-field limits correspond to gradient flows of energy functionals on spaces of probability densities on $\mathbb R^d$ equipped with Wasserstein-type metrics. We extend this viewpoint by deriving accelerated attention blocks from inertial, Nesterov-type damped Hamiltonian dynamics on these density spaces, developing the geometry and differential calculus needed to make the construction rigorous. In particular, we introduce a local-mobility geometry for the Otto-Wasserstein and softmax-Wasserstein settings, and a quotient Stein geometry that resolves the degeneracy of the linear-attention kernel to yield a well-defined metric and differential calculus. We provide rigorous foundations when softmax attention admits a gradient-flow formulation and when its inertial counterpart admits a damped Hamiltonian on explicitly characterized domains. For linear attention, we obtain a finite-dimensional solution theory with sharp conditions for global existence versus finite-time second-moment blow-up. We further prove a quantitative link between continuous moment blow-up and the discrete-layer depth at which token norms cross a prescribed threshold. Finally, motivated by the finite-token geometry, we propose geometric corrections to token and momentum updates. In decoder-only, nanoGPT-style experiments on TinyStories and OpenWebText, these corrections lower validation negative log-likelihood on next-token prediction relative to momentum-only controls.

5. Cross-Spectral Feature Fusion for Multispectral Document Binarization
Authors: Yasas Savinda, Maheshi Buddhinee Dissanayake
Link: http://arxiv.org/abs/2610.30863v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 4.5
Abstract: Historical document binarization remains challenging when faded ink, bleed-through, and background degradation exhibit wavelength-dependent behavior across visible and near-infrared observations. This study investigates whether adaptive cross-spectral feature fusion and targeted structural guidance can improve multispectral document binarization beyond fixed fusion and generic attention mechanisms. Four registered SMADI bands at 500, 600, 700, and 1000 nm are processed using a multi-branch conditional generative adversarial network (cGAN). Visible, NIR, and structural feature streams are fused at encoder depth L = 3 using spatial- and channel-wise softmax gating, while auxiliary edge maps derived from selected VIS-NIR band pairs provide targeted structural guidance. Nine controlled fusion and structural configurations are evaluated using five-fold document-level cross-validation, DIBCO-standard metrics, and Holm-corrected statistical testing. The F3 + NIR edge-guided configuration provides the strongest overall performance among the evaluated models, achieving mean F1 = 0.7916, p-FM = 0.8044, and IoU = 0.6654. Relative to the fixed Mid AVG baseline, it improves F1 by 0.0269, p-FM by 0.0360, and IoU by 0.0321, with all three gains remaining statistically significant after Holm correction. Mean NRM and DRD are also reduced, although these reductions are not statistically significant after correction. Targeted cross-spectral structural guidance provides an effective mechanism for regulating intermediate multispectral fusion, improving primary foreground-overlap performance while retaining the complete four-band observation.

## Additional Papers

6. Evaluating the Applicability of LLM Inference Optimizations on Apple Silicon | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.31479v1
7. How Depth Growth and Looping Shape In-Context Learning in Language Models | Not Relevant | Theory + Experiment | Score: 4.0 | http://arxiv.org/abs/2610.31421v1
8. SQuAT: Spherical Lattice Vector Quantization-Aware Training | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.31412v1
9. Probabilistic Energy Modeling Unifies Versatile Swarm Control | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.31371v1
10. Stream4D: Streaming 4D Reconstruction with Training-free Motion Decoupling via Causal KV-Cache Attention | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.31320v1
