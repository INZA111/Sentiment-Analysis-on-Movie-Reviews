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

### While pre-processing the original dataset we have taken into consideration the following points.
1. We will classify a review to be positive if and only if the corresponding Score for the given review is 3 or 4.
2. We will classify a review to be negative if and only if the corresponding Score for the given review is 0 or 1.
3. We will ignore the reviews for the time being which has a Score rating of 2. Because 2 can be thought of as a neutral review. It's neither negative nor positive.
4. We will remove the duplicate entries from the dataset.
5. We will train our final model using four featurizations -> bag of words model, tf-idf model, average word-to-vec model and tf-idf weighted word-to-vec model.
6. So at end of the training the model will be trained on the above four featurizations to determine if a given review is positive or negative.

### Preprocessing Review
1. Begin by removing the html tags.
2. Remove any punctuations or limited set of special characters like , or . or # etc.
3. Check if the word is made up of english letters and is not alpha-numeric
4. Check to see if the length of the word is greater than 2 (as it was researched that there is no adjective in 2-letters)
5. Convert the word to lowercase
6. Remove Stopwords
7. Finally Snowball Stemming the word (it was obsereved to be better than Porter Stemming)

### Bag of Words
A bag-of-words model, or BoW for short, is a way of extracting features from text for use in modeling, such as with machine learning algorithms. The approach is very simple and flexible, and can be used in a myriad of ways for extracting features from documents. Suppose we have N reviews in our dataset and we want to convert the words in our reviews to vectors. We can use BOW as a method to do this. What it does is that for each unique word in the data corpus, it creates a dimension. Then it counts how many number of times a word is present in a review. And then this number is placed under that word for a corresponding review. We will get a Sparse Matrix representation for all the worods in the review.


### TF-IDF
TF or Term Frequency for a word is basically the number of times a word occurs in a review divided by the total number of words present in that same review. For example, in the text corpus that we have considered in the above example, the TF for word w1 is (2/9) and for word w9 is (1/3). Intuitively, higher the occurence of a word in a text is, greater will be its TF value. TF values lies between 0 and 1.
IDF or Inverse Document Frequency for a word is given by the formula log(N/n), where 'N' is equal to the total number of reviews in the corpus 'D' and 'n' refers to the number of reviews in 'D' which contains that specific word. Intuitively, IDF will be higher for words which occur rarely and will be less for words which occurs more frequently. IDF values are more than 0.
So for each word in each review we will consider the product of (TF x IDF), and represent it in a d dimensional vector.

### AVG W2V
In this model we convert each word present in a review to vectors. For each sentence we will compute the average word to vec representation.

### TFIDF Weighted W2V
In this model we convert each word present in a review to vectors. For each sentence we will compute the tf-idf average word to vec representation.

### Splitting the data
After performing featurisation, we split our data and predict the performance of the model on new unseen data.

### Training different Models
I tried different models like KNN, Naive Bayes, Logistic Regression, SVMs, Decision Tree, Random Forest.

### Result:
Logistic Regression worked very well.

### Model Deployment:
I am going to deploy the model using Flask and AWS EC2 instance.
Link: ec2-18-222-1-146.us-east-2.compute.amazonaws.com:8080/index

### Future Work
The Deep Learning algos like BERT can also be implemented.
