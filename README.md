# ⭑✮💳⊹ Financial Blind-Spot Detection

### Finding hidden financial risks inside 116K+ bank transactions using data analytics and machine learning.


Ever looked at a bank statement and wondered if there are patterns you're completely missing?

A single transaction may look normal. But over time, rising spending, unusual cash withdrawals, increasing charges, missing income, or spending more than you receive can signal a problem.

This project finds those hidden patterns - called **financial blind spots**.

I cleaned and analyzed bank transactions, converted messy transaction descriptions into useful categories, created monthly behaviour profiles, detected unusual months, identified 10 financial blind spots, and built a machine learning model to predict whether a blind spot could appear in the **next month**.

SHAP was also used to explain *why* the model made each prediction.

---

## ✦ Dataset

Public **Bank Transactions Dataset from Kaggle**

✦ 116,000+ transaction records  
✦ Single corporate bank account  
✦ Multiple years of transaction history  
✦ Includes dates, transaction descriptions, withdrawals, deposits, value dates, cheque details, and balances  
✦ **116,162 transactions after cleaning**

> 📌 **Dataset Note:** The dataset was named `bank.xlsx` when the notebook was originally developed. The same file is renamed `dataset.xlsx` in this repository. The data itself is unchanged.

---

## ✦ What This Project Does

🧹 **Data Cleaning**  
Cleaned missing values, duplicates, dates, account numbers, transaction amounts, unnecessary columns, and messy transaction descriptions.

🏷️ **Transaction Categorization**  
Used keywords from transaction descriptions to identify merchants and classify transactions into salary income, interest income, cash withdrawals, bank charges, loan payments, UPI payments, tax payments, other credit, and other debit.

📅 **Behavioural Feature Engineering**  
Converted individual transactions into monthly behaviour features such as spending, transaction count, debit, credit, savings, cash usage, charges, merchant diversity, transaction variation, and debit-to-credit ratio.

👥 **Behaviour Segmentation**  
Used **K-Means Clustering** to identify four behaviour groups:
- High-volume heavy spenders
- Medium-stable spenders
- Low-activity, high-value spenders
- Cash-heavy behaviour

🚨 **Anomaly Detection**  
Used **Isolation Forest** to detect months with unusually different financial behaviour.

👀 **Blind-Spot Detection**  
Created 10 financial warning signals from the transaction behaviour.

🤖 **Risk Prediction**  
Used a **Random Forest Classifier** to predict whether the next month could contain a financial blind spot.

🔍 **Explainable AI**  
Used **SHAP** to understand which financial behaviours influenced the model's predictions.

🧪 **Stress Testing**  
Artificially created extreme financial situations to check whether the model could recognize unusual risk patterns.

---

## 👀 The 10 Financial Blind Spots

| Blind Spot | Simple Meaning |
|---|---|
| Low Transaction Behaviour | Activity becomes unusually low |
| No Spending Pattern | Spending becomes irregular |
| Cash Spike | Cash withdrawals suddenly increase |
| Merchant Overdependence | Too much spending goes to one merchant |
| Lifestyle Inflation | Spending keeps increasing |
| Charge Spike | Bank charges suddenly increase |
| Salary Missing | Expected income is missing |
| Salary Drop | Income becomes significantly lower |
| Negative Savings | More money goes out than comes in |
| Subscription Drift | Subscription spending suddenly increases |

---

## ✦ Project Workflow

**Raw Transactions → Data Cleaning → Text Processing → Transaction Categories → Monthly Behaviour Features → K-Means Clustering → Anomaly Detection → Blind-Spot Detection → Random Forest Prediction → SHAP Explanation → Stress Testing**

---

## 📊 Key Results

✦ **Merchant Overdependence** was the most common blind spot  
✦ **Negative Savings** appeared frequently  
✦ Lifestyle Inflation and Charge Spikes were important risk signals  
✦ Salary behaviour was mostly stable, with some irregular periods  
✦ Cash behaviour was mostly stable, with a few unusual spikes  

### 🤖 Prediction Results

| Metric | Result |
|---|---:|
| Accuracy | **68%** |
| Precision for Risk | **73%** |
| Recall for Risk | **76%** |
| F1 Score for Risk | **74%** |

The model correctly identified **76% of upcoming risky months**.

SHAP showed that important risk factors included previous savings, anomaly probability, transaction count, debit and credit amounts, bank charges, spending variation, lifestyle inflation, and debit-to-credit ratio.

---

## 🧪 Synthetic Stress Test

The model was also tested using artificial financial stress situations:

💸 Salary Crash  
🏦 Charges Explosion  
📈 Lifestyle Overheat  
💳 Subscription Shock  
💵 Cash Addiction  
📱 UPI Mania  
🌪️ Chaotic Transaction Month  

The model detected risk in **all but one** of the synthetic stress scenarios.

---

## 🛠️ Built With

**Python • Pandas • NumPy • Scikit-learn • SHAP • Matplotlib • Seaborn • Google Colab • Excel**

### Machine Learning Used

**K-Means** → Behaviour segmentation  
**Isolation Forest** → Anomaly detection  
**Random Forest** → Next-month risk prediction  
**SHAP** → Prediction explanation

---



### ▶️ Running the Notebook

The project was originally developed in **Google Colab**.

The notebook expects the dataset as `bank.xlsx`, while the repository contains the same file renamed as `dataset.xlsx`.

To rerun the original notebook:

**Rename `dataset.xlsx` → `bank.xlsx` and upload it to the location expected in the notebook.**

---

## ✦ Why This Project Matters

Bank statements show **what happened**.

This project goes one step further and looks for **patterns hidden across thousands of transactions**.

It demonstrates how raw financial data can be cleaned, transformed, analyzed, and used with machine learning to detect unusual behaviour and provide understandable early-risk signals.

> ⚠️ This is an academic data analytics project using one corporate account. The detected blind spots are analytical warning signals, not confirmed fraud or professional financial advice.

---

## ⊹ Author

**Manogna**

⭑✮ If you found this project interesting or have suggestions, feel free to connect. Always happy to learn and collaborate ₊˚⊹
