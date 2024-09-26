Business Case: LoanTap Logistic Regression
Context:

LoanTap is an online platform committed to delivering customized loan products to millennials. They innovate in an otherwise dull loan segment, to deliver instant, flexible loans on consumer friendly terms to salaried professionals and businessmen.

The data science team at LoanTap is building an underwriting layer to determine the creditworthiness of MSMEs as well as individuals.

LoanTap deploys formal credit to salaried individuals and businesses 4 main financial instruments:

    Personal Loan
    EMI Free Loan
    Personal Overdraft
    Advance Salary Loan
Data dictionary:
    loan_amnt : The listed amount of the loan applied for by the borrower. If at some point in time, the credit department reduces the loan amount, then it will be reflected in this value.
    term : The number of payments on the loan. Values are in months and can be either 36 or 60.
    int_rate : Interest Rate on the loan
    installment : The monthly payment owed by the borrower if the loan originates.
    grade : LoanTap assigned loan grade
    sub_grade : LoanTap assigned loan subgrade
    emp_title :The job title supplied by the Borrower when applying for the loan.*
    emp_length : Employment length in years. Possible values are between 0 and 10 where 0 means less than one year and 10 means ten or more years.
    home_ownership : The home ownership status provided by the borrower during registration or obtained from the credit report.
    annual_inc : The self-reported annual income provided by the borrower during registration.
    verification_status : Indicates if income was verified by LoanTap, not verified, or if the income source was verified
    issue_d : The month which the loan was funded
    loan_status : Current status of the loan - Target Variable
    purpose : A category provided by the borrower for the loan request.
    title : The loan title provided by the borrower
    dti : A ratio calculated using the borrower’s total monthly debt payments on the total debt obligations, excluding mortgage and the requested LoanTap loan, divided by the borrower’s self-reported monthly income.
    earliest_cr_line :The month the borrower's earliest reported credit line was opened
    open_acc : The number of open credit lines in the borrower's credit file.
    pub_rec : Number of derogatory public records
    revol_bal : Total credit revolving balance
    revol_util : Revolving line utilization rate, or the amount of credit the borrower is using relative to all available revolving credit.
    total_acc : The total number of credit lines currently in the borrower's credit file
    initial_list_status : The initial listing status of the loan. Possible values are – W, F
    application_type : Indicates whether the loan is an individual application or a joint application with two co-borrowers
    mort_acc : Number of mortgage accounts.
    pub_rec_bankruptcies : Number of public record bankruptcies
    Address: Address of the individual

Summary of Analysis on Loan Dataset

1. Data Preprocessing

    Ordinal Mapping: Numeric values were assigned to loan grades (A-G) to facilitate numerical analysis.
    Feature Engineering: Additional features were created as needed, ensuring the dataset was clean and ready for modeling.

2. Exploratory Data Analysis (EDA)

    Chi-Square Test: A Chi-Square test analyzed the relationship between loan grades and loan payment statuses, concluding that a significant relationship exists based on the p-value (p < 0.05).
    ANOVA Test: An ANOVA test assessed whether there are significant differences in annual income across different loan statuses, resulting in a significant F-statistic (2258.48) and p-value (0.0000).

3. Model Building

    Train-Test Split: The dataset was split into training (80%) and testing (20%) sets.
    Standardization: Features were standardized using StandardScaler to normalize data for model training.

4. Logistic Regression Model

    Model Initialization and Fitting: A Logistic Regression model was initialized with a specified regularization parameter (C=1/10) and fitted to the training data.
    Evaluation Metrics: Accuracy, recall, and precision were calculated for both training and testing datasets, yielding:
        Training Accuracy: 0.67
        Test Accuracy: 0.67
        Training Recall: 0.65
        Test Recall: 0.62
        Training Precision: 0.67
        Test Precision: 0.32

5. Hyperparameter Tuning

    Regularization Parameter Exploration: Accuracy was plotted against varying values of the regularization parameter (λ) to understand its impact on model performance.

6. ROC and Precision-Recall Curves

    ROC Curve: The ROC curve was plotted to visualize model performance across different threshold settings, highlighting the true positive rate against the false positive rate.
    Precision-Recall Curve: The precision-recall curve was plotted to analyze the trade-off between precision and recall for different thresholds.

7. Polynomial Regression

    Pipeline for Polynomial Features: Models with polynomial features (degrees 0 to 2) were constructed, noting that higher degrees increased training accuracy but affected generalization to the test set.
    Performance Observations:
        Degree 0: High test accuracy with no positive predictions.
        Degree 1: Reasonable performance but potential overfitting.
        Degree 2: Improved training accuracy with lower test recall.

8. Conclusion and Future Improvements

    Overall Findings: The analysis indicated a relationship between loan grades and payment statuses, with significant differences in annual income based on loan status. Logistic regression performed moderately well but showed signs of overfitting.
    Recommendations for Improvement:
        Utilizing advanced models like Random Forests or Gradient Boosting for improved accuracy and recall.
