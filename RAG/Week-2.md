
**Search Approaches:**

**Hybrid Search:**
**Keyword Search:** Looks for exact words.
**Semantic Search:** Looks for similar meaning.
**Metadata Filtering:** Excludes documents based om rigid criteria.

**Metadata Filtering:**

Uses  a rigid criteria to narrow down docs based on metadata like title, author, creation date, access privileges, etc.

**Pros:**
Simple to understand and debug.
Fast, optimized, mature and reliable.
Enforces strict retrieval rules

**Cons:**
Not true search.
Rigid, ignores content and provides no way of ranking.
Useless alone.

**Keyword Search:**
**TF-IDF (Term Frequency - Inverse Document Frequency)**

**BM25 (Best Matching 25):**
**Term Frequency Saturation** (1.2-2)
**Document Length Normalization** (0-1)
2 Tunable Parameters: **k_1** and **b**

**Pros:**
Simple
Guaranteed keyword matching
**Cons:**
When prompt contains different words, but same meaning

**Semantic Search:**

Generate vectors by running doc and prompt through a mathematical model called an embedding model, it map tokens to a location in space, represented by a vector

**Measuring Vector Distance:**
Euclidean Distance
Cosine Similarity
Dot Product

**Contrast Training** on Embedding model, using the contrast provided by positive and negative egs to evaluate its performance.

Update internal parameters based on scoring positive and negative pairs.
Repeat process.

100s or 1000s of dimensions

**Hybrid Search:**

2 Ranked Lists combined using **Reciprocal Rank Fusion**

Control weight of keyword vs semnatic ranking.

**Hyperparameters:** k, beta (weight rankings)

**Retriever Quality Metrics:**

**Precision**