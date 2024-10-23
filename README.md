# LoanTap Logistic Regression Analysis

### Goal
The primary goal of this analysis is to build an underwriting layer that determines the creditworthiness of MSMEs and individuals applying for loans at LoanTap. By analyzing the loan dataset, the objective is to predict loan statuses effectively and provide insights into factors influencing loan repayment behaviors.

### Data Dictionary
- **loan_amnt**: The listed amount of the loan applied for by the borrower.
- **term**: The number of payments on the loan (36 or 60 months).
- **int_rate**: Interest Rate on the loan.
- **installment**: The monthly payment owed by the borrower.
- **grade**: LoanTap assigned loan grade (A-G).
- **sub_grade**: LoanTap assigned loan subgrade.
- **emp_title**: The job title provided by the borrower.
- **emp_length**: Employment length in years (0-10).
- **home_ownership**: Home ownership status provided by the borrower.
- **annual_inc**: Self-reported annual income provided by the borrower.
- **verification_status**: Indicates if income was verified.
- **issue_d**: The month the loan was funded.
- **loan_status**: Current status of the loan (target variable).
- **purpose**: Category provided by the borrower for the loan request.
- **title**: Loan title provided by the borrower.
- **dti**: Debt-to-Income ratio.
- **earliest_cr_line**: Month the earliest reported credit line was opened.
- **open_acc**: Number of open credit lines in the borrower's credit file.
- **pub_rec**: Number of derogatory public records.
- **revol_bal**: Total credit revolving balance.
- **revol_util**: Revolving line utilization rate.
- **total_acc**: Total number of credit lines in the borrower's file.
- **initial_list_status**: Initial listing status of the loan (W, F).
- **application_type**: Indicates individual or joint application.
- **mort_acc**: Number of mortgage accounts.
- **pub_rec_bankruptcies**: Number of public record bankruptcies.
- **Address**: Address of the individual.

### Summary of Analysis on Loan Dataset

1. **Data Preprocessing**
    - **Ordinal Mapping**: Numeric values were assigned to loan grades (A-G).
    - **Feature Engineering**: Additional features were created for better analysis.

2. **Exploratory Data Analysis (EDA)**
    - **Chi-Square Test**: Analyzed the relationship between loan grades and payment statuses; significant relationship found (p < 0.05).
    - **ANOVA Test**: Significant differences in annual income across loan statuses (F-statistic: 2258.48, p-value: 0.0000).

3. **Model Building**
    - **Train-Test Split**: Dataset split into training (80%) and testing (20%).
    - **Standardization**: Features standardized using StandardScaler.

4. **Logistic Regression Model**
    - **Model Initialization and Fitting**: Logistic Regression model initialized with regularization parameter (C=1/10).
    - **Evaluation Metrics**:
        - Training Accuracy: 0.67
        - Test Accuracy: 0.67
        - Training Recall: 0.65
        - Test Recall: 0.62
        - Training Precision: 0.67
        - Test Precision: 0.32

5. **Hyperparameter Tuning**
    - Explored varying values of the regularization parameter (λ) and its impact on model performance.

6. **ROC and Precision-Recall Curves**
    - **ROC Curve**: Visualized model performance, highlighting the true positive rate against the false positive rate.
    - **Precision-Recall Curve**: Analyzed trade-off between precision and recall.

7. **Polynomial Regression**
    - Constructed models with polynomial features (degrees 0 to 2), noting performance observations.
        - Degree 0: High test accuracy, no positive predictions.
        - Degree 1: Reasonable performance but potential overfitting.
        - Degree 2: Improved training accuracy, lower test recall.

8. **Conclusion and Future Improvements**
    - **Overall Findings**: Indicated a relationship between loan grades and payment statuses; significant income differences based on loan status. Logistic regression showed moderate performance but overfitting signs.
    - **Recommendations for Improvement**: Consider advanced models like Random Forests or Gradient Boosting for improved accuracy and recall.

