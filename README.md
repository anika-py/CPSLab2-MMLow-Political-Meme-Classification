# CPSLab2@MMLow 2026: A Hierarchical Multimodal Framework with Stratified K-Fold Training for Political Meme Classification

## Abstract
Political memes communicate opinions using the interplay between visual and textual information, posing a challenging multimodal classification task. In this work, we present a hierarchical multimodal framework for political meme classification, which decomposes the task into stance and target entity prediction. Our framework is evaluated on the data from the Multi-Level Political Meme Classification Shared Task at MMLow @ AACL-IJCNLP 2026. The task comprised two levels of classification: (i) predicting the political stance of a meme as either Support/Praise or Troll/Oppose, and (ii) identifying the target of the meme combined with the stance. We approach the task by first predicting the Level-1 labels followed by predicting the target entity (Person/Party) and then combining them in a deterministic manner to predict the final Level-2 labels. We propose a multimodal approach that used a SigLIP vision transformer for stance classification and a hybrid SigLIP-XLM-RoBERTa architecture for target classification with feature level concatenation. We trained our models using class-weighted loss and 5-fold stratified cross-validation with checkpoint ensembling. We also performed ablation experiments to analyze the contribution of individual modalities, observing that visual features are more informative for stance prediction while textual features contain more information for target identification, which supports the multimodal task at hand. Our system achieved a macro F1 score of 0.9027 and 0.6694 for Level-1 and Level-2 classification, respectively, achieving a final score of 0.7860, ranking first in the shared task.

## Notebooks

- [Main training](./cpslab2_meme_classification.ipynb)
- [Ablation study](./ablation_study.ipynb)

## Experimental Setup
The proposed approach was implemented in Python 3.12.13 using PyTorch library (version 2.11.0+cu128) and Hugging Face Transformers (version 5.13.1). In particular, the vision encoder was implemented using the pretrained SigLIP Vision Transformer (google/siglip-base-patch16-512), while the text encoder used was the pretrained XLM-RoBERTa-base (xlm-roberta-base). Finally, the evaluation scores including Precision, Recall, and F1 were calculated using scikit-learn library, while all computations were performed on the NVIDIA GPU with CUDA acceleration.

## References

1. Anderau, G., & Barbarrusa, D. (2024). The function of memes in political discourse. *Topoi, 43*(5), 1529–1546. https://doi.org/10.1007/s11245-024-10112-0

2. Rajiakodi, S., et al. (2026). Overview of the Shared Task on Multilevel Political Meme Classification in Tamil and Malayalam. In *Proceedings of the Sixth Workshop on Speech, Vision, and Language Technologies for Dravidian Languages* (pp. 101–113). https://doi.org/10.18653/v1/2026.dravidianlangtech-1.12

3. Zhai, X., Mustafa, B., Kolesnikov, A., & Beyer, L. (2023). *Sigmoid Loss for Language Image Pre-Training*. arXiv. https://arxiv.org/abs/2303.15343

4. Radford, A., et al. (2021). *Learning Transferable Visual Models From Natural Language Supervision*. arXiv. https://arxiv.org/abs/2103.00020

5. Conneau, A., et al. (2020). *Unsupervised Cross-lingual Representation Learning at Scale*. arXiv. https://arxiv.org/abs/1911.02116

6. Kohavi, R. (1995). A study of cross-validation and bootstrap for accuracy estimation and model selection. In *Proceedings of the 14th International Joint Conference on Artificial Intelligence* (Vol. 2, pp. 1137–1143).

7. Chakravarthi, B. R., et al. (2021). Findings of the Shared Task on Offensive Language Identification in Tamil, Malayalam, and Kannada. In *Proceedings of the First Workshop on Speech and Language Technologies for Dravidian Languages* (pp. 133–145). https://aclanthology.org/2021.dravidianlangtech-1.17/

8. B, P., et al. (2022). Findings of the Shared Task on Multimodal Sentiment Analysis and Troll Meme Classification in Dravidian Languages. In *Proceedings of the Second Workshop on Speech and Language Technologies for Dravidian Languages* (pp. 254–260). https://doi.org/10.18653/v1/2022.dravidianlangtech-1.39

9. Sokolova, M., & Lapalme, G. (2009). A systematic analysis of performance measures for classification tasks. *Information Processing & Management, 45*(4), 427–437. https://doi.org/10.1016/j.ipm.2009.03.002

10. Thapa, S., Veeramani, H., Hu, L., Zhang, Q., Wang, W., & Naseem, U. (2025). A multimodal prompt-based framework for analyzing Code-Mixed and Low-Resource memes. *Proceedings of the International AAAI Conference on Web and Social Media, 19*, 1913–1923. https://doi.org/10.1609/icwsm.v19i1.35909

