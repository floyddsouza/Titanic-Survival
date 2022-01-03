# Titanic-Survival
Kaggle Competition on predicting Titanic Survivors
Steps on completing the project:
1) EDA analysis
2) Splitting the name feature into its honorific we observe patterns in the survival. 
      -we will use the honorific as a new feature in the data. We will also combine some of the honorifics as they mean the same thing.  
3) Observed Null values in dataset. Age, Cabin, Embarked features in Train data are null. Age, Fare, Cabin in test data are null.
4) Around 80% of feature Cabin is null, we will drop this feature, 
5) We will fill the rest of nan values using KNN imputer but first we will have to set up dataset for this
    -We will one-hotencode all categorized features
    -We will then standardize the dataset of numerical values
    -Run sklearn KNN imputer
    -inverse standardize the dataset
    -round any numerical discrete data
6) We will only pick features with the most relevance, to find this:
    - We will run SelectKBest algoritm with Chi2 from Sklearn
    - I will choose the top 10 features
7) we will use KFold cross validation in order to use all the train data for training. As the data is imbalanced I will use Sklearn StratifiedKFold with 5 folds
8) We will try some Ensemble bagging and boosting algorithms we will try:
    1) KNN with bagging 
    2) Random Forest
    3) SVM with bagging
    4) XGBoost
    5) AdaBoost

XGBoost gave us the best accuracy of 84%
