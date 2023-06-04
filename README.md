# Sentiment-Analysis
Sentiment Analysis Program written using Python that predicts whether a review is positive or negative.

There are two models for binary classification of text. The first model uses a Forward Propagation Neural Network while the second model is an XGBoost Decision Tree. 

This program was tested on two things:
1)	Given a review of a movie, is it a positive or negative review?
2)	Given a game review, is it a positive or negative review?

The links to the datasets used for training and testing are as follows:

https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews
https://www.kaggle.com/datasets/piyushagni5/sentiment-analysis-for-steam-reviews

Both models were trained and tested seperately on both datasets.

For movie review sentiment analysis, the dataset consists of 50,000 IMDB movie reviews (the first link given above) which was divided into a training set of 40,000 and a testing set of 10,000 examples. Whereas, for the game review sentiment analysis, the dataset used contains 17,494 game reviews taken from Steam. This was divided into a training set and testing set of 10,000 and 7,494 examples respectively. 

Before the datasets were divided into training and testing sets, each of the reviews was processed to remove symbols, emoticons, and html tags to prevent them from adversely affecting the results. 

Note: Stopwords were not removed because they can also affect the results in a negative way. For example, take a review "The movie was not good" which will become "movie good" after stopwords are removed, completely changing the meaning.

In the program, ‘1’ is set as the positive class/label and ‘0’ is the negative class/label.

The Neural Networks Model uses a Forward Propagation algorithm provided by the Keras library which works on top of the TensorFlow library. The library deals with most of the calculations, word embeddings and tokenization. The sigmoid activation function in the last layer of the Neural Network makes it a binary classifier. A binary cross entropy loss function is used to calculate the loss in the Neural Network. Since a Neural Network model needs an established input size, all reviews went through a padding process to limit the length. Padding added extra symbols with the reviews that were not equal to the required length, which in this program is a 100 tokens in length. Padding also shortened the longer reviews by only selecting the first 100 tokens.

The Neural Networks had the following accuracies and losses with both datasets:

Movie reviews:
<br>Training Accuracy:  0.9186750054359436
<br>Training Loss:  0.2134408950805664
<br>Testing Accuracy:  0.8360000252723694
<br>Testing Loss:  0.39441898465156555

Steam game reviews:
<br>Training Accuracy:  0.9302999973297119
<br>Training Loss:  0.19634073972702026
<br>Testing Accuracy:  0.7760875225067139
<br>Testing Loss:  0.5083554983139038

The last function of the first model allows a user to type in a comment to be analyzed by the sentiment analysis program whose results are shown as either "positive" or "negative".

For the second model, XGBoost library is used to build decision trees for binary classification of data. 

The XGBoost Decision Tree had the following accuracies with both datasets:

Movie reviews:
<br>Training Accuracy: 0.8532
<br>Testing Accuracy: 0.8264

Steam game reviews:
<br>Training Accuracy: 0.8748
<br>Testing Accuracy: 0.7036295703229251




