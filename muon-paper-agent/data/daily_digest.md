# Daily Muon Paper Digest

No strong matches today. Showing the best available 10 candidates.

## Top Highlights

1. RADIOlogy: A Single-Pass Approach to Training-Free Zero-Shot Anomaly Detection
Authors: Joaquín Figueira, Giacomo D'Amicantonio, Egor Bondarau
Link: http://arxiv.org/abs/2610.40580v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 5.0
Abstract: Current zero-shot anomaly detection methods often rely on complex prompt-learning techniques or computationally expensive sliding-window strategies to achieve fine-grained visual alignment to detect small-scale anomalies. This reliance stems from the fundamental limitation of standard CLIP architectures, where [CLS] token attention and spatial patch pooling struggle to capture subtle, localized anomaly features. While prompt-learning approaches aim to bridge this gap, they typically require a large number of ground-truth segmentation masks from auxiliary datasets, which are often unavailable in specialized domains. In this work, we show an emerging property of multi-head attention pooling in vision-language models: remarkable zero-shot anomaly localization and detection right out of the box. We translate this property into a single-pass anomaly detection technique, RADIOlogy, that does not require dense, windowed execution and significantly outperforms other training-free baselines. Instead, the method relies on a simple contrastive scoring approach that compares the average similarity between vision features and a suite of normal and abnormal prompts. Furthermore, we leverage the agglomerative features of RADIO models to enhance pixel-level anomaly segmentation using a dense anomaly refinement pipeline. Finally, we show how the vision-language family of training-free zero-shot anomaly detection techniques can be applied successfully to the medical domain with minimal modifications. Code is available at https://github.com/jacomof/RADIOlogy.

2. The Privacy and Security Risks of Edge LLM Optimization
Authors: Mingchen Li, Ren-Yi Huang, Dumindu Samaraweera, Prashant Shekhar, J. Morris Chang
Link: http://arxiv.org/abs/2610.40543v1
Category: Not Relevant
Paper type: Theory
Relevance score: 5.0
Abstract: Edge deployment of Large Language Models requires optimization techniques that reduce memory, computation, and energy costs. However, preserving task performance does not necessarily preserve security. We argue that optimization is an information transformation that can alter representations, decision pathways, and trust boundaries, creating security drift and optimization-induced attack surfaces.

3. LucidLyra: Feed-Forward Generative 3D Scene Reconstruction and Joint Understanding via Multi-Task Distillation
Authors: Oliver Hahn, Rodrigo Marcuzzi, Sangeetha Grama Srinivasan, Alessandro Burzio, Sherwin Bahmani, Jiahui Huang
Link: http://arxiv.org/abs/2610.40495v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.5
Abstract: We present LucidLyra, a framework that makes generatively reconstructed 3D scenes directly queryable for semantics and instances in a feed-forward manner from video latents. While generative 3D reconstruction can synthesize virtual environments from a single image, downstream applications in robotics and physical AI require not only visual realism but also access to scene semantics and object identities. Existing 3D understanding approaches, however, require captured multi-view scenes, have limited generalization capabilities, or rely on expensive per-scene processing and optimization. To bridge this gap, our method distills complementary knowledge from a camera-controlled video diffusion model and frozen 2D vision foundation models into a unified model to jointly infer 3D Gaussians encoding geometry, appearance, open-vocabulary semantics, and class-agnostic instance cues. The resulting scenes support novel-view rendering, open-vocabulary segmentation, and object grouping without per-scene optimization, while training requires neither manual 3D annotations nor captured multi-view data. Our method outperforms baselines combining state-of-the-art 3DGS segmentation approaches with generative 3D scene reconstruction on curated synthetic and real-image-conditioned benchmarks, while preserving reconstruction quality. Furthermore, our latent formulation naturally extends to monocular video, reconstructing structured dynamic 3D scenes across time. By turning renderable but unstructured outputs into queryable 3D worlds, LucidLyra enables downstream applications including 3D scene editing, 3D asset mining, and robotic simulation.

4. IMPACT: Inverter-Informed Multimodal Learning for Photovoltaic Generation Forecasting
Authors: Anushka Katiyar, Cong Feng, Jing Wang, Tristan Liu, Simon Julien, Zachary Jacobs
Link: http://arxiv.org/abs/2610.40418v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.5
Abstract: This work develops a physics-informed multimodal deep learning framework for 10- to 110-minute-ahead probabilistic photovoltaic power forecasting. The forecasting model is built on a four-branch architecture that separately encodes plant-level temporal history and inverter-level spatial cloud dynamics through a graph attention encoder with a learned adjacency, known-future solar geometry, and the current meteorological state, fused through gated cross-attention. The geometry branch adds two forward-looking physical signals, spatial cloud heterogeneity and inverter ramp-down activity, each empirically weighted toward the horizon where it is most predictive. The decoder anchors its prediction to a smart persistence baseline, learning a horizon-conditioned correction, and the resulting quantile forecasts are calibrated online through a kernel-weighted adaptive conformal calibration step. The proposed model outperforms all 14 baselines, achieving a forecast skill score (FSS) of 0.2950, 0.099 above the next-best model. A branch-composition ablation shows that every branch contributes positively and the model retains substantial skill in challenging overcast and variable sky conditions (FSS 0.198 and 0.255).

5. First-Order Bilevel Optimization for Non-truthful Auction Design
Authors: Shing-Hei Ho, April Niu, Ellen Vitercik, Kai Wang
Link: http://arxiv.org/abs/2610.40403v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.5
Abstract: Automated mechanism design has enabled the learning of complex auction mechanisms using neural networks. However, designing non-truthful auctions remains challenging because bidders' equilibrium strategies depend on the auction mechanism and thus evolve as the mechanism is optimized. In this work, we formulate auction design as a Stackelberg game with multiple strategic followers and develop a fully first-order algorithm for revenue optimization in non-truthful auctions. We establish non-asymptotic guarantees for hypergradient approximation and show that, under standard smoothness and strong-monotonicity assumptions, our method reaches an $O(ε)$-stationary point using $\tilde{\mathcal{O}}(ε^{-2})$ first-order oracle calls. Experiments on symmetric and asymmetric single-item auctions, as well as multi-item auctions, show that our method converges faster than second- and zeroth-order baselines and scales better as the number of bidders increases. Our method also discovers auctions that achieve revenue close to truthful baselines. These results provide a scalable framework for automated mechanism design beyond truthful auctions.

## Additional Papers

6. Don't Lose the Thread: Empowering Long-Horizon LLM Agents with Cognitive Resource Self-Allocation | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.40350v1
7. A Unified Hessian-Guided Framework for Post-Training Quantization | Not Relevant | Unclear | Score: 4.0 | http://arxiv.org/abs/2610.40345v1
8. DYNAS: A Dynamic Network Penetration Testing Framework Using Deep Hierarchical Reinforcement Learning | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.40214v1
9. Understanding axial attention in TSFMs through single location regression | Not Relevant | Theory + Experiment | Score: 4.0 | http://arxiv.org/abs/2610.40188v1
10. How Far Are We From On-Device VLM Inference? A Measurement Study on Edge NPUs | Not Relevant | Theory + Experiment | Score: 4.0 | http://arxiv.org/abs/2610.40039v1
