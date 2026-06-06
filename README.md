# Car-Price-Prediction-ML
Machine  Learning car price analysis
# 🚗 Car Price Prediction & Market Analysis

An end-to-end Machine Learning project to analyze competitive pricing dynamics in the United States automotive market. This project evaluates multiple regression algorithms to provide an optimized simulation tool for management to understand price variations, manipulate vehicle designs, and target specific price brackets effectively.

---

## 📈 Key Project Results
* **Best Performing Model:** Hyperparameter-tuned Random Forest Regressor
* **Validation Accuracy ($R^2$ Score):** **0.9573** (Explains 95.73% of price variances on unseen test data)
* **Top Pricing Drivers:** Engine Size (`enginesize`), Vehicle Weight (`curbweight`), and Performance (`horsepower`).

---

## 🏗️ Project Architecture & Pipeline
The code implements a robust scikit-learn workflow to prevent data leakage and handle mixed data types:

1. **Preprocessing Pipeline:**
   * **Numerical Features:** Processed with a median imputer and normalized using `StandardScaler`.
   * **Categorical Features:** Handled via a most-frequent imputer and encoded cleanly using `OneHotEncoder(drop='first')`.
2. **Model Evaluation:** Five regression models were tested side-by-side: Linear Regression, Decision Tree, Random Forest, Gradient Boosting, and Support Vector Regression (SVR).
3. **Hyperparameter Tuning:** Utilized 3-Fold Cross-Validation via `GridSearchCV` to optimize the Random Forest model constraints (`max_depth: 10`, `min_samples_split: 5`, `n_estimators: 200`).

---

## 📊 Evaluation Metrics Matrix

| Model | Validation R-squared ($R^2$) | Operational Performance |
| :--- | :---: | :--- |
| **Random Forest (Tuned)** | **0.9573** | **Best Generalization.** Minimal variance and highly robust against outliers. |
| **Baseline Random Forest** | 0.9588 | Highly accurate but structurally more complex than the tuned model. |
| **Gradient Boosting** | ~0.9200 | Strong competitive baseline with low bias. |
| **Linear Regression** | ~0.8300 | Struggles to capture complex, non-linear feature interactions. |
| **Support Vector Regressor** | < 0.0000 | Poor baseline fit without deep, customized kernel tuning. |

---

## 💡 Strategic Business Insights for Management

* **Product Design Manipulation:** Because **Engine Size** and **Curb Weight** hold the highest feature importance weights, manufacturing teams can directly control price points by scaling core vehicle dimensions up or down.
* **Performance Tiering:** Management can easily differentiate entry-level, mid-tier, and premium vehicle variants by modifying **Horsepower** limits while utilizing a shared structural chassis.
* **Risk Reduction:** This model serves as an analytical gateway into the US market, allowing the company to simulate competitor pricing profiles and accurately estimate baseline vehicle values before launching a production line.
