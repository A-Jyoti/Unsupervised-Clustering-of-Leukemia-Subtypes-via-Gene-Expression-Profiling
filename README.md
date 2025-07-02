# Unsupervised-Clustering-of-Leukemia-Subtypes-via-Gene-Expression-Profiling
Collecting workspace informationCertainly! Here’s a professional, flow-wise analysis and description of your gene expression clustering project, including the technologies used and the problem addressed:

---

## Project Overview

This project performs unsupervised clustering and visualization of gene expression profiles from leukemia (AML/ALL) patient samples. The goal is to determine whether gene expression data can distinguish between cancer types, using advanced data science and machine learning techniques.

---

## Problem Statement

**Challenge:**  
Leukemia subtypes (e.g., AML vs. ALL) have distinct gene expression signatures, but these are high-dimensional and noisy. The task is to process, reduce, and cluster this data to reveal underlying biological groupings—potentially aiding diagnosis or research.

---

## Workflow & Technologies

### 1. **Data Acquisition and Preparation**
- **Technology:** `pandas`
- **Process:**  
  - Load patient labels (actual.csv) and two gene expression datasets (data_set_ALL_AML_independent.csv, data_set_ALL_AML_train.csv).
  - Remove metadata columns and non-expression data.
  - Concatenate datasets to form a comprehensive expression matrix.
  - Transpose so each row represents a patient, and append the true cancer label.

### 2. **Data Normalization**
- **Technology:** `scikit-learn` (`StandardScaler`)
- **Process:**  
  - Separate features (gene expression values) from labels.
  - Apply Z-score normalization to ensure all genes contribute equally, mitigating bias from scale differences.

### 3. **Dimensionality Reduction**
- **Technology:** `scikit-learn` (`PCA`), `matplotlib`
- **Process:**  
  - Use Principal Component Analysis (PCA) to reduce dimensionality while retaining 95% of variance.
  - Visualize the first two principal components, colored by true cancer type, to assess separability.

### 4. **Clustering Analysis**
- **Technology:** `scikit-learn` (`KMeans`)
- **Process:**  
  - Apply KMeans clustering to the PCA-reduced data.
  - Use the elbow method (plotting inertia vs. cluster count) to determine the optimal number of clusters (k=2).
  - Assign cluster labels to each patient.

### 5. **Cluster Evaluation**
- **Technology:** `scikit-learn` (`adjusted_rand_score`, `silhouette_score`)
- **Process:**  
  - Quantitatively assess clustering quality using Adjusted Rand Index (ARI) and Silhouette Score.
  - ARI compares clustering with true labels; Silhouette Score measures cluster cohesion and separation.

### 6. **Visualization**
- **Technology:** `seaborn`, `matplotlib`
- **Process:**  
  - Create a scatterplot of the first two principal components.
  - Color points by cluster and style by true label to visually inspect clustering performance.

---

## Technologies Used

- **pandas:** Efficient data manipulation and cleaning.
- **scikit-learn:**  
  - `StandardScaler` for normalization  
  - `PCA` for dimensionality reduction  
  - `KMeans` for clustering  
  - `adjusted_rand_score` and `silhouette_score` for evaluation
- **matplotlib & seaborn:** High-quality, publication-ready data visualization.

---

## Artful Address of the Problem

This project elegantly bridges the gap between raw, high-dimensional biological data and actionable insights. By leveraging robust statistical preprocessing, state-of-the-art dimensionality reduction, and unsupervised learning, we reveal the latent structure in gene expression profiles. The workflow not only demonstrates technical rigor but also provides interpretable visual and quantitative evidence that gene expression can meaningfully distinguish leukemia subtypes—an essential step toward precision medicine.

---

**In summary:**  
We systematically transformed complex gene expression data into clear, interpretable clusters using a modern data science stack, validating our results both visually and statistically. This approach exemplifies how machine learning can empower biomedical research and clinical diagnostics.
