# Bank Marketing: Term Deposit Subscription Prediction

## 📌 Project Objective
The goal of this project is to predict whether a customer will subscribe to a bank term deposit based on marketing campaign data. By leveraging Machine Learning, we aim to identify the key factors that influence a customer's decision, allowing the bank to optimize its outreach strategy and increase conversion rates.

---

## 📊 Project Summary
This project follows a complete Data Science pipeline: from data preprocessing and feature engineering to model evaluation and deep interpretability using SHAP values.

### 1. Data Analysis and Preprocessing
The dataset contains **11,162 samples** with a mix of categorical and numerical features.
* **Feature Engineering:** Categorical features (10 total) were transformed using `OneHotEncoder` via a `ColumnTransformer`. 
* **Dimension Expansion:** The dataset was expanded to **53 features** after encoding to capture the nuances of categorical variables.
* **Data Splitting:** The data was partitioned into:
    * **Training Set:** 8,929 samples
    * **Testing Set:** 2,233 samples

### 2. Model Performance Comparison
We compared two classification models: **Logistic Regression** and **Random Forest**. The Random Forest model consistently outperformed Logistic Regression across all evaluation metrics.

| Metric | Logistic Regression | Random Forest |
| :--- | :--- | :--- |
| **Accuracy** | 0.82 | **0.85** |
| **Precision** | 0.80 | **0.82** |
| **Recall** | 0.82 | **0.85** |
| **F1-Score** | 0.81 | **0.84** |

---

## 🔍 Model Interpretability (SHAP Analysis)
To understand **why** the model makes certain predictions, we used **SHAP (SHapley Additive exPlanations)**. This allows us to see the contribution of each feature to the final result.

### 📈 Key Drivers of Success (Positive Impact)
* **`duration`**: The most critical feature. The longer the conversation during the last contact, the higher the likelihood of subscription.
* **`poutcome_success`**: If a previous campaign was successful for a customer, they are highly likely to subscribe again.
* **`balance`**: Customers with higher account balances show a greater tendency to subscribe.
* **Demographics & Timing**: Being **retired** or being contacted in **March** or **October** significantly increased the probability of subscription.

### 📉 Negative Impact Factors
* **`month_may`**: Campaigns in May showed a noticeably lower success rate.
* **Financial Liability**: Customers with **housing loans** or **personal loans** were less likely to subscribe.
* **Unknown Data**: Lack of information regarding contact methods or previous outcomes generally led to lower prediction scores.

---

## 💡 Business Insights & Recommendations
* **Focus on High-Value Leads**: Prioritize customers with higher balances and those who have responded positively in the past.
* **Optimize Timing**: Shift campaign efforts toward March and October, while investigating why May performs poorly.
* **Quality over Quantity**: Since `duration` is a top predictor, staff should be trained to engage customers in more meaningful, longer conversations rather than making quick, high-volume calls.
* **Loan-Based Segmentation**: Develop specialized products or different messaging for customers who already have housing or personal loans.

---

## 🛠️ Tech Stack
* **Language:** Python
* **Libraries:** * `Pandas`, `NumPy` (Data Manipulation)
    * `Scikit-Learn` (Machine Learning & Preprocessing)
    * `SHAP` (Model Interpretability)
    * `Matplotlib`, `Seaborn` (Visualization)

---

## 🚀 How to Use
1.  **Clone the Repository:**
    ```bash
    git clone [(https://github.com/taimoordata607-arch/Task-1-Term-Deposit-Subscription-Prediction-Bank-Marketing-/new/main)]
    ```
2.  **Install Requirements:**
    ```bash
    pip install pandas numpy scikit-learn shap matplotlib seaborn
    ```
3.  **Run the Analysis:**
    Execute the Python script to train the models and generate the SHAP plots.
    ```bash
    python task_1_term_deposit_subscription_prediction.py
    ```
