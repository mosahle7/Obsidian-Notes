
**LLM:**

Tokens  --> **Dense Semantic Vector** (First Guess of meaning)
		   **Position Vector** (Position in prompt)
		   
Enters **Attention mechanism**
**Attention:** Process that lets model decide which tokens or words are most important to consider when generating each new token, so it can capture relations and context across entire sequence. 

Mechanism used to assign attention: **Attention Head**
Smaller: 8-16 heads, Larger: over 100

Enters **Feed Forward** Phase (Biggest part, contains most of params).
Based on each token's original embedding, position and attention, it assigns updated vector embeds for each token.

Repeat **8-64** times.

Probability of tokens

**Greedy Decoding:** Sampling strategy that always select token with highest probability at each step.
Deterministic.
Can get stuck in a loop

**Temperature**
**Top-K, Top-P** (more dynamic) 
**Repetition Penalty**
**Logit Biases**: Allow direct manipulation of token probs by adding or subtracting values from model's raw calculated probs.

**Large:** (100-500) B params, **Small:** (1-10) B params

**Benchmarks for LLMs:**

1. **Automated Benchmarks**:
- Evaluated with code
- Common format is MCQ tests on various subjects
- **MMLU** covers 57 subs from STEM to humanities.

2. **Human Evaluated Benchmarks:**
- 2 anonymous LLMs respond to same prompt and asking human evaluators to choose which response they prefer.
- Uses **ELO** algo to create comparative leaderboards.
- **LLM Arena**: popular host.

3. **LLM-as-a-judge Benchmarks:**
- One LLM rate another LLM's response to a collection of Q's.
- Judge LLM has access to set of reference answers.
- Cheap and Flexible Evaluation Method.

**Managing of Context Window of RAG Systems:** Include only chunks relevant to latest question.

**Overcoming Hallucinations:**

**Self-Consistency Methods:** Repeatedly generate responses to same prompt and confirm consistency.

**Citation Generation:** Provide sources. **ContextCite** (attributes sentences in response to retrieved documents)

**Evaluating Citation Quality in LLMs:**

**ALCE Benchmark:** 

Aims to measure how well a system references and cites sources when generating responses.

Tests RAG responses on prepared prompts.

Evaluates responses on:
**Fluency:** How clearly
**Correctness:** How factually accurate
**Citation Quality:** How well do citations align with correct sources

**Don't control hallucinations!!!**

**Evaluating LLM Performance:**

**Ragas** Metrics:

1. **Response Relevancy:** 

- Measures response is relevant to user prompt, regardless of accuracy.

- Response sent to Evaluator LLM and it generates new sample prompts that could have led to response.

- Embed og and sample prompts to vectors and calc cosine similarity. Avg. similarity scores --> final relevancy measure.

2. **Faithfulness:**

- Measures whether response is consistent with retrieved information.

- LLM identifies all factual claims in response, more LLM calls to det if claims are factually supported by retrieved info. 

- % of supported claims --> faithfulness.

**Agentic RAG:**

**Workflows:**
- **Sequential**
- **Conditional**
- **Iterative**
- **Parallel**




