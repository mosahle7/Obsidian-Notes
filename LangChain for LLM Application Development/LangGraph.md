
**Agents**

**Many kind of Agents:** 
**Router:**  LLM controls a single step in a flow.
**Fully Autonomous:** Pick any seq of steps.

**LangGraph**: build agents that maintain reliability even with high level of control given to LLM or agent.

**Pillars:**

Persistence
Streaming
Human-in-the-loop
Controllability

**State:** A shared DS that represents current snapshot of app. It is defined using a shared state schema.

**Nodes:** Functions that encode logic of agents. 

**Edges:** Functions that determine which Node to execute next based on current state. Conditional or Fixed.

