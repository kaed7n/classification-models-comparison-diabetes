# Classification Models Comparison: *Diabetes Prediction*
## Log Reg, Random Forest, Gradient Boosting

### Purpose
To predict diabetes risk from recorded health metrics such as glucose, BMI, insulin, etc. and compare Logistic Regression vs tree-based models among other observations.

### Dataset
- Pima Indians Diabetes dataset (768 rows, 9 columns). Target: `Outcome` (1 = diabetes, 0 = no diabetes).
- Public, well-known educational dataset.

### Process
1. **Cleaning**
   - Replaced impossible zeros in table fields (`Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, `BMI`) using median imputation.
2. **Models**
   - Logistic Regression (with StandardScaler in pipeline)
   - Random Forest (300 trees)
   - Gradient Boosting
3. **Model Evaluation**
   - Metrics: Accuracy, Precision, Recall, F1, ROC-AUC
   - Visuals: Confusion Matrix per model, ROC Curves
   - Interpretability: Feature importance

### Results — Test Set
* Logistic Regression: Accuracy=0.760, Precision=0.698, Recall=0.556, F1Score=0.619, ROC_AUC=0.813
* Random Forest: Accuracy=0.747, Precision=0.653, Recall=0.593, F1Score=0.621, ROC_AUC=0.839
* Gradient Boosting: Accuracy=0.753, Precision=0.660, Recall=0.611, F1Score=0.635, ROC_AUC=0.829

**Best by ROC-AUC:** Random Forest

## Feature Importance (For Tree Models)
- Random Forest and Gradient Boosting (the tree-based models) provide **feature importance scores**.
- Generally, Glucose, BMI, and Age have most feature importance. Some differences are present as the gradient boosting model has a surprising importance score of approx. 0.4 for glucose compared to just 0.25 for the random forest model.
