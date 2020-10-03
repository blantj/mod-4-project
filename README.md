# mod-4-project
## Introduction
We set out to build an NLP model that could predict S&P 500 stock market movement based upon the text of the previous Federal Reserve Minutes. We collected 130 Federal Reserve minutes from 2004-present and measured the S&P 500 returns for the 28 day period from when minutes were released across 3 classes: Positive(>0.01), Negative(<-0.01), and Flat(-0.01 - 0.01).  Naive Bayes modeling yielded a Testing F1 Score of .29, while our top performing model, Random Forest, produced a Testing F1 Score of .43.  

## Obtain Data 
We downloaded 130 Federal Reserve Meeting Minutes PDFs from the FRASER website and read them into Pandas.  We then downloaded a CSV file with daily S&P 500 prices from the Wall Street Journal from 2004-present in order to get the 28 day return following the Federal Reserve Minutes release.  We merged the tweo files together, resulting in 130 datapoints

## Scrub Data
After collecting the data, we removed both NLTK and custom Stopwords from the minutes.  We then lemmatized the Minutes and vectorized the Minutes using TFIDF.  We calculated 28 day S&P 500 return from the date of Minutes release and created Positive(>0.01), Negative(<-0.01), and Flat(-0.01 - 0.01)S&P 500 return classes. Finally, we upsampled under-represented classes.

## Explore Data
We created most frequent word charts and word clouds for each class.

https://github.com/ChrisFiorentine/mod-4-project/blob/master/Flat_bar_freq.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/Flat_word_cloud.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/Negative_bar_freq.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/Negative_word_cloud.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/Positive%20Word%20Cloud.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/positive_bar_freq.png

## Model Data
1. First, we built a Dummy Classifier baseline model.  The resulting evaluation metics were:

Training Accuracy Score : 0.26
Testing Accuracy Score : 0.33

Training F1 Score : 0.25
Testing F1 Score : 0.33

2. Next, we performed Naive Bayes modeling with the following results:

Training Accuracy Score : 0.68
Testing Accuracy Score : 0.30

Training F1 Score : 0.68
Testing F1 Score : 0.29

Confusion Matrix: https://github.com/ChrisFiorentine/mod-4-project/blob/master/Naive_Bayes_Confusion_Matrix.png

3. We next performed Random Forest with Accuracy Scoring based Gridsearch CV.  This yielded the following results:

Training Accuracy Score : 1.0
Testing Accuracy Score : 0.45

Training F1 Score : 1.0
Testing F1 Score : 0.34

Confusion Matrix: https://github.com/ChrisFiorentine/mod-4-project/blob/master/Random_Forest_Accuracy_Confusion_Matrix.png

4. Finally Random Forest Gridsearch CV with F1 Scoring had the following results:

Training Accuracy Score : 0.93
Testing Accuracy Score : 0.45

Training F1 Score : 0.93
Testing F1 Score : 0.43

Confusion Matrix: https://github.com/ChrisFiorentine/mod-4-project/blob/master/Random_Forest_F1_Confusion_Matrix.png

## Analyze Results And Next Steps
Random Forest Gridsearch based on F1 score was our best model with a testing F1 score of .43, which modestly outperformed the baseline F1 score of .33.  With more time, we would further clean our text in order to fix fragmented words from improper PDF formatting that might have made our model less accurate by overfitting to word fragments that would not show up in the testing set.
We would also like to remove Federal Reserve Banks specific stop words that created noise within the model. 
Also we would like to look at other data points from the Federal Reserve that might affect S&P 500 movement. 

# Github Files
Chris_Analysis.ipynb: Source of Final EDA 

Jesse_Analysis.ipynb: Source of Final Modeling

