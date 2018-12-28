# parallelisedclustering

The clustering algorithm parallelised by the Rmd file is described below:

If there are n data points and want to detect any small clusters with at least x, y or z (denote as
vector J) data points, M is the number of small clusters wanted for each value in vector J (i.e. M =
n/J by recycling single element vector n). L is the number of large clusters wanted.
For each value in vector J. Use Multivariate Hypergeometric Distribution to check if a cluster (small
cluster) under M-means has an unbias sample of the clusters (large clusters) under L-means. If a
cluster under M-means (small cluster) has an unbias sample (i.e. hypothesis test is insignificant), we
have detected a small cluster.

For example, we have a data set with 1,000,000 data points and we
want to detect small clusters with 1,000 or 2,000 data points after
performing a 3-means.

The parameters will be: 

n = 1,000,000 

M = [1,000 500] because n/J = 1,000,000 / [1,000 2,000]

L = 3

We then perform a 1,000-means and 500-means clustering.

Then, the multivariate hypergeometric distribution will be used to
check if each of the clusters found under the 1,000-means and 500-
means has an unbias membership across the three large clusters
created under the 3-means.

Each unbias cluster detected is a potential small cluster. Because
conversely, if a small cluster has a bias distribution across the three
large clusters by having almost all data points that belong to the same
large cluster, that small cluster is probably a subset of that large
cluster.
