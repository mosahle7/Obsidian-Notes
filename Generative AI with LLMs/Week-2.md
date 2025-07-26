
**Fine-Tuning:**

Supervised learning process uses dataset of labeled egs to update weights of LLM, labeled egs r prompt completion pairs.

**Instruction Fine Tuning**: improcing a model perfomace on a variety of tasks.

Instruction fine tuning where all mdoel wrigyst are updated is knowna s **full fine-tuning**. 

Model after Instruction fine-tuning: **Instruct LLM**.

**Fine-tuning on a single task:** Only 500-1000 egs needed to finr-tune a single task.
Downside: **Catastrophic Forgetting:**  degrade perfomance on other tasks

Avoid by:
**fine-tune on multipl tasks:** requires (50-100) 1000 eges across many tasks 

**Parameter Efficient Fine-tuning (PEFT):** Set of technique ste preserves weights of original LLM and train sonlyu a small numbe rof task-specific adapter layers and parameters. 

**Multi-Task Fine-tuning:**

with **FLAN (Fine-tuned Language Net):**
set of instructions used to perfom intsruction fine-tuning

**LLM Evaluation - Metrics:**

**ROUGE (Recall Oriented Understudy for Jesting Evaluation ):** Assess quality of automatically generated summaries by comparijg them to human generated summaries.

**Recall**,**Precision**,**F1 Score**
**ROGUE-1,2 , ROGUE-L**


**BLEU (Bilingual Evaluation Understudy):** Algorithm evaluated to evaluate quality of machine translated text by comparing it to human generated translations.



