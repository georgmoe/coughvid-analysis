## Questions

How to decide for a represantative audio sample?
- randomly select for each class few examples


is there a max time?
- max 2h runtime


How should the justification for certain feature extractions look like? Refer to a paper?
- refer to another source
- e.g. in another study this has proven successful (with link)
- but we can also write that we try something
- what is logical for covid or healthy





## preprocessing
for few missing data: drop row or impute median
for lots of missing data: consider dropping the column

- calculate correlation between features and output variable to reduce the dimensionality
    - one hot encoding would be necessary

- data normalization

## Analysis (1/2) Supervised
Model
- one simple: it should be explainable like changing a feature should result in Y (e.g. linear regression, logistic, decision tree)
- and one complex technique

## Evaluation
- use different metrics (accuracy, f1, precision, recall)
- hyperparameter tuning (if necessary)
- what are the most important features for both of the models?
    - she expects a diagram like on praktikum slide 50


- mean misclassification error (MMCE)
- Measure of concordence: (True positive, True negative)
- Measures of Discordence (False positives, False negatives)
    --> plot a confusion matrix
- accuracy, recall (sensitivity), specificity, f1 score
- ROC curve


## model success
- if it doesnt work, explain why
- performance is not top 1 priority.
- Explanation why it didnt work is important
    - e.g. features could not differentiate between the classes
- short sentences

## Analysis (2/2) Unsupervised
- compare results of unsupervised model with the target
- k-means
- evaluate the clustering fitness 
- use autoencoders to extract features from the data (use the same models as before)