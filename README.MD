# Developing your first sentiment classifier in Python

## The project
We develop a supervised classification Bag of Words (BoW) model with Bayes algorithm on movie reviews corpus.
This model must predict which movie reviews are likely to belong to one of the two sentiment categories: positive or negative with 70% or greater accuracy. Adding other categories as output such as neutral, slightly positive or slightly negative would be closer to real word cases.

## Dataset Description
- 2.000 movie reviews with sentiment polarity classification crawled from Rotten Tomatoes. 
- 1000: reviews labelled as negative & 1000: reviews labelled as positive.
- Reviews are stored one per file with a naming convention cv000 to cv999 for each of neg and pos.  
- Each movie review has a unique file identifier. 

## Bayes Theorem

- <b>P(label)</b> is the prior probability of a label. P(negative) =  number of negative reviews/total number of reviews. P(positive) =  number of positive reviews/total number of reviews.
- <b>P(features|label)</b> is the likelihood probability, the likelihood of evidence:  What is the probability that a given feature set (outcome) will occur, given this positive or negative label (evidence). i.e.   P(Hate & Negative) = P(Hate) * P(Negative | Hate) 
- <b>P(features)</b> = number of feature set/total number of feature. It is the prior probability that a given feature set is occurred.     

## Steps
1. Exploring the data
2. Data Preprocessing
    - word tokenization
    - remove punctuation
    - shuffle them
3. Bag of Words Feature Extractor 
    - Create a list of most popular words found in movie reviews
    - Remove stopwords from the list
    - Define a function that will search for the features in reviews
4. Train data with the feature extractor
    - During training, the feature extractor is used to convert each input value to a feature set. These feature sets, which capture the basic information about each input that should be used to classify it. Pairs of feature sets and labels are fed into the machine learning algorithm to generate a model. Use the above defined function.
5. Prediction accuracy
    - During prediction, the same feature extractor is used to convert unseen inputs to feature sets. These feature sets are then fed into the model, which generates predicted labels.
    - Lastly, we print model's accuracy

The folder contains a text processing file with basic processing techniques found in nltk documentation. It is not necessary for running the project.
"Well this is pretty basic!"
Yes, it is but hey we all do start somewhere right?

## Model's Bias
BoW ignores the position of the words and the importance of semantic information in the document. Analysis of sentiments via mere word-level analysis namely BoW model and subjective words counting extract results that are not valid. Nevertheless, we follow this approach because it is the first approach to use in order to become familiar with natural language processing. Additionally, Bayes is based on the assumption that all words (aka features) are indepedent.

## Requirements

To run the project, it is required that the following are installed in your system:
- [Pyhton](https://www.python.org/download/releases/2.7/) version: "^2.7"
- [NLTK](http://www.nltk.org/install.html) version: "^3.2.5"