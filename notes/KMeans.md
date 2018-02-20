K-Means Clustering
==================

## K Means

#### Q: What is K?
**Answer:** Number of clusters selected by users. Is not garenteed to work with given data so K-Means can be considered a naive algorithm.

#### Q: Where do we place the initial centroids?
**Answer:** Use the elbow method https://bl.ocks.org/rpgove/0060ff3b656618e9136b

#### Q: What is a distance measure?
**Answer:** Euclidean distance aka d2. Other distance algorithms of dm with m=1 are also common.

#### Q: How to calculate the center. 
**Answer:** Sum of each n commonent divided by n for each component.
If using Euclidean distance, the Centriod C should be (Sum Xi from i=1 to n)*1/n

#### Q: What is the computational cost of K-Means?
**Answer:** Ixf A has n examples and m attributes. Then it has O(i*n*m*k).

#### Q: How do we normalize data?
**Answer:** We can divide each attribute by the max to make it go from -1 to 1 or 0 to 1.

#### Q: How should we preprocess data?
**Answer:** Normalize data and elimate outliers.

## Hierarchical Clustering: Agglomerative

Agglomerative: This is a "bottom up" approach: each observation starts in its own cluster, and pairs of clusters are merged as one moves up the hierarchy.

#### Distance Options:
* Min
* Group Avg
* Max
* Ward's Method

Dendrogram can be used to get up to m number of clusters. 

## CODE
```javascript
var sse = {};
for (var k = 1; k <= maxK; ++k) {
    sse[k] = 0;
    clusters = kmeans(dataset, k);
    clusters.forEach(function(cluster) {
        mean = clusterMean(cluster);
        cluster.forEach(function(datapoint) {
            sse[k] += Math.pow(datapoint - mean, 2);
        });
    });
}
```
