Software and version: **jupyter-notebook 6.0.3**
OS: **Windows 10**

## Algorithms and parameters used
**Logistic Regression** – search was done for penalty: ["l1", "l2"], C: [0.01, 0.05, 0.1, 0.5, 1, 5], fit_intercept: [False, True] and solver set as "liblinear".
**Linear SVC** – search was done for C: [0.01, 0.05, 0.1, 0.5, 1, 5], fit_intercept: [False, True]. We also set the penalty to "l2" and max_iter to 1e6.
**Random Forest Classifier** – search was done for estimator values: [50, 100], criterion: ["gini", "entropy"] and bootstrap: [False, True].

## Preprocessing
1. ID column is dropped in the beginning because it is not predictive.
2. There were a total of 211 missing values which we imputed using mode (most frequent value) of the column.
3. Duplicate rows were removed from train dataset.
4. All columns are converted to numeric using cat.codes function.
5. In order to do more experiments with the algorithms, the data is also standardized using StandardScaler.

## Best model selection
Linear SVC classifier had the highest score using the 10-fold cross-validation method where's Logistic Regression scored the same using holdout method. As the best model we selected the model that was fit with standardized data to the Linear SVC classifier with paramenters: *C=0.1, fit_intercept=True, penalty=l2 and max_iter=1e6.*