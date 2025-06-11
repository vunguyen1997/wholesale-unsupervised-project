# Wholesale Customer Segmentation – Unsupervised Learning

## Project  
We apply a full unsupervised learning pipeline to the “Wholesale Customers” dataset from Kaggle, which records annual spending (in monetary units) of 440 clients across six product categories (Fresh, Milk, Grocery, Frozen, Detergents_Paper, Delicassen). Our goal is to discover natural customer segments that can inform targeted marketing and inventory decisions.

## Goals  
1. **Understand** the distribution, skewness, and correlations in the raw spending data.  
2. **Cluster** customers into meaningful groups using K-Means and hierarchical clustering.  
3. **Validate** and visualize segment separation via Principal Component Analysis.  
4. **Summarize** actionable insights for each segment.

## Process  
1. **EDA & Preprocessing**  
   - Loaded and inspected the dataset (no missing values).  
   - Visualized distributions (histograms, boxplots) to detect skew and outliers.  
   - Computed correlation heatmap to gauge feature relationships.  
   - Standardized all spending features (zero mean, unit variance).  
2. **K-Means Clustering**  
   - Used the elbow method (k = 2–10) to select **k = 5**.  
   - Fitted K-Means, extracted and interpreted cluster centers.  
   - Visualized scaled Fresh vs. Milk and confirmed segment separation.  
3. **Hierarchical Clustering**  
   - Computed a Ward linkage dendrogram (full view, no truncation).  
   - Chose a 3-cluster cut for a coarse “high/medium/low” segmentation.  
4. **PCA Validation**  
   - Plotted cumulative explained variance: PC1 + PC2 capture ~72 %.  
   - Reduced to two components and scattered points colored by K-Means labels.

## Results  
1. **Five distinct K-Means segments** emerged:  
  - High Fresh & Grocery buyers
  - Heavy Milk & Detergents_Paper purchasers  
  - Multi-category spenders (above-average Frozen & Delicassen)  
  - Balanced, mid-range buyers  
  - Low-volume clients  
2. **Hierarchical clustering** revealed three broad tiers—top-tier, mid-range, and low-spending—that align with the K-Means groups.  
3. **PCA** confirmed clear separation of the five segments in a 2D projection.

## Challenges  
- Extreme right-skew and outliers in spending categories required careful scaling (and potential log transforms) to prevent distortion.  
- Choosing the optimal number of clusters involved balancing statistical criteria (elbow, dendrogram jumps) with business interpretability.  
- Dendrograms become dense when plotted at full resolution, necessitating careful label formatting and color thresholds.

## Future Goals  
- Experiment with **log-transformed** features or **robust scaling** to further mitigate outlier impact.  
- Evaluate cluster quality with **silhouette scores** and **Calinski–Harabasz** metrics.  
- Incorporate **customer metadata** (Channel & Region) directly into clustering.  
- Test alternative algorithms (e.g., **DBSCAN**, **Gaussian Mixture Models**) for non-spherical segment shapes.  
- Build a **dashboard** to allow business users to explore segment assignments and key statistics interactively.
