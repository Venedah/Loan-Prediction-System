# Loan-Prediction-System
![alt text](https://github.com/Venedah/Loan-Prediction-System/blob/main/Images/1.LOAN%20PREDICTION%20SYSTEM.jpeg)

## Problem Statement:
A banks' primary business is lending. The main source of profit is the interest on the loan. After an extensive verification and validation process, the loan companies grant a loan. They do not, however, have assurance that the applicant will be able to repay the loan without difficulty. In the lending industry, the two most important questions are:

    1. What is the borrower's risk level?
    2. Should we lend to the borrower, given his/her risk?

In the current era, banks' data science teams use machine learning to construct predictive models to estimate how likely a client is to default on a loan when they only know a few pieces of information. Loan Prediction is a relatively prevalent real-life issue that every retail bank will confront at some point throughout its existence. It can save a lot of man hours at the end of a retail bank if done correctly.

## Goal of the Project:
A company that deals in home loans needs to automate the loan eligibility process (real time) based on customer details provided while filling online application form. To automate this process, we have been given a problem to identify the customers’ segments, those that  eligible for loan amount so that they can specifically target these customers. The goal of this project is to predict whether a loan would be approved or not.

## Hypothesis Generation:
The following are some of the elements that I believe can influence Loan Approval (the dependent variable in this loan prediction problem):

    1.Salary: An applicant with a high salary should have a better probability of getting a loan.

    2. Previous Credit History: Applicants who have paid off prior debts should have a better chance of getting a loan.

    3. Loan Amount: The loan amount should also influence loan approval. If the loan amount is little, the odds of approval are likely to be high.

    4. Loan Term: A loan for a shorter period of time and for a lower amount of money should have a better probability of being approved.

    5. EMI: The lower the monthly repayment amount, the more likely the loan will be approved.

## Data Sources:
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

![alt text](https://github.com/Venedah/Loan-Prediction-System/blob/main/Images/4.%20Univariate%20Analysis_2.png)

The above bar plots can be used to draw the following conclusions: 

    1. The majority of the applicants have no dependents. 

    2. Graduates make up about 80% of the applications. 
    
    3. The majority of applicants are from the Semiurban area.

Probability density maps can be used to visualize the distribution of numerical data.

![alt text](https://github.com/Venedah/Loan-Prediction-System/blob/main/Images/5.%20Univariate%20Analysis_3.png)
The boxplot verifies the presence of a lot of extreme values/outliers, and it can be extrapolated that most of the data in the distribution of applicant income is towards the left, which is not normally distributed. This can be attributable to the society's income disparity.

### 2. Bivariate Analysis:
We examine each variable with respect to target variable.
![alt text](https://github.com/Venedah/Loan-Prediction-System/blob/main/Images/6.%20Bivariate%20Analysis.jpg)

The above bar charts can be used to get the following conclusions: 
    1. It appears that those having a credit score of 1 are more likely to be approved for loans.

    2. When compared to rural and urban areas, the proportion of loans authorized in semi-urban areas is higher. 
    
    3. The proportion of married applicants who are authorized for loans is greater. 
    
    4. For both approved and unapproved loans, the ratio of male and female applicants is roughly the same.

### 3. Correlation Plot:
The correlation between all numerical variables is depicted in the heatmap below. The variable with a darker color indicates their correlation is more.
![alt text](https://github.com/Venedah/Loan-Prediction-System/blob/main/Images/7.Correlation.png)
We can see that (Applicant Income – Loan Amount) and (Credit History – Loan Status) are the most correlated variables. LoanAmount and CoapplicantIncome are also correlated.

# Preprocessing of Data:
The quality of the model's inputs will determine the quality of the output. The data was pre-processed in the following steps before being fed into the prediction model.

    1. Missing Value Attribution
    We may now impute missing values and treat outliers after we've figured out all of the variables in the data, because missing data and outliers might hurt the model's performance.

    We look at the following values in each characteristic one at a time.
    We impute categorical variables using mode.     
    For numerical variables:Imputation using the mean or median because it is clear from Exploratory Data Analysis that the loan amount has outliers. 
    We used the median to impute the missing values. 
    The mean would not be the best technique because it is heavily influenced by the presence of outliers.

    2. Treatment of Outliers
    LoanAmount is biased to the right because it contains outliers. The log transformation is one approach to get rid of the skewness. As a result, we get a distribution that resembles the normal distribution and reduces the higher values while having little effect on the smaller ones.
![alt text](https://github.com/Venedah/Loan-Prediction-System/blob/main/Images/8.%20Outlier%20Treatment.png)

The LoanAmount distribution now resembles that of a normal distribution, with the effect of extreme numbers greatly reduced.

# Building the Baseline Model:
To predict the loan status, We used a basic logistic regression model over the baseline model. The training data is split into two sets: training and validation. As we have the true predictions for the validation part, we may validate our predictions this way. The accuracy of the baseline logistic regression model is 84 percent. The F-1 score derived from the classification report is 82 percent.

# Feature Engineering:
We can think of new characteristics that might affect the target variable based on domain expertise. Following are three new features that we can think of:

    1. Total Income
    We will combine the applicant and coapplicant incomes, as indicated by Exploratory Data Analysis. If your total salary is high, you may have a better chance of getting a loan.

    2. EMI
    The EMI is the amount that the borrower must pay each month to repay the loan. The reason for include this variable is that consumers with high EMIs may find it difficult to repay their loans. We may compute EMI by multiplying the loan amount by the period of the loan.

    3. Balanced Income
    After the EMI is paid, this is the remaining income. The idea behind this variable is that if the value is high, a person is more likely to repay the loan, increasing the likelihood of loan acceptance.

    Let's get rid of the columns we used to make these new features. The reason for this is that the correlation between the old and new features will be extremely high, whereas logistic regression implies that the variables are not highly associated. We also want to get rid of the noise in the data, so deleting linked features will help with that.

# Model Building:
In this case, StratifiedShuffleSplit is employed as a cross validation technique.
This cross-validation technique has the advantage of combining StratifiedKFold with ShuffleSplit to produce stratified randomized folds. The folds are created by keeping track of the percentage of samples in each class.
We can continue the model-building process after adding new features. As a result, we started with a logistic regression model and progress to more complex models such as Decision Tree, Random Forest, and XGBoost.