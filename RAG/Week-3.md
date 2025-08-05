
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

**Hierarchical Navigable Small World (HNSW):**

Enhances NSW by speeding up early parts of search.
**Hierarchical Proximity Graph**

If 1000 docs,
Layer 1: All 1000 vectors with complete proximity graph 
Layer 2: Randomly drop to 100 vectors and create new proximity graph.
Layer 3: Randomly drop to just 10 vectors and create new proximity graph.

Start from Layer 3 --> 2--> 1

Run-time: **Logarithmic**

**Vector DB:**

Designed for Vector Search.
Outperform RDBs
Optimized for ANN Search

**Weaviate**

**Chunking:**
Practice of breaking longer text docs from knowledge base to smaller text chunks.

**Token Limits, Improved Relevancy, Ensures only relevant text**.

**Overlapping Chunking**
**Recursive Character Splitting:** Splitting text into chunks at a specified character, for eg: newlines.
Variable chunk size, better accounts for doc structure. 

**Advanced Chunking:**

**Semantic Chunking:** Tries to place sentences together in chunks if they have similar meaning.

**Pros:** Follows author's train of thought, smarter chunk boundaries, high recall and precision.

**Cons:** Computationally expensive, Repeated Vec calcs.

**Language Based Chunking:** Prompt LLM to create chunks from a doc.

