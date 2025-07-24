**LLMs:**

GPT, BERT, LLaMa, FLAN-T5, BLOOM, PaLM

**Tasks:** Essay Writer, Summarization, Translation, Code Generation, Entity Extraction

**Transformers:**

- Scale Efficiently
- Parallel Process
- Attention to input meaning

Learn relevance and context of all words in a sentence.

**Transformer Architecture:**

The Transformer architecture consists of an encoder and a decoder, each of which is composed of several layers. Each layer consists of two sub-layers: **a multi-head self-attention mechanism and a feed-forward neural network**. The multi-head self-attention mechanism allows the model to attend to different parts of the input sequence, while the feed-forward network applies a point-wise fully connected layer to each position separately and identically.

The Transformer model also uses **residual connections and layer normalization** to facilitate training and prevent overfitting. In addition, the authors introduce a **positional encoding scheme** that encodes the position of each token in the input sequence, enabling the model to capture the order of the sequence without the need for recurrent or convolutional operations.

**Encoder:**

Encodes input sequences into a deep representation of structure and meaning of input.

**Decoder:**

Uses encoder's contextual understanding to generate new tokens.

**Encoder only Model:** Understanding tasks where input and output are aligned in length. Tasks like POS Tagging, NER, etc. **Bert**

**Encoder Decoder Model:** Tasks where input and output can be of different lengths like Translation. **Bart, T5**

**Decoder Only Models:**  Used for generative tasks where the model produces output tokens one-by-one, such as text generation, summarization, or chatbots. **GPT, BLOOM, Jurassic, LLaMa**

**Types of Attention:**

**Self-Attention:** Each token attends to other tokens in same sequence.
**Cross-Attention:** Decoder attends to encoder's output.
**Multi-Headed Attention:** Multiple attention heads capture different patterns like subject-verb pairs, long range dependencies, punctuation or sentence structure.

**Residual Connection:**

Technique used in deep neural networks (including Transformers) to help with training by **adding the input of a layer back to its output**.

**Output = x + F(x)**

- Prevents vanishing gradients.
- Preserve original information from earlier layers.
- Eases training.

**Transformer in Machine Translation**:

1. **Encoder** reads the input sentence and converts it into a **context-representation** using **self-attention**.

2. **Decoder** generates translated sentence one token at a time using:
- Encoder's output (via **Cross-Attention**)
- Previously generated tokens (via **Self-Attention**)

1. This continues until a special "end" token is predicted.

**In-Context Learning:** Providing examples inside context window

**Encodi**


