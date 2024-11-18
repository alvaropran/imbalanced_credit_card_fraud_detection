The credit card data was extracted from Kaggle and tested on Google Colab, the code is attached in the file. 

The goal of this project was to explore different machine learning models and how they differentiate from one another, focusing on how each of their pros and cons.

Different machine learning models and their accuracy measurements for different parameters:

Sorted on descending f-1 score. 

Classifying ‘Fraud’ since the imbalanced data towards getting ‘Not Fraud’ is all positive
___
### Key Insights and Business Impact:

1. **Imbalanced Dataset**:
   - **Challenge**: Skewed towards "Not Fraud," leading to potential financial losses from undetected fraud.
   - **Best Performers**: Linear SVM (F1: 0.71) and Shallow NN (F1: 0.70).
   - **Impact**: High recall is crucial to minimize missed fraud cases, even if precision slightly drops.

2. **Balanced Dataset**:
   - **Results**: Models improve significantly, with Shallow NN and Logistic Regression achieving the highest F1-scores (0.94).
   - **Impact**: Balancing ensures fair detection of fraud and reduces bias, improving trust and reliability.

3. **Model Use Cases**:
   - **Fraud Detection**: Prioritize Shallow NN or Logistic Regression for high fraud recall while maintaining strong precision.
   - **Operational Efficiency**: Linear SVM offers simplicity with competitive accuracy.
   - **Cost-Sensitive Scenarios**: Gradient Boosting balances precision for "Not Fraud" but sacrifices recall.

4. **Real-World Applications**:
   - **Financial Systems**: Effective fraud detection reduces financial loss.
   - **Healthcare**: High recall ensures rare but critical cases (e.g., diseases) aren't missed.
   - **Customer Experience**: Balanced models reduce false positives, maintaining user trust.

5. **Recommendations**:
   - Balance datasets to improve fairness.
   - Prioritize F1-scores over accuracy for imbalanced problems.
   - Use interpretable models (e.g., Logistic Regression) for high-stakes decisions.

___
## Imbalanced Dataset
| Machine learning model on val | precision | recall | f-1 score |
| ------------- | ------------- | ------------- | ------------- |
| Linear svm  | 0.65 | 0.78  | 0.71  |
| Shallow_nn (Keras, Sequential)  | 0.64 | 0.78 | 0.70  |
| GradientBoostingClassifier  | 0.67  | 0.67  | 0.67  |
| LogisticRegression  | 0.73  | 0.53  | 0.61 |
| Random Forest | 0.81  | 0.47  | 0.60  |

Next step: change the data set to match the number of classes for Not Fraud and Fraud

## Balanced Dataset

| LogisticReression | precision | recall | f-1 score | support |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Not Fraud | 0.96 | 0.93  | 0.94  | 72  |
| Fraud | 0.93 | 0.96 | 0.94  | 70 |

| Shallow_nn | precision | recall | f-1 score | support |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Not Fraud | 0.90 | 1.00  | 0.95  | 72  |
| Fraud | 1.00 | 0.89 | 0.94  | 70 |

| Linear svm | precision | recall | f-1 score | support |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Not Fraud | 0.89 | 1.00  | 0.94  | 72  |
| Fraud | 1.00 | 0.87 | 0.93  | 70 |

| Random Forest | precision | recall | f-1 score | support |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Not Fraud | 0.69 | 1.00  | 0.82  | 72  |
| Fraud | 1.00 | 0.54 | 0.70  | 70 |

| GradientBoostingClassifier | precision | recall | f-1 score | support |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Not Fraud | 0.81 | 1.00  | 0.89  | 72  |
| Fraud | 1.00 | 0.76 | 0.86  | 70 |

After reviewing all of the machine learning models used above, I decided to go with the neutral_net model as it had
some of the highest scores in precision, recall, and f-1. 

Note that any of the above models could have been picked according to the business case. 

## TESTED NEURAL NET
| Shallow_nn | precision | recall | f-1 score | support |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Not Fraud | 0.88 | 1.00  | 0.94  | 73  |
| Fraud | 1.00 | 0.86 | 0.92  | 69 |



