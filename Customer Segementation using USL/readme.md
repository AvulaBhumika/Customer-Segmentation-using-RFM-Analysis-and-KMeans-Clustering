# 🛍️ Customer Segmentation using RFM Analysis and KMeans Clustering

This project segments customers based on their purchasing behavior using **Recency, Frequency, and Monetary (RFM)** metrics. Leveraging **KMeans Clustering**, it helps identify key customer groups such as high-value loyal buyers, at-risk customers, and occasional shoppers. These insights can be used for personalized marketing, retention strategies, and revenue optimization.

---

## 📊 Project Overview

- **Objective:** Group customers into distinct segments to enable data-driven targeting.
- **Dataset:** UK-based online retail transactions.
- **Techniques Used:** RFM Modeling, KMeans Clustering, Elbow Method, Data Visualization.

---

## 🧠 Methodology

### 1. **Data Preprocessing**
- Removed missing Customer IDs.
- Filtered cancelled orders (negative quantities).
- Converted `InvoiceDate` to datetime and calculated necessary aggregates.

### 2. **Feature Engineering (RFM)**
- **Recency:** Days since the last purchase.
- **Frequency:** Total number of invoices per customer.
- **Monetary:** Total amount spent by customer.

### 3. **Normalization**
- Scaled RFM features using `MinMaxScaler` to ensure comparability.

### 4. **Clustering**
- Applied **KMeans** with optimal `k` determined via the **Elbow Method**.
- Segmented customers into meaningful groups based on RFM behavior.

---

## 📌 Segment Profiles

| Cluster | Recency (↓) | Frequency (↑) | Monetary (↑) | Count | Description |
|---------|-------------|---------------|---------------|--------|-------------|
| **2**   | 7.4 days    | 82.5          | 127,338       | 13     | 💎 Top Spenders – highly loyal and valuable customers |
| **3**   | 15.5 days   | 22.3          | 12,709        | 204    | 🧡 Active & Loyal – consistent purchasers, high value |
| **0**   | 43.7 days   | 3.7           | 1,359         | 3054   | 🧊 Infrequent Buyers – low value, moderate recency |
| **1**   | 248.1 days  | 1.6           | 480           | 1067   | ⚠️ Churn Risk – inactive and low-value customers |

---

## 📈 Visualizations

### Customer Segments: Recency vs Monetary
![Customer Segments](image.png)

- **Cluster 2**: Very recent and high spenders (ideal for loyalty rewards).
- **Cluster 1**: Dormant and low-value customers (targets for reactivation).
- **Cluster 0 & 3**: Medium to high engagement, potential for upselling.
