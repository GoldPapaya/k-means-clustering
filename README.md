# k-means-clustering WIP
This project applies k-means clustering to segment data from a popular wine dataset, originally introduced by Aberhard et al. in their 1994 study, <a href='https://www.semanticscholar.org/paper/Comparative-analysis-of-statistical-pattern-methods-Aeberhard-Coomans/83dc3e4030d7b9fbdbb4bde03ce12ab70ca10528'> Comparative Analysis of Statistical Pattern Recognition Methods in High Dimensional Settings.</a> Instead of using the k-means clustering algorithm that is built in to scikit-learn, I made my own k-means algorithm to practice translating theory into a real application.

So what do the data actually look like? The original wine dataset as referenced above includes some data for unsupervised learning, so I found a derivative version that removes that <a href='https://www.kaggle.com/datasets/harrywang/wine-dataset-for-clustering'>here</a>. There are 178 instances each with 13 features, expressing wine characteristics like alcohol level and color intensity. Most k-means classification that I've come across has been implemented in 2 dimensions for simplicity, so I decided to deviate slightly here and do 3 dimensions instead.

The first stage in k-means clustering is to first standardize all the data. A computer has no way of knowing how a 14.23 alcohol level relates to a 5.64 color intensity; a process must be used that can contextualize information irrespective of the units used for measurement. The scikit-learn StandardScalar does exactly this -- it translates measurements in terms of a mean value of 0 and a standard deviation of 1, and in the case of multivariate data (which is the case for this wine dataset) this principle applies to all attribute columns. For the examples from earlier, a 14.23 alcohol level measurement translates to 1.52 standard deviations above the mean, and a 5.64 color intensity translates to 0.25 standard deviations above the mean.



<img src="assets/k-means-iterative.gif"></img>
