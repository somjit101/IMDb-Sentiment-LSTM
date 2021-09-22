# IMDb-Sentiment-LSTM
A study of the use of Long Short Term Memory (LSTM) for the sentiment classification of movie reviews on the well-known IMDb website.

## Problem Statement

Given a dataset containing textual movie reviews found on the popular movie website, IMDb, along with binary labels indicating if the overall 'mood' or 'sentiment' of the reviews are 'positive' or 'negative', the task is to classify given test samples of movie reviews as having a positive or negative sentinment in overall. This is a well-studied sentiment classification problem in the field of Natural Language Processing (NLP). 

In general, there are multiple ways to featurize a given piece of sentence to obtain feature vector which summarizes the content of the sentence in numerical values, but it is important to note that the overall semantic meaning and mood of a sentence depends heavily on the sequence of words used in it, and not just the words themselves. LSTMs do not suffer from the problem of vanishing gradients while propagating them back in time during training, leading to short term depencies of the output on the sequence items in a traditional Recurrent Neural Network (RNN). Hence they are capable of effectively preserving important features even in long sequences.

**Here, we look at a simple implementation of a sentiment classifier using LSTMs from the well-known Keras library.**

## Dataset

The [Keras IMDb Sentiment Classification Dataset](https://keras.io/api/datasets/imdb/) contains 25,000 movies reviews from IMDB, labeled by sentiment (positive/negative). Reviews have been preprocessed, and each review is encoded as a list of word indexes (integers). For convenience, words are indexed by overall frequency in the dataset, so that for instance the integer "3" encodes the 3rd most frequent word in the data.

