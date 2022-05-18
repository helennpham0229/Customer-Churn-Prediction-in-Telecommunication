# Customer-Churn-Prediction-in-Telecommunication

# Introduction
SyriaTel is a telecommunications company looking to predict and prevent customer churn. Customer churn is the percentage of customers that stopped using a company's product or service during a certain time frame. It can be a major problem because it impacts a company's customer loyalty and eventually affects company's revenue. 

To help SyriaTel fix the problem of customer churn, I did an Exploratory Data Analysis and then built a machine learning classifier that will predict whether the customers are going to churn. 

# Obtain
This project used the churn in telecoms dataset, which can be found in this repo (customer_churn_data.csv), and on kaggle via this [link](https://www.kaggle.com/becksddf/churn-in-telecoms-dataset/code). This dataset included 21 columns and 3333 unique values. It was already clean with no outliers or null values.

# Scrub & Explore
In this portion, We learned that the churn percentage is about 14% or 483 out of 3333 customers. And we are going to explore different factors that can potentially lead to the mentioned rate. Here, I wonly highlight some interesting findings. You can find more details in the notebook.

### Account Length
We can see that account_length doesn't seem to have a significant effect whether a customer leaves the company or not because we have similar mean values and standard deviations for account length.
![Alt text](https://raw.githubusercontent.com/helennpham0229/Customer-Churn-Prediction-in-Telecommunication/main/images/1.png)

### State
It is clear that there are certain states with much higher churn. When grouped by state, CA, MD, NJ, TX have the highest churn percentages (approx 25%). States with the least churn include Alaska, Hawaii (approx 5%). However, we don't have information on "why" - it could be due to cell signal, different offers, etc.
![alt text](https://raw.githubusercontent.com/helennpham0229/Customer-Churn-Prediction-in-Telecommunication/main/images/2.png)

### International Plan
The percentage of customers who churn is higher for customers with international plans than for customers without international plans.
![alt text](https://raw.githubusercontent.com/helennpham0229/Customer-Churn-Prediction-in-Telecommunication/main/images/3.png)

### Voicemail Plan
The percentage of customers who churned is higher for customers without voicemail plans than for customers with voicemail plans.
![alt text](https://raw.githubusercontent.com/helennpham0229/Customer-Churn-Prediction-in-Telecommunication/main/images/4.png)

People who receive more voicemail messages in average tend to churn more often.
![alt text](https://raw.githubusercontent.com/helennpham0229/Customer-Churn-Prediction-in-Telecommunication/main/images/5.png)

### Customer Service Calls
When we look at customer service calls, we can see that as the number of customer service calls increases, the likelihood of churning increases as well. The majority of customers who DID NOT churn made 1-2 customer service calls. However, the majority people who DID churn made over 3 calls to customer service. 
![alt text](https://raw.githubusercontent.com/helennpham0229/Customer-Churn-Prediction-in-Telecommunication/main/images/6.png)

### Total Calls
Customers who churned and those that did not churn had almost exactly the same usage across day, eve, night and international calls. 
![alt text](https://raw.githubusercontent.com/helennpham0229/Customer-Churn-Prediction-in-Telecommunication/main/images/7.png)

### Rates
* Day Rate: 0.17
* Eve Rate: 0.085
* Night Rate: 0.045
* International Plan Rate: 0.27
* Non-International Plan Rate:  0.27

The rates for international minutes are the same regardless of whether the customer has an international plan or not (27 cents per minute). 

# Model
In this portion of the project, I explored different classification models including logistic regression, KNN, random forest, and XGBoost. For each model, I observed the confusion matrix, ACU, precision, recall, accuracy, and F1 score for both training and testing splits.

# Interpretation
The best model was XGBoost with GridSearch tuning (with 0.96 accuracy and 0.84 F1 score). 

The top 3 important features are customer service calls, voicemail plan, and international plan.
![alt text](https://raw.githubusercontent.com/helennpham0229/Customer-Churn-Prediction-in-Telecommunication/main/images/8.png)

# Recommendations
* Revisit and revise company’s customer service protocol and offer a larger incentive to customers making more than 3 customer service calls 
* Changing the rates for international minutes/international plan
* Initiating customer feedback surveys for customers leaving

# Future Works
* Get more data on cell signal across the US to look for patterns in states with higher churn
* Information from customer service calls such as Payments, Complaints, Web inquiries, etc.
