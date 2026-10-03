# AI Math Assistant: LangChain Tool Calling with Ollama

A small project showing how an AI agent can call tools to add numbers, using LangChain and a local `llama3.1:8b` model through Ollama. No API keys needed.

## What it covers
- Creating tools with the `Tool` constructor and the `@tool` decorator
- A multi-input tool (`add_numbers_with_options`)
- Building an agent with `create_agent`

## Setup
```bash
ollama pull llama3.1:8b
pip install "langchain>=1.0" langchain-ollama langchain-community jupyter
jupyter notebook AI-Math-Assistant_Tool_Calling_Ollama.ipynb
```
Make sure the Ollama server is running, then run the cells from top to bottom.

## Example
```python
llm = ChatOllama(model="llama3.1:8b", temperature=0)
agent = create_agent(model=llm, tools=[add_numbers_with_options])
agent.invoke({"messages": [("human", "Add -10, -20, and -30 using absolute values.")]})
```

## Note
Small local models can sometimes pass tool arguments in an unexpected type. Re-run the cell if the output looks off.
