# 📊 Ancillary Revenue Optimization System for Hotels

Hotels often miss opportunities to upsell room upgrades and services due to lack of real-time customer insights.  
This project builds a predictive system to identify guests most likely to purchase upgrades.



<img width="600" height="264" alt="propensity-chart" src="https://github.com/user-attachments/assets/5e1f1107-1c3c-4d90-99e8-baf964d5c83c" />

---

## 🔍 Problem Statement

Hotels lack a structured way to identify customers who are likely to upgrade their bookings.  
This leads to missed revenue opportunities and inefficient targeting.

**Goal:**  
Predict upgrade propensity to enable targeted offers and maximize ancillary revenue.

---

## ⚙️ Approach

- Engineered a synthetic **upgrade target variable** using:
  - Lead time
  - ADR (Average Daily Rate)
  - Stay duration
  - Loyalty indicators
  - Customer engagement signals  

- Introduced controlled randomness to simulate **real-world decision variability**  
- Avoided deterministic modeling to improve generalization  

---

## 🧹 Data Processing

- Handled missing values using domain-informed strategies  
- Created behavioral features:
  - `is_corporate`
  - `is_direct_booking`
- Extracted temporal features from reservation dates  
- Applied one-hot encoding for categorical variables  
- Removed high-cardinality and leakage-prone features  

---

## 🤖 Models Evaluated

- Logistic Regression  
- Random Forest  
- Gradient Boosting  
- XGBoost  

---

## 🎯 Threshold Optimization

Instead of relying on default predictions, probability thresholds were tuned to align with business goals.

**Strategy:**
- Prioritized **Recall over Precision**
- Goal: Capture more upgrade opportunities

**Thresholds tested:**
- 0.2  
- 0.25  
- 0.3  

---

## 📊 Model Performance Comparison

| Model                | Threshold | Recall | Precision |
|---------------------|----------|--------|-----------|
| Logistic Regression | 0.2      | 0.39   | 0.35      |
| Gradient Boosting   | 0.2      | 0.37   | 0.35      |
| Random Forest       | 0.2      | 0.38   | 0.27      |
| XGBoost             | 0.2      | 0.36   | 0.32      |

---

## 🧠 Key Insights

- Logistic Regression performed best after threshold tuning  
- Simpler models can outperform complex ones when aligned with business objectives  
- Key drivers of upgrade behavior:
  - Early booking (lead time)
  - Higher spending (ADR)
  - Repeat customers (loyalty)

---

## 🏨 Business Perspective

### Why Recall > Precision?

Sending an upgrade offer:
- 📩 Cost: Very low (email, app notification)
- 💰 Upside: Additional revenue

**Trade-off:**
- High Recall → Capture more upgrade opportunities  
- Lower Precision → Some unnecessary offers  

👉 It is better to **target more customers** than miss potential upgrades

---

## 💡 Business Impact

- Improved identification of high-propensity customers  
- Enables targeted marketing via:
  - Email campaigns  
  - App notifications  
  - Front desk recommendations  

---

## 🚀 Future Improvements

- Deploy model using a simple web application (Streamlit)  
- Integrate with real-time booking systems  
- Implement model monitoring for data drift  

---

## 🧰 Tech Stack

- Python  
- Pandas, NumPy  
- Scikit-learn  
- XGBoost  

---

## 📌 Conclusion

This project demonstrates how machine learning can be aligned with business goals to drive revenue.  
By prioritizing recall and focusing on customer behavior, the system provides actionable insights for hospitality businesses.
