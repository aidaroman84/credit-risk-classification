# credit-risk-classification

## Overview of the Analysis
The primary objective of this analysis was to develop a machine learning model capable of accurately predicting the risk associated with loans. Specifically, we aimed to distinguish between "healthy" loans, which are likely to be repaid, and "high-risk" loans, which have a significant chance of default. This differentiation is crucial for financial institutions to manage risk effectively, allocate resources efficiently, and ultimately, safeguard their financial stability.  

The dataset for this analysis comprised various financial metrics derived from loan applications and borrowers' financial histories. The key piece of information we needed to predict was the loan_status, which was categorized as 0 (healthy loan) or 1 (high-risk loan). This binary classification allowed us to focus on identifying patterns and characteristics that differentiate high-risk loans from healthy ones.  

The target variable, loan_status, indicates whether a loan is considered healthy (0) or high-risk (1), with value counts initially reflecting an imbalanced distribution favoring healthy loans. The dataset also included several features relevant to assessing loan risk, such as: loan_size, interest_rate, borrower_income, debt_to_income,num_of_accounts, num_of_accounts,
derogatory_marks, total_debt.

The analysis followed these key stages: Data preparation, Initial model training, Resampling and Model training with Resampled data.

One of the methods used was Logistic Regression. Its output can be interpreted as the probability of a loan being high-risk, providing a straightforward metric for decision-making. The RandomOverSampler was also utilized to address the class imbalance problem by oversampling the minority class in the training set.

## Results

#### Machine Learning Model 1:</ins> Logistic Regression with Original Data
 * Accuracy: The model demonstrated a high accuracy, suggesting it performs well on the overall dataset.
 * Precision: For healthy loans (0), precision was nearly perfect, indicating a very low false positive rate.
   For high-risk loans (1), precision was lower, reflecting some false positives but still at a good level.
 * Recall: For healthy loans, recall was exceptionally high, showing the model's effectiveness in identifying true negatives.
   For high-risk loans, recall was also impressive, indicating strong capability in detecting true positives among
   potential defaults.

 #### Machine Learning Model 2: Logistic Regression with Resampled Data
 * Accuracy: The accuracy remained high, indicating overall strong performance similar to Model 1, but this metric was 
   enhanced for balanced dataset considerations.
 * Precision:For healthy loans, precision stayed high, ensuring few healthy loans were incorrectly identified as high-risk.
   For high-risk loans, precision saw an improvement compared to Model 1, due to the balancing effect of oversampling, 
   reducing the proportion of false positives.
 * Recall: Recall for healthy loans was maintained at a high level, similar to Model 1.
   For high-risk loans, recall reached 100%, showing that the model could now identify all high-risk loans, a direct benefit 
   of addressing the class imbalance.

## Summary

#### Models performance
Model 1 (Original Data) demonstrated high accuracy, precision, and recall overall. It performed exceptionally well in identifying healthy loans (label 0) but was slightly less precise in identifying high-risk loans (label 1), though it still showed strong recall for these.
Model 2, trained on resampled data, outperforms Model 1 when considering the critical objective of accurately identifying high-risk loans without significantly compromising the ability to identify healthy loans. The improvement in recall for high-risk loans (from strong to perfect) and the increase in precision for these loans highlight the effectiveness of addressing class imbalance through resampling.  

The choice between these models largely depends on the specific objectives and costs associated with false positives (incorrectly labeling healthy loans as high-risk) versus false negatives (failing to identify a loan as high-risk). If missing a high-risk loan carries a high cost (e.g., financial loss from default), the improved recall for high-risk loans in Model 2 makes it the preferable choice. Conversely, if false positives carry significant consequences (e.g., lost opportunity from incorrectly denying a loan), the balance between precision and recall becomes crucial.

#### Recommendation
Given the analysis, Model 2 (Resampled Data) is recommended for use. This model ensures that nearly all high-risk loans are identified (100% recall), a critical factor in risk management and financial decision-making. The slight decrease in precision for high-risk loans compared to the precision for healthy loans is a reasonable trade-off, considering the importance of identifying potential defaults. Furthermore, this model still maintains high overall accuracy and precision for healthy loans, making it a robust solution for predicting loan risk.
