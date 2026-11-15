# Daily Muon Paper Digest

No strong matches today. Showing the best available 10 candidates.

## Top Highlights

1. DRAMA: Dissecting Attention Redundancy for Accelerating Multimodal Diffusion Large Language Models
Authors: Yi-Hsin Hung, Fangfu Liu, Shao-Yuan Lo, Chu-Song Chen
Link: http://arxiv.org/abs/2611.16345v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 4.0
Abstract: Multimodal diffusion large language models (dLLMs) generate text through iterative masked denoising with bidirectional attention, offering a compelling alternative to autoregressive vision-language modeling. However, each denoising step requires a full forward pass over long multimodal sequences in which visual tokens dominate the sequence length, and a fixed step budget further compounds this quadratic per-step cost. Existing inference acceleration approaches for multimodal dLLMs characterize attention redundancy implicitly, motivating designs from isolated attention visualizations rather than from measurement. We close this gap with DRAMA, a training-free acceleration framework grounded in a systematic dissection of attention redundancy in multimodal dLLMs. By probing attention tensors along spatial and temporal axes, we reveal two persistent redundancy structures: (i) attention mass consistently concentrates on a sparse subset of visual tokens, and (ii) attention distributions rapidly stabilize across denoising steps after an initial formation phase. These findings motivate two complementary mechanisms: Spatial-Redundancy-Aware Visual Token Pruning (SVTP) and Sufficiency-Guided Adaptive Stopping (SGAS). Together, DRAMA achieves an average 18.67 times inference speedup across six vision-language benchmarks without training, architectural modification, or attention caching, while maintaining competitive accuracy. Our results establish a strong, measurement-grounded acceleration baseline for multimodal dLLM inference.

2. An Extensive Evaluation of Machine Learning and Deep Learning Approaches for Sentiment Analysis: Insights from Amazon Customer Reviews
Authors: Muhammed Ihsan Corak, Cuiyuan Wang, Xiaowen Zhang
Link: http://arxiv.org/abs/2611.16201v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 4.0
Abstract: The rapid growth of user-generated text on online platforms creates opportunities for understanding customer opinion and supporting data-driven decisions. This study compares five traditional machine learning classifiers (Random Forest, Logistic Regression, Bernoulli Naive Bayes, Linear Support Vector Classifier, and Multinomial Naive Bayes) and six deep learning architectures (LSTM, Bi-LSTM, GRU, RNN, Attention, and FastText) for three-class sentiment classification of 568,454 Amazon Fine Food Reviews. Machine learning models used Bag-of-Words (BoW) and TF-IDF features limited to 5,000 terms; deep learning models used learned embeddings over a 20,000-word vocabulary. Models were evaluated on the original imbalanced data and on a random-oversampled balanced set of 1,070,469 reviews, using accuracy, macro and per-class precision, recall, and F1-score, and training time. On the balanced set, Random Forest with BoW achieved 99\% accuracy and the Attention model achieved 98.7\%. Linear SVC reached 89\% accuracy in 1 min 15 s, and Logistic Regression reached 90\% in 3 min 37 s. On the imbalanced set, the Attention model achieved 97.8\% accuracy, and FastText achieved 95.3\% in 3 min 26 s, while the RNN reached 91.9\% with a neutral-class F1-score of 0.08. Deep learning models were more stable across class distributions, whereas the best classical model depended on balancing. We also report a user-facing application that applies the trained Random Forest and Attention models to new review text. Because the labels are derived from star ratings, the results measure agreement with rating-derived sentiment classes rather than annotated sentiment; the dataset is a single source, and the findings should be read with that limitation in mind.

3. Self-Supervised Attention-Based Virtual Metrology for CMP MRR Prediction
Authors: Jonathan Adam Rico, Nagarajan Raghavan, Senthilnath Jayavelu
Link: http://arxiv.org/abs/2611.16172v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: Chemical mechanical planarization (CMP) is a critical semiconductor manufacturing process where material removal rate (MRR) is a key metric for process monitoring and advanced process control (APC). Virtual metrology enables MRR estimation from process time series signals, supporting run-to-run(R2R) control and process optimization while reducing reliance on physical metrology. Existing approaches typically rely on simplified linear assumptions or require handcrafted feature engineering. In this paper, we propose Global Regression Pretraining(GREP), a self-supervised, attention-based framework for CMP MRR prediction. GREP learns temporal representations from unlabeled sensor signals through global proxy-target regression, followed by supervised fine-tuning for MRR estimation. The framework is evaluated against a feature-engineered supervised baseline under three conditions: limited labeled data, sensor noise, and temporal process drift. Experiments on the PHM 2016 CMP dataset demonstrate competitive performance under limited labeled-data conditions, with improvements in selected cases and performance largely comparable to the baseline across different labeled-data fractions. Both models exhibit relatively small changes in prediction error with increasing noise, while GREP achieves a 17.0% RMSE reduction in the final temporal interval.

4. Vocabulary-Free Next-Event Prediction on Temporal Graphs
Authors: Zhishang Luo, Venu Madhav Tammali, Amila Weerasinghe, Osso Vahabzadeh, Olcay Boz, Xue Hao
Link: http://arxiv.org/abs/2611.16063v1
Category: Not Relevant
Paper type: Theory + Experiment
Relevance score: 4.0
Abstract: Autoregressive transformer training through next-token prediction has driven remarkable advances in language modeling and has become increasingly effective for time-series modeling. Yet its success in temporal graph learning remains limited, and most temporal link-prediction methods are discriminative rather than autoregressive. While temporal graphs can have a natural serialization through chronological ordering edges, they lack an obvious graph-independent tokenization: existing node tokenization often uses a vocabulary that grows with the number of nodes, limiting scalability and cross-graph training. We propose GTGT, Generative Temporal Graph Transformer, a simple yet powerful vocabulary-free framework for self-supervised next-event prediction on temporal graphs. It predicts events for observed destinations, behavioral descriptors for novel destinations, and time gaps before new event. These targets have shared meanings across graphs, allowing one transformer to train across disjoint node sets without node-specific learned parameters. Local node identifiers let attention capture graph structure: Theoretically, we can show that our transformer-based model has the capacity for time-respecting message passing mechanisms. On Temporal Graph Benchmark (TGB), our GTGT not only achieves comparable or better link-prediction performance than established baselines, but also has much lower training cost. These results open the door to temporal graph pretraining for forecasting and other downstream tasks, providing a concrete step toward temporal graph foundation models.

5. TRACE: Trajectory Synchronization for Training-Free Resolution Extension in Video Generation
Authors: Libo Zhu, Fan Li, Zhixin Wang, Binglu Wang, Weisheng Dong, Yulun Zhang
Link: http://arxiv.org/abs/2611.15983v1
Category: Not Relevant
Paper type: Experiment
Relevance score: 4.0
Abstract: More text-to-video models are available, but many remain limited to low resolutions. Training them for higher resolutions is costly, while existing training-free methods still struggle with fine detail, scene structure, and efficiency. We propose TRACE, a training-free method that synchronizes low- and high-resolution generation trajectories. During early denoising, TRACE aligns predicted scene content at corresponding noise levels. It computes high-resolution updates from low-resolution predictions and the current high-resolution state, without high-resolution model inference. The high-resolution trajectory retains fine-grained variation for generating new details. Local window attention then refines fine details in a shared high-resolution latent state. TRACE checks suspected duplicate subjects against the corresponding low-resolution layout and corrects selected regions and their solver history while preserving detail elsewhere. Experiments across all kinds of video generation backbones and resolutions show improved perceptual quality and text-video alignment over FreeSwim, a state-of-the-art training-free method, with 2.0-2.9x end-to-end speedups. Our code and models will be released at https://github.com/libozhu03/TRACE.

## Additional Papers

6. Copied, Mixed or Computed? Testing Latent Intermediate Values with Minimal Pairs | Not Relevant | Unclear | Score: 4.0 | http://arxiv.org/abs/2610.28498v3
7. PIM: A Physical Intuition Model for Low-Latency Prediction of Object Interaction Outcomes | Not Relevant | Unclear | Score: 3.5 | http://arxiv.org/abs/2611.16673v1
8. FlowIR: Depth-driven Rectified Flow for Resolving Thermal Ambiguity in Infrared Super-Resolution | Not Relevant | Theory + Experiment | Score: 3.5 | http://arxiv.org/abs/2611.16269v1
9. SPEM: Scan-Prior Entropy Modeling for LiDAR Point Cloud Compression | Not Relevant | Experiment | Score: 3.5 | http://arxiv.org/abs/2611.16212v1
10. MOSAIC: Modular Obstacle and Spatial-Aware Framework for Manipulation In Cluttered Scenes | Not Relevant | Experiment | Score: 3.5 | http://arxiv.org/abs/2611.15937v1
