# KNN-Hierarchical-Clustering
# ✈️ EastWest Airlines Customer Segmentation

This project applies **unsupervised learning techniques** to segment frequent flyer members of EastWest Airlines based on their travel behavior and mileage activities.

## 📦 Dataset

- **Rows:** 3,999 passengers
- **Source:** EastWest Airlines frequent flier program data
- **Features include:**
  - Balance miles
  - Qualifying miles
  - Miles from credit cards
  - Bonus miles and transactions
  - Flight miles in last 12 months

## 🎯 Objective

To segment customers into **distinct clusters** based on their travel and loyalty behavior using:

- **Hierarchical Clustering**
- **K-Means Clustering**
- Evaluate cluster stability
- Recommend targeting strategies

---

## 🧠 Methods

### 1. Data Preparation
- Standardized numeric variables using `scale()`
- Removed `ID` column and set it as rownames (optional)
- Checked for missing values and variable distributions

### 2. Clustering Approaches

#### 🔗 Hierarchical Clustering
- **Distance metric:** Euclidean
- **Linkage:** Ward’s method
- **Number of clusters chosen:** 5 (based on dendrogram gaps)

#### ⚙️ K-Means Clustering
- Re-ran with 5 clusters to compare with hierarchical output
- Similar segmentation trends observed

### 3. Cluster Insights (Hierarchical)

| Cluster | Engagement Level | Key Traits |
|---------|------------------|------------|
| 1       | Low              | Low mileage, few flights, medium balance |
| 2       | High             | High bonus miles, frequent flyer |
| 3       | Moderate         | Decent travel and bonus activity |
| 4       | High             | Highest miles, high engagement |
| 5       | Low              | Infrequent flyers, minimal bonus |

### 4. Stability Test
- Removed 5% of dataset at random
- Re-ran clustering and found **consistent patterns**
- Negative values emerged due to centering (no issue)

---

## 🎁 Business Recommendations

📌 **Target Clusters: 1 & 3**
- Lower engagement
- Potential to convert into loyal customers

💡 **Offer Ideas:**
- 25% off every third flight
- Bonus 100 miles per flight for 3 months
- Personalized upgrade emails for mid-tier travelers

---

## 💻 How to Run

```r
# Required packages
install.packages(c("ggdendro", "tidyverse", "dplyr"))

# Run the script
source("eastwest_airlines_clustering.R")
