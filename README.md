# Amazon Review Rating Prediction

## Overview
This project predicts Amazon review ratings based on review text, user item interactions, and item metadata. The project treats this as a regression
problem and explores contribution of these features
both individually and combined and have
shown how they differ.

## Bias
Different users may have different scale
of reviews, so even if their ratings are same, the review
texts can have very different polarity (Figure 1). Also,
the review texts may sound similar but ratings may
differ a lot. So it is not reasonable to determine the
sentiment scale of a review purely based on its textual
content since different reviewers or different products
may have consistent biases when being associated the
same terms.

<p align="center">
  <img src="https://github.com/reyasadhu/Review_rating_prediction/blob/main/71da4df0a55d670857555e68c2db4b14359b11ba" alt="Figure" width="500"/>
</p>

## Features
- **Dataset**: Utilizes the Amazon Product Review dataset, focusing on the Fashion category. Includes 2M users, 2.5M reviews, and 826K items. The data can be downloaded [here](https://amazon-reviews-2023.github.io/) under the amazon fashion category.
- **Input Features**:
  - Review body and title (textual data).
  - Item metadata (e.g., average rating, number of ratings).
  - Historical user-item interactions.
- **Models**:
  - Baseline Collaborative Filtering (User-User and Item-Item).
  - Matrix Factorization (SVD).
  - Neural Matrix Factorization (NMF).
  - XGBoost with textual and metadata features.

## Data Preprocessing
- Filtered users with at least 4 interactions and products with sufficient historical data.
- Processed textual features using:
  - Lowercasing, punctuation, and whitespace normalization.
  - Stopword removal and lemmatization.
  - Feature extraction using Count Vectorizer, TF-IDF, Word2Vec, and BERT embeddings.
- Selected only meaningful metadata columns to avoid sparsity issues.

## Implementation
1. **Collaborative Filtering**:
   - User-User and Item-Item similarity using cosine similarity.
   - Matrix Factorization via SVD.

2. **Textual Features and Metadata**:
   - Experimented with unigram and bigram models.
   - Combined review body, title, and item features for enhanced predictions.

3. **Neural Matrix Factorization**:
   - Modified NMF framework incorporating user-item interactions and review embeddings.
   - Optimized for regression tasks using MSE loss.
   ![Neural Matrix Factorization](https://github.com/reyasadhu/Review_rating_prediction/blob/main/image.png)

## Results
- **Mean Squared Error (MSE)**:
  - Traditional methods (Collaborative Filtering): 1.435 (User-User), 1.459 (Item-Item).
  - Textual features with XGBoost: 0.704 (TF-IDF, bigram).
  - Neural Matrix Factorization: 0.48.

- **Key Insights**:
  - Combining review title and body significantly improves performance.
  - Item metadata like average rating and rating count enhance prediction accuracy.
  - Simple word vectorization techniques (e.g., TF-IDF) outperform complex embeddings like BERT for this task.




