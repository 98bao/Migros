### Report 📋

## Data Mining and Machine Learning - Université de Lausanne

## Team Migros - Real or Not? NLP with Disaster Tweets


## Classification problem
In this project we analyzed a dataset of tweets to know if a tweet is about a real disaster (target = 1) or not (target = 0). To do so we builded a machine learning model and trained it with the dataset provided by the university.

# First Iteration
In this first iteration we just fit the training data in the Logistic regression and observe the accuracy.
 
 1) At first we submitted a simple logistic regression without data cleaning which gave us a satisfying accuracy of **0.805** on AICrowd
  
  2) We cleaned the text by deleting unecessary elements, then applied a logistic regression with cross validation (LRCV). Although the model built on the train data is pretty good, the accuracy on AICrowd got lower: **0.797**

  3) We used the Random Forest Classifier (RFC) and its model accuracy seemed very promising (0.97 for the train data) however, whilst submitting to AICrowd we got only a result of **0.77**. It seems like we are missing an important point as our accuracy keeps getting lower. Perhaps our model is overfitting the train data, thus we have to correct our parameters
  
  
