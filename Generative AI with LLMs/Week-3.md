
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

**RL Algorithm:** **Proximal Policy Optimization  (PPO)** :

