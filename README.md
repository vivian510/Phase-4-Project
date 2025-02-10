# APPLE TWITTER SENTIMENT ANALYSIS 

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

# Modelling
>Logistic Regression which is simple and interpretable and effective for text classification task,I used it in Binary classification which then expanded to multiclass classification.
> Decision tree was performed and ensemble methods like Bagging to improve the prediction accuracy though it did not help improve the accuracy.it helped reduce overfitting.
> XGBoost was used to capture complex patterns but did not improve the model over Logistic Regression.

# Evaluation
>The models were evaluated with Accuracy,Precision,Recall and F1 score.
> The best model was Logistic Regression with Gridsearch,it had  Accuracy of 72% ,precision of 68% and Bagged RandomForestClassifier with Accuracy 71% and precision 70%.
> In the Validation approach,I used a Train_test split to validate the model performance,ensuring the results are well generelised with new data.The dataset was split into 70% training data and 30% test data.




# Hyperparameter Tuning
Hyperparameter Tuning was performed using GridsearchCV to find optimal parameters.Performed cross validation with 5 folds to ensure model generelized well on unseen data.
- Feature engineering with Tfidvectorizer with different n_gram range.
- Removed stop words to reduce noise and improve performance.
- Logistic Regression with class_weight ='balanced' was used to handle the class imbalance and improve performance.
