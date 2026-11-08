# Daily Muon Paper Digest

No strong matches today. Showing the best available 10 candidates.

## Top Highlights

1. Patch Attention Wisely: Understanding Patch Length in Attention-Based Forecasting
Authors: Junyu Chen, Likai Chen, Weining Wang
Link: http://arxiv.org/abs/2611.08160v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 4.0
Abstract: Attention-based time series forecasters commonly group consecutive observations into patches. Patch length is known to have a substantial impact on forecasting performance, yet its selection remains largely empirical. We develop a theoretical framework that explains why patch length matters for forecasting accuracy and provides a principled basis for its selection. For linear state-space models, we derive an exact factorization of the forecasting coefficient matrix that separates forecast dynamics from filtering dynamics. We show that dominance of a single forecast component at long horizons does not generally imply a rank-one representation. This explains why longer horizons alone need not reduce representational complexity. We combine the factorization with estimation bounds to develop a patch-selection criterion that balances representation and estimation errors under temporal dependence. Our analysis establishes conditions under which balanced patching is justified and clarifies how predictive structure, head count, training sample size, and long-run dependence enter the selection criterion.

2. Improving Context-Shift Robustness of Convolutional Networks via Context-Regularized Cross-Entropy
Authors: Jinen Setpal, Chaoyue Liu
Link: http://arxiv.org/abs/2611.08157v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 4.0
Abstract: Image classification models often encounter objects in diverse and unpredictable contexts at test time, which may differ substantially from those seen during training. This phenomenon, termed context shift, exposes a key fragility in neural networks: when models rely on non-causal contextual cues for prediction, shifts in context can lead to significant performance degradation. In this paper, we propose a novel training framework to improve the robustness of convolutional neural networks under context shift. Our approach leverages spatial feature attribution to guide models toward making predictions that rely less on contextual regions and more on object-relevant features. As a first step, recognizing a theoretical limitation of existing feature attribution methods we introduce a new variant, ContrastiveCAMs, which produces more faithful attribution maps of model predictions. Building on ContrastiveCAMs, we further propose Context-Regularized Cross-Entropy (CR-CE), a modification of the standard cross-entropy loss that regularizes the model's attention by suppressing the influence of contextual regions, thereby improving robustness to context shift. We evaluate the effectiveness of our approach on several medium-to-large scale datasets (Waterbirds, Spawrious, ImageNet/ImageNet-BG, Hard-ImageNet), and report consistent improvements in context-shift robustness.

3. MUSS: A Multi-scale and Sequence-based Model for Single-cell Gene Regulation
Authors: Kangjie Zheng, Amirhossein Vahidi, Liying Jin, Joseph Clarke, Vijaya Baskar MS, Connor Rogerson
Link: http://arxiv.org/abs/2611.08086v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: Modeling gene regulation in single cells requires jointly representing DNA sequence, chromatin accessibility, and gene expression across regulatory scales. Sequence-based models capture DNA-level regulatory grammar but often lack cell-level resolution, whereas many single-cell omics models represent genes and peaks as fixed-vocabulary tokens without their underlying sequence. Here, we present MUSS, a sequence-based multi-scale model for single-cell gene regulation that preserves both DNA-level and cell-level resolution. MUSS derives peak- and gene-level representations from DNA using a frozen pre-trained sequence encoder and integrates them through peak-peak self-attention and distance-biased peak-gene interactions. Peak masked language modeling followed by training on paired scATAC-seq and scRNA-seq aligns these representations with cell-specific regulatory states. Across gene expression prediction, enhancer-gene linking, motif-guided regulatory prioritization, and zero-shot cell clustering, MUSS achieves strong performance against sequence-based and single-cell omics baselines. It further predicts expression for genes and peaks unseen during task training. These results support sequence-grounded, multi-scale representations for decoding cell-type-specific regulatory programs. Code, datasets, and model checkpoints are available at https://github.com/Lotfollahi-lab/MUSS_neurips26.

4. AttnSR: Attention Step Reward for Long-Horizon Agentic RL
Authors: Mengsong Wu, Tianchen Zhou, Zhaochen Su, Zhenhua Liu, Zhe Cui, Aimin Zhou
Link: http://arxiv.org/abs/2611.07932v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: Long-horizon LLM agents make multi-step decisions, yet outcome-reward-only reinforcement learning provides little direct supervision for individual steps. We introduce AttnSR, a step-level reward augmentation method that derives reward allocations from policy attention extracted during training replay, without a separately trained reward model or additional rollouts. AttnSR traces backward through the policy model attention graph to estimate the relevance of earlier steps to the final response. The terminal step, measured relative to a running baseline, determines whether these rewards reinforce or penalize the selected steps. In a controlled Qwen2.5-7B-Instruct study, AttnSR consistently outperforms the PPO baseline across all evaluated checkpoints on ALFWorld, raising final held-out success from 91.2% to 97.1%. The ablation experiment shows that the benefit depends on how intermediate rewards are assigned, rather than simple accumulation of step rewards over time. AttnSR also improves ScienceWorld at every checkpoint while cutting environment interactions by 29.9%. These results support policy attention as a practical prior for step-level reward allocation in long-horizon agentic RL. Code is available at https://github.com/fairyshine/AttnSR .

5. Axis-LoRA: Probing and Adapting Embedding Models for Personal-Memory Retrieval
Authors: Dohoon Kim, Junho Park, Hyunwoong Bae, Seyoon Kim, Taesup Moon
Link: http://arxiv.org/abs/2611.07820v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: As LLMs are increasingly asked questions about a user's personal experiences, retrieval must distinguish memories by time, place, person, and event. Current personal-memory pipelines rely on frozen dense embedding models to embed memories for retrieval, but we find that these models do not capture the four axes well. Swapping a memory's date or place barely shifts its embedding, and a trained projection on top of the frozen embedding does not recover the missing signal. The problem lives inside the model, where each axis is encoded by a distinct attention-head pattern. Guided by these findings, we propose Axis-LoRA, a per-axis adapter that places four LoRA branches inside the embedding model and combines them via a per-query gate. Across three standard embedding models evaluated on LongMemEval, ATM-Bench, and LoCoMo, Axis-LoRA improves 4-benchmark mean R@10 by $+1.28$ to $+1.56$~pp while training only a small fraction of the base parameters on a small axis-counterfactual training set. Code is available at https://github.com/dohoonkim-ai/axis-lora.

## Additional Papers

6. The Gating Mechanism of KV Cache Eviction | Not Relevant | Unclear | Score: 4.0 | http://arxiv.org/abs/2611.07605v1
7. WeLM-Image: A Unified Image Generation Model towards Visual Intelligence | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2611.07392v1
8. Breaking the Modality Barrier: Multimodal Fusion With Missing Modalities for Cybersickness Prediction | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2611.07386v1
9. Hierarchical Incremental Beta Splatting for Online Reconstruction | Not Relevant | Theory | Score: 3.5 | http://arxiv.org/abs/2611.08288v1
10. Wedge-Jamming Mechanism for String Configuration | Not Relevant | Experiment | Score: 3.5 | http://arxiv.org/abs/2611.07748v1
