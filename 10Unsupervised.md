While Bayes' Theorem and Naive Bayes are primarily used for **Supervised Learning** (where we have labeled data like "Spam" or "Not Spam"), **Unsupervised Learning** is used when we have no labels. 

In Unsupervised Learning, the computer looks at a pile of data and tries to find patterns, structures, or groups on its own.

Here are the most common algorithms used in Unsupervised Learning, categorized by their goal:

---

# 1. Clustering Algorithms (Grouping)
The goal is to group data points so that items in the same group are more similar to each other than to those in other groups.

### A. K-Means Clustering
*   **The Concept:** You tell the algorithm how many groups ($K$) you want. It picks $K$ center points ("centroids") and assigns every data point to the nearest one. It then moves the centers and repeats until the groups are stable.
*   **Best Use:** Market segmentation (grouping customers by spending habits).

### B. Hierarchical Clustering
*   **The Concept:** It builds a tree-like structure (called a **Dendrogram**). You can either start with every point as its own cluster and merge them (Agglomerative) or start with one big cluster and split it (Divisive).
*   **Best Use:** Taxonomy (organizing animals into species/sub-species) or Gene sequence analysis.

### C. DBSCAN (Density-Based Spatial Clustering)
*   **The Concept:** Unlike K-Means, it doesn't need to know how many groups you want. It looks for "dense" areas of points. If a point is in a crowded area, it’s part of a cluster. If it's in a lonely area, it's labeled as **noise**.
*   **Best Use:** Detecting clusters of irregular shapes and identifying outliers (anomalies).

---

# 2. Dimensionality Reduction (Simplifying)
When you have too many variables (e.g., 100 different columns in a spreadsheet), these algorithms "squash" the data down to the most important parts without losing the core information.

### A. PCA (Principal Component Analysis)
*   **The Concept:** It finds the "directions" (Principal Components) where the data varies the most. It flattens the data while trying to keep as much "spread" as possible.
*   **Best Use:** Speeding up other ML algorithms or visualizing high-dimensional data on a 2D graph.

### B. t-SNE (t-Distributed Stochastic Neighbor Embedding)
*   **The Concept:** It focuses on keeping "neighbors" together. If two points were close in 100-dimensional space, t-SNE tries very hard to keep them close in a 2D map.
*   **Best Use:** Visualizing complex clusters (e.g., seeing how different types of handwritten digits group together).

---

# 3. Association Rule Learning (Finding Links)
This looks for "If-Then" rules that happen frequently in your data.

### A. Apriori Algorithm
*   **The Concept:** It identifies items that frequently appear together in a dataset. If people buy $A$, they are $X\%$ likely to buy $B$.
*   **Best Use:** **Market Basket Analysis.** (e.g., Amazon seeing that people who buy a "Camera" also buy an "SD Card," so it suggests it to you).

---

# 4. Anomaly Detection (Finding the "Weird" Stuff)
The goal is to find data points that don't fit any pattern.

### A. Isolation Forest
*   **The Concept:** It works on the principle that anomalies are few and different. It randomly "splits" the data. Since anomalies are outliers, they get "isolated" much faster than normal points.
*   **Best Use:** Credit card fraud detection (finding a transaction that looks nothing like your usual behavior).

---

# Summary Comparison Table

| Algorithm | Category | Core Idea | Real-World Example |
| :--- | :--- | :--- | :--- |
| **K-Means** | Clustering | Groups data into $K$ number of circles. | Segmenting "High Spenders" vs. "Bargain Hunters." |
| **DBSCAN** | Clustering | Groups data based on how "crowded" it is. | Filtering out "noise" or "static" from a signal. |
| **PCA** | Dim. Reduction | Flattens 100 features into 2 or 3. | Reducing file size while keeping info. |
| **Apriori** | Association | Finds things that usually go together. | "People who bought this also bought..." |
| **Isolation Forest**| Anomaly | Isolates "weird" points quickly. | Detecting a hacker logging in from a new city. |

### Which one should you start with?
If you are new to Unsupervised Learning, **K-Means** is the best place to start for grouping, and **PCA** is the best place to start for simplifying data. They are the "workhorses" of the industry.