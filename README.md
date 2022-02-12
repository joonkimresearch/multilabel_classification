# Multilabel classification with BERT
1. Goal
  - Build a model that predicts tags (keywords) of articles published on arxiv.
  - Compare different solutions for class imbalance problem and multilabel classification problem. Specifically: 
    - Sampling methods: LPROS vs. MLROS. 
    - Multilabel classification: binary relevance vs. classifier chain vs. KNN vs. deep learning)

2. Data: https://www.kaggle.com/spsayakpaul/arxiv-paper-abstracts?select=arxiv_data.csv

3. Class Imbalance
  - The dataset is imbalanced when the occurrence of each label is not equal. In the current notebook, I used the label powerset random oversampling and multilabel random oversampling methods. The LPROS and MLROS approaches are chosen because two methods outperformed other techniques in a recent article ([Terekegn et al., 2021](https://www.sciencedirect.com/science/article/pii/S0031320321001527))

4. BERT
  - Bidirectional Encoder Representations from Transformers (BERT) is a transformer-based machine learning technique for natural language processing (NLP) pre-training developed by Google ([Devlin et al., 2018](https://arxiv.org/abs/1810.04805)). A transformer is a deep learning model that adopts the mechanism of self-attention, differentially weighting the significance of each part of the input data.

5. Binary Relevance vs. Classifier Chain
  - Binary relevance approach works by building an independent binary classifier for each class. 
  - Classifier chain approach works by buidling a binary classifier for each class. The classifier for class i uses predictions from classifier class j where i > j. 

6. MLKNN
  - ML-KNN is derived from the traditional K-nearest neighbor (KNN) algorithm. For each unseen
instance, its K nearest neighbors in the training set are firstly identified. After that, based on information gained from the label sets of
these neighboring instances, maximum a posteriori (MAP) principle
is utilized to determine the label set for the unseen instance ([Zhang & Zhou, 2007](https://www.sciencedirect.com/science/article/pii/S0031320307000027)).
