# Daily Muon Paper Digest

## Top Highlights

1. A Transformer-Derived Iterative Preconditioner
Authors: Patrick Lutz, Themistoklis Haris, Aditya Gangrade, Venkatesh Saligrama
Link: http://arxiv.org/abs/2611.22941v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 7.5
Abstract: Transformers trained on in-context prediction problems can learn known numerical algorithms, e.g., gradient descent. We go further, showing that their internal computations can reveal new algorithms with provable guarantees. A softmax-attention transformer trained to solve linear systems $Xw=y$ implicitly improves matrix conditioning. Tracing $XX^\top$ reveals an iterative preconditioning primitive, which we develop into RAPID, a standalone algorithm requiring no learned components. RAPID is an anytime preconditioner for symmetric positive definite (SPD) matrices, using randomized mixing and sparse local corrections to improve conditioning. Proof-of-concept experiments on synthetic and real-world problems consistently improve conditioning and reduce conjugate gradient iterations needed to reach a target accuracy. For a Haar-mixing idealization, we prove convergence to any fixed target condition number regardless of spectral distribution, with only logarithmic dependence on initial conditioning. Together, these results show how a transformer can discover a broadly applicable numerical algorithm.

2. Identifying and Repairing Energy Smells with Agent Skills
Authors: Mohammadjavad Mehditabar, Saurabhsingh Rajput, Tushar Sharma
Link: http://arxiv.org/abs/2611.23203v1
Category: Muon-Adjacent Experiments
Paper type: Experiment
Relevance score: 5.5
Abstract: Energy smells are inefficient implementations that waste energy. Once code reaches production, these smells become costlier and riskier to fix, so energy efficiency checks should shift left, i.e., move earlier in the development lifecycle, to where code is written. Existing energy smell tools rely on fixed static rules and do not measure energy savings, whereas LLM-based optimizers mostly target execution time and rarely ground their changes in concrete smell definitions. To address both limitations, we present DR. GREENS, an agent skill that detects and repairs energy smells in Python code within the developer's coding environment. The skill grounds the coding agent in our taxonomy of 12 energy smells and 65 root causes, augmented with repair guidance drawn from 230 measured cases. The skill also encapsulates a static analyzer and an independent verifier to confirm behavior preservation and energy saving for each attempted repair. We evaluated DR. GREENS in 18 sessions on three open-source repositories, with two models and three skill configurations. Of the 258 measured repairs, 68.6% saved energy, with a median saving of 24.9%. Compared with a baseline skill that lacks the taxonomy, the full skill found more energy smells with verified savings in all three repositories with both models. DR. GREENS helps developers detect energy hotspots and fix them reliably without altering program behavior, which makes energy-efficient development more feasible.

3. SWIR-cGAN: Synthesizing SWIR Bands Using VNIR Imagery from CBERS and AMAZONIA-1
Authors: Alisson Cleiton de Oliveira, Rennan de Freitas Bezerra Marujo, Thales Sehn Körting
Link: http://arxiv.org/abs/2611.22922v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 7.5
Abstract: Spectral band synthesis is an important research topic in remote sensing. The Brazilian satellites CBERS-4, CBERS-4A, and AMAZONIA-1 provide high temporal resolution (1-3 days) visible and near-infrared (VNIR) imagery through the Wide-Field Imager (WFI), but lack short-wave infrared (SWIR) bands. Recent deep learning methods have shown promising results for spectral synthesis, but challenges remain for cross-satellite generalization and spectrally distant bands. This paper presents a conditional Generative Adversarial Network (cGAN) with an attention-enhanced U-net generator and a multi-loss objective to synthesize Sentinel-2/MSI SWIR bands 11 (SWIR-1) and 12 (SWIR-2) from WFI VNIR inputs. Experiments used 4,125 patches for training and cross-validation and 1,026 unseen patches for testing, with hyperparameters optimized using a subset of the training data. On SWIR-1, the model achieved SSIM of 0.900, PSNR of 31.44 dB, and MAE of 0.019 in TOA reflectance. On SWIR-2, it achieved SSIM of 0.917, PSNR of 33.35 dB, and MAE of 0.015. Benchmarking was performed on the test dataset, with each model optimized separately prior to evaluation. SWIR-cGAN outperformed the baselines, particularly for SWIR-2. The ablation study identified the multi-loss as the main performance contributor, while the attention and residual modules provided additional improvements. Our results demonstrate the feasibility of synthesizing SWIR bands from WFI imagery. The SWIR-cGAN is available at https://github.com/marujore/swir-cgan.

4. Do LLM Agents Still Need to Be Told How to Self-Improve?
Authors: Shobhita Sundaram, Cansu Sancaktar, Phillip Isola
Link: http://arxiv.org/abs/2611.23219v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 5.5
Abstract: LLM agents increasingly drive their own learning. Self-improvement methods delegate various components of model optimization to the models themselves. As models become more capable, this motivates a basic question: do these increasingly capable models still need us to specify how they should self-improve? In this paper we study an autonomous paradigm in which, given basic primitives, resources, and a general goal for self-improvement, agents construct their own self-learning algorithm for context-based optimization. Using the setting of gameplay as a testbed, a frozen LLM agent is given a compute budget and tools for collecting experience and updating text documents, and allowed to freely experiment without an externally imposed loop or access to real-world data. We find that sufficiently capable models do self-improve under these conditions, demonstrating strategies that align with classic cognitive frameworks for self-regulated learning and constructs from machine learning literature on self-generated curricula. Furthermore, we study the extent to which the learned text artifacts transfer to external benchmarks, observing improvement across different game horizons, mechanics, and 3D navigation.

5. Say Less, Hallucinate Less? Diagnosing and Restoring Object Coverage in Preference-Optimized Vision-Language Models
Authors: Hansang Lee
Link: http://arxiv.org/abs/2611.23179v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 5.5
Abstract: Preference optimization (PO) is the standard way to reduce object hallucination in large vision-language models. We find that four public PO checkpoints of LLaVA-1.5-7B also lower object coverage. They name fewer object categories, and their lower hallucination rates bring no significant gain in set-level object F1 on CHAIR. We therefore ask how much of the PO gain the base model can reproduce by stopping earlier. A positive end-of-sequence (EOS) logit bias lets the base model reach the recall of each PO model, and this early stopping alone reproduces 58 to 86 percent of the CHAIRi gain of three checkpoints on two disjoint COCO sets. Writing longer does not bring the lost categories back. Under greedy decoding, a negative EOS bias recovers only 2 to 9 percent of the lost CHAIR recall of these checkpoints, and 94 to 96 percent of the added object mentions repeat categories already named. On CHAIR, the base caption of the same image still names about half of the missed object categories. We therefore propose base-guided object-category restoration, which appends high-confidence base-only categories to the PO caption without training. With thresholds fixed on a development set, it brings three checkpoints within one point of the base recall on a held-out COCO set with a lower distinct-object hallucination rate than the base model. Against the recall-matched base stopping curve, its gain holds for RLAIF-V near the base recall and for RLAIF-V and CHAIR-DPO at an intermediate recall. We will release the code of the recall-controlled evaluation.

## Additional Papers

6. Get Hint-Augmented GRPO Done Right Through Activation Steering | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2611.23124v1
7. M3OPD-Reasoner: An Open Recipe for Post-Training Multimodal Reasoning with Multi-Teacher On-Policy Distillation | Not Relevant | Experiment | Score: 5.0 | http://arxiv.org/abs/2611.23034v1
8. Is model self-assessment enough for diverse LVLM ensembles? | Not Relevant | Experiment | Score: 5.0 | http://arxiv.org/abs/2611.22956v1
9. 3D-VASE: Volumetric-Aware Scalable and Efficient Multi-Layer Design Synthesis for 3D-Printed Microfluidics | Not Relevant | Experiment | Score: 4.5 | http://arxiv.org/abs/2611.22983v1
10. Outcome-Balanced PPO and Policy-Induced Flow Rectification for Flow-Based VLA Policies | Not Relevant | Experiment | Score: 4.5 | http://arxiv.org/abs/2611.22878v1
