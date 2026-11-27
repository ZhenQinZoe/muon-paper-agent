# Daily Muon Paper Digest

## Top Highlights

1. BReD: Block Replay Dithering for Stable Low-Bit EMA Optimizer States
Authors: Heshen Zhan, Youhan Huang, Yunke Peng, Yao Wang, Linghui Kong, Ziwei Zhu
Link: http://arxiv.org/abs/2611.33951v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 5.0
Abstract: Low-bit storage of optimizer states can substantially reduce the memory footprint of large-scale training. In practice, however, these states are not quantized once: at every training step, they are dequantized, updated, requantized, and written back. This iterative quantization pipeline can destabilize training. We identify a failure mode behind this instability: for states updated via exponential moving averages (EMAs), quantization errors are recursively fed into subsequent updates. As a result, biased errors accumulate over time while high-variance errors are amplified, particularly when the EMA decay factor is close to 1. To address this error accumulation, we propose BReD (Block Replay Dithering), a method that reduces rounding bias and controls rounding variance during quantization. BReD adapts classical subtractive dithering to optimizer-state quantization by combining deterministic seed replay with block-wise shared dither values, avoiding auxiliary random-tensor storage and per-element dither values generation. Across the default pretraining settings (five optimizers at 120M; AdamW and Muon at 1.1B and 3.4B model) and supervised fine-tuning (AdamW and Muon at 7B model), 4-bit BReD closely matches training with full-precision optimizer states, with PPL shifts $\leq0.5$ in pretraining and $\leq0.2$ in fine-tuning and average downstream performance changes within 0.7 points. Moreover, 3-bit BReD preserves stable convergence in the evaluated settings, offering a more aggressive alternative. Our implementation of BReD is available at: https://github.com/ZhanHeshen/BReD

2. BRIAR: Martingale Belief Smoothing on Bifurcation-Guided Reasoning Trees
Authors: Tianyi Yang, Haoran Zhang, Yifan Chen, Zixuan Li
Link: http://arxiv.org/abs/2611.34746v1
Category: Muon-Adjacent Theory
Paper type: Theory
Relevance score: 4.5
Abstract: Reinforcement learning with verifiable rewards (RLVR) has rapidly advanced long-chain reasoning, yet standard policy optimizers distribute rollout compute and gradient credit blindly across a trajectory. On hard problems, an early misstep derails the remaining trace, whereas on solvable problems, the policy keeps generating redundant verification long after the answer is already determined. We trace both pathologies to a single structural fact: under an on-policy verifier, the true prefix pass probability $V^π(u)$ along a reasoning trace forms a $[0,1]$-bounded Doob martingale whose learnable credit variance is strictly conserved and bounded above by $V^π(u)(1-V^π(u))$, vanishing at both the derailed ($V^π\to 0$) and absorbed ($V^π\to 1$) boundaries. We introduce BRIAR (Bifurcation-guided Rollout and Inference on Adaptive Reasoning trees), a tree-structured RLVR framework built directly around this martingale geometry. First, BRIAR expands discourse-aligned reasoning trees along an upper-confidence outcome-bifurcation frontier, steering rollouts away from absorbed rumination and toward unresolved decision points. Second, it models latent node values with boundary-scaled heteroscedastic edge variances and computes exact global posteriors in linear $\mathcal{O}(|V|)$ time via two-pass Rauch--Tung--Striebel (RTS) tree belief smoothing, eliminating $\mathcal{O}(m^3)$ matrix inversions while gating out spurious boundary noise. Third, BRIAR detects minimal absorbed frontier nodes and applies zero-sum log-length centered suffix advantages strictly post-absorption, leaving pre-absorption derivations provably invariant.

3. WorldBridge: Bridging Scattered Views for Coherent 3D World Generation
Authors: Weilong Yan, Jingyu Hu, Hongli Xu, Yifan Zhan, Beibei Lin, Anbang Wang
Link: http://arxiv.org/abs/2611.34079v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 5.5
Abstract: Generating coherent and explorable 3D worlds from scattered images with little or no visual overlap is a fundamental and long-standing challenge in computer vision, which existing geometry-aware methods fail to address. Meanwhile, existing image- and video-based methods may generate unseen regions but produce inconsistent geometry across views. To bridge this gap, we present WorldBridge, a framework for coherent and controllable 3D world generation under scattered images with little or no visual overlap. WorldBridge encodes scattered references into a global scene context to guide geometry and appearance generation across views. Our temporal and spatial reference attention mechanism further enhances the fidelity of temporal references along the target trajectory and supports flexible spatial references outside it. A plug-and-play latent-reference consistency strategy improves reference fidelity through reprojection-guided test-time optimization. We also introduce the WorldBridge benchmark suite to evaluate 3D world generation from scattered, low-overlap references, which is rarely explored by current benchmarks. Both qualitative and quantitative results demonstrate that our method enables controllable and coherent 3D world generation, surpassing the existing state-of-the-art solutions. Our project page is available at https://davidyan2001.github.io/WorldBridge/.

4. Mixture-of-Loops Transformer
Authors: Lianghui Zhu, Shijie Wang, Xinggang Wang, Jinze Bai, Bo Wang, Xiang Bai
Link: http://arxiv.org/abs/2611.34923v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 5.0
Abstract: Looped Transformers boost expressivity by reusing shared layers across loops, yet at the cost of efficiency. Pushing their expressivity-efficiency frontier requires rethinking the core mechanism connecting adjacent loops: What should be passed as a Transformer loops? We introduce Mixture-of-Loops Transformer (MoLT), whose Mixture-of-Loops Attention (MoLA) uses keys and values (KV) as memory for selective reuse across depths and loops. Under loop residual, MoLT-R retains the residual stream and reads local KV across loops for expressivity. Under loop KV, MoLT-KV instead restarts from embeddings and reads current-loop local KV with preceding-loop memory KV at earlier positions for efficiency. MoLT-KV eliminates same-position cross-loop dependence and, paired with loop forcing for parallel training, unlocks single-traversal Mixture-of-Loops (MoL) decoding beyond the training loop horizon. To balance efficiency and quality, we introduce U-shaped MoLT (U-MoLT), which separates memory construction from prediction readout and skips unused decoder traversals without changing predictions. In 400B-token pretraining, U-MoLT outperforms OLMo3 across 700M/1.5B dense and 3B MoE models, achieving 1.7x validation cross-entropy (CE) token efficiency at 700M while improving 3B MoE 10-domain perplexity by 0.75 and 10-task accuracy by 2.1 percentage points. In 100B-token continued pretraining of Qwen3.5-0.8B-Base, our U-MoLT adaptation lowers CE on all 11 domains over the matched baseline with 1.4x mean token efficiency. At inference, U-MoLT with MoL-Hybrid-2 matches non-looped OLMo3 latency at 996.6 vs. 1,000.6 ms on S-size (~113M) models. Code is available at https://github.com/hustvl/MoLT

5. HOG-WAM: Improving Visual Robustness through Future Gradient Prediction
Authors: Boxuan Dong, Yupeng Qian, Ying Wu, Heshuai Li, Junhao Tan, Zhenxiong Tan
Link: http://arxiv.org/abs/2611.34811v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 5.0
Abstract: World-action models jointly predict future observations and actions, yet visual corruption can disrupt the resulting policies. We introduce HOG-WAM, which adds future Histograms of Oriented Gradients (HOG) as structural supervision derived directly from demonstration images. An auxiliary HOG diffusion transformer (DiT) module reads RGB features through asymmetric attention, allowing its objective to shape the visual representation used for control. The module is used only during training and removed at inference, preserving FastWAM's RGB-to-action architecture. We evaluate four controlled observation corruptions through a visual-corruption extension of RoboTwin, termed RoboTwin-Plus; HOG-WAM achieves the highest success among the compared policies under all four. Mixed-noise success increases from 78.86% to 82.86% relative to FastWAM, with comparable performance on clean scenes. On LIBERO Plus, overall success increases from 74.49% to 75.26%, with the largest gain under sensor noise, from 74.14% to 78.89%. Across four Franka tasks, average success increases from 40% to 59% under clean observations and from 17% to 24% under noisy observations. A representation ablation favors combining RGB observations with auxiliary HOG prediction over replacing RGB with HOG. These findings support future-gradient prediction as complementary supervision for visually robust control, with larger absolute gains on physical tasks than in simulation. Code is available at https://github.com/iPPLab/HOG-WAM.

## Additional Papers

6. WorldExpand: Building Coherent 3D Worlds via Sparse Joint Panoramic Expansion | Not Relevant | Experiment | Score: 5.0 | http://arxiv.org/abs/2611.34810v1
7. Make the Adversary Spend More: Stateful Deception as a Cost-Exchange Primitive for AI-Era Cyber Defense | Not Relevant | Theory + Experiment | Score: 5.0 | http://arxiv.org/abs/2611.34770v1
8. One Model, Many Modes: Evolving System Prompt Ensembles for Creative Generation | Not Relevant | Experiment | Score: 5.0 | http://arxiv.org/abs/2611.34760v1
9. Spectrum Adaptation of AI-Native Autoencoder Communications with Transfer Learning | Not Relevant | Experiment | Score: 4.5 | http://arxiv.org/abs/2611.34942v1
10. Transferring Architecture as an Optimization Prior | Not Relevant | Experiment | Score: 4.5 | http://arxiv.org/abs/2611.34816v1
