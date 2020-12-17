# Detection of Crime Hotspots

This project aims to identify regions where the crime rate is high. The knowledge is of importance to researchers and the security forces.

## Prerequisites

Dataset Used: [*Vancouver Open Data Catalogue*](https://www.kaggle.com/wosaku/crime-in-vancouver?select=crime.csv) 

Source: Kaggle

This project was made using [Google Colab](https://colab.research.google.com/notebooks/intro.ipynb#recent=true).

## Problem Statement & Approach

The dataset has all past criminal records from 2003 to 2017 with all the requisite details for Vancouver city. The problem statement is to find regions where the crime rate is high. We use an unsupervised learning approach for the same.
DBSCAN Algorithm finds the clusters which are regions where crime rate is maximum. This is useful because if a location or coordinate of Vancouver City is specified one can predict if the area falls in a crime hotspot or not. The noise points found here could either mean an erroneous value or very crimes- so those regions with let’s say just 1 incident (with no criminal events even in the close vicinity) wouldn’t be as risky as any other region which is a crime hotspot. 

## Procedure

Algorithm used: Density-based spatial clustering of applications with noise (DBSCAN)
* Pre-process: Removal of missing data, extraction of just 2 features - (x,y) coordinates for the position.
* Logic: Scratch code implementation of DBSCAN algorithm
* Data Visualisation: Scatter Plot to see the clusters in the data

**Inbuilt libraries have only been used for Data Visualisation and Dataframes. No in-built libraries have been used for the implementation of DBSCAN Algorithm, the code is purely for understanding the algorithmic logic.**

## Inference

In the output, non-spherical density based clustering can be seen. The clustering shows the crime hotspots in Vancouver City and some points have also been identified as noise or outliers.

## Contributors

* [Trisha Sarkar](https://github.com/trishasarkar)

## Points to be Noted

* Estimation of Hyper parameters:
1. Estimation of MinPts: MinPts value is taken as 4. It has been seen by some researchers that for 2 dimensional datasets, value of MinPts beyond 4 doesn't yield much of a difference, hence MinPts=4 has been taken.

Reference: [Paper on DBSCAN](http://www2.cs.uh.edu/~ceick/7363/Papers/dbscan.pdf)

2. Estimation of Epsilon: The approach suggests finding the distance of all points from their k nearest neighbors, sorting the distances plotting them and the elbow point is picked as optimal epsilon using that curve. Hence, I have chosen esp=400.

Reference:[Medium Article](https://towardsdatascience.com/machine-learning-clustering-dbscan-determine-the-optimal-value-for-epsilon-eps-python-example-3100091cfbc )
