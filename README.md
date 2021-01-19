# Sentiment-Analysis-on-Movie-Reviews

## Data Information
Get the data from kaggle https://www.kaggle.com/c/sentiment-analysis-on-movie-reviews

## Attribute Information
1. Phrase Id
2. Sentiment Id
3. Phrase
4. Sentiment

## Objective:
Given a review, our main objective is to determine if the review is positive or negative. We can do this by using two approaches.

## While pre-processing the original dataset we have taken into consideration the following points.
1. We will classify a review to be positive if and only if the corresponding Score for the given review is 3 or 4.
2. We will classify a review to be negative if and only if the corresponding Score for the given review is 0 or 1.
3. We will ignore the reviews for the time being which has a Score rating of 2. Because 2 can be thought of as a neutral review. It's neither negative nor positive.
4. We will remove the duplicate entries from the dataset.
5. We will train our final model using four featurizations -> bag of words model, tf-idf model, average word-to-vec model and tf-idf weighted word-to-vec model.
6. So at end of the training the model will be trained on the above four featurizations to determine if a given review is positive or negative.
