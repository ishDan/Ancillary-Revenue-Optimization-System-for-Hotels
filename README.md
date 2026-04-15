# Ancillary-Revenue-Optimization-System-for-Hotels
Hotels often miss opportunities to upsell room upgrades and services due to lack of real-time customer insights. The goal of this project is to build a predictive system that identifies guests most likely to purchase upgrades.

🔍 Problem Statement

Hotels often miss opportunities to upsell room upgrades and services due to lack of real-time customer insights. The goal of this project is to build a predictive system that identifies guests most likely to purchase upgrades.

⚙️ Approach
Engineered a synthetic upgrade target variable using behavioral and transactional features such as:
Lead time
ADR (average daily rate)
Stay duration
Loyalty indicators
Customer engagement signals
Introduced controlled randomness to simulate real-world uncertainty and avoid deterministic modeling.
🧹 Data Processing
Handled missing values using domain-informed strategies
Created behavioral features:
is_corporate
is_direct_booking
Extracted temporal features from reservation dates
Applied one-hot encoding for categorical variables
Removed high-cardinality and leakage-prone features
🤖 Models Evaluated
Logistic Regression
Random Forest
Gradient Boosting
XGBoost
🎯 Threshold Optimization

Instead of relying on default predictions, probability thresholds were tuned to align with business goals:

Focused on maximizing recall (capturing upgrade opportunities)
Evaluated models across thresholds: 0.2, 0.25, 0.3
📊 Model Comparison
Model	Threshold	Recall	Precision
Logistic Regression	0.2	0.39	0.35
Gradient Boosting	0.2	0.37	0.35
Random Forest	0.2	0.38	0.27
XGBoost	0.2	0.36	0.32
✅ Key Insight
Logistic Regression performed best when tuned properly
Simpler models can outperform complex ones when aligned with business objectives
Early booking behavior, pricing (ADR), and customer loyalty were key drivers of upgrades
💡 Business Impact
Increased ability to identify high-propensity customers
Enables targeted offers via:
Email campaigns
App notifications
Front desk recommendations
