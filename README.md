# Amazon Review Rating Prediction

Reviews and ratings have a significant influence
on consumer shopping behaviour. An
online review typically consists of free-form
text and a star rating out of 5. The problem
of predicting a user’s star rating for a product,
given the user’s text review for that product, is
called Review Rating Prediction and has lately
become a popular problem in machine learning.
In this project, I treat this as a regression
problem, where I use item metadata, reviews
and also the user-item interaction to predict
the rating of a particular review given by a
user. I have explored contribution of these features
both individually and combined and have
shown how they differ.

## Bias
On websites
like Amazon, where there are hundreds of thousands
of reviews and ratings, its not possible to go through
every one of them to understand customer behaviour or
preferences. Its possible to summarize the numeric ratings,
but the relationship between reviews and ratings
is not obvious. Different users may have different scale
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

## Experimentation

I have experimented with different feature extraction
models to represent the review body and title as high
dimensional embeddings. I have used xgboost as a regression
model and as final features for the model. I
have tried different combination of features like, only
review body textual features, review title and body features,
user interactions, item metadata and different
combination of them.
