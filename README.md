## Clustering-significance-test

A Permutation test for identification of statistically significant clusters in a phylogenetic tree

![test_passed](https://user-images.githubusercontent.com/34155351/227522244-899e2f2c-4913-464f-91cc-48f4653aafd1.png)

The general idea of a permutation test is to compare the observed data to a null distribution generated by randomly permuting the data. If the observed data is significantly different from the null distribution, we can reject the null hypothesis and conclude that the observed pattern is statistically significant.

In the context of a phylogenetic tree, we can use a permutation test to test the statistical significance of clustering of different metadata annotations. Here's a general outline of how the test could be performed:

**Define the null hypothesis**: The null hypothesis is that the observed clustering of metadata annotations is no different from what we would expect by chance.

**Define the test statistic**: The test statistic is a measure of how different the observed clustering is from what we would expect by chance. One possible test statistic is the purity of clusters in the observed tree. Purity of a cluster measures the extent to which clusters contain a single class. Thus, clusters containing a single class would have purity score of 1.

$$ Purity = \frac 1 N \sum_{i=1}^k max_j | c_i \cap t_j | $$


**Generate null distributions**: To generate null distributions, we need to randomly permute the positions of labels of metadata annotations in the phylogenetic tree many times (e.g., 1000 times). Each permutation changes the clustering of metadata annotations, and we can compute the test statistic for each branch of the tree by recursive traversal.

**Calculate p-values**: The p-value is the proportion of permutations that have a test statistic that is at least as extreme as the observed test statistic. If the p-value is small (e.g., less than 0.05), we can reject the null hypothesis and conclude that the observed clustering is statistically significant.

Interpret the results: If the null hypothesis is rejected, we can conclude that the observed clustering is statistically significant. 

## How to run?

```
python permutation_test.py -t viruses.tree -m meta.tsv -i1 1 -i2 3 -p 0.05 -r 10000 -o output_dir
```

## Dependencies
```
pandas (v1.0.0 or later)
numpy (v1.18.0 or later)
treeswift (v1.0.0 or later)
queue (included in Python standard library)
tqdm (v4.0.0 or later)
seaborn (v0.10.0 or later)
matplotlib (v3.0.0 or later)

```
Note: These are minimum version requirements and newer versions of the packages may work as well.

