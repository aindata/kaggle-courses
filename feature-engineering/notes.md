# Kaggle course on feature engineering

# Table of contents
1. [Introduction](#introduction)
2. [Mutual Information](#mutualinfo)
3. [Creating Features](#createfeat)
4. [Clustering with K-Means](#kmean)
5. [Principal Component Analysis](#pca)
6. [Target Encoding](#te)
7. [Miscellaneous](#misc)
<a name="te"></a>

# Introduction <a name="introduction"></a>
[This course](https://www.kaggle.com/learn/feature-engineering) covers some practical solutions for feature engineering. In this post, we present main take away notes from the course. Solving the exercise notebooks is highly encouraged.

# Mutual Information <a name="mutualinfo"></a>
Mutual information describes the relationships in tersm of *uncertainty*. The mutual information (MI) between two quantities is a measure of the extent to which knowledge of one quantity reduces uncertainty about the other. For detailed explanation please refer to [this notebook](https://www.kaggle.com/ryanholbrook/mutual-information).

# Creating Features <a name="createfeat"></a>
Tips on discovering new features:
* Understand the features. Refer to your dataset's data documentation, if available
* Research the problem domain to acquire *domain knowledge*. 
* Study previous work. [Solution write-ups](https://www.kaggle.com/sudalairajkumar/winning-solutions-of-kaggle-competitions) from past Kaggle competitions are a great resource.
* Use data visualization. Visualization can reveal pathologies in the distribution of a feature or complicated relationships that could be simplified. Be sure to visualize your dataset as you work through the feature engineering process.

Tips on creating features:
* Linear models learn sums and differences naturally, but can't learn anything more complex.
* Ratios seem to be difficult for most models to learn. Ratio combinations often lead to some easy performance gains.
* Linear models and neural nets generally do better with normalized features. Neural nets especially neeed features scaled to values not too far from 0. Tree-based models (like random forests and XGBoost) can sometimes benefit from normalization, but usually much less so.
* Tree models can learn to approximate almost any combination of features, but when a combination is especially important they can still benefit from having it explicitly created, especially when data is limited.
* Counts are especially helpful for tree models, since these models don't have a natural way of aggregating information across many features at once.

For more information please refer to this [notebook](https://www.kaggle.com/ryanholbrook/creating-features)

# Clustering with K-Means <a name="kmean"></a>
K-means clustering measures the similarity using ordinary straight-line distance (Euclidean). It creates clusters by placing a number of poits, called centroids, inside the feature-space.

For more information please refer to this [notebook](https://www.kaggle.com/ryanholbrook/clustering-with-k-means)

# Principal Component Analysis (PCA) <a name="pca"></a>
* PCA only works with numeric features, like continuous quantities or counts.
* PCA is sensitive to scale. It's good practice to standardize your data before appylying PCA, unless you know you have a good reason not to.
* Consider removing or constraining outliesr, since they can have an undue influence on results.


For more information please refer to this [notebook](https://www.kaggle.com/ryanholbrook/principal-component-analysis)

# Target Encoding <a name="te"></a>
Target encoding is great for:
* **High-cardinality features**: A feature with a large number of categories can be troublesome to encode: a one-hot encoding would generate too many features and alternatives, likea lable encoding, might not be appropriate for that feature. A target encoding derives numbers for the categories using the feature's most important property: its relationship with the target.

* **Domain-motivated features:** From prior experience, you might suspect that a categorical features should be important even if it scored poorly with a feature metric. A target encoding can help reveal a feature's true informativeness.


For more information please refer to this [notebook](https://www.kaggle.com/ryanholbrook/target-encoding)

# Miscellaneous <a name="misc"></a>
Some resources to learn feature engineering:
* *The Art of Feature Engineering*, a book by Pablo Duboue.
* *An Empirical Analysis of Feature Engineering for Predictive Modeling*, an article by Jeff Heaton.
* *Feature Engineering for Machine Learning*, a book by Alice Zheng and Amanda Casari. The tutorial on clustering was inspired by this excellent book.
* *Feature Engineering and Selection*, a book by Max Kuhn and Kjell Johnson.