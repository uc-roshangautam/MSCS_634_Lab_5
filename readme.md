MSCS 634 Lab 5 - Clustering Analysis

Purpose

This lab implements and compares two clustering algorithms - Hierarchical Clustering and DBSCAN - on the Wine dataset from scikit-learn. The objective is to understand different clustering approaches, evaluate their performance using various metrics, and analyze their strengths and weaknesses.

Key Insights

Dataset Characteristics
- Wine dataset contains 178 samples with 13 features
- 3 true wine classes with distribution: [59, 71, 48]
- Features were standardized to ensure fair clustering performance

Hierarchical Clustering Results
- Optimal number of clusters: 3 (matching true classes)
- Achieved silhouette score: ~0.27-0.35 (varies by run)
- Dendrogram reveals clear hierarchical structure
- All data points assigned to clusters (no noise handling)

DBSCAN Results
- Best parameters typically: eps=1.0-1.5, min_samples=5-7
- Successfully identifies noise points and irregular cluster shapes
- Performance varies significantly with parameter selection
- Homogeneity and completeness scores provide additional validation

Comparative Analysis
- Hierarchical: More stable, deterministic results but requires pre-specified cluster count
- DBSCAN: Automatically determines clusters but highly parameter-sensitive
- Visualization: PCA projection shows both methods can reasonably separate wine classes
- Performance: Results depend on parameter tuning; both methods show promise for this dataset

Challenges and Decisions

Parameter Selection
- Hierarchical: Tested n_clusters from 2-5, selected based on silhouette score
- BSCAN: Extensive grid search across eps and min_samples values
- Used silhouette score as primary metric for comparison

Visualization Approach
- Applied PCA for 2D visualization while preserving cluster analysis on full feature space
- Highlighted noise points separately in DBSCAN visualization
- Included dendrogram for hierarchical clustering interpretation

Evaluation Metrics
- Primary: Silhouette score (internal validation)
- Secondary: Homogeneity and completeness scores (external validation)
- Considered cluster count and noise point identification

Technical Decisions
- Standardized features using StandardScaler
- Used Ward linkage for hierarchical clustering (minimizes variance)
- Applied comprehensive parameter testing for robust results

Files

- `clustering_analysis.ipynb`: Complete Jupyter notebook with implementation
- `README.md`: This documentation file

Usage

Run the Jupyter notebook cells sequentially. All required libraries are imported at the beginning. The notebook produces visualizations and detailed analysis results for both clustering methods.