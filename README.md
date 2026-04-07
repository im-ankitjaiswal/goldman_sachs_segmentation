# Customer Segmentation for Personalized Banking
## Goldman Sachs — Credit Card Customer Analysis

![Python](https://img.shields.io/badge/Python-3.9-blue)
![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-yellow)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-KMeans-orange)
![Status](https://img.shields.io/badge/Status-Complete-green)

---

## Business Problem
Goldman Sachs wants to personalize banking services for 8,950 active 
credit card customers. A one-size-fits-all marketing approach is 
inefficient. The goal is to identify distinct customer behavioral 
segments and design targeted strategies for each group.

## Objective
Segment credit card customers based on spending behavior, balance 
patterns, and payment habits using unsupervised machine learning — 
then visualize findings in an interactive Power BI dashboard.

---

## Tools & Technologies
| Tool | Purpose |
|------|---------|
| Python (Pandas, NumPy) | Data loading, cleaning, EDA |
| Scikit-learn | KMeans clustering, PCA |
| Matplotlib & Seaborn | Jupyter visualizations (8 charts) |
| Power BI Desktop | Interactive business dashboard |
| MySQL / SQL | Data extraction queries |
| Jupyter Notebook | End-to-end analysis pipeline |

---

## Dataset
- **Source:** [Kaggle — Credit Card Dataset for Clustering](https://www.kaggle.com/datasets/arjunbhasin2013/ccdata)
- **Size:** 8,950 customers × 18 features
- **Period:** 6 months of credit card usage behavior
- **Key features:** BALANCE, PURCHASES, CASH_ADVANCE, 
  CREDIT_LIMIT, PAYMENTS, MINIMUM_PAYMENTS, TENURE

---

## Project Pipeline

### Step 1 — Exploratory Data Analysis (EDA)
- Analyzed distributions of all 18 features
- Identified 313 missing values in MINIMUM_PAYMENTS (3.5%)
- Found strong correlation (0.92) between PURCHASES 
  and ONEOFF_PURCHASES
- Detected right-skewed distributions in BALANCE and CASH_ADVANCE

### Step 2 — Data Cleaning & Preprocessing
- Filled MINIMUM_PAYMENTS nulls using **median imputation** 
  (preferred over mean due to skewed distribution)
- Dropped CUST_ID (non-analytical identifier)
- Applied **StandardScaler** to normalize all features
  (critical for KMeans distance-based algorithm)

### Step 3 — KMeans Clustering
- Used **Elbow Method** to determine optimal k = 4
- Trained KMeans with k=4, random_state=42, n_init=10
- Assigned cluster labels to all 8,950 customers

### Step 4 — PCA Visualization
- Reduced 17 features to 2 principal components
- PC1 explains ~28% variance, PC2 explains ~16% variance
- Generated 2D scatter plot confirming clear cluster separation

---

## Results — 4 Customer Segments

| Segment | Customers | % Share | Avg Purchases | Avg Balance | Strategy |
|---------|-----------|---------|---------------|-------------|----------|
| Inactive / Low-Engagement | 3,980 | 44.4% | ~$90 | ~$500 | Re-engagement cashback |
| Installment Buyers | 3,370 | 37.6% | ~$1,900 | ~$1,200 | 0% EMI campaigns |
| Cash Advance Users | 1,200 | 13.4% | ~$180 | ~$3,200 | Loan consolidation |
| High Spenders | 410 | 4.6% | ~$5,500 | ~$2,100 | Premium card upsell |

---

## Key Business Insights

**1. 44% of customers are inactive** — the largest segment represents 
a major re-engagement opportunity. Even a 10% activation rate would 
add ~$400K in annual transaction revenue.

**2. High Spenders are only 4.6% but highest value** — this segment 
needs premium retention strategies (concierge service, travel rewards) 
not acquisition spend.

**3. Cash Advance Users show financial stress signals** — high balance 
relative to credit limit (~70% utilization) indicates risk. Bank should 
offer debt consolidation products proactively.

**4. Credit is severely underutilized portfolio-wide** — average 
purchase ($1,003) is only 22% of average credit limit ($4,494). 
Targeted spend activation campaigns could significantly increase 
interchange revenue.

---

## Visualizations (Jupyter Notebook)
| # | Chart | Insight |
|---|-------|---------|
| 1 | Missing values heatmap | MINIMUM_PAYMENTS has 3.5% nulls |
| 2 | Feature distribution grid | Right-skewed spend data |
| 3 | Correlation heatmap | Purchases & OneOff highly correlated |
| 4 | Elbow curve | Optimal k=4 identified |
| 5 | PCA scatter (hero chart) | 4 distinct cluster clouds visible |
| 6 | Avg metrics bar chart | High Spenders dominate purchases |
| 7 | Balance/Purchase boxplots | Cash Advance Users — outlier balances |
| 8 | Pie chart + summary table | Segment size distribution |

---

## Power BI Dashboard
Interactive dashboard with 4 visuals + segment slicer:
- Donut chart — customer distribution by segment
- Clustered bar — avg purchases vs cash advance by segment  
- Scatter plot — balance vs credit limit colored by segment
- KPI cards — total customers, avg balance, avg credit limit, avg purchase

> Screenshot: 👉 [View Full Analysis](https://github.com/im-ankitjaiswal/goldman_sachs_segmentation/blob/main/goldman_sachs_segmentation.pdf)



*Dataset source: Kaggle — Credit Card Dataset for Clustering*
