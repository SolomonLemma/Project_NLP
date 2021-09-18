<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 3: Classification of  Subreddit Data with NLP 


## Objectives of the Project

The project aimed to build classification models that used to  correctly classify the subreddit topics based on submitted subreddit with best accuracy.


### Overview of the workflow of the project
- The methods employed for scraping subreddit data kept in separate data collection folder.
- The collected data loaded to the dataframes and combined to one dataframe. 
- The text documents were cleaned  by removing the stopwords, special characters. Other language symbols and fill the missed values
- Visualized the most frequent words of the cleaned data in each subreddits.
- Vectorized the text using countvectorizor or TfidfVectorizer.
- Perform grid search to obtain the optimal hyperparameter for five different models.
- Evaluate models based on accuracy score, confusion matrices of each models in order to select the best performing model for further evaluation.


### Data Collection

The data scraped from (https://www.reddit.com/r/datascience)  and (https://www.reddit.com/r/math) with a total of 26000 rows. The obtained baseline accuracy of the data is 50% which is well balanced to go for modeling and evaluation.
```

### Data Cleaning

Primarily all non-alphabetic characters, default stopwords were used to filter the clean text for first step cleaning. Later customized stop words were created after checking 
the data with visualization of the words. Finally, the cleaned data was vectorized to make the data ready for modelling.



### Model results with best grid search parameters for r/datascience and r/math

The table is the summary of the best performed models with confusion matrix evaluation for the best classification.

| Models               | Accuracy   | Sensitivity | Specificity | Precision   | 
| -------------------- | ---------- | ----------  | ----------- | ----------  | 
| Logistic Regression  | 0.932      | 0.968       | 0.909       | 0.904       | 
| Naive Bayes          | 0.915      | 0.878       | 0.964       | 0.964       | 
| Extra Trees          |0.924       | 0.932       | 0.918       | 0.917       | 

Accuracy tells how much percentage of the models are accurate to classify correctly the given data of subreddits. Sensitivity confirmed much percentage of math predicted 
correctively  from the actual math. In the same manner, Specificity tells how much percentage of the datascience subreddit predicted correctly from actual datascience. 
Precision presented about how much of the predicted math is actually math. In addition the AUR curve shows 93% the logistic regression model effectively classified the data.


In summary, Logistic Regression did better accuracy than the rest of all the models with closer values of Training and Testing accuracy scores with 2.5% difference between 
the scores. On the contrary, the KNN performed very low accuracy with a high degree of overfitting about 43% difference between train and test scores accuracy. The Logistic 
Regression was used for the rest of the analysis to see how many values were correctly/incorrectly predicted using a confusion matrix and further explanations of the 
classification.


### Conclusion and Recommendations

Different models were used to evaluate the best classification of the subreddit math and data science with a baseline accuracy of 50%. All the model results performed at 
least 40% greater than the baseline with accuracy values of above 91%, except KNN which performed with lower accuracy of about 56%. The results demonstrated a strong ability 
to classify more than  4 in 5 posts into the correct subreddit. However, the clear winner was the logistic regression(LR) model, which was able to correctly classify 4 in 5 
posts. Therefore, the results suggested to Reddit administrators to use the LR model to help them to classify the posts under their subreddit.  The second-best performing 
model is ExtraTreesClassifier with little overfitting behaviour. Naive Bayes model with a data size of 26000 having accuracy values of 92% with little overfitting about 2.56% 
difference of the scores and lower values of sensitivity (0.88) to predict maths from the actual. In conclusion, the Reddit administrator needs to be aware of some 
misclassified categories of the subreddits. The company may need to use other alternative methods to control such misclassified posts since the nature of the posts are very 
dynamic based on time and the situation to create wrong classification.

