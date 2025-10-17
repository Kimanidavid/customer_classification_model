# Customer Classification Using Machine Learning

## 🧠 Project Overview
This project focuses on building predictive models to classify customers based on their **shopping behavior and purchase frequency**. Using real-world retail data from **Kenyan shopping trends**, the aim is to help businesses like Amazon or local e-commerce platforms understand and segment their customers for **personalized marketing, targeted promotions, and improved retention**.

The models used — **Linear Discriminant Analysis (LDA)** and **Random Forest (RF)** — were compared to determine which provides higher classification accuracy and generalization capability.

---

## 📊 Dataset Description
The dataset used is `shopping_trends_kenya_data.csv`, containing **3,900 customer records** with 18 variables. Each record represents a customer’s shopping behavior including demographics, purchase history, and product preferences.

**Key Features:**
- `Age` – Numeric value representing the customer’s age  
- `Gender` – Male/Female  
- `Item Purchased` – Product bought  
- `Category` – Clothing, Footwear, Accessories, etc.  
- `Purchase Amount (USD)` / `Purchase Amount (KES)` – Monetary value of the purchase  
- `Location` – City or region within Kenya  
- `Subscription Status`, `Discount Applied`, `Promo Code Used` – Boolean indicators of engagement  
- `Previous Purchases` – Numeric indicator of loyalty  
- `Frequency of Purchases` – Target variable (`Weekly`, `Quarterly`, `Annually`, etc.)

---

## ⚙️ Methodology

### 1. **Data Preprocessing**
- Removed irrelevant columns like `Customer ID` to avoid data leakage.
- Encoded categorical variables into numeric format using **Label Encoding**.
- Split data into **training (80%)** and **testing (20%)** sets.
- Normalized numeric features for consistent model behavior.

---

### 2. **Model 1: Linear Discriminant Analysis (LDA)**
LDA was selected as a **baseline classifier** because it assumes features follow a Gaussian distribution and seeks to find linear combinations that best separate classes.

**Why LDA:**
- Simple, interpretable model
- Works well when class distributions are fairly separable
- Establishes a baseline for comparison

**Performance Summary:**
| Metric | Score |
|:-------|:------|
| Accuracy | ~0.74 |
| Precision | ~0.70 |
| Recall | ~0.72 |
| F1-Score | ~0.71 |

**Interpretation:**  
LDA performed moderately well, capturing the general trends in customer frequency but struggled with overlapping purchase behavior among classes. It’s efficient for quick insights but limited for complex relationships.

**Screenshot Placeholder:**  
`![LDA Confusion Matrix](images/lda_confusion_matrix.png)`

---

### 3. **Model 2: Random Forest Classifier**
Random Forest (RF) is an ensemble learning algorithm that builds multiple decision trees and averages their results for improved performance.

**Why RF:**
- Handles non-linear relationships effectively  
- Robust to noise and overfitting  
- Automatically estimates feature importance

**Performance Summary:**
| Metric | Score |
|:-------|:------|
| Accuracy | ~0.82 |
| Precision | ~0.85 |
| Recall | ~0.78 |
| F1-Score | ~0.81 |

**Interpretation:**  
The Random Forest outperformed LDA across all metrics, demonstrating strong generalization. It effectively captured hidden patterns like purchase frequency variations tied to **season, gender, and subscription status**.

**Feature Importance Example:**
Top influencing features included:
- `Previous Purchases`
- `Review Rating`
- `Season`
- `Category`
- `Subscription Status`

**Screenshot Placeholders:**  
- `![Random Forest Confusion Matrix](images/rf_confusion_matrix.png)`  
- `![Feature Importance Plot](images/rf_feature_importance.png)`

---

## 📈 Results Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|:------|:----------|:----------|:--------|:----------|
| LDA | 0.74 | 0.70 | 0.72 | 0.71 |
| Random Forest | 0.82 | 0.85 | 0.78 | 0.81 |

**Conclusion:**  
Random Forest provided the most reliable classification results, suggesting that customer purchase frequency is influenced by complex interactions between demographic and behavioral factors.

---

## 💡 Business Insights
- **Frequent buyers** tend to have higher review ratings and consistent subscription engagement.  
- **Seasonal variations** strongly affect purchase patterns — “Summer” and “Spring” buyers are more active.  
- **Discounts and promos** significantly boost short-term purchase frequency.  
- Using the Random Forest model, marketing teams can build **predictive customer segments** and **launch retention campaigns** with higher precision.

---

## 🖼️ Visualization Gallery
Insert your model output screenshots here:
- LDA Confusion Matrix → `images/lda_confusion_matrix.png`
- RF Confusion Matrix → `images/rf_confusion_matrix.png`
- RF Feature Importance → `images/rf_feature_importance.png`
- Accuracy Comparison → `images/model_accuracy_comparison.png`

---

## 🚀 Future Work
- Extend analysis to include deep learning models (LSTM, CNN) for time-based behavior prediction.  
- Integrate customer segmentation clustering (K-Means, DBSCAN) for finer granularity.  
- Deploy the best-performing model as an API for real-time classification in e-commerce systems.

---

## 🧩 Author
Developed by **David**, a Data Analyst and Software Developer passionate about using machine learning to drive business intelligence and customer engagement.

---
