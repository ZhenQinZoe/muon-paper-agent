# Daily Muon Paper Digest

No strong matches today. Showing the best available 10 candidates.

## Top Highlights

1. HiSA: Sparsifying the Hidden Dimension of RoPE Attention in LLMs
Authors: Ambroise Borbely, Mathieu Salzmann, Olivier Verscheure
Link: http://arxiv.org/abs/2611.26363v1
Category: Not Relevant
Paper type: Unclear
Relevance score: 4.0
Abstract: Attention in large language models (LLMs) scores every query against every key with a full dot product. We investigate whether this dot product must be computed completely for attention to be effective. We propose Hidden Sparse Attention (HiSA), which keeps the query and key projections intact but only computes a partial dot product, following a static, parameter-free rule set by the token positions: attention becomes sparse in the hidden (feature) dimension, an axis much less explored than token sparsity, rather than over tokens as in almost all sparse attention methods. Based on the structure of rotary position embeddings (RoPE), we decompose keys and queries into parts which can be omitted when computing attention. By training LLMs from scratch with HiSA, we find that this partial dot product does not hurt but improves performance compared with the complete product while computing only about a third of the query-key products. During inference HiSA improves decoding speed and shrinks memory footprint. We also extend HiSA to FlashAttention-3 kernels for training and inference. Finally, we motivate our approach by showing that dense attention learns to suppress the attention score parts that HiSA drops. Code is available at https://github.com/ambroise-b/hisa.

2. SKILL.PNG: Learning Agent Skills in Pixel Space
Authors: Maximilian Seeth, Chengzhi Martin Hu, Marie Kempkes, Paul Röttger, Leo Schwinn
Link: http://arxiv.org/abs/2611.26296v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: AI agents are commonly specialized for new tasks and domains using skills, i.e. natural language instructions placed in their context. However, the discrete nature of textual skills prevents continuous optimization. Gradient-based approaches such as finetuning, on the other hand, are typically model-specific, preventing skill transfer across different agents. Since many agents today are built on vision-language models (VLMs), we can address these limitations by introducing Skill.png: a method for obtaining skill-like image inputs whose pixels are optimized with gradient descent through the vision encoder of a frozen VLM. Image skills are compatible with any VLM, and a single image can be optimized jointly for an ensemble of models. We show that Skill.png significantly outperforms state-of-the-art textual skills optimized using frontier LLMs in 9 of 16 settings (across 4 VLMs and 4 benchmarks) while requiring only 64 to 256 image tokens instead of roughly 900 to 2000 text tokens at inference time. Hybrid skills, i.e. text and image skills jointly optimized, further improve agent performance. Moreover, an image optimized with an ensemble of VLMs can successfully transfer across the models in the ensemble. Skill.png thus presents the first agent skill that can be optimized with gradient descent while retaining transfer benefits of text skills. Our code is available at: https://github.com/omseeth/skill.png

3. dLoop: Looped Diffusion Language Models via Recurrent Latent Refinement
Authors: Handa Li, Pengxiang Li, Mingyu Cao, Xilu Wang, Li Shen, Da Li
Link: http://arxiv.org/abs/2611.26275v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: Diffusion language models (DLMs) support parallel generation, yet they often require many denoising steps because only a fraction of token predictions are sufficiently reliable to be committed at each step. Existing acceleration methods primarily optimize confidence learning or commitment policies. However, these approaches operate on the outputs of a single denoising forward pass, in which information from the prompt, previously committed tokens, and uncommitted positions may not yet be fully integrated. Consequently, some predictions remain under-refined when the commitment decision is made, and modifying the commitment policy alone cannot improve their underlying representations. We introduce dLoop, which restructures a pretrained diffusion language model into a Prelude-Loop-Coda architecture and recurrently applies a parameter-shared intermediate block to the same partially masked state. Rather than advancing the denoising process, each additional loop provides further latent computation, allowing information distributed across uncommitted positions to continue interacting and become more fully integrated before commitment. Experiments on GSM8K, MATH, MBPP, and HumanEval show that dLoop achieves the highest or tied-highest accuracy on every benchmark. With tokens per forward pass (TPF) adjusted for loop computation, it outperforms Fast-dLLM in both accuracy and TPF on all four benchmarks and dParallel on three, and is more accurate than d3LLM on all four, while d3LLM attains higher TPF; no compared method surpasses dLoop in both. Mechanistic analyses show that extra loops mainly help on slow, unstable trajectories and that updates at uncommitted positions drive changes in token decisions and later generation. Pre-commitment latent computation thus makes predictions more reliable, offering a route to DLM acceleration distinct from forcing confidence through the training loss.

4. Learn, Freeze, and Transfer an Activation Function Across Architectures
Authors: Arun Prakash A
Link: http://arxiv.org/abs/2611.26201v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: Transfer learning typically reuses knowledge acquired by a source network through its learned weights. We investigate whether a learned activation function can also be transferred and remain useful in networks trained from scratch. We study this complementary form of transfer through a learn-freeze-transfer protocol, in which the activation is optimized jointly with a source network in a single training run, and is then frozen and reused in target networks trained from scratch. A pointwise activation with globally shared parameters is independent of layer dimensions and can therefore be incorporated into networks of different architectures trained from scratch. We instantiate this protocol with FAct, a five-parameter activation represented by a two-harmonic truncated Fourier series, initialized from a Fourier approximation of GELU and learned in a Vision Transformer (ViT) on ImageNet-1K. When reused in a ViT of the same architecture trained from scratch on ImageNet-1K, the frozen activation (Frozen FAct) improves top-1 accuracy by 1.46 percentage points over GELU. Across four smaller target architectures (standard ViT, Swin Transformer, linear-attention ViT, and MLP-Mixer) and four image-classification datasets, it achieves the highest mean accuracy among eleven activation functions in 15 of 16 settings under a common training configuration, with improvements of up to 1.71 percentage points over the best conventional activation. When the learning rate and weight decay are tuned separately for each activation under the same search budget, Frozen FAct still ranks first in 11 of the 16 settings, second in four, and fourth in one. These results provide empirical evidence that a learned activation function can retain its usefulness when transferred across vision architectures, independently of the weights with which it was learned.

5. When Sounds Turn Heads: Recovering Event Timing That Audio LLMs Fail to Say
Authors: Jongbhin Woo, Jaewook Jeong, Joon Son Chung
Link: http://arxiv.org/abs/2611.25960v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: Audio LLMs can know when a queried sound occurs but fail to say it. We find a few attention heads that track the queried sound: they shift when the query changes, follow the sound when it moves, and removing or blocking them often hurts the model's timestamps. Yet the answer does not express what they track. Intervals read directly from these heads outperform the model's original answer and recover events that its timestamps miss. To bring this timing into the answer, we introduce head-guided decoding, which needs no training. It keeps the model's decision on whether the sound is present and rescores its candidate timestamps with a prior from these heads. Heads selected on development data transfer unchanged to new recordings and free-text queries, where head-guided decoding improves the timestamps of three audio LLMs, scores above their head readout on every benchmark, and, in most settings, outperforms random-head guidance. On recordings released after the models were trained, head-guided decoding raises mIoU from 0.07-0.36 to 0.48-0.56. These results suggest that poor temporal answers in audio LLMs partly reflect a failure to say rather than to hear, and that the model's own attention can close part of this gap.

## Additional Papers

6. DTS: Delta-Based Tile Scoring for Efficient Long-Context Sparse Attention | Not Relevant | Theory | Score: 4.0 | http://arxiv.org/abs/2611.25938v1
7. From Sequence to Space: Explicit Spatial Belief with Vision-Language Distillation for Active Geo-Localization | Not Relevant | Unclear | Score: 4.0 | http://arxiv.org/abs/2611.25866v1
8. Efficient and Robust Drafting with Multi-Token Prediction | Not Relevant | Unclear | Score: 4.0 | http://arxiv.org/abs/2611.25813v1
9. From Attention to Semantics: Detecting and Mitigating Sound Event Hallucinations in Large Audio-Language Models | Not Relevant | Experiment | Score: 4.0 | http://arxiv.org/abs/2611.25789v1
10. Spatially Conditioned Trajectory Diffusion | Not Relevant | Experiment | Score: 3.5 | http://arxiv.org/abs/2611.26127v1
