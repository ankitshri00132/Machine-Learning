# Loan Approval Prediction using Machine Learning

## 📌 Problem Statement
The goal of this project is to build a classification model that predicts whether a loan should be approved or not based on customer features such as age, income, credit score, experience, etc.  
Both **false positives** (approving risky customers) and **false negatives** (rejecting good customers) are costly for the business, so we focus on **F1-score** as the primary evaluation metric.

---

## 📊 Dataset
- Synthetic dataset generated for practice
- Features include:
  - age, income, education_years, experience_years
  - credit_score, hours_per_week
  - owns_house, owns_car
  - num_dependents, city_tier
- Target variable:
  - `loan_approved` (0 = No, 1 = Yes)

---

## 🛠️ Approach

1. Data loading and basic exploration (EDA)
2. Train-test split with stratification
3. Baseline model: Decision Tree
4. Improved models:
   - Bagging Classifier
   - Random Forest Classifier
5. Hyperparameter tuning:
   - GridSearchCV
   - RandomizedSearchCV
6. Model evaluation using:
   - Precision
   - Recall
   - F1-score
   - Confusion Matrix
   - ROC-AUC
7. Decision threshold tuning using predicted probabilities to maximize F1-score

---

## 🤖 Models Tried

- Decision Tree (with hyperparameter tuning)
- Bagging Classifier
- Random Forest (base model)
- Random Forest (RandomizedSearchCV tuned)
- Random Forest (GridSearchCV tuned)

---

## 📈 Evaluation Metrics

Since both Type I and Type II errors are costly, the **primary metric** used is:
- **F1-score**

Supporting metrics:
- Precision
- Recall
- Accuracy
- ROC-AUC

---

## 🏆 Final Model

**Model:** Random Forest (tuned with GridSearchCV / RandomizedSearchCV)  
**Decision Threshold:** ~0.35–0.37 (chosen to maximize F1-score)

### 📊 Final Test Set Performance

- Precision (class 1): ~0.71  
- Recall (class 1): ~0.81–0.82  
- F1-score (class 1): ~0.76  
- Accuracy: ~0.80  
- ROC-AUC: ~0.86  

**Confusion Matrix (at best threshold):**

[ [478 129] \
  [ 76 317] ]

---

## 🧠 Key Insights

- Default probability threshold (0.5) was not optimal for F1-score.
- Tuning the decision threshold significantly improved the balance between precision and recall.
- Random Forest outperformed a single Decision Tree and Bagging in terms of stability and overall performance.
- Cross-validation showed consistent performance, indicating good generalization.

## 📌 Conclusion

We compared multiple tree-based models and selected a Random Forest classifier with tuned hyperparameters and optimized decision threshold as the final model.
By optimizing for F1-score, we achieved a good balance between precision and recall, which is suitable for business scenarios where both false positives and false negatives are costly.