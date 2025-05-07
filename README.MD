# 🔍 Predicting Client Churn Using Random Forest

## 🧠 Business Context

### Situation
PowerCo is a power supply company serving thousands of small and medium-sized enterprises (SMEs). Due to increasing competition in the market, clients are now more likely to switch providers. Initial analysis reveals a **churn rate of 9.7%**.

### Problem
To retain clients, PowerCo is considering a discount program. However, offering this to all clients would be costly and inefficient. The company needs to **identify high-value clients at risk of churning** to target them more effectively.

### Proposed Solution
A **Random Forest classification model** is developed to **predict which clients are likely to churn within 3 months**, enabling targeted retention efforts.

---

## 📊 Methodology

### Data
The project uses two datasets:
- `Client_data.csv`: Contains client attributes (e.g., contract info, consumption, and demographics).
- `Price_data.csv`: Contains pricing data per client across different periods.

### Exploratory Data Analysis (EDA)
- 100% stacked bar charts are used to visualize churn across sales channels and other dimensions.
- Confirmed overall churn rate: **~9.7%**.

### Data Cleaning
- Converted date columns from object to `datetime64`.

### Feature Engineering
- Applied **log transformation** to skewed numeric variables.
- Converted **categorical variables** using one-hot encoding.
- Transformed **boolean fields** to 0/1.
- Removed **highly correlated features** to reduce multicollinearity.

### Modeling
- Built and tuned **Random Forest classifiers** using:
  - Hyperparameter tuning
  - Class weighting
  - SMOTE for oversampling minority (churn) class

Despite tuning, the model suffers from **low recall** (~7–11%) for churners.

---

## 📈 Results & Insights

- The model shows **decent precision** but **poor recall**.
- Indicates that existing features **do not capture the underlying drivers** of churn.
- Hypothesis: The dataset is **missing important behavioral or qualitative variables** relevant to churn.

---

## 💡 Recommendations

### 1. Data Enrichment
Enhance the dataset with additional variables:
- Client complaints and feedback
- Interaction logs (e.g., calls, emails)
- Survey responses
- Competitor offers
- Macroeconomic trends
- Sales representative engagement metrics

### 2. Business Use of Current Model
If the **cost of retention** is lower than the **cost of losing a client**, consider using the model with **threshold adjustments**:
- It can still **identify ~50% of churners**.
- Predicted churners should receive special attention (discounts, support, follow-up).
- Predicted retained clients can be **manually reviewed**, although this is time-consuming and may lack consistency.

### 3. Strategic Insight
If the cost-benefit analysis is unfavorable, it's best to pause the model deployment and instead:
- Conduct **client interviews**
- Consult **domain experts**
- Focus on **collecting better data**

---

## 📌 Suggestions for Improvement

### 🔧 Project Enhancements
- Try additional models: **XGBoost, LightGBM, Logistic Regression**
- Use **feature importance** to understand weak signals
- Explore **time series trends** (e.g., contract duration, seasonal usage)
- Run **cost-benefit simulations** of false positives vs. false negatives

### 📄 Report Enhancements
- Add performance metrics table: precision, recall, F1-score, confusion matrix
- Include sample visualizations from EDA
- Explain technical terms (e.g., SMOTE) if non-technical readers are expected
- Add flowcharts or process diagrams to improve clarity

---

## ✅ Conclusion

Although the model cannot currently predict churn with high recall, the effort reveals a critical insight: **churn behavior may depend on untracked factors**. This project is a strong foundation for future iterations that incorporate richer data and deeper domain knowledge.
