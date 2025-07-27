
**Fine-Tuning:** Supervised learning process uses dataset of labeled egs to update weights of LLM, labeled egs are prompt completion pairs.

**Instruction Fine Tuning**: Improves a model performance on a variety of tasks.

Instruction fine tuning where all model weights are updated is known as **full fine-tuning**. 

Model after Instruction fine-tuning: **Instruct LLM**.

**Fine-tuning on a single task:** Only 500-1000 egs needed to fine-tune a single task.
Downside: **Catastrophic Forgetting:**  degrade performance on other tasks.

Avoid by:
**fine-tune on multiple tasks:** requires (50-100) 1000 egs across many tasks.

**Parameter Efficient Fine-tuning (PEFT):** Set of techniques to preserve weights of original LLM and trains only a small number of task-specific adapter layers and parameters. 

**Multi-Task Fine-tuning:**

with **FLAN (Fine-tuned Language Net):**
set of instructions used to perform instruction fine-tuning.

**LLM Evaluation - Metrics:**

**ROUGE (Recall Oriented Understudy for Jesting Evaluation ):** Assess quality of automatically generated summaries by comparing them to human generated summaries.

**Recall**,**Precision**,**F1 Score**
**ROGUE-1,2 , ROGUE-L**


**BLEU (Bilingual Evaluation Understudy):** Algorithm evaluated to evaluate quality of machine translated text by comparing it to human generated translations.

Avg. of precision of multigrams

**Evaluation Benchmarks:**

- **GLUE (General Language Understanding Evaluation), SUPERGLUE, HELM**
- **Massive Multitask Language Understanding (MMLU):** modern LLMs.
- **BIG-bench:** 

**PEFT:**

Only train a set of parameters or train with additional layers.
Less prone to catastrophic forgetting problems

**PEFT Methods:**

**Selective:** Select subset of initial LLM parameters to fine-tune.
**Reparameterization:** Reparameterize model weights using a low-rank representation. **LoRA**
**Additive:** Add trainable layers or parameters to model.
- **Adapters**: Add new trainable layers to architecture of model inside encoder or decoder components after attention of feed-forward layers.
- **Soft Prompts**: Keep model architecture frozen and focus on manipulating input to achieve better performance. Adding trainable parameters to prompt embeddings or keeping i/p fixed and retraining embedding weights. **Prompt Tuning**.

**Low-Rank Adaptation of LLMs (LoRA):**

Freeze most of the original LLM parameters and inject a **2 rank decomposition matrices** alongside og wts. Dimensions of smaller matrices r set so that their product is a mt with smae dims as the weightsthey r modifying. Train smaller matrices using supervised learning process. 

Matrix multiply low rank matrices
Add to original weights

rank: 4-32

**Prompt Tuning:**

Add additional trainable tokens to prompt and supervised learning process determines their optimal values. Set of trainable tokens is called a soft prompt, and it gets prepended to embedding vectors that represent your input text. The soft prompt vectors have the same length as the embedding vectors of the language tokens.

**(20 -100)** virtual tokens.

Weights of the large language model are frozen and the underlying model does not get updated. Instead, the embedding vectors of the soft prompt gets updated over time to optimize the model's completion of the prompt.

One potential issue to consider is the interpretability of learned virtual tokens. Because the soft prompt tokens can take any value within the continuous embedding vector space, trained tokens don't correspond to any known token, word, or phrase in the vocabulary of the LLM. However, an analysis of the nearest neighbor tokens to the soft prompt location shows that they form tight semantic clusters. In other words, the words closest to the soft prompt tokens have similar meanings. The words identified usually have some meaning related to the task, suggesting that the prompts are learning word like representations.



