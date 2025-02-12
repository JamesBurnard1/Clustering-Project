# Clustering-Project
Clustering Project

Author: James Burnard

Date: 11/6/2024

**Overview**

In this project, I explore three different clustering techniques applied to a dataset from the wine industry:

Hierarchical Clustering

K-means Clustering

Model-based Clustering

**Libraries Used**

The following R libraries are used for clustering and evaluation:

mclust (version 6.1.1)

flexclust

NbClust

cluster

fpc

knitr

**Data Processing**

The dataset consists of 13 chemical measurements of different wines, along with a "Cultivar" column that indicates the type of plant used. Clustering is performed on the 13 chemical measurements, and the results are compared with the Cultivar column to assess correlation.

**Data Preprocessing**

Read dataset: wine.data <- read.csv("wine_cultivar_data.csv")

Remove missing values: wine.data <- na.omit(wine.data)

Convert Cultivar to a factor.

Scale numerical columns: wine.data.scaled <- scale(wine.data[-1])

**Part 1: Hierarchical Clustering**

Compute distance matrix: dist.mat <- dist(wine.data.scaled)

Perform clustering: clusters <- hclust(dist.mat)

Plot dendrogram: plot(clusters)

Cut tree into clusters and evaluate purity.

**Part 2: K-means Clustering**

Run k-means with different cluster sizes.

Assess results using:

Within-cluster sum of squares (WSS)

Between-cluster sum of squares (BSS)

Cluster purity

Determine optimal clusters using the "elbow" method with WSS.

Compare clusters to Cultivar values.

**Part 3: Model-Based Clustering (mclust)**

Perform clustering with Mclust().

Select optimal number of clusters using Bayesian Information Criterion (BIC).

Visualize clusters in 2D using principal component analysis (PCA).

**Key Findings**

Hierarchical and model-based clustering suggest that 3 clusters are optimal, aligning with the number of unique Cultivar values.

K-means clustering supports 3 clusters as the best fit based on WSS and purity evaluations.

The Adjusted Rand Index (ARI) confirms a strong correlation between cluster membership and Cultivar.

Model-based clustering provides the most refined clustering solution, automatically selecting the best cluster structure.

**Conclusion**

This project demonstrates how clustering techniques can uncover natural groupings in wine chemistry data. The results confirm that chemical composition is strongly related to grape cultivar, providing useful insights for winemakers in selecting grape varieties.




