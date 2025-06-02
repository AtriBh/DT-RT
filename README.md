# DT-RT

# Heart Disease Prediction using Decision Tree and Random Forest

This project demonstrates training, evaluation, and optimization of **Decision Tree** and **Random Forest** classifiers on a heart disease dataset using scikit-learn.

---

## 📊 Dataset
The dataset contains medical features like age, blood pressure, cholesterol, etc., with a binary target indicating the presence (`1`) or absence (`0`) of heart disease.

---

## 🎯 Objective
To build models that can accurately predict heart disease and minimize **false negatives** — i.e., not missing actual cases of heart disease.

---

## 🧪 Evaluation Metric: Recall
**Why recall?**

In medical diagnoses, missing a true positive (i.e., predicting no disease when disease is present) can be **life-threatening**. Hence, **recall** is prioritized over accuracy or precision.

---

## 🌲 Decision Tree Classifier

### Steps:
1. Trained a base `DecisionTreeClassifier`.
2. Evaluated using **cross-validation (5-fold)** with `recall` as the scoring metric.
3. Used **GridSearchCV** to find the best value for `max_depth`.
4. Applied **Cost Complexity Pruning (`ccp_alpha`)** to reduce overfitting.
5. Visualized pruning effect on train/test performance.
6. Extracted feature importances for interpretability.

### Key Techniques:
- **Pre-pruning**: Using `max_depth`, `min_samples_leaf`, etc.
- **Post-pruning**: Using `ccp_alpha` (cost complexity pruning path).
- **GridSearchCV**: To find optimal hyperparameters based on recall.

---

## 🌳 Random Forest Classifier

### Steps:
1. Trained a `RandomForestClassifier` with default and tuned settings.
2. Used **GridSearchCV** to tune `n_estimators`, `max_depth`, etc., based on **recall**.
3. Evaluated using cross-validation and test set recall.
4. Extracted and visualized **feature importances**.

### Note:
- No pruning was needed; Random Forest inherently prevents overfitting using **bagging** and **feature randomness**.



## ✅ Conclusion
- **Decision Trees** are simple and interpretable, but prone to overfitting without pruning.
- **Random Forests** are more robust out of the box and often give better generalization.
- **Recall** is crucial when false negatives are costly — as in heart disease prediction.

---

## 🧠 Future Work
- Try XGBoost or LightGBM.
- Add ROC/AUC evaluation.
- Build a simple UI for predictions.
