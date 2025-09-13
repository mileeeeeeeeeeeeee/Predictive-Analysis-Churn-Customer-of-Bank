# Customer Churn Prediction and Strategy Development for Bank X

## Data Source
Bank Customer Churn Dataset: https://www.kaggle.com/datasets/gauravtopre/bank-customer-churn-dataset

## Background

According to data from the European Banking Federation [1], the number of banks in Europe declined by 33% between 2009 and 2020, largely due to fierce competition in the sector. Bank X is facing a customer churn rate of 20.37%, which makes it difficult to retain clients and ensure sustainable growth.


<img width="828" height="526" alt="image" src="https://github.com/user-attachments/assets/15f308b5-e04e-461d-9be5-ab6a96fd01fb" />


To stay competitive, banks need to go beyond traditional strategies and find new ways to keep existing customers while attracting new ones. In this project, I built a predictive model to analyze customer behavior and proposed strategies that can help Bank X manage churn more effectively.

## Problem Identification

Using the 5 Whys analysis, the root cause of churn at Bank X was traced to the lack of strategies aimed at building long-term customer relationships.

<img width="1506" height="1323" alt="Portfolio drawio" src="https://github.com/user-attachments/assets/c1613756-db98-4d81-b92c-0eb97fcdc082" />

## Building the Prediction Model

To have better understanding towards factors contributing to churn, I conducted a comprehensive analysis of customer attributes. This analyis revealed that Age, Active Membership Status, Geography, and Gender are the key features to consider. Based on these features, I trained and compared several machine learning algorithms:
- K-Nearest Neighbors (KNN)
- Random Forest (RF)
- Gradient Boosting Machine (GBM)
- Support Vector Machine (SVM)

Each model was evaluated not only on accuracy, but also on cost-benefit analysis to ensure business relevance.

## Evaluate Model

Let's take a look at the accuracy first. Among the models, GBM achieved the highest accuracy at 83.7%

| Model | Accuracy |
| ----- | -------- |
| KNN | 81.73% |
| RF | 82.67% |
| **GBM** | **83.7%** |
| SVM | 83.27% |

Looking deeper into false positives (FP) and false negatives (FN), the KNN model was more effective in identifying customers at risk of churn (TP).

| Model | TP | TN | FP | FN | 
| ----- | -- | -- | -- | -- | 
| **KNN** | 258 | 2194 | 179 | 258 |
| RF | 220 | 2260 | 113 | 407 |
| GBM | 225 | 2286 | 87 | 402 |
| SVM | 162 | 2336 | 37 | 465 |

Next, use this number for cost-benefit analysis. Assuming the bank offers a $1,000 retention incentive per high-risk customer and earns a 3% profit margin from customer net value, KNN delivered the highest projected profit.

| Model | Total Loss | Total Benefit | Profit |
| --- | --- |--- | --- | 
| **KNN** | $1.025.689 | $6.108.151 | **$5.082.462** |
| RF | $1.046.882 | $6.020.958 | $4.974.076 |
| GBM | $1.009.409 | $6.032.431 | $5.023.022 |
| SVM | $1.103.966 | $5.887.874 | $4.783.909 |

## Strategies
Based on both accuracy and business impact, the K-Nearest Neighbors model is recommended as the most effective approach. With its predictions, Bank X can proactively implement retention strategies such as:
- Loyalty programs tailored to customer segments
- Personalized offers for at-risk clients
- Improved customer service initiatives to strengthen long-term relationships
These actions would not only reduce churn but also enhance customer satisfaction and profitability.


## Reference
[1] https://ec.europa.eu/eurostat/cache/digpub/european_economy/bloc-3d.html
