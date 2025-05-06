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

Clustering Methods
KMeans Clustering
Optimal clusters: 3 (based on Elbow & Silhouette Score)

Segments:

Cluster 0: High Balance, High Cash Advance, Low Purchases

Cluster 1: Low Balance, High Purchases, Low Cash Advance

Cluster 2: Low Balance, Low Purchases, Low Cash Advance

![image](https://github.com/user-attachments/assets/cec60741-67dd-4694-8810-c1de39b29204) ![image](https://github.com/user-attachments/assets/e329cd7e-661b-42e4-a33e-df69b0279476) ![image](https://github.com/user-attachments/assets/dcc501b9-55f2-412a-996f-b649c69787e8)



DBSCAN
eps=2.5, min_samples=4 gave optimal performance with 4 clusters.
Segments:

Cluster -1 (Noise/Outliers):
Varied behavior with irregular or extreme values; unique combinations of balance, purchases, and cash advances.

Cluster 0:
Moderate Balance, Moderate Purchases, Moderate Cash Advance
Balanced usage behavior with neither high nor low spending patterns.

Cluster 1:
Low Balance, Low Purchases, Low Cash Advance
Low activity, minimal credit engagement.

Cluster 2:
High Balance, Low Purchases, High Cash Advance
Preference for liquidity over transactional spending.



Gaussian Mixture Model (GMM)
Best silhouette score at 4 components

Captures soft cluster assignments (probabilistic)

Visualization
PCA 2D plots to visualize KMeans and DBSCAN clusters

Boxplots showing feature distributions across clusters

Conclusion
Cluster 0: Likely heavy users of cash advances — may be at higher financial risk

Cluster 1: Active spenders with frequent purchases — potential premium customers

Cluster 2: Minimal activity — possibly dormant or cautious users


Tools & Libraries
Python (Pandas, NumPy, Matplotlib, Seaborn)

scikit-learn (Clustering, PCA, StandardScaler, silhouette_score)

TSNE, DBSCAN, GMM

