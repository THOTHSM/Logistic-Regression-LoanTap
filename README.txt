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
