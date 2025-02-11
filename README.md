# APPLE TWITTER SENTIMENT ANALYSIS 

![image](https://github.com/user-attachments/assets/69055492-074f-476d-b995-37ef3a82de20)

# Background
>Sentiment analysis helps in identifying and extracting subjective information from a text.Companies use Sentiment analysis to analyse customer feedback and  make dnd make data driven decision.
>This project uses tweets about Apple and Google products rated by humans for sentiments to train and evaluate the NLP model.

# Business Problem 
>Apple and Google company is interested in understanding the customer sentiments so as to improve their products and enhance customer satisfaction.By building an NLP model that accurately predicts sentiments of the tweets can help the company to make informed decision which can improve their performance hence contributing to business growth. 

# Business and Data Understanding
>The dataset was sourced from CrowdFlower via data.world,the link for Kaggle is  https://www.kaggle.com/datasets/slythe/apple-twitter-sentiment-crowdflower
>>The key Features are :
<br>1. sentiment - sentiment labels
<br>2. sentiment:confidence - confidence score for sentiment
<br>3. date- when tweet was posted
<br>4. query- search query used
<br>5. text- actual tweet

>The project aims in sentiment analysis.It analyses Apple and Google products and classify them into Positive(5),Negative(1),Neutral(3),Non relevant(non_relevant)
>The data sourced from Twitter enables the company to gauge the customer satisfaction and get an insight of areas to improve to enhance the company performance.

# Data Cleaning
>The dataset had 2 columns which had missing data and also the columns were irrelevant according to my objective so i dropped the columns plus other columns which were relevant and remained with two columns which were sentiment and text.

# Preprocessing
>Text preprocessing to remove URLs,Hashtags,mentions,special characters which helped to reduce noise and focus on the actual content of the tweet and converting text to lowercase to reduce vocabulary size and improve word frequency analysis.
- Stopwords were removed and Lemmatization together with stemming applied to reduce word to their base form.

# Sentiment Analysis
## Distribution of different sentiments in the texts

![image](https://github.com/user-attachments/assets/f1656cde-71e2-48d8-8801-1b6add6db3ac)

> Neutral(3) had the highest sentiment,followed by Negative sentiment(1),then Positive(5) and the non_relevant which had the smallest.
> Filtered out the non_relevant class as it was not relevant to the Apple and Google products so it was bringing  noise to the data hence reducing the modeling performance

## Binary classification 
Performed Binary classification using Logistic Regression,the accuracy score was 81%

![image](https://github.com/user-attachments/assets/ee9c4dc4-4a12-47f2-ad8b-2ac91cb5e1a5)

## Multiclass classification
The best score was accuracy with 72% using Logistic Regression with Gridsearch. 

![image](https://github.com/user-attachments/assets/f87f0209-45a5-4785-84f6-9d15d835dff2)

# Modelling
>Logistic Regression which is simple and interpretable and effective for text classification task,I used it in Binary classification which then expanded to multiclass classification.

> Decision tree and Random Forest was performed and ensemble methods like Bagging to improve the prediction accuracy though it did not help improve the accuracy.it helped reduce overfitting.

# Bagged Decision tree Classifier
![image](https://github.com/user-attachments/assets/d1fb9e84-4a22-47b1-b013-0e3fd7d5f4b4)
Had an accuracy of 69% and Precision of 64%.

# Bagged RandomForestclassifier
> ![image](https://github.com/user-attachments/assets/c3e53fc9-43dd-4d19-93df-dcc886d69297)
> Had an Accuracy 0f 71% and Precision of 69%.

## XGBoost
> XGBoost was used to capture complex patterns but did not improve the model over Logistic Regression.

![image](https://github.com/user-attachments/assets/e8f25502-c2f4-4b16-be42-f3010f4b8716)
Had an Accuracy of 68% and Precision of 63%.

# Hyperparameter Tuning
- Hyperparameter Tuning was performed using GridsearchCV to find optimal parameters.Performed cross validation with 5 folds to ensure model generelized well on unseen data.
- Feature engineering with Tfidvectorizer with different n_gram range.
- Removed stop words to reduce noise and improve performance.
- Logistic Regression with class_weight ='balanced' was used to handle the class imbalance and improve performance.

# Evaluation
>The models were evaluated with Accuracy,Precision,Recall and F1 score.
>Both Logistic Regression with grid search and Bagged Random Forest performed the best with Accuracy of 71%.
>The Logistic Regression with gridsearch  achieved an accuracy of 0.713 and precision of 0.677 while Bagged Random Forest with accuracy of 0.708 and precision of 0.685

> In the Validation approach,I used a Train_test split to validate the model performance,ensuring the results are well generelised with new data.The dataset was split into 70% training data and 30% test data.

model	              Accuracy	Precision	Recall	F1
0	LogisticRegression	71	 68	61	63
1	Bagging Ensemble(rf)	71	69	57	59
2	Bagging Ensemble(DT)	69	64	58	59
3	XGBoost	              68	63	55	56

# Achievement of objective
> Insights gained can help business better understand customer sentiment and make Data driven decision to enhance products and service.

# Conclusions
> Both Logistic Regression with grid search and Bagged Random Forest performed the best with Accuracy of 71%.
> The Logistic Regression with gridsearch  achieved an accuracy of 0.713 and precision of 0.677 while Bagged Random Forest with accuracy of 0.708 and precision of 0.685.
> There is still room for improvement, particularly in handling the positive class (5).

# Recommendations
By doing the following,the model performance will improve:
- Experimenting with advanced feature engineering, 
- Experiment further with different other  models
- Implement further ensemble methods
- Perform extensive Hyper parameter Tuning


