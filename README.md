# Marketing Spend Optimization using Machine Learning

## 📌 Problem Statement
An online advertising firm wants to optimize its marketing spends across various ad placements, banners, and campaigns to **maximize post-click sales**. The company seeks to use data science techniques to identify what strategies work best and forecast outcomes to support **data-driven budget planning**.

---

## 🎯 Objective
- Analyze the marketing spend dataset to uncover **actionable insights**
- Use **exploratory data analysis (EDA)** and **statistical methods** to understand feature relationships
- Build a **regression model** to forecast post-click sales amount
- Recommend a marketing strategy backed by insights and model performance

---

## 🧩 Dataset
The dataset contains historical marketing data with the following key features:
- `cost`: Money spent on ads
- `placement`: Ad location (e.g., website section)
- `banner_size`: Dimensions of the ad
- `campaign_number`: Marketing campaign identifier
- `user_engagement`: Binary indicator of high/low engagement
- `displays`, `clicks`, `conversions`, `revenue`, `post_click_sales_amount`
- Engineered Features: ROAS, cost_per_conversion, conversion_rate

---

## 🔍 Exploratory Data Analysis & Insights

### 📊 Key Insights:
1. **Campaign 1 with High User Engagement** consistently yields the highest ROAS — optimal cost-effective marketing strategy.
2. **Ad Displays vs. Clicks** show a strong linear relationship (Pearson correlation = **0.77**).
3. **Banner Sizes** such as `240×400`, `580×400`, and `728×90` generate the most post-click sales per cost spent.
4. **Placements `ghi` and `mno`** are high-performing ad slots, balancing both higher cost and high post-click sales amount.

---

## 📈 Modeling Approach

### ✅ Model Used
- **Random Forest Regressor**  
  Chosen for its ability to handle non-linear relationships, feature importance interpretation, and robustness to outliers.

### 🎯 Target Variable
- `post_click_sales_amount`

### 📦 Features Used
- `cost`, `placement`, `banner_size`, `displays`, `clicks`, `campaign_number`, `user_engagement`
- Dropped derived variables like `ROAS`, `conversion_rate`, and `cost_per_conversion` to avoid multicollinearity

---

## ⚙️ Preprocessing
- **Label Encoding** applied to categorical features (`placement`, `banner_size`, `campaign_number`, `user_engagement`)
- No scaling required due to tree-based model
- Handled missing values and removed duplicates

---

## 📊 Performance Metrics

| Metric       | Training Set | Testing Set  |
|--------------|--------------|--------------|
| R² Score     | 0.948        | 0.940        |
| RMSE         | 2388.06      | 2611.50      |
| MAE          | 376.34       | 414.40       |

> High R² with low RMSE and MAE indicates strong predictive performance and generalization.

---

## 📌 Strategy Recommendation

Based on EDA and model results, the recommended strategy includes:
- Focus ad spend on **Campaign 1 with High Engagement**
- Prioritize **ghi** and **mno** placements for maximum sales impact
- Invest in **banner sizes 240×400, 580×400, and 728×90**
- Use the trained model to **forecast outcomes** and plan ad budgets intelligently

---

## 🛠️ Tools & Libraries
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn (Random Forest, LabelEncoder, Metrics)
