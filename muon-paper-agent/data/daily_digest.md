# Daily Muon Paper Digest

## Top Highlights

1. MUON-RT Reusing the Teacher's Trajectory for Momentum-Free Muon for LLM Self-Distillation
Authors: Aryan Das, Vinay Kumar Verma, Aakansha Mishra
Link: http://arxiv.org/abs/2610.41104v1
Category: Muon Core
Paper type: Theory
Relevance score: 21.5
Abstract: Self-distillation methods for large language models with an exponential moving average (EMA) teacher already retain a history of student updates. Muon nevertheless stores a separate momentum buffer, increasing persistent training memory. We propose Muon with Reused Teacher (Muon-RT), which reuses the teacher-student displacement to eliminate momentum buffers for hidden weight matrices. We show that this displacement encodes an exponentially weighted history of applied updates and smooths temporally uncorrelated noise under a local model. Muon-RT removes its radial component, normalizes it spectrally, and mixes it with the current gradient after Newton-Schulz (NS) orthogonalization. Under explicit regularity and alignment assumptions, we establish linear contraction of an expected objective-gap bound toward a residual error level. With Self-Distillation Fine-Tuning (SDFT) on Qwen2.5-7B-Instruct, Muon-RT improves average accuracy over AdamW by 2.6 points with 42% less persistent memory, and over momentum Muon by 5.4 points with 27% less persistent memory. With Self-Distillation Policy Optimization (SDPO) on Olmo-3-7B-Instruct, it improves average accuracy over AdamW by 2.0 points.

2. SACQ: Structure-Aware Codebook Quantization for Ultra-Low-Bit Vision-Language-Action Models
Authors: Haesung Lee, Insu Han
Link: http://arxiv.org/abs/2610.41408v1
Category: Muon-Adjacent Theory
Paper type: Theory
Relevance score: 6.0
Abstract: Vision-Language-Action (VLA) models enable capable robot behavior, but their large memory footprint limits deployment on resource-constrained robotic platforms. Weight quantization is a natural remedy, yet post-training quantization (PTQ) recipes inherited from large language models degrade when applied to VLAs at ultra-low precision. Existing low-bit PTQ methods often fail to explicitly account for the structure of downstream operations and allocate precision without considering its effect on the policy actions. We introduce SACQ, an ultra- low-bit weight-only vector-codebook quantization framework for VLAs. SACQ combines (1) structure-aware codebook fitting with role-specific quadratic metrics that reflect input statistics and downstream sensitivity; (2) action-aware mixed-bit allocation based on the increase in final-action error as individual layers are compressed; and (3) two-stage post-quantization refinement that reassigns codeword indices with second-order error compensation and calibrates codebooks and row-group scales against the decoded action. Using GR00T N1.7, SACQ achieves 93.85% average success across four LIBERO suites at 1.5 bits per language/action weight while reducing model memory by 4.83x. With INT8 activation quantization and low-precision attention, it retains 93.55% success while running 1.51x faster than BF16. On SimplER, SACQ further achieves 63.76% and 52.27% success under Visual Matching and Variant Aggregation at 2 bits per language/action weight, compared to 58.90% and 53.45% for BF16, respectively.

3. Stochastic and Noisy Oracles in Smooth Continuous Optimization
Authors: Albert S. Berahas, Liyuan Cao, Katya Scheinberg
Link: http://arxiv.org/abs/2610.41086v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 6.0
Abstract: We review models of inexact computational oracles in smooth continuous optimization and their implications for the convergence, computational complexity, and attainable accuracy of optimization algorithms. We adopt a framework in which zeroth-,first-, and second-order oracles are characterized by quantitative error bounds and may accept additional control parameters that influence both their accuracy and computational cost. We introduce deterministic and stochastic oracle models and illustrate their properties through a variety of examples, including finite-difference approximations, stochastic gradients, and randomized derivative estimators. Particular attention is given to the distinction between absolute and relative errors, bias and variance, and stochastic function evaluations with independent or coupled randomness. A central theme of the review is the use of common analytical tools to recover and compare convergence and complexity guarantees under different oracle models. For deterministic and stochastic first-order methods, we show how a general descent inequality leads to complexity bounds under various assumptions on the objective function and all proposed oracle models. In the stochastic setting, we develop bounds on expected stopping times and the accuracy that can be guaranteed under different oracle conditions. We also examine the total computational complexity of algorithms relying on specific oracle constructions and briefly review models of inexact second- order information and their use in optimization algorithms.

4. Structure-Aware Skill Retrieval and Arbitration for Optimization Modeling
Authors: Anran Liu, Benzhao Hou, Zongsheng Cao, Daichao Wang, Lang Chen, Shitong Chen
Link: http://arxiv.org/abs/2610.41909v1
Category: Muon-Adjacent Theory+Experiments
Paper type: Theory + Experiment
Relevance score: 5.5
Abstract: Large Language Models (LLMs) can turn natural-language optimization tasks into solver-checked answers, but current agents remain brittle under narrative rewrites and often store reusable experience at the instance level. We introduce \textsc{ArchOR}, an archetype-centric skill agent that builds on \textsc{OptSkills} by adding two retrieval-focused modules. \emph{Centroid-Aware Representation Learning} (CARL) refines the ordering of cached skill representations through a low-rank prototype residual. \emph{Signature-Guided Retrieval} (S\textsuperscript{3}R) attaches open-dimensional structural signatures to skills, prioritizes candidates by weighted Jaccard overlap, and bounds semantic re-ranking to a top-$K$ set. A baseline-preserving arbitration rule determines when the structural route should replace the original selector. With the same DeepSeek-V4.1-Flash backbone and released skill library, \textsc{ArchOR} reaches 65.00\% Micro-Avg.\ Pass@1 across five benchmarks, improving over \textsc{OptSkills} by 1.64~pp Micro-Avg.\ and 2.68~pp Macro-Avg.

5. bf16 Rounding Silently Discards Most RL Policy Updates: A Hidden Training-Inference Mismatch and an Unbiased One-Line Fix
Authors: Andrew Gao, William Gao
Link: http://arxiv.org/abs/2610.41073v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 7.0
Abstract: Reinforcement learning (RL) post-training of language models keeps fp32 master weights in the optimizer and serves rollouts from a bf16 copy produced by round-to-nearest conversion. At the learning rates in common use, most per-step updates are smaller than half a bf16 spacing and the conversion discards them: on Qwen3-1.7B only 0.4-0.5% of served weights change per step, and the policy that generates the training data lags the optimizer by 50-150 steps. Existing mismatch corrections cannot see this lag because they compare two copies downstream of the same rounding. We propose Fair Cast: export the master with an unbiased rounding rule (stochastic rounding or error feedback) and compute the training loss on the served copy. The change is one line at the export call, adds no hyperparameters and costs 22-38 ms per export of 1.7B parameters. Across 25 matched seed-pairs on Qwen3-0.6B to 4B with AdamW and Muon, Fair Cast is ahead on 18, tied on 6 and behind on 1, with a mean gain of 6.1 points; on zebra puzzles it reaches 0.57 +/- 0.16 over four runs where round-to-nearest collapses to 0.33 +/- 0.10. It also makes the saved fp32 checkpoint agree with the served model, and it exposes the implicit lag of round-to-nearest as a regularizer that can be restored explicitly when a task needs it.

## Additional Papers

6. ReLift: Dense 3D Tracking as Lifted Trajectory Repair | Not Relevant | Unclear | Score: 5.5 | http://arxiv.org/abs/2610.42136v1
7. Subquadratic Attention with a Hierarchical Tree-Structured Indexer | Not Relevant | Theory + Experiment | Score: 5.5 | http://arxiv.org/abs/2610.42112v1
8. Rethinking Asymmetry in Self-Supervised 3D Geometry Learning | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2610.42092v1
9. Optimizing Stochastic Policy Geometry for Few-Step Flow Reinforcement Learning | Not Relevant | Unclear | Score: 5.5 | http://arxiv.org/abs/2610.41949v1
10. TopoHyperClinicalGraph: A Geometry and Topology-Aware Multimodal Framework for Cancer Survival Prediction | Not Relevant | Experiment | Score: 5.5 | http://arxiv.org/abs/2610.41556v1
