# Building-Advanced-RAG-With-Multiple-Data-Source-Using-Langchain
Building Advanced RAG With Multiple Data Source Using Langchain
### Will create agents in this project
Project Summary
![image](https://github.com/user-attachments/assets/03d25b41-79de-4654-aa8e-3e1081317a3b)



So here if the answer to query is not present in pdf, then through various TOOLS we will retrieve info from wiki and arxiv


Agents
By themselves, language models can't take actions - they just output text. A big use case for LangChain is creating agents. Agents are systems that use an LLM as a reasoning engine to determine which actions to take and what the inputs to those actions should be. The results of those actions can then be fed back into the agent and it determine whether more actions are needed, or whether it is okay to finish.

LangGraph is an extension of LangChain specifically aimed at creating highly controllable and customizable agents. Please check out that documentation for a more in depth overview of agent concepts.

There is a legacy agent concept in LangChain that we are moving towards deprecating: AgentExecutor. AgentExecutor was essentially a runtime for agents. It was a great place to get started, however, it was not flexible enough as you started to have more customized agents. In order to solve that we built LangGraph to be this flexible, highly-controllable runtime.

If you are still using AgentExecutor, do not fear: we still have a guide on how to use AgentExecutor. It is recommended, however, that you start to transition to LangGraph. In order to assist in this, we have put together a transition guide on how to do so.

ReAct agents
One popular architecture for building agents is ReAct. ReAct combines reasoning and acting in an iterative process - in fact the name "ReAct" stands for "Reason" and "Act".

The general flow looks like this:

The model will "think" about what step to take in response to an input and any previous observations.
The model will then choose an action from available tools (or choose to respond to the user).
The model will generate arguments to that tool.
The agent runtime (executor) will parse out the chosen tool and call it with the generated arguments.
The executor will return the results of the tool call back to the model as an observation.
This process repeats until the agent chooses to respond.
There are general prompting based implementations that do not require any model-specific features, but the most reliable implementations use features like tool calling to reliably format outputs and reduce variance.

Please see the LangGraph documentation for more information, or this how-to guide for specific information on migrating to LangGraph.

