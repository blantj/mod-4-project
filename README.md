# mod-4-project
Mod 4 Project

# Introduction

Our objective was to use NLP to predict S&P 500 stock price movement based upon the release of the Federal Reserve Minutes.
The timespan of the data was from 2004-present.
S&P 500 returns were calculated for a 28 day period from when minutes were released.

# The Data 
We downloaded 130 Federal Reserve Meeting Minutes PDF's from the FRASER website and read them into the jupyter notebook.
We downloaded a CSV file with daily S&P 500 prices from the Wall Street Journal to gather stock prices from 2004-present.

# The Process
1. Collected Data
2. Removed NLTK and custom Stopwords from the minutes
3. Lemmatized Minutes
4. Vectorized Minutes using TFIDF
5. Calculated 28 day S&P 500 return from the date of Minutes release
6. Established Positive(>0.01), Negative(<-0.01), and Flat(-0.01 - 0.01), for S&P 500 return classes.
7. Upsampled under-represented classes.

# EDA
Created most frequent word charts and word clouds for each class.

# Data Visulization
https://github.com/ChrisFiorentine/mod-4-project/blob/master/Flat_bar_freq.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/Flat_word_cloud.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/Negative_bar_freq.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/Negative_word_cloud.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/Positive%20Word%20Cloud.png

https://github.com/ChrisFiorentine/mod-4-project/blob/master/positive_bar_freq.png


# Modeling
1. Naive Bayes

Training Accuracy Score : 0.68
Testing Accuracy Score : 0.30

Training F1 Score : 0.68
Testing F1 Score : 0.29

Confusion Matrix: https://github.com/ChrisFiorentine/mod-4-project/blob/master/Naive_Bayes_Confusion_Matrix.png

2. Random Forest Gridsearch (Accuracy)

Training Accuracy Score : 1.0
Testing Accuracy Score : 0.45

Training F1 Score : 1.0
Testing F1 Score : 0.34

Confusion Matrix: https://github.com/ChrisFiorentine/mod-4-project/blob/master/Random_Forest_Accuracy_Confusion_Matrix.png

3. Random Forest Gridsearch (F1 Score)

Training Accuracy Score : 0.93
Testing Accuracy Score : 0.45

Training F1 Score : 0.93
Testing F1 Score : 0.43

Confusion Matrix: https://github.com/ChrisFiorentine/mod-4-project/blob/master/Random_Forest_F1_Confusion_Matrix.png

# Analysis 
Random Forest Gridsearch with F1 score was our best model. However it did not greatly outperform random assignments of data points to classes.
With more time, we would further clean our text in order to fix fragmented words from improper PDF formatting that might have made our model less accurate by overfitting to word fragments that would not show up in the testing set.
We would also like to remove Federal Reserve Banks specific stop words that created noise within the model. 
Also we would like to look at other data points from the Federal Reserve that might affect S&P 500 movement. 

# Github Files
Chris_Analysis.ipynb: Source of Final EDA 

Jesse_Analysis.ipynb: Source of Final Modeling

