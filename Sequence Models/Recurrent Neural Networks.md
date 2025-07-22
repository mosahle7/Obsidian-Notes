
Speech Recognition, Music Generation, Sentiment Classification, DNA Sequence Analysis, Machine Translation, Video Activity Generation, Name Entity Recognition

Simple neural networks can't handle sequential data well because they lack memory and can't capture the order of inputs. They treat each input independently, which doesn't work for tasks where context or sequence matters (like language or time series). Models like RNNs or LSTMs are used instead because they maintain hidden states that remember previous inputs.

#### **RNN**:

Neural networks designed to process **sequential data** by maintaining a hidden state that captures information from **previous time steps**, allowing them to model **temporal dependencies**.

- Uses the o/p from previous unit
- Shared Parameters
- **Limitation**: Only uses the information that is earlier in sequence to make a prediction, not the information later in sequence, overcome by **BRNNs**.
- **AF**: tanh, ReLu for hidden layers.

- Backpropagation through time.

**Types:**
One to One, One to Many, Many to One, Many to Many (lengths are equal), Many to Many (lengths are unequal)

**Language modelling**:
Word-Level, Character-Level

**Limitations**:

Vanishing and exploding gradients happen in RNNs with very long sequences (many time steps), not necessarily large number of units.

**Vanishing Gradients**: RNNs not very good at capturing very long-term dependencies. When training RNNs, gradients are repeatedly multiplied by weights at each time step. If these weights are < 1, the gradients shrink exponentially, eventually becoming too small to update earlier layers. This prevents the network from learning long-term dependencies.

**Exploding Gradients**: If the weights are > 1, repeated multiplication causes gradients to grow rapidly, becoming extremely large. This makes training unstable, often leading to weight overflow or NaN values during backpropagation. **Gradient clipping** is a common solution: If gradient vectors are bigger than some threshold, clip it. 

- **Vanishing gradients → poor memory of long-term dependencies**
- **Exploding gradients → unstable training / divergence**


#### **Gate Recurrent Unit (GRU):**

Type of RNN that uses gates to control flow of information, helping it to capture long-term dependencies. It combines the **forget** and **input gates** into a single **update gate**, and also includes a **reset gate**.

**c** = candidate memory

**γᵤ (Update Gate):** Controls how much of the new candidate c~⟨t⟩ should replace the old memory.

| γᵤ Value       | Meaning                               |
| -------------- | ------------------------------------- |
| Close to **1** | **Update heavily** with new candidate |
| Close to **0** | **Keep most** of the previous memory  |

**γʳ (Reset Gate):** Controls how much of the past memory (previous hidden state) is used to compute the candidate.

|γʳ Value|Meaning|
|---|---|
|Close to **0**|**Forget past**, ignore previous memory|
|Close to **1**|**Use full past context**|

#### **Long Short Term Memory (LSTM):**

Type of RNN that uses gate and a memory cell to control the flow of information, allowing it to capture long-term dependencies. It includes a **forget gate, update/input gate, output gate and a dedicated memory cell** to retain important information across time steps.

|Gate|Notation|Purpose|
|---|---|---|
|**Forget Gate**|`Γ_f`|Decides what part of past memory (`cᵗ⁻¹`) to forget|
|**Input (Update) Gate**|`Γ_u`|Decides how much new information to add to memory|
|**Output Gate**|`Γ_o`|Decides what part of memory to output as hidden state `aᵗ`|

|Aspect|LSTM|GRU|
|---|---|---|
|**Gates**|3 gates: forget, input, output|2 gates: update, reset|
|**Memory**|Has a separate memory cell `c`|No separate memory — just hidden state|
|**Complexity**|More complex (more parameters)|Simpler (fewer parameters)|
|**Relation**|More flexible/powerful|GRU is a **simplified version of LSTM**|

#### **Bidirectional RNN:**

Extension of RNN that processes input data in both forward and backward directions using two hidden layers. It overcomes the limitation of RNNs in considering only past context in tasks where future context is also useful.

**Disadvantage:** Need entire sequence of data before making predictions.

#### **Deep RNNs:**

RNN with multiple stacked hidden layers, where output of one RNN layer is passed as input to the next. Used in tasks that require complex sequential pattern learning.


