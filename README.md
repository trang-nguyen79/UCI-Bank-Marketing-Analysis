# UCI-Bank-Marketing-Analysis

## Executive Summary

### 1. Customer Business and Target Values

Defining customer business and objective:

The data represents a marketing campaign conducted by a Portuguese banking institution.  
The campaign is based on phone calls with clients. In some cases, multiple contacts with the same client were required to determine whether the client would subscribe to a bank term deposit (with the outcome being either 'yes' or 'no').

The objective is to predict whether a client will subscribe to a term deposit (variable y) and to identify the attributes that have the greatest impact on clients likely to subscribe.

Target questions:

1. What factors influence whether a customer subscribes (y)?
2. Predicting the characteristics that determine if a customer will subscribe or not to a term deposit.
3. How to adjust customer communication to increase the likelihood of customer subscription?                            

### 2. Data Dictionary 

Dataset overview:

The dataset consists of 45,211 observations and 17 columns (descriptions) that relate to a bank marketing campaign. Overall, the dataset contains both, numerical and categorical values that capture demographic information, financial status, contact- related information and past campaign outcomes.

Target Variable is (y). This is a binary target variable that indicates whether a client subscribed to a term deposit. Value "yes' is '1', "no" is '0'.

Features selected based on relationship with target variable:

Numerical Features Used in the Model 
age: Age of the client.  
balance: Average yearly balance in the client’s account. 
duration: Last contact duration in seconds.
campaign: Number of contacts performed during this campaign. 
pdays: Days since the client was last contacted from a previous campaign. 
previous: Number of contacts before this campaign.

Categorical Features Used in the Model 
job: Type of job                                                                                                                                                                                                                            marital: Marital status.
education: Education level. 
default: Whether the client has credit in default.
housing: Whether the client has a housing loan. 
loan: Whether the client has a personal loan.
contact: Communication type.
month: Last contact month.

### 3. Data Pre-processing

Key steps taken:
- handling missing values
- handling outliers
- data transformation
- drop not useful columns
- convert to numerical values

### 4. Exploratory Data Analysis

Correlation Analysis Findings
- duration had the strongest correlation with subscription especially call > 5mins. Short calls (<2mins) rarely led to subscriptions
- Customers previouslycontacted were twice as likely to subscribe compared to those never contacted before
- Customers with successful past outcomes (poutcome = success) had a 64% conversion rate.
- pdays: Customers contacted recently (<60 days) had higher conversion rates than those contacted a long time ago (>180 days).
- Higher balance customers were more likely to subscribe, but impact was moderate.
- Customers without housing loans or personal loans were more likely to subscribe.
- job and age: seniors and high-income professionals had higher conversions
- education and marital variables didn't appear with clear pattern, but we still keep them for modeling
- There is no patterns I could see in month and day_of_week variables

### 5. Predictive modeling

Key steps taken:
- Splitting datasets
- Building model
- Testing model
- Choose best features for the model

Summary:
- Call duration emerged as a strong predictor, confirming that longer conversations increase the likelihood of a positive response. Conversely, financial commitments such as housing and personal loans negatively impacted subscription probability, suggesting that customers with existing financial obligations are less likely to subscribe. These insights highlight the importance of focusing on customer engagement strategies and refining target audiences for marketing efforts
- The model achieved 90% accuracy, primarily driven by correctly identifying non-subscribers
- However, it exhibited low recall for actual subscribers (26%), indicating difficulty in detecting customers who would subscribe. The confusion matrix revealed a high false negative rate, meaning many potential subscribers were misclassified as non-subscribers
- This imbalance suggests that while the model is effective in ruling out non-subscribers, it lacks the sensitivity to capture actual conversions, which could hinder business decision-making and marketing effectiveness.

### 6. Recommendations 

Factors that influence whether customer subscribes:
- Two strongest predictors that indicate that a customer will most likely subscribe is call duration and days since last contact.
- Predicting characteristics that impact the likelihood of subscription:

Focus on Target Profiles: 
- Target clients have the following attributes: long call duration, higher number of past interactions, higher balance, no loans, no history of default and higher education. These attributes have a higher chance of a customer subscribing. 

Adjusting customer communication to increase the chances of customer subscription:
1. Develop separate strategies for first-time contacts vs. returning clients. 
2.Create a separate strategy for segment communication: seniors may need a tailored message due to higher conversion rate and single clients respond differently than married client due to marital status. 
3. Longer gaps between contact may improve success (based off pdays). 
4. Limit active campaign contacts to avoid possible client fatigue due to overwhelming marketing.





