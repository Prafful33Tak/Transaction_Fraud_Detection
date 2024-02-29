# Transaction_Fraud_Detection
Empowering Blocker Fraud Company's Brazilian expansion, this cutting-edge data science and ML initiative fortifies fraud detection in financial transactions. With precision analytics and advanced ML, it safeguards revenue streams while mitigating risks, ensuring robust growth and security in a dynamic marketplace.

<div align="center">
    <img alt="churn" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRaqEta_pX_1GqEpkFMUHcL9I4yLQChuglrz-uFb8f1mY5vcsXmOrIr7l2Sj-mzgXy8yBs&usqp=CAU" width="100%" height="300">
</div>

<br>


## 1.0 Business Problem
The Blocker Fraud Company is a company specialized in detecting fraud in financial transactions made through mobile devices. The company has a service called "Blocker Fraud" which guarantees the blocking of fraudulent transactions.

The business model of the company is of the Service type with the monetization made by the performance of the service provided, in other words, the user pays a fixed fee on the success in detecting fraud in the customer's transactions.

However, the Blocker Fraud Company is expanding in Brazil and to acquire customers more quickly, it has adopted a very aggressive strategy. The strategy works as follows:

  1. The company will receive 25% of the value of each transaction truly detected as fraud;

  2. The company will receive 5% of the value of each transaction detected as fraud, but the transaction is truly legitimate.

  3. The company will return 100% of the value to the customer, for each transaction detected as legitimate, however the transaction is truly a fraud.

With this aggressive strategy, the company assumes the risks of failing to detect fraud and is remunerated for assertive fraud detection.

For the client, it is an excellent business to hire the Blocker Fraud Company. Although the fee charged is very high on success, 25%, the company reduces its costs with fraudulent transactions detected correctly and even the damage caused by an error in the anti-fraud service will be covered by the Blocker Fraud Company itself.

For the company, in addition to getting many customers with this risky strategy to guarantee reimbursement in the event of a failure to detect customer fraud, it depends only on the precision and accuracy of the models built by its Data Scientists, in other words, how much the more accurate the “Blocker Fraud” model, the greater the company's revenue. However, if the model has low accuracy, the company could have a huge loss.


## 2.0 Business Assumptions
Fraud prevention is the implementation of a strategy to detect fraudulent transactions or banking actions and prevent these actions from causing financial damage and the reputation of the client and the financial institution.

There are always financial frauds and They can happen through virtual and physical ways. So the investment in security has been increasing.

The losses caused by fraud can reach R\$ 1 billion - which corresponds to half the amount that institutions invest in technology systems aimed at information security every year, according to [Febraban's 2020 Banking Technology Survey](https://blog.simply.com.br/tecnologia-bancaria-2020/).


## 3.0 Solution Strategy
My solution to solve this problem will be the development of a data science project. This project will have a machine learning model which can predict whether a transaction is fraudulent or not.

**Step 01. Data Description:** In this first section the data will be collected and studied. The missing values will be threated or removed. Finally, a initial data description will carried out to know the data. Therefore some calculations of descriptive statistics will be made, such as kurtosis, skewness, media, fashion, median and standard desviation.

**Step 02. Feature Engineering:** In this section, a mind map will be created to assist the creation of the hypothesis and the creation of new features. These assumptions will help in exploratory data analysis and may improve the model scores.

**Step 03. Data Filtering:** Data filtering is used to remove columns or rows that are not part of the business. For example, columns with customer ID, hash code or rows with age that does not consist of human age.

**Step 04. Exploratory Data Analysis:** The exploratory data analysis section consists of univariate analysis, bivariate analysis and multivariate analysis to assist in understanding of the database. The hypothesis created in step 02 will be tested in the bivariate analysis.

**Step 05. Data Preparation:** In this fifth section, the data will be prepared for machine learning modeling. Therefore, they will be transformed to improve the learning of the machine learning model, thus they can be encoded, oversampled, subsampled or rescaled.

**Step 06. Feature Selection:** After the data preparation in this section algorithms, like Boruta, will select the best columns to be used for the training of the machine learning model. This reduces the dimensionality of the database and decreases the chances of overfiting.

**Step 07. Machine Learning Modeling:** Step 07 aims to train the machine learning algorithms and how they can predict the data. For validation the model is trained, validated and applied to cross validation to know the learning capacity of the model.

**Step 08. Hyparameter Fine Tuning:** Firstly selected the best model to be applied in the project, it's important to make a fine tuning of the parameters to improve its scores. The same model performance methods apllied in the step 07 are used.

**Step 09. Conclusions:** This is a conclusion stage which the generation capacity model is tested using unseen data. In addition, some business questions are answered to show the applicability of the model in the business context.


## 4.0 Top 3 Data Insights

* #### All the fraud amount is greater than 10,000.

    **TRUE:** The values are greater than 10.000. But it's important to note that the no-fraud values is greater than 100.000 also.

    ![hypothesis2](Reports/Figures/Hypothesis_2.png)

* #### 60% of fraud transaction occours using cash-out-type method.

    **FALSE:** The fraud transaction occours in transfer and cash-out type. However they're almost the same value.

    ![hypothesis3](Reports/Figures/Hypothesis_3.png)

* #### Values greater than 100,000 occours using transfers-type method.

    **FALSE:** The majority transactions occours in trasnfer-type, however transactions greater than 100.000 occour in cash-out and cash-in too.

    ![hypothesis4](Reports/Figures/Hypothesis_4.png)


## 5.0 Machine Learning Applied

Here's all cross validation results of the machine learning models with their default parameters. The cross validation method is important to show the capacity of the model to learn.

#### Dummy Model

| Balanced Accuracy |  Precision  |    Recall   |      F1     |      Kappa     |
|:-----------------:|:-----------:|:-----------:|:-----------:|:--------------:|
|   0.5 +/- 0.0   | 0.0 +/- 0.0 | 0.0 +/- 0.0 | 0.0 +/- 0.0 | 0.0 +/- 0.0 |

#### Logistic Regression

| Balanced Accuracy |  Precision  |      Recall     |        F1       |      Kappa      |
|:-----------------:|:-----------:|:---------------:|:---------------:|:---------------:|
|  0.565 +/- 0.013  | 1.0 +/- 0.0 | 0.129 +/- 0.026 | 0.228 +/- 0.041 | 0.228 +/- 0.041 |

#### K Nearest Neighbors

| Balanced Accuracy |    Precision    |      Recall     |        F1       |      Kappa      |
|:-----------------:|:---------------:|:---------------:|:---------------:|:---------------:|
|  0.705 +/- 0.017  | 0.943 +/- 0.033 | 0.411 +/- 0.034 | 0.572 +/- 0.038 | 0.572 +/- 0.038 |

#### Support Vector Machine

| Balanced Accuracy |  Precision  |     Recall     |        F1        |      Kappa      |
|:-----------------:|:-----------:|:--------------:|:----------------:|:---------------:|
|  0.596 +/- 0.017  | 1.0 +/- 0.0 | 0.192 +/- 0.034 | 0.32 +/- 0.047 | 0.32 +/- 0.047 |

#### Random Forest

| Balanced Accuracy |    Precision    |      Recall     |        F1       |      Kappa      |
|:-----------------:|:---------------:|:---------------:|:---------------:|:---------------:|
|  0.861 +/- 0.019  | 0.969 +/- 0.018 | 0.721 +/- 0.038 | 0.827 +/- 0.029 | 0.827 +/- 0.029 |

#### XGBoost

| Balanced Accuracy |    Precision    |      Recall     |       F1       |      Kappa     |
|:-----------------:|:---------------:|:---------------:|:--------------:|:--------------:|
|  0.887 +/- 0.021  | 0.938 +/- 0.017 | 0.775 +/- 0.042 | 0.848 +/- 0.023 | 0.848 +/- 0.023 |

#### LightGBM

| Balanced Accuracy |   Precision  |      Recall     |        F1       |      Kappa      |
|:-----------------:|:------------:|:---------------:|:---------------:|:---------------:|
|  0.696 +/- 0.08  | 0.251 +/- 0.167 | 0.394 +/- 0.158 | 0.299 +/- 0.175 | 0.297 +/- 0.175 |


## 6.0 Machine Learning Performance

The chosen model was **XGBoost** and it was tuned to improve their parameters and scores. Below there's a table with the capacity of the model to learn.

| Balanced Accuracy |    Precision    |      Recall     |       F1       |      Kappa     |
|:-----------------:|:---------------:|:---------------:|:--------------:|:--------------:|
|  0.887 +/- 0.021  | 0.938 +/- 0.017 | 0.775 +/- 0.042 | 0.848 +/- 0.023 | 0.848 +/- 0.023 |

It's possible to determinize the capacity of the model to generalize using unseen data. In other words, capcity of the model to classify new data as shown.

| Balanced Accuracy | Precision | Recall |   F1  | Kappa |
|:-----------------:|:---------:|:------:|:-----:|:-----:|
|       0.912       |   0.957   |  0.823 | 0.885 | 0.885 |


## 7.0 Business Results

* #### The company receives 25% of each transaction value truly detected as fraud.

    The company can receive R\$ 60,638,881.09 detecting fraud transactions.

* #### The company receives 5% of each transaction value detected as fraud, however the transaction is legitimate.

    For wrong decisions, the company can receive R\$ 108,137.29.

* #### The company gives back 100% of the value for the customer in each transaction detected as legitimate, however the transaction is actually a fraud.

    The company must return the amount of R\$ 3,445,682.59.

* #### What is the model's Precision and Accuracy?

    For unseen data, the values of balanced accuracy is equal 91% and precision is equal 96%.

* #### How reliable is the model in classifying transactions as legitimate or fraudulent?

    The model can detect 83.7% +/- 1.8% of the fraud. However it detected 0.885 of the frauds from a unseen data.

* #### What is the revenue expected by the company classify 100% of transactions with the model?

    Using the model the company can revenue R\$ 60,747,018.38. Using the currently method to detect fraud the revenue is 0.00.

* #### What is the loss expected by the Company if it classifies 100% of the transactions with the model?

    For wrong classifications the company must return the amount of R\$ 3,445,682.59. In contrast, for wrong classifications using the currently method, the company must return the amount of R\$ 246,001,206.94.

* #### What is the profit expected by the blocker fraud company when using the model?

    The company can expect the profit of R\$ 57,301,335.79. The profit value of the currently method is R\$ -246,001,206.94.


## 8.0 Conclusions

The data is extremaly unbalanced, however it was possible to make all the data analysis and create with good scores.

The company may expect a revenue of R\$ 57,301,335.79. This result may show the capacity of a project of data science and help the company.
