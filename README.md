# E-Commerce Growth Analysis & RFM Customer Segmentation

This project investigates a significant sales downturn for a Turkish e-commerce platform in Q1 2024. By combining exploratory data analysis (EDA) with K-Means clustering, the study identifies core business drivers and develops a targeted RFM (Recency, Frequency, Monetary) strategy to stabilize the active customer base.

## 📊 Project Overview
* **Data Source:** [Kaggle - E-commerce Customer Behavior (Turkey)](https://www.kaggle.com/datasets/umuttuygurr/e-commerce-customer-behavior-and-sales-analysis-tr)
* **Dataset Scale:** transactions of 5,000 customers including regional, categorical, and temporal data.
* **Interactive Dashboard:** [View Tableau Dashboard](https://public.tableau.com/views/e-comdatasetkaggle/Dashboard1?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

## 🔍 Phase 1: Sales Trend Analysis & Hypothesis
**Objective:** Evaluate Q1 2024 performance and identify variables influencing revenue shifts.

### Key Findings
* **The Downturn:** A universal downward trend across all product categories and regions (excluding Gaziantep and Konya).
* **Volume vs. Value:** While Average Order Value (AOV) and orders-per-customer remained stable within a 95% confidence interval, total order volume plummeted **14.2% below the mean** in February and March.
* **Audience Shift:** New user acquisition collapsed from **39.7%** in early 2023 to just **2.3%** by March 2024. 

> **Core Hypothesis:** The sales decline is driven by a failure in **customer acquisition and retention** rather than a change in individual purchasing power or behavior.

---

## 🤖 Phase 2: RFM Segmentation Model
**Objective:** Address the shrinking active user base by segmenting customers for personalized re-engagement.

### Methodology
1.  **Feature Engineering:** Aggregated transaction data into user-level metrics:
    * **Recency:** Transactions within the last 2 months.
    * **Frequency:** Users with >1 order during the observation period.
    * **Monetary:** Average Order Value (AOV).
2.  **Clustering:** Applied **K-Means Clustering**. Despite a 9% outlier rate, all data points were retained to ensure a comprehensive view of the total customer base.
3.  **Validation:** Optimal cluster count determined via Silhouette Score analysis.



### Segment Profiles
| Cluster | Label | Recency | Frequency | Monetary (Avg) | Description |
|:---:|:---|:---|:---:|:---:|:---|
| **0** | **Hibernating** | > 6 months | 1 | ₺430 | One-time buyers; long-term inactive. |
| **1** | **At Risk** | ~ 5-6 months | 2 | ₺350 | Low-value customers drifting away. |
| **2** | **Champions** | < 1 month | 5 | ₺1400 | High-value, frequent, recent shoppers. |
| **3** | **Potential Loyalists** | ~ 3 months | 3 | ₺1530 | High spenders; recently inactive. |
| **4** | **Loyal Budgeters** | < 1 month | 4 | ₺420 | Frequent shoppers; low per-transaction spend. |

---

## 🚀 Strategic Roadmap

### 🏆 Champions (Cluster 2)
* **Strategy:** Focus on **Exclusivity** over discounts.
* **Tactics:** Early access to new collections and personalized loyalty rewards.

### 🐋 Potential Loyalists (Cluster 3)
* **Strategy:** **High-touch re-engagement** to prevent churn.
* **Tactics:** "We miss you" campaigns with incentives (e.g., 15% discount) valid for 7 days.

### 📈 Loyal Budgeters (Cluster 4)
* **Strategy:** Increase **Average Order Value (AOV)**.
* **Tactics:** Implement "Free Shipping" thresholds and product bundling (e.g., Buy 3 for 2).

### 💤 At Risk / Hibernating (Clusters 0 & 1)
* **Strategy:** **Automated Reactivation** or list pruning.
* **Tactics:** Send a final "Last Chance" deep discount. If inactive after 30 days, move to a "Cold" list to protect email deliverability.

---
