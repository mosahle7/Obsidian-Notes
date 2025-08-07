
**LLM:**

Tokens  --> **Dense Semantic Vector** (First Guess of meaning)
		   **Position Vector** (Position in prompt)
		   
Enters **Attention mechanism**
Mechanism used to assign attention: **Attention Head**
Smaller: 8-16 heads, Larger: over 100

Enters **Feed Forward** Phase (Biggest part, contains most of params).
Based on each token's original embedding, position and attention, it assigns updated vector embeds for each token.

Repeat 8-64 times.

Probability of tokens

**Greedy Decoding:** Sampling strategy that always select token with highest probability at each step.
Deterministic.
Can get stuck in a loop

**Tempearture**
**Top-K, Top-P** (more dynamic) 
**Repetition Penalty**
**Logit Biases**: Allow direct manipulation of token probs by adding or subtracting values from model's raw calculated probs.
