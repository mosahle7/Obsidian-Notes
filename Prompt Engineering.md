**Prompt Engineering Parameters:**

**Temperature**: controls randomness. Increasing the weights of other possible tokens.

**T<1 => Strongly peaked PD.**
**T>1 => Broader, Flatter PD.**

**Top P**: A sampling technique with temperature, called nucleus sampling. It chooses the smallest possible set of tokens whose cumulative probability adds up to top\_p. Alter temperature or Top P but not both.

**Max Length**: Limits the number of tokens. Prevents irrelevant response and control costs.

**Stop sequences**: String that stops the model from generating response. Controls length and structure.

**Frequency Penalty**: Applies a penalty on next token proportional to no of times already appeared in response and prompt. Reduces the repetition of words.

**Presence Penalty**: Applies penalty on repeated tokens, penalty is same for all repeated tokens. Prevents from repeating phrases too often.

**Top K**: Model chooses from only the k most probable next tokens instead of all tokens.


**Zero-shot prompting**:

Q: Question?

A:



Elements of a Prompt:



Instruction - a specific task or instruction you want the model to perform



Context - external information or additional context that can steer the model to better responses



Input Data - the input or question that we are interested to find a response for



Output Indicator - the type or format of the output.





**PROMPT ENGINEERING TECHNIQUES:**



1. Zero-Shot Prompting:



Prompt used to interact with the model won't contain examples or demonstrations. The zero-shot prompt directly instructs the model to perform a task without any additional examples to steer it.



2\. Few-Shot Prompting:



A technique to enable in-context learning where we provide demonstrations in the prompt to steer the model to better performance. 



3\. Chain-of-Thought Prompting:



Enables complex reasoning capabilities through intermediate reasoning steps.



**Automatic Chain-of-Thought (Auto-CoT):**



Auto-CoT is a method that automatically generates reasoning demonstrations for few-shot prompts by clustering questions and using zero-shot CoT to produce step-by-step answers — reducing the need for manual prompt engineering.



Auto-CoT consists of two main stages:



Stage 1): **question clustering**: partition questions of a given dataset into a few clusters

Stage 2): **demonstration sampling**: select a representative question from each cluster and generate its reasoning chain using Zero-Shot-CoT with simple heuristics





**4. Meta Prompting:**



Meta prompting is an advanced technique that focuses on the structure and syntactical aspect of a task instead of its specific content. It teaches the model how to think or respond by showing patterns, not just examples.



Key Characteristics:

1\. **Structure-oriented**

**2. Syntax-focused**

**3. Abstract examples:** Employs abstracted examples as frameworks

**4. Versatile**

**5. Categorical approach:**  breaking down a task into clearly labeled parts



Egs:


Example 1: **Teaching Format** (Not Specific Content):

When answering, always use this structure:

**Problem**

**Reasoning**

**Final Answer**


Example 2**: Pattern-Based QA**

**"All answers should be short, direct, and end with a one-word summary in caps."**



**Example 3: Abstract Template:**

"Here’s how to respond to any question:

Step 1: Rephrase the question

Step 2: Think step by step

Step 3: Give a confident answer"



**Advs of Meta Over Few Shot:**


1. **Token Efficiency**
2. **Fair Comparison**
3. **Zero-shot efficacy**





**5. Self-Consistency:**  



Advanced prompt engineering technique. Instead of using just one step-by-step answer (like in standard Chain-of-Thought prompting), it generates multiple diverse reasoning paths and selects the most consistent answer. This replaces **basic greedy decoding**(model picks most likely next word at each step without exploring alternatives) and helps improve performance on tasks like arithmetic and commonsense reasoning.



Instead of using greedy decoding, Self-Consistency:

1. Samples multiple reasoning paths (e.g. 5–10 answers)

2\. Looks at all final answers

3\. Picks the most frequent (consistent) one


6. **Generated Knowledge Prompting:**
   
Technique where the model is asked to answer factual or widely known questions, relying on its built-in knowledge rather than reasoning or task-specific skills.

7. **Prompt Chaining:**

Method where you break a big task into smaller subtasks an d then its response is used as input to another prompt.

   

















