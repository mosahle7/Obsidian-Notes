
**Vector Databases:**

Databases optimized to store and search through huge quantities of vector data.

Simplest Form of Vector Retrieval: **KNN**
To improve, retrievers use a family of algos: **Approximate Nearest Neighbors (ANN)**

**ANN:**

Uses clever data structures to enable significantly faster searches.
Make a small sacrifice in quality of results

ANN Algorithm: **Navigable Small World**

Creates a DS called **Proximity Graph**:

Compute distances btw all doc vectors.
Add one node to graph for each doc.
Connect each node to its nearest neighbors.
Can traverse graph moving along edges btw neighboring docs.
Web-like structure

Prompt --> Prompt Vector 
Start with candidate vector and traverse to nearest neighbor that is closer to prompt vector and that will become new candidate an this continues till candidate becomes the closest.

Slight Variation: **Hierarchical Improvement**




