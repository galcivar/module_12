# Module 12 Report

## Overview of the Analysis
In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
We are trying to decide whether Oversampling our data helps to improve our model improving accuracy, recall and therefore our f1_score

* Explain what financial information the data was on, and what you needed to predict.
We have Lending data provided in a .csv which included:
    - loan_size
    - interest_rate
    - borrower_income
    - debt_to_income
    - num_of_accounts
    - derogatory_marks
    - total_debt
    - loan_status

We needed to predict the loan_status, a 0 represents a Healthy loan and a 1 represents a High-risk loan

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
In the data we had **75036 loans that were healthy** and **2500 considered high risk**
* Describe the stages of the machine learning process you went through as part of this analysis.
We used model-fit-predict-evaluate pattern, where we first modeled the data using Logistic Regression Model, the we fitted the data to our model, then we tried an predict our loan_status outcome, and then we evaluated the results to improve them. 
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
We used a Logistic Regression which is the appropriate regression analysis to conduct when the dependent variable (loan_status) is binary. Logistic regression is used to describe data and to explain the relationship between one dependent binary variable and one or more nominal, ordinal, interval or ratio-level independent variables.
Given our data was imbalanced between healthy and high-risk loans we chose to use Random Oversampling to fit the data better.



## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
    Our Logistic Regression model without any resampling gave us the following:
    |y|precision|recall|specificity|f1_score|
    |--|--|--|--|--|
    |0|1.00|0.99|0.91|1.00|
    |1|0.85|0.91|0.99|0.88|

* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
    Our Logistic Regression model with Random OverSampling gave us the following:
    |y|precision|recall|specificity|f1_score|
    |--|--|--|--|--|
    |0|1.00|0.99|0.99|1.00|
    |1|0.84|0.99|0.99|0.91|

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
Th overSampled model preformed better. We can see it through the increase of the f1_score from 0.88 to 0.91 for the High-Risk Loans and no decay in the f1_score for the Healthy Loans.
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
I think given that defaulting on loans is not a simple matter, it is easier to predict why people do not default versus what factors contribute to defaulting and thus making it a High Risk Loan.

If you do not recommend any of the models, please justify your reasoning.
As an Institution I would like to research more on applications that do not pass the test in order to improve our data and model, probably increasing features to make better predictions. Given the high accuracy of the model for Healthy Loans I would use it to predict and approve them instantly, whilst forward the ones that are considered High-risk more focus and analysis.

---

## Installation Guide
1. Clone this project using git with the following command: `git clone git@github.com:galcivar/module_12.git`
2. Install Python you should follow this instructions depending on you OS: https://realpython.com/installing-python/

---

## Usage
You can use this program by navigating to the folder of the project and run:
`voila credit_risk_resampling.ipynb` in the terminal

---

## Contributors
Gabriel Alcivar
[Email](mailto:galcivar@galgomedia.com) - [LinkedIn](https://www.linkedin.com/in/gabriel-alcivar-aa83a710b/) - [GitHub](https://github.com/galcivar/)

---

## MIT License

Copyright (c) [2022] [Gabriel Alcivar]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
