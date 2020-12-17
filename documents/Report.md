# Report 📋

## Data Mining and Machine Learning - Université de Lausanne

## Team Migros - Real or Not? NLP with Disaster Tweets

In this project we analyzed a dataset of tweets to know if a tweet is about a real disaster (target = 1) or not (target = 0). To do so we builded a machine learning model and trained it with the dataset provided by the university. This report will be a summary of the course of action we did and how we achieved our best accuracy in the leaderboard.

#### First Iteration
In this first iteration we just fit the training data in the Logistic regression and observe the accuracy.
 
 1) At first we submitted a simple logistic regression without data cleaning which gave us a satisfying accuracy of **0.805** on AICrowd

 2) We made EDA on our files in order to be more aware about the database and all its characteristic.
 
 3) We used the Random Forest Classifier (RFC) and its model accuracy seemed very promising (0.97 for the train data) however, whilst submitting to AICrowd we got only a result of **0.77**. It seems like we are missing an important point as our accuracy keeps getting lower. Perhaps our model is overfitting the train data, thus we decided to clean our data set properly and try different classifier.


#### Second Iteration
Since our accuracy did not improve in the first iteration, we decided on the follwing steps.

 4) First we cleaned the text by removing unnecessary elements such as retweets and tags from the data sets. Further we removed all the noises we could find, such as url adresses, punctuation, numbers, stopwords and other special characters. We then built a model applying a logistic regression with cross validation, which gave a pretty good accuracy on the train data. However the accuracy on AICrowd get lower: **0.797**
 
 5) Secondly we tried to use different classifier to see if there is a change in accuracy with the cleaned data set. We tried again the Randon Forest Classifier and kkn model. However, our accuracy did not change and we realised that the problem might not be with the classifier. We even tried to use a different verctorizer to see if that might improve the accuracy on the cleaned data set. Using Doc2Vec instead of TF-IDF again gave a good accuracy on the train data set, but on AICrowd our accuracy and rank kept sinking. 
 
 
#### Third Iteration
Although we had cleaned our data set, our accurcy kept sinking. Therefor we decided to analyize our cleaning process in detail. Further we decided that we are moving on with the TF-IDF Vectorization for our model and to improve its parameter to get the optimal parameter values for our model.
 
  6) We came back on the EDA in order to find if there was something we were missing for the data cleaning. On EDA we found out very frequent words which did not give much information for the analysis quite the opposite represented noise. We deleted them from the text and we ran again the Logistic Regression which increares the test accuracy. We kept going making different combinantion of data cleaning in order to see which one gaves the best result. We found our that we needed to be careful not to remove too much special character. Removing character like 'û' and 'rt' was not useful and we could condlude that words with that character loose their meaning if they are removed. Previously we cleaned all the nummbers of the text but we then realized, that making this decreases the model's test accuracy. Our hypotesis was that numbers such as dates or ages could give usefull information. Otherwise there was others numbers which represented noise but we weren't able to clean only that part. 

 7) We decided that the TF-IDF classifiers are the most suitable for our model and tried to improve the parameters. To do so, we proceed by running a logistic regression with a random_state=72 for every combination of the tf-idf parameters, which gave us the optimal TF-IDF Vector for our model.

 8.) As a last step in this iteration, we tried to compare different model and find a optimal model for our analysis. With the use of cross-validation we compared the Logistic Regression, Random Forest classifier and the kkn-model. By comparing the mean accuracy of the train data set for each model, we could detect that the Logistic Regression was the most suitable model for our analysis.

#### Fourth Iteration 
In the last iteration we conducted before the deadline, we tried to correct the parameters to improve our test accuracy for the LogisticRegression. This lead to the best accuracy of **0.819** on AICrowd.

  9) To understand the parameter in the Logistic Regression and how they influence the score, we first conducted a simple analysis of the parameter "solver", "C" and "max_iteration". Here for example we could see that the parameter "max_iteration" basically has no great influence on the score, whereas it was quite important which solver we used for our model. Finally we did a Logistic Regression with GridSearchCV with the optimal TF-IDF parameters we already had defined in the last iteration. 
  
  8) After finding our optimal model, we still tried to improve that with Standardization and PCA. However we did not succeed with this model and gave up on this path. Instead we tried to include the "Keyword" column in our model. Here we tried again using the three different model from above, since we were not that sure anymore, if the logistic regession was still the optimal model. The results of the regression suggested again, that the logistic regression was the optimal model even with including the keyword column. Sadly we could not submitt the new score on the AICrowd to see, if the including the Keywords really influenced the test accuracy. 

## Takeaways

Both, the competion on AICrowd and building a machine learning model from scratch was a new experiance for all of us. It was very good opportunity to use the theory we studied at the university in a hands on project. Even if we needed several tries to succeed, it was very helpful to fully understand the different models and techniques. For future project, it would be good, if we do not first jump into different models and classifiers, but spend a little time in the beginning to effectively clean the data to make it useful. After that we can still compare different models and classifier to find the optimal solution for the given problem. However, mistakes made now are a lesson for the future and we hope that we are able to overcome future hurdles in this field through the lessons we learned through this project.
