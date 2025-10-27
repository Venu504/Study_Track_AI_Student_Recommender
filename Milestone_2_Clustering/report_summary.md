 🎯 Milestone 2: Clustering and Pattern Detection

 🧠 Objective

This milestone focuses on discovering **distinct learning behavior groups** among students based on their academic performance and study habits. Through clustering, we classify learners into actionable categories that help guide academic interventions and future decision-making.

📊 Dataset Information

| Attribute          | Details                                              |
| ------------------ | ---------------------------------------------------- |
| **Dataset Name**   | `data_merged.csv` (merged version from Milestone 1) |
| **Total Students** | Same as Milestone 1 after cleaning                   |
| **Data Source**    | Student demographic + study logs + performance data  |

Numerical Features Used for Clustering

Automatically selected using datatype filtering:

```
study_hours  
attendance_rate  
average_score  
(and any other valid numeric fields present)
```

Missing values were handled using **mean imputation**.

⚙️ Methodology

1️⃣ Data Preparation

• Selected valid numeric features using `select_dtypes()`
• Standardized data using **StandardScaler** for fair comparison across metrics

2️⃣ Dimensionality Reduction (PCA)

• Reduced numerical features into **two principal components**
• Improved **cluster interpretability and visualization**

3️⃣ K-Means Clustering

• Evaluated optimal cluster count using:

* **Elbow Method**
* **Silhouette Score**
  • Assigned cluster labels back to dataset

4️⃣ Cluster Analysis

Computed cluster-wise averages to identify differences in study engagement and academic success

🖼️ Visualizations Created

| Plot Type                 | Purpose                                           | File Name                        || ------------------------- | ------------------------------------------------- | -------------------------------- |
| PCA Scatter Plot          | Shows cluster separation visually                 | `cluster_scatter.png`            |
| Cluster Profile Bar Chart | Compares mean study & performance across clusters | `cluster_profile_bar.png`        |
| Correlation Heatmap       | Relationship among numeric attributes             | `correlation_heatmap.png`        |

All plots stored inside:
📁 `visualizations/`

---

🔍 Insights and Interpretation

Based on score + attendance + study hours patterns:

| Cluster | Behavior Pattern                                | Academic Insight                     |
| ------- | ----------------------------------------------- | ------------------------------------ |
| **0**   | High study time, strong attendance, high scores | Stable high performers               |
| **1**   | Average study and performance                   | Potential to improve with support    |
| **2**   | Low study/attendance leading to lower results   | Need targeted academic interventions |

**Study behavior links strongly to performance**, confirming expectations:
✔ Higher study_hours → Higher average_score
✔ Attendance_rate positively influences exam outcomes


