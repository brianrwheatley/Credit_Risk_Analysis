# Credit Risk Analysis

## Quick Overview
The goal of this analysis is to take in a variety of data about individuals to determine risk for new lines of credit.  More than 75 individual attributes were taken into account to determine the risk with new loans, including credit history, loan amount, annual income, and past deliquencies.

The models trained and evaulated the risks using libraries from imbalanced-learn and scikit-learn. The data was oversampled and undersampled with different algorithms, plus a combination with a SMOTEENN algorithm.

I did experience problems using the impalanced-learn Balanced Random Forest Classifier and Easy Ensemble AdaBoost Classifier. After comparing the code to the documentation, I determined that the problem is local and likely an install issue.

## Results
### Native Random Oversampling
- Accuracy Score: **64.6%**

| |pre|rec|spe|f1|geo|iba|sup|
|-|-|-|-|-|-|-|-|
|high_risk|0.01|0.63|0.66|0.02|0.65|0.42|90|
|low_risk|1.00|0.66|0.63|0.79|0.65|0.42|17115|
|avg/total|0.99|0.66|0.63|0.79|0.65|0.42|17205|

### SMOTE Oversampling
- Accuracy Score: **66.2%**

| |pre|rec|spe|f1|geo|iba|sup|
|-|-|-|-|-|-|-|-|
|high_risk|0.01|0.64|0.68|0.02|0.66|0.44|90|
|low_risk|1.00|0.68|0.64|0.81|0.66|0.44|17115|
|avg/total|0.99|0.68|0.64|0.80|0.66|0.44|17205|

### Undersampling
- Accuracy Score: **54.8%**

| |pre|rec|spe|f1|geo|iba|sup
|-|-|-|-|-|-|-|-|
|high_risk|0.01|0.62|0.48|0.01|0.54|0.30|90|
|low_risk|1.00|0.48|0.62|0.64|0.54|0.29|17115|
|avg/total|0.99|0.48|0.62|0.64|0.54|0.29|17205|

### SMOTEEN Combined
- Accuracy Score: **66.3%**

| |pre|rec|spe|f1|geo|iba|sup
|-|-|-|-|-|-|-|-|
|high_risk|0.01|0.72|0.60|0.02|0.66|0.44|90|
|low_risk|1.00|0.60|0.72|0.75|0.66|0.43|17115|
|avg/total|0.99|0.61|0.72|0.75|0.66|0.43|17205

## Summary
The standard oversample and undersample models struggled with this credit risk project. None of the models (Native & SMOTE Oversampling, Undersampling, SMOTE Combined) reached a 70% accuracy.  This is likely due to an imbalance of actual risk (high vs low).

One overaching factor is human behavior. No matter the modeling, human behavior is still unpredictable.

While no model will ever reach 100% accuracy, knowing what I know about the BRFC and EEAC models, I would expect that both would improve upon all the other standard models, likely peaking somewhere near 85-90% accuracy, making them the peferred choice in determining credit risk using the data provided.
