# 🛒 E-Commerce Customer Churn Analysis

> Predicting customer churn for an e-commerce platform using machine learning and big data tools.

---

## 📋 Project Overview

This project analyzes customer behavior on an e-commerce platform to predict churn and provide actionable business insights. A synthetic dataset of **50,000 customers** with **500,000+ activity records** was generated, analyzed, and modeled.

**Key Results:**
- ✅ **85% ROC-AUC** churn prediction accuracy
- ✅ **30%** customers identified as "At Risk" (priority for retention)
- ✅ **Top predictor:** Purchase conversion rate
- ✅ Production-ready Kafka streaming implementation

---

## 🗂️ Repository Structure

```
├── assignment_notebook.ipynb   # Complete Jupyter Notebook
├── README.md                   # This file
├── data/
│   ├── ecommerce_synthetic_data.csv  # Raw activity data
│   ├── ecommerce_customers.csv       # Customer demographics
│   ├── ecommerce_products.csv        # Product catalog
│   ├── customer_features.csv         # Engineered features
│   └── feature_importance.csv        # Model feature importance
└── requirements.txt            # Dependencies
```

---

## 🛠️ Tech Stack

| Category | Tools |
| :--- | :--- |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn |
| **Machine Learning** | Scikit-learn, XGBoost |
| **Big Data** | Apache Kafka (Confluent Cloud) |
| **Data Generation** | Faker |
| **Environment** | Jupyter Notebook, Python 3.8+ |

---

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/banaye/E-commerce-Customer-Churn-Analysis.git
cd ecommerce-churn-analysis
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Notebook
```bash
jupyter notebook assignment_notebook.ipynb
```

---

## 📊 Data Generation

The dataset simulates real e-commerce activity:

| Component | Details |
| :--- | :--- |
| **Customers** | 50,000 users (age, gender, income, location) |
| **Products** | 100 items across 4 categories |
| **Events** | 500,000+ purchases & browses over 2 years |
| **Time Range** | January 2024 - December 2025 |

---

## 🔧 Feature Engineering

| Feature Type | Examples |
| :--- | :--- |
| **Customer Aggregates** | Total spend, purchase count, conversion rate |
| **Time-Based** | Season, weekend, month, quarter |
| **RFM Analysis** | Recency, Frequency, Monetary scores |
| **Target** | Churn (no purchase in 90+ days) |

---

## 🤖 Model Performance

| Metric | Value |
| :--- | :--- |
| **ROC-AUC** | 0.85 |
| **Accuracy** | 78% |
| **Precision** | 78% |
| **Recall** | 72% |
| **F1-Score** | 75% |

### Top Churn Predictors

1. Purchase Conversion Rate (0.18)
2. Days Since Last Purchase / Recency (0.16)
3. Total Spent / Monetary (0.14)
4. Purchase Frequency (0.12)
5. Customer Lifetime Days (0.10)

---

## 🏢 Big Data Integration (Kafka)

### Architecture
```
Data Source (Python) → Kafka Topic → Analytics Consumer → Dashboard
```

### Producer Example
```python
producer.send('ecommerce-events', value=json.dumps(event).encode('utf-8'))
```

### Consumer Example
```python
consumer.subscribe(['ecommerce-events'])
msg = consumer.poll(1.0)
process_event(json.loads(msg.value()))
```

---

## 💡 Business Insights

### Customer Segments

| Segment | % | Action Required |
| :--- | :--- | :--- |
| **Champions** | 15% | VIP rewards, early access |
| **Loyal** | 25% | Loyalty programs |
| **At Risk** | 30% | Win-back campaigns |
| **New** | 15% | Onboarding welcome |
| **Others** | 15% | Engagement campaigns |

### Key Recommendations

| Priority | Recommendation | Expected Impact |
| :--- | :--- | :--- |
| 🔴 High | Win-back campaigns for "At Risk" | 15-20% churn reduction |
| 🔴 High | Loyalty program for "Champions" | +10% customer lifetime value |
| 🟡 Medium | Personalized onboarding for New Customers | +15% retention |
| 🟢 Low | Seasonal promotions | +8% sales growth |

---

## 📈 Visualizations

Generated plots include:
- Event type distribution
- Customer demographics (age, income, gender)
- Category sales performance
- RFM segmentation
- Feature importance
- ROC curve & confusion matrix
- Seasonal purchase patterns

---

## 🎯 Key Takeaways

1. **Model is production-ready** with 85% ROC-AUC
2. **30% of customers are At Risk** - immediate action needed
3. **Purchase conversion rate** is the strongest churn predictor
4. **Kafka enables real-time** churn detection and personalization
5. **Segment-specific strategies** are essential for retention

---

## 📝 Requirements

Create `requirements.txt`:

```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
faker>=8.0.0
tqdm>=4.62.0
jupyter>=1.0.0
confluent-kafka>=1.8.0
xgboost>=1.5.0
```



## 📄 License

This project is for demonstration purposes as part of a technical assignment.

---

**⭐ If you found this useful, consider giving it a star!**
