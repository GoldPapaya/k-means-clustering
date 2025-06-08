# k-means-clustering WIP
This project applies k-means clustering to segment data from a popular wine dataset, originally introduced by Aberhard et al. in their 1994 study, <a href='https://www.semanticscholar.org/paper/Comparative-analysis-of-statistical-pattern-methods-Aeberhard-Coomans/83dc3e4030d7b9fbdbb4bde03ce12ab70ca10528'> Comparative Analysis of Statistical Pattern Recognition Methods in High Dimensional Settings.</a> Instead of using the k-means clustering algorithm that is built in to scikit-learn, I made my own k-means algorithm to practice translating theory into a real application.

So what do the data actually look like? The original wine dataset as referenced above includes some data for unsupervised learning, so I found a derivative version that removes that <a href='https://www.kaggle.com/datasets/harrywang/wine-dataset-for-clustering'>here</a>. There are 178 instances each with 13 features, expressing wine characteristics like alcohol level and color intensity. Most k-means classification that I've come across has been implemented in 2 dimensions for simplicity, so I decided to deviate slightly here and do 3 dimensions instead.

The first stage in k-means clustering is to first standardize all the data. A computer has no way of knowing how a 14.23 alcohol level relates to a 5.64 color intensity; a process must be used that can make sense of information regardless of the unit of measure. The scikit-learn StandardScalar does exactly this -- it translates measurements with respect to a mean value of 0 and a standard deviation of 1, and in the case of multivariate data (which is the case for this wine dataset) it applies to all attribute columns. For the examples from earlier, a 14.23 alcohol level measurement translates to 1.52 standard deviations above the mean, and a 5.64 color intensity translates to 0.25 standard deviations above the mean.

After scaling all data, a choice needs to be made about which method to employ to carry out dimensionality reduction. The dataset has 13 features (dimensions), which needs to be reduced to 3. There are several methods that can accomplish this, but the Principal Component Analysis (PCA) method is especially painless and also intuitive in this case. This technique involves choosing the top n vectors responsible for the highest proportion of dataset variance, therefore preserving the maximum amount of information possible while reducing dimensions to a desired level. These curated data can be plotted in a 3d graph, which will reveal a point cloud.







<img src="assets/k-means-iterative.gif"></img>
