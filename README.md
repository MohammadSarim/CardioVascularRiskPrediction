# CardioVascularRiskPrediction
**Cardiovascular Risk Prediction** dataset provides the patients' information. The dataset contains information on **3,390 individuals with 16 predictor variables and 1 target variable**. Each variable (attribute) is a potential risk factor. There are demographic, behavioral, and medical risk factors. We were tasked **to predict the 10-year risk of developing coronary heart disease (CHD)**.

After understanding the data and getting variables, we first gathered and **cleaned the data, handled the null values** by checking the distribution and outliers in the data after that we have also typecasted the needed features into required format by **type casting** in order to visualize them properly. We performed indepth **EDA** and plotted different types of graphs by separating them into univariate, bivariate and multivariate categories as a result, We came accross some meaningful insights that helped us to make future decisions of ML model pipeline. Then further on, using **feature engineering** and data preprocessing  we have extracted new features like pulse_pressure and glucose_diabetes with the help of some features which are not directly impacting to tenYearCHD. We also tried to get some impacting features by removing **multicollinearity** within the independent variables with the help of **various inflation factor(VIF)**. In this dataset we have not **handled outliers** as removing them could potentially lead to a loss of important information and biased results. Also, we noticed that some of the features were categorical in nature and ML model can not understand the language of alphabets(strings).So, we have encoded them into numericals using **BINARY LABEL ENCODING** .

In order to get normally distributed data we have applied various **transformation techniques** such as Logarithmic Transformation, Exponential Transformation, Square root Transformation and some others as well and plotted the quantie-quantile plot to visualize how far our data points are from the normal distribution.To scale the data We used the sklearn library **StandardScaler**.

It was an **highly imbalanced** dataset as the distribution of the target variable, TenYearCHD, was found to be imbalanced, with only **15%** of individuals being classified as having a high risk of developing CHD. So we used **SMOTE(Synthetic Minority Oversampling Technique)** to create a balanced dataset.

Now as we are ready with our final features we **splitted** the data so that we will get the stratified samples of both the class in train and test sets.We have implimented the most basic and least complex model which is **Logistic Regression** and followed by the **Random forest, XGboost, Naive Bayes, KNN, SVM** and compared the various metrics obtained from classification reports such as **Precision, Recall, F1 Score, Accuracy and AUC-ROC**. We have also compared the exact number of patients that are correctly or wrongly classified by our model with the help of **confusion matrix**. Since, we have the **healthcare data**, we have more **emphasised on the Recall** as it reduces the number of FN cases(we don't want our model to predict the infected ones as healthy),  which is our major objective, moreover we have focused on the f1 score and then accuracy from the various metrics.

Among all the models we have implimented we have **achieved the highest Recall, precision, f1 score, accuracy and AUC-ROC score from XGboost with the values of (0.94,0.85),(0.85,0.94),(0.90,0.89),(0.89),(0.94) for the class (0,1) respectively by hyperparamter tuning with the learning rate of 0.1, maximum tree depth of 5 and the total number of 350 trees in the forest**. From the above experiments, identifications and comparision, we have choosen the **XGboost as our final optimal model** among all 6 models for deployment.

Overall, while building a machine learning model on Cardiovascular risk prediction data, we applied combination of data processing, machine learning techniques, and model evaluation skills. It was a challenging task and we faced some failures as well but with the right approach and knowledge, we successfully created a model that can accurately predict a patient that can be infected with CHD in future.








