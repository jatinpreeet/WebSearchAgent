Created a LangGraph Web Search Agent that uses web search(Tavily) and wikipedia search to gather the context and answer on the basis of context. Used ChatGPT's 4o as the LLM .


  <img width="754" alt="Screenshot 2025-06-05 at 4 26 52 PM" src="https://github.com/user-attachments/assets/cae1b8f6-6455-420e-8270-896dbfbdad5b" />

LangGraph mermaid diagram explains the overall workflow on how the nodes are placed and how are they processed further


### get results from different web tools , and put all in the context , and after getting that context ask the llm to answer based on that context

We  have created in the state the three states: question:str , answer:str , context: Annotated[list , operator.add]  , here web search tools add to the context , and then for LLM answering based on the question and the context “ prompt like answer this {question} based on this {context}”

Search tool 1 + Search tool 2 + Search tool n ——> Context

Context ——> Answer using this {Context}
