
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

**Context-Aware Chunking**: Add context to every chunk.
Costly pre-processing.

**Query Parsing:**

**Query Rewriting:** Use an LLM to rewrite query before it is submitted to retriever.

**Named Entity Recognition:** Identifies and categorizes specific types of information within queries like places, people, dates, characters, etc for more targeted search and filtering strategies.
**GLINER**

**Hypothetical Document Embeddings (HyDE)**: 

Uses generated hypothetical docs to help with search process.
Embedding vec of hypo doc is used to complete search.
Improves performance.
Adds latency and some cost.

**High Quality Retriever with Sophisticated Architectures:**

**Bi-Encoder** (have been using)

**Cross-Encoder:**

Concatenate each doc with prompt
Pass combined text into specialized embedding model
Develops deep contextual understanding of interaction between prompt and doc because of concatenation.
CE directly outputs relevance score (0-1).

**Pros:** Better search than a bi encoder
**Cons:** Scale terribly with millions or billions of docs, Can't preprocess as run on prompt-doc pairs, too inefficient to use as a default search technique.

**ColBERT (Contextualized Late Interaction Over BERT):**

Still generate doc vectors, try to capture deeper interactions btw text of prompt and each doc like cross encoder.

Each token gets a vector

Each token in prompt tries to find its most similar token in doc.
Score: Sum of maximum relevancy score found by each token in a prompt

**Pros:**
Scalability of bi-encoder, rich interactions of cross-encoder
Reasonably fast.
**Cons:**
Significant vector storage 