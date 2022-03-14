# Loan-Prediction-System
![alt text](https://github.com/Venedah/Loan-Prediction-System/blob/main/Images/1.LOAN%20PREDICTION%20SYSTEM.jpeg)

## Problem Statement
A banks' primary business is lending. The main source of profit is the interest on the loan. After an extensive verification and validation process, the loan companies grant a loan. They do not, however, have assurance that the applicant will be able to repay the loan without difficulty. In the lending industry, the two most important questions are:

    1. What is the borrower's risk level?
    2. Should we lend to the borrower, given his/her risk?

In the current era, banks' data science teams use machine learning to construct predictive models to estimate how likely a client is to default on a loan when they only know a few pieces of information. Loan Prediction is a relatively prevalent real-life issue that every retail bank will confront at some point throughout its existence. It can save a lot of man hours at the end of a retail bank if done correctly.

## Goal of the Project
A company that deals in home loans needs to automate the loan eligibility process (real time) based on customer details provided while filling online application form. To automate this process, we have been given a problem to identify the customers’ segments, those that  eligible for loan amount so that they can specifically target these customers. The goal of this project is to predict whether a loan would be approved or not.

## Hypothesis Generation
The following are some of the elements that I believe can influence Loan Approval (the dependent variable in this loan prediction problem):

    1.Salary: An applicant with a high salary should have a better probability of getting a loan.

    2. Previous Credit History: Applicants who have paid off prior debts should have a better chance of getting a loan.

    3. Loan Amount: The loan amount should also influence loan approval. If the loan amount is little, the odds of approval are likely to be high.

    4. Loan Term: A loan for a shorter period of time and for a lower amount of money should have a better probability of being approved.

    5. EMI: The lower the monthly repayment amount, the more likely the loan will be approved.

## Data Sources
We got two CSV files for this problem: train and test. The train file will be used to train the model, which means that our model will learn from it. All of the independent variables are included, as well as the target variable. The independent variables are all present in the test file, but not the target variable. For the test data, we'll use the model to forecast the target variable. Each variable's description and data type are listed below.
![alt text](https://github.com/Venedah/Loan-Prediction-System/blob/main/Images/2.%20Data%20Dictionary.png)

We got 614 rows and 13 columns in the train dataset and 367 rows and 12 columns in the test dataset.

## Exploratory Data Analysis:
The exploratory data analysis is divided into two categories:

### 1. Univariate Analysis:
We took a look at each variable separately. Then, we utilize frequency tables or bar plots to calculate the number of each category in a variable for categorical features.
![alt text](https://github.com/Venedah/Loan-Prediction-System/blob/main/Images/3.%20Univariate%20Analysis_1.png)

The above bar plots show : 
    1. Males account for 80% of the applicants in the dataset. 

    2. Almost 65 percent of the candidates are married. 

    3. Self-employed candidates make up about 15% of the applicants in the database.
    
    4. Approximately 85% of applicants have paid off their debts.