# Bankmarketing
Bank Marketing Campaign using Classification 

### Data Understanding

Our dataset comes from the UCI Machine Learning repository [link](https://archive.ics.uci.edu/ml/datasets/bank+marketing).  The data is from a Portugese banking institution and is a collection of the results of multiple marketing campaigns.  We will make use of the article accompanying the dataset [here](CRISP-DM-BANK.pdf) for more information on the data and features.

## Understanding the Features


Examine the data description below, and determine if any of the features are missing values or need to be coerced to a different data type.


```
Input variables:
# bank client data:
1 - age (numeric)
2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
5 - default: has credit in default? (categorical: 'no','yes','unknown')
6 - housing: has housing loan? (categorical: 'no','yes','unknown')
7 - loan: has personal loan? (categorical: 'no','yes','unknown')
# related with the last contact of the current campaign:
8 - contact: contact communication type (categorical: 'cellular','telephone')
9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')
10 - day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')
11 - duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
# other attributes:
12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
14 - previous: number of contacts performed before this campaign and for this client (numeric)
15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')
# social and economic context attributes
16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)
17 - cons.price.idx: consumer price index - monthly indicator (numeric)
18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)
19 - euribor3m: euribor 3 month rate - daily indicator (numeric)
20 - nr.employed: number of employees - quarterly indicator (numeric)

Output variable (desired target):
21 - y - has the client subscribed a term deposit? (binary: 'yes','no')
```


## Business Objective

The main aim of this Machine Learning analysis is to pinpoint a model that effectively predicts the success of a contact - whether a client will subscribe to the deposit. By accomplishing this, we can significantly improve campaign efficiency by identifying crucial characteristics that influence success. Consequently, this enables better resource management and the selection of a high-quality, cost-effective potential customer base.

To achieve this objective, we compare the performance of various algorithms including k-nearest neighbors, logistic regression, decision trees, and support vector machines. By evaluating the effectiveness of each model, we can determine which one best suits our needs and provides the most accurate predictions regarding client subscription to the deposit.

## Approach
The project will adhere to the CRISP-DM (Cross-Industry Standard Process for Data Mining) methodology. Our objective is to identify the model with the highest accuracy, while also considering its interpretability. Understanding the factors influencing a client's decision can offer valuable insights for the business.

The process will involve the following stages:

Data Understanding: This phase involves gaining familiarity with the dataset, its structure, and its features. Understanding the data is crucial for selecting appropriate preprocessing techniques and modeling strategies.

Data Preparation: In this phase, we'll clean the data, handle missing values, and perform feature engineering if necessary. Data preprocessing plays a vital role in ensuring the quality and reliability of our model.

Modeling: Here, we'll develop and train machine learning models using various algorithms such as k-nearest neighbors, logistic regression, decision trees, and support vector machines. We'll assess each model's performance and select the one that best meets our criteria.

Evaluation: Finally, we'll evaluate the selected models based on their accuracy and interpretability. We'll also consider additional metrics such as precision, recall, and F1-score to comprehensively assess model performance.

The details of each stage, along with code implementation and analysis, can be found in the Python notebook: prompt_III.ipynb.

The dataset used for this project is available in the following files:

/data/bank-additional-full.csv
/data/bank-additional-names.txt
/data/bank-additional.csv (subset of the full dataset)
Additionally, we'll reference the accompanying article for more insights into the dataset's features and context. This comprehensive approach ensures thorough exploration, analysis, and selection of the most suitable model for predicting client subscription to the deposit.


## Results


To address our business challenge of predicting term subscription based on campaign performance, maximizing recall is crucial for boosting revenue. Therefore, selecting a model with high recall and minimizing false negatives is paramount. Consequently, we opted for the Logistic Model to enhance customer term deposit predictions.

The refined logistic model exhibits a improvement in recall compared to the baseline logistic model.

Despite the various classification reports generated by the model, they consistently indicate predominant classification of the majority class (0). This suggests potential for further model optimization or exploration of alternative unsupervised learning classification models.

Each false positive incurred by the bank translates into expenditure and diverts resources from other revenue-generating avenues. Conversely, false positives erode customer trust and may lead to customer attrition, compounding the loss.

False negatives pose the risk of missing out on potential customers, thereby reducing the bank's revenue potential.

For the marketing campaign, attracting more term deposit subscriptions is pivotal for revenue generation. Any customer loss resulting from the campaign's output—termed as customer churn—could severely impact the bank's bottom line. Therefore, minimizing false negatives is essential to mitigate this risk and sustain customer engagement.

## Recommendations

After analyzing the results and conducting exploratory data analysis, it's evident that certain features significantly influence customers' decisions to purchase term deposits. Here's a breakdown of the key features the bank should prioritize to attract more customers:

Duration: This feature emerges as one of the most influential factors, with longer call durations correlating to higher sales probabilities. To capitalize on this insight, the bank should focus on improving call quality by fostering rapport with customers, minimizing wait times, conducting follow-ups, and actively seeking customer feedback.

Age: Analysis indicates that the majority of term deposit purchases occur within the age range of 25 to 58 years. Therefore, the bank should concentrate its marketing efforts on targeting this demographic and allocate resources accordingly to attract more customers from this age group.

Campaign: The number of calls made during the current campaign is a crucial factor. However, customers generally prefer not to be inundated with excessive calls. Therefore, it's essential for the bank to strike a balance, typically between 1 to 5 calls, depending on individual customer interests. Training the sales team to discern customer preferences based on behavioral cues such as tone, voice modulation, and pitch can be beneficial in achieving this balance.

Euribo3: Higher interest rates tend to attract more customers, as evidenced by the data trend. The bank can leverage this insight by targeting age groups more likely to respond favorably to higher interest rates (e.g., 4.5-5%). Additionally, ramping up marketing efforts during periods of elevated interest rates can help attract more clients to term deposits.

nr.employed: The data suggests that a higher number of employees correlates with a greater number of customers. This underscores the importance of expanding the workforce to target more leads effectively and provide adequate follow-up and customer support. Establishing a dedicated after-sales team can further enhance customer satisfaction and retention.

By focusing on these key features and implementing targeted strategies, the bank can optimize its efforts to attract more customers and drive term deposit sales.
