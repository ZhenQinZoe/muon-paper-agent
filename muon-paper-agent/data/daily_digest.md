# Daily Muon Paper Digest

No strong matches today. Showing the best available 10 candidates.

## Top Highlights

1. Model Predictive Control of Wind Turbines: A Model-Oriented Review of Prediction Models, Control Objectives, and Nonlinear Aerodynamic Formulations
Authors: Roya Khalili-Amirabadi, Mohsen Jalaeian-Farimani, Mahdi Ghane
Link: http://arxiv.org/abs/2610.31295v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 4.0
Abstract: Model predictive control (MPC) has been applied to wind-turbine regulation with markedly different internal prediction models, ranging from linearized low-order turbine models to nonlinear, aeroelastic, floating, and data-driven predictors. This review organizes the literature primarily by the model propagated by the controller and treats model order, predictor representation, MPC formulation, control objective, and validation plant as separate descriptors. Primary studies show that low-order linear or piecewise-affine predictors are attractive for constrained power and speed regulation, whereas flexible drivetrain, structural, and floating models are needed when drivetrain twist, tower motion, blade loads, or platform dynamics are explicit control quantities. Nonlinear and economic MPC studies further demonstrate coordinated pitch/torque control across broad operating regions, while preview, repetitive, and data-driven formulations address wind prediction, periodic loads, and model mismatch. Particular attention is given to aerodynamic pitch dependence: variable-pitch turbine dynamics can be non-affine with respect to applied pitch, and the term NMPC alone does not prove that the original nonlinear pitch map is retained inside the optimizer. The review therefore adopts a conservative, equation-based classification for direct nonlinear applied-pitch propagation. Here, direct nonlinear applied-pitch propagation means that the applied pitch at each prediction step is evaluated inside the original nonlinear aerodynamic map, rather than replacing that dependence by a linearized, scheduled, piecewise-affine, or learned surrogate. The literature supports a remaining integration challenge at the intersection of flexible drivetrain prediction, nonlinear aerodynamic pitch treatment, explicit constraints and load objectives, and validated adaptive or learned model correction.

2. RIFT: KV Cache Compression for Draft Models with Complementary Compressibility Training
Authors: Dor Tsur, Maor Ashkenazi, Maximilian Golub, Peter Hicks, Yaniv Galron, Talor Abramovich
Link: http://arxiv.org/abs/2610.31098v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 4.0
Abstract: Speculative decoding is a popular decode acceleration method. As such, it is particularly relevant to long-output generation, which requires an increasingly large KV cache. KV cache compression offers a way to constrain costs in long-context drafting. However, compression methods that focus on prefill information can lose relevance as the output length grows. We term this phenomenon decode staleness and show that it degrades draft model accuracy under selection-based KV cache compression. We introduce RIFT, a family of selection-based KV cache compression strategies that balance prefill information and recent generated tokens. We show that refreshing the KV cache selection during token generation significantly improves the drafter's quality at the cost of additional decode latency. To alleviate the refresh costs, we propose an adaptive KV refresh strategy that reduces the number of score calculations while retaining the drafter's quality. We further demonstrate how a compressibility-driven drafter training phase, based on sparse attention masks, can improve the drafter's quality under a compressed KV cache. Combined with compressibility training, RIFT enables Qwen3.5-4B, drafting for Qwen3.5-122B, to retain over 98% of its full-cache acceptance length on 32K-token inputs, 4K-token outputs, and an 8K-token KV cache budget.

3. ICGF-CXRMate: Image-Conditioned Clinical Context Compression and Gated Fusion for Chest X-ray Report Generation
Authors: Vu Minh Tran, Thuc Huynh, Son Thanh Luu, Doanh C. Bui
Link: http://arxiv.org/abs/2610.30928v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: Auxiliary patient data can improve chest X-ray report generation, but directly concatenating heterogeneous clinical information with visual tokens produces long, variable-length decoder prompts and may expose the model to redundant or image-irrelevant context. We propose ICGF-CXRMate, an image-conditioned clinical context compression and gated fusion framework. Learnable queries are first conditioned on the current chest X-ray representations and then attend to the patient-data sequence, compressing it into a fixed number of clinical context tokens. Gated cross-attention selectively integrates these tokens into the visual stream, while the compressed tokens are retained in the decoder prompt as a direct clinical pathway. Experiments on linked MIMIC-CXR and MIMIC-IV-ED examinations show that ICGF-CXRMate improves report quality while reducing the average prompt length. In Stage~2, it improves RadGraph-F1 from 24.00 to 28.86, CXR-BERT similarity from 56.86 to 62.80, and BLEU-4 from 5.14 to 7.96 compared with CXRMate-ED, while reducing the average prompt length from 373.89 to 288.37 tokens, corresponding to a 22.9\% reduction. After self-critical sequence training, ICGF-CXRMate outperforms CXRMate-ED on six of eight report-quality metrics in Stage~3. Ablation studies confirm the complementary contributions of image-conditioned compression, gated fusion, and direct retention of the compressed clinical tokens.

4. Watch and Learn: Teaching Visual In-Context Learning by Removing Textual Shortcuts
Authors: Nimrod Shabtay, Asaf Yehudai, Avihu Dekel, Eli Schwartz, Raja Giryes
Link: http://arxiv.org/abs/2610.30913v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: Vision-language models (VLMs) struggle with in context learning compared to their textual counterparts. Our preliminary study shows that VLMs rely on textual shortcuts and underutilize the visual demonstrations. We therefore hypothesize that VLMs are insufficiently trained to perform visual in-context learning (vICL). To this end, we construct MIME, a task-agnostic vICL training set without textual shortcuts. We ensure the instruction does not state the rule linking the demonstration images to their answers, so the model must infer it from the visual demonstrations. Fine-tuning on MIME improves vICL accuracy by 8.1 to 18.0 points across three VLMs, preserves single-image performance, and improves multi-image and text only in-context learning. In contrast, stating the rule in the training data sharply reduces this gain. We further propose DTAD (Demonstration Text Attention Dropout), which randomly withholds demonstration labels during training so that the VLM must infer the rule from the demonstration images. While achieving comparable vICL accuracy to fine-tuning on MIME, DTAD yields more consistent attention to the demonstration images. On TrueMICL, Qwen3-VL-8B trained on MIME matches frontier models such as Claude Opus 5, and surpasses them with DTAD. Finally, adding MIME to the instruction-tuning mix of LLaVA 1.5 13B more than doubles its vICL accuracy without hurting single-image abilities, whereas a same-size multi-image set improves it only slightly. These results suggest that vICL data should be a standard component of VLM training.

5. CAVC: Convergence-Adaptive Audio-Visual Cache for Modality-Asymmetric Diffusion Generation
Authors: Lifan Jiang, Yibo Zhao, Senlin cheng, Bolei Xu, Xiaobo Li, Can Ye
Link: http://arxiv.org/abs/2610.30854v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 4.0
Abstract: Diffusion-based audio-visual generation methods typically perform joint denoising of audio and video latents throughout the entire sampling trajectory, repeatedly executing modality-specific denoising branches and cross-modal attention at every timestep. However, we observe that such uniform joint computation is not always necessary. The key is a modality-asymmetric recoverability: audio-side drift introduced by mid-stage caching can be substantially reduced by only a few terminal joint denoising steps, whereas video-side degradation caused by caching leads to persistent loss of motion and temporal details. This asymmetry suggests that inference acceleration should selectively cache recoverable audio-side computation while preserving full video refinement. Motivated by this observation, we propose \textbf{Convergence-Adaptive Audio-Visual Cache (CAVC)}, a training-free modality-asymmetric caching framework. CAVC adopts a sandwich-structured computation allocation: after detecting that audio denoiser outputs enter a cache-tolerant regime, it caches and reuses the audio denoiser output to bypass audio denoising and cross-modal attention in the middle stage, while the video branch continues independent spatio-temporal refinement; a few joint steps are then restored at the end to reduce accumulated cross-modal drift and improve synchronization. Experiments across multiple public benchmarks demonstrate that CAVC achieves 1.10--1.35x wall-clock acceleration, improves several visual dynamics and temporal statistics, and maintains competitive audio fidelity and audio-visual alignment.

## Additional Papers

6. RECAP: Looking Once Is Not Enough for Vision-Language Reasoning | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.30834v1
7. ULME: Predictive Coupling for Mutually Reinforcing Embedding and Language Modeling | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.30705v1
8. Live Thread Reconstruction for Autonomous Manipulation | Not Relevant | Unclear | Score: 4.0 | http://arxiv.org/abs/2610.30694v1
9. CODI: Improving Self-Supervised Vision Transformers with Cross Distillation | Not Relevant | Theory + Experiment | Score: 4.0 | http://arxiv.org/abs/2610.30639v1
10. Refining Open-Vocabulary Semantic Segmentation via Regional Semantics and Visual Prototypes | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2610.30623v1
