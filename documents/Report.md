### Report 📋

## Data Mining and Machine Learning - Université de Lausanne

## Team Migros - Real or Not? NLP with Disaster Tweets

In this project we analyzed a dataset of tweets to know if a tweet is about a real disaster (target = 1) or not (target = 0). To do so we builded a machine learning model and trained it with the dataset provided by the university. This report will be a summary of the course of action we did and how we achieved our best accuracy in the leaderboard.

# First Iteration
In this first iteration we just fit the training data in the Logistic regression and observe the accuracy.
 
 1) At first we submitted a simple logistic regression without data cleaning which gave us a satisfying accuracy of **0.805** on AICrowd

 2) We made EDA on our files in order to be more aware about the database and all its characteristic.
 
 3) We used the Random Forest Classifier (RFC) and its model accuracy seemed very promising (0.97 for the train data) however, whilst submitting to AICrowd we got only a result of **0.77**. It seems like we are missing an important point as our accuracy keeps getting lower. Perhaps our model is overfitting the train data, thus we decided to clean our data set properly and try different classifier.


# Second Iteration
Since our accuracy did not improve in the first iteration, we decided on the follwing steps.

 4) First we cleaned the text by removing unnecessary elements such as tweets and tags from the data sets and all the noices we could find, such as url adresses, punctuation, numbers, stopwords and other special characters. We then built a model applying a logistic regression with cross validation, which gave a pretty good accuracy on the train data. However the accuracy on AICrowd get lower: **0.797**
 
 5) Secondly we tried to use different classifier to see if there is a change in accuracy with the cleaned data set. However, our accuracy did not change and we realised that the problem might not be with the classifier, but more with the parameter for the regression. Therefore we decided to correct the parameters in the next iteration.
 
 
 # Third Iteration
 
 In the last iteration we conducted before the deadline, we tried to correct the parameters to improve our test accuracy for the LogisticRegression. Before analysing the parameter, we first checked our data cleaning process.
 
  6) We came back on the EDA in order to find if there was something we were missing for the data cleaning. On EDA we found out very frequent words which did not give much information for the analysis quite the opposite represented noise. We deleted them from the text and we ran again the Logistic Regression which increares the test accuracy. We kept going making different combinantion of data cleaning in order to see which one gaves the best result. We found our that we needed to be careful not to remove too much special character. Removing character like 'û' and 'rt ' was not useful and we could condlude that words with that character loose their meaning if they are removed. Previously we cleaned all the nummbers of the text but we realized that making this decreases the model test accuracy. Our hypotesis was that numbers such as dates or ages could give usefull information. Otherwise there was others numbers which represented noise but we weren't able to clean only that part. 

  7) In order to make a good comparison between different model, we realized that was usefull verify every model using cross-validation. We campared four different models and we found out that LogisticRegression was the most accurate for our analysis.
  
  8) As a final step, to improve our model even more, we try to include the keywords into our model. Here we created a new column including the the keyword and text column. Thelogistic regression with cross validation resulted in even better accuray than just using the text column.
