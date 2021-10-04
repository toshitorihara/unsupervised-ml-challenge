# Cryptocurrency Clusters (Unsupervised-ML)

## Objective
To create a report that includes what cryptocurrencies (CCs) are on the trading market and determine whether they can be grouped to create a classification system for a new investment. Pre-process the raw data to fit the machine learning models, and exlore whether CCs can be grouped using several clustering algorithms, and share the findings by data visualization.

## Instructions

### Data Preparation
* Read `crypto_data.csv` into Pandas. The dataset was obtained from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist).
* Discard all cryptocurrencies that are not being traded, and drop the `IsTrading` column from the dataframe.
* Remove all rows that have at least one null value.
* Filter for cryptocurrencies that have been mined (greater than zero).
* Delete the `CoinName` from the original dataframe.
* Convert the remaining features with text values, `Algorithm` and `ProofType`, into numerical data by creating dummy variables. (examine # of rows and columns)
* Standardize your dataset so that columns that contain larger values do not unduly influence the outcome.

### Dimensionality Reduction
* Creating dummy variables above dramatically increased the number of features in your dataset. Perform dimensionality reduction with PCA. Rather than specify the number of principal components when you instantiate the PCA model, it is possible to state the desired **explained variance**. For example, say that a dataset has 100 features. 

* Using `PCA(n_components=0.99)` creates a model that will preserve approximately 99% of the explained variance, whether that means reducing the dataset to 80 principal components or 3. For this project, preserve 90% of the explained variance in dimensionality reduction. How did the number of the features change?

* Next, further reduce the dataset dimensions with t-SNE and visually inspect the results. In order to accomplish this task, run t-SNE on the principal components: the output of the PCA transformation. Then create a scatter plot of the t-SNE output. Observe whether there are distinct clusters or not.

### Cluster Analysis with k-Means
* Create an elbow plot to identify the best number of clusters. Use a for-loop to determine the inertia for each `k` between 1 through 10. Determine, if possible, where the elbow of the plot is, and at which value of `k` it appears.

### Recommendation
* Based on your findings, make a brief (1-2 sentences) recommendation to your clients. Can the cryptocurrencies be clustered together? If so, into how many clusters? 
