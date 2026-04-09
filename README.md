# AI LangGraph Agents

A collection of AI agent projects built with [LangGraph](https://github.com/langchain-ai/langgraph).

Organized into modules covering progressively advanced topics — from basic graphs and chains to memory, human-in-the-loop, sub-graphs, and deployment.

Each module folder contains Jupyter notebooks and a `studio` subdirectory with graphs for use with LangGraph Studio.

## Setup

### Python version

Requires Python 3.11, 3.12, or 3.13.

### Install dependencies

```
uv sync
```

### Install pre-commit hooks

```
uv run python -m pre_commit install
```

### Running notebooks

```
uv run jupyter notebook
```

### Environment variables

Set the following API keys in your environment:

```bash
export OPENAI_API_KEY="your-api-key-here"
export LANGSMITH_API_KEY="your-api-key-here"
export LANGSMITH_TRACING_V2="true"
export TAVILY_API_KEY="your-api-key-here"
```

* [OpenAI API key](https://openai.com/index/openai-api/)
* [LangSmith](https://docs.langchain.com/langsmith/create-account-api-key#create-an-account-and-api-key)
* [Tavily Search API](https://tavily.com/) (used in Module 4)

### LangGraph Studio

Studio can be run locally for viewing and testing agents. Graphs are in `module-x/studio/` folders.

```
cd module-x/studio
uv run langgraph dev
```

Create `.env` files for each module's studio directory:

```bash
for i in {1..5}; do
  cp module-$i/studio/.env.example module-$i/studio/.env
  echo "OPENAI_API_KEY=\"$OPENAI_API_KEY\"" > module-$i/studio/.env
done
echo "TAVILY_API_KEY=\"$TAVILY_API_KEY\"" >> module-4/studio/.env
```
