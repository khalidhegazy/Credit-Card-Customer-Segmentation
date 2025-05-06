# Credit Card Customer Segmentation

This project uses clustering techniques (KMeans, DBSCAN, and Gaussian Mixture Models) to segment credit card customers based on their usage behavior. Dimensionality reduction techniques like PCA and t-SNE are also applied for visualization and preprocessing.

Dataset
Source: CC GENERAL.csv
Records: 8950 customers

Data Preprocessing
Removed duplicates and null values

Standardized features using StandardScaler

Visualized distributions and correlations using histograms and heatmaps

Dimensionality Reduction
PCA: Reduced features to retain 90%+ variance (9 components)

t-SNE: Used for 2D visualization of customer clusters
![image](https://github.com/user-attachments/assets/e315a990-2435-4596-9287-4f1cf0d3773e)


Clustering Methods
KMeans Clustering
Optimal clusters: 3 (based on Elbow & Silhouette Score)

Segments:

Cluster 0: High Balance, High Cash Advance, Low Purchases

Cluster 1: Low Balance, High Purchases, Low Cash Advance

Cluster 2: Low Balance, Low Purchases, Low Cash Advance

![image](https://github.com/user-attachments/assets/cec60741-67dd-4694-8810-c1de39b29204) ![image](https://github.com/user-attachments/assets/e329cd7e-661b-42e4-a33e-df69b0279476) ![image](https://github.com/user-attachments/assets/dcc501b9-55f2-412a-996f-b649c69787e8)



DBSCAN
eps=2.2, min_samples=4 gave optimal performance with 3 clusters.
Segments:

Cluster -1 (Noise/Outliers) : Irregular or Extreme Behavior
These customers do not fit into the main clusters and may represent outliers. Their spending patterns are inconsistent—some may have unusually high or low balances, purchases, or cash advances.


Cluster 0 : Moderate Balance, Low Purchases, High Cash Advance
These customers maintain moderate credit balances but rely heavily on cash advances. They make fewer purchases, suggesting a preference for liquidity over regular spending.


Cluster 1 : Low Balance, High Purchases, Low Cash Advance
These are active spenders with low balances. They frequently make purchases but rarely use cash advances, indicating a reliance on credit for transactions rather than cash withdrawals.

![image](https://github.com/user-attachments/assets/49b4d229-c737-413d-98cd-3f5346ffe6a7)
![image](https://github.com/user-attachments/assets/ff42cb8c-6576-4300-9d9f-65ad9854bc08)
![image](https://github.com/user-attachments/assets/a3705cea-571f-461d-90f8-011b3cd018d5)



Gaussian Mixture Model (GMM)
Best silhouette score at 4 components

Captures soft cluster assignments (probabilistic)

Visualization
PCA 2D plots to visualize KMeans and DBSCAN clusters
![image](https://github.com/user-attachments/assets/48fb3b58-b9db-4ab5-a66e-ba9d37c5d841)
![image](https://github.com/user-attachments/assets/7533780e-282c-489c-ba95-f1f9474208b3)



Boxplots showing feature distributions across clusters

Conclusion
Cluster 0: Likely heavy users of cash advances — may be at higher financial risk

Cluster 1: Active spenders with frequent purchases — potential premium customers

Cluster 2: Minimal activity — possibly dormant or cautious users


Tools & Libraries
Python (Pandas, NumPy, Matplotlib, Seaborn)

scikit-learn (Clustering, PCA, StandardScaler, silhouette_score)

TSNE, DBSCAN, GMM

