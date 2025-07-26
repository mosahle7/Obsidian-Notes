
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
