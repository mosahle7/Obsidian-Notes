
**HHH:** Helpful, Honest, Harmless

**Reinforcement Learning from Human Feedback (RLHF):**

Uses reinforcement learning to finetune the LLM with human feedback data, resulting in a model that is better aligned with human preferences. 

RLHF to make sure that your model produces outputs that 
maximize usefulness and relevance to the input prompt. 

RLHF can help minimize the potential for harm. You can train your model to give caveats that acknowledge their limitations and to avoid toxic language and topics.

The agent's policy that guides the actions is the LLM, and its objective is to generate text that is perceived as being aligned with the human preferences. 

The environment is the context window of the model, the space in which text can be entered via a prompt. The state that the model considers before taking an action is the current context.

The action here is the act of generating text. The action space is the token vocabulary.

The action that the model will take, meaning which token it will choose next, depends on the prompt text in the context and the probability distribution over the vocabulary space. The reward is assigned based on how closely the completions align with human preferences.

**RL Algorithm:** **Proximal Policy Optimization  (PPO)**, **Q-Learning**

**Potential Problem - Reward Hacking:**

The agent learns to cheat the system by favoring actions that maximize the reward received even if those actions don't align well with the original objective. 

To prevent reward hacking from happening, use the initial instruct LLM as performance reference (reference model). The weights of the reference model are frozen and are not updated during iterations of RHF. This way, it maintains a single reference model to compare to. During training, each prompt is passed to both models, generating a completion by the reference LLM and the intermediate LLM updated model.

Compare the two completions and calculate a value called the **Kullback-Leibler divergence, or KL divergence**, a statistical measure of how different two probability distributions are. It is calculated for each generated token across the whole vocabulary of the LLM. Using a softmax function, the number of probabilities are reduced to much less than the full vocabulary size. 

After KL divergence between the two models are calculated, a penalty term is added to the reward calculation. This will penalize the RL updated model if it shifts too far from the reference LLM and generates completions that are too different.

**Scaling Human Feedback:**

**Model self-supervision - Constitutional AI**