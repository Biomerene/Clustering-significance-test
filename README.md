# Clustering-significance-test

A Permutation test for identification of statistically significant clusters in a phylogenetic tree

The general idea of a permutation test is to compare the observed data to a null distribution generated by randomly permuting the data. If the observed data is significantly different from the null distribution, we can reject the null hypothesis and conclude that the observed pattern is statistically significant.

In the context of a phylogenetic tree, we can use a permutation test to test whether the observed clustering of taxa is statistically significant. Here's a general outline of how the test could be performed:

Define the null hypothesis: The null hypothesis is that the observed clustering of taxa is no different from what we would expect by chance.

Define the test statistic: The test statistic is a measure of how different the observed clustering is from what we would expect by chance. One possible test statistic is the number of clusters in the observed tree.

Generate null distributions: To generate null distributions, we need to randomly permute the labels of the taxa in the phylogenetic tree many times (e.g., 10,000 times). Each permutation generates a new tree, and we can compute the test statistic for each new tree.

Calculate p-values: The p-value is the proportion of permuted trees that have a test statistic that is at least as extreme as the observed test statistic. If the p-value is small (e.g., less than 0.05), we can reject the null hypothesis and conclude that the observed clustering is statistically significant.

Interpret the results: If the null hypothesis is rejected, we can conclude that the observed clustering is statistically significant. We can then examine the clustering to see if it corresponds to any known biological or ecological patterns.

It's worth noting that there are many different ways to define the null hypothesis and test statistic, and the choice of these parameters can affect the results of the test. Additionally, permutation tests can be computationally intensive, especially for large trees or when many permutations are required to generate accurate null distributions.


# Dependencies
```
pandas (v1.0.0 or later)
numpy (v1.18.0 or later)
treeswift (v1.0.0 or later)
queue (included in Python standard library)
tqdm (v4.0.0 or later)
seaborn (v0.10.0 or later)
matplotlib (v3.0.0 or later)
Note: These are minimum version requirements and newer versions of the packages may work as well.
```
