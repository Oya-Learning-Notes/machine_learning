# K-Means Algorithm

## Introduction

KMeans algorithm is an unsupervised clustring algorithm.

- Manually specify the $K$
- Usually when compared to other clustring method
- No direct information about the cluster quality
- Sensitive to noise
- May fall into local minimal

## Algorithm Detail

### Initialize Centroid

First of all, we should determine the $K$ of this clustring, which will be the final number of the clusters after the algorithm finished.

Then, we just randomly pick $K$ points to be the initial centroids, and assign the rest points to its closest centroid to form the initial clusters.

### Iteration

For each iteration, we do two things:

- Update centroids
- Reassign points to new centroids, form new clusters

---

More specifically, we first calculte the new coordinate of the centroid of each cluster, which is essentially just the average coordinate of all points in that cluster.

Then we assign all points to its closest centroid to form a new set of clusters.

Below is a pseudo code:

```python
points: list[Point]
clusters: list[set[Point]]

centroids: list[Point]

for i in range(iteration_time):
    # update centroid
    for cluster_idx in range(len(clusters)):
        new_centroid = get_avg(clusters[cluster_idx])
        centroids[cluster_idx] = new_centroid
    
    # reassign points to clusters with new centroids
    
    # first clear previous clustering
    for c in clusters:
        c.clear()

    # assign to cluster based on the updated centroids
    for p in points:
        c = closest_cluster(point=p, centroids=centroids)
        c.add(p)
```
