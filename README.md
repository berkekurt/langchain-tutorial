# LangChain for LLM Application Development

A comprehensive tutorial repository for learning LangChain, a framework for developing applications powered by language models. This repository contains hands-on lessons covering Ai agents.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/berkekurt/langchain-tutorial/blob/main/introduction.ipynb)

## 📚 Table of Contents

- [Installation](#installation)
- [Quickstart](#quickstart)
- [Repository Structure](#repository-structure)
- [Tutorial Content](#tutorial-content)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Resources](#resources)

## Installation

### Requirements

- Python 3.10 or higher

### Install LangChain

To install the core LangChain package:

```bash
pip install -U langchain
```

### Install Integrations

LangChain offers integrations with various language model providers. Install the integrations you need:

```bash
# OpenAI integration
pip install -U langchain-openai

# Anthropic integration
pip install -U langchain-anthropic

# Community integrations
pip install -U langchain-community

# Experimental features
pip install -U langchain-experimental
```

For a comprehensive list of available integrations, refer to the [LangChain Integrations documentation](https://docs.langchain.com/oss/python/integrations/providers/overview).

### Additional Dependencies

This tutorial repository also uses:

```bash
pip install python-dotenv openai requests
```

## Quickstart

### Basic Agent Example

Here's a simple example to get you started with LangChain agents:

```python
from langchain.agents import create_agent

def get_weather(city: str) -> str:
    """Get weather for a given city."""
    return f"It's always sunny in {city}!"

agent = create_agent(
    model="claude-sonnet-4-5-20250929",
    tools=[get_weather],
    system_prompt="You are a helpful assistant",
)

# Run the agent
result = agent.invoke(
    {"messages": [{"role": "user", "content": "what is the weather in sf"}]}
)
print(result)
```

### Real-World Agent Example

For a more comprehensive example with memory, structured output, and context, see the [LangChain Quickstart Guide](https://docs.langchain.com/oss/python/langchain/quickstart).

## Repository Structure

```
.
├── README.md
├── introduction.ipynb         # Tutorial notebook

```

## Tutorial Content

The `introduction.ipynb` notebook is structured as follows:

1. **Environment Setup**
   - Installing required packages
   - Configuring API keys
   - Setting up the development environment

2. **AI Agent Example**
   - Basic agent implementation
   - Introduction to LangChain agents
   - Simple tool usage

3. **Complex AI Agent Example**
   - Advanced agent features
   - Memory usage
   - Enhanced agent capabilities

## Prerequisites

Before starting, make sure you have:

1. **Python 3.10+** installed
2. **API Keys** for the language model providers you want to use:
   - [OpenAI API Key](https://platform.openai.com/account/api-keys)
   - [Anthropic API Key](https://www.anthropic.com/) (optional, for Claude models)

## Getting Started

1. **Clone this repository:**
   ```bash
   git clone https://github.com/berkekurt/langchain-tutorial.git
   cd langchain-tutorial
   ```

2. **Install dependencies:**
   ```bash
   pip install -U langchain langchain-openai langchain-core python-dotenv openai
   pip install langchain-openai langchain-community
   pip install langchain-experimental
   ```

3. **Set up environment variables:**
   
   Create a `.env` file in the root directory:
   ```bash
   OPENAI_API_KEY=your_openai_api_key_here
   ANTHROPIC_API_KEY=your_anthropic_api_key_here  # Optional
   ```

   Or use Python's `getpass` to securely input your API key:
   ```python
   from getpass import getpass
   api_key = getpass("Enter your OpenAI API key: ")
   ```

4. **Open the tutorial notebook:**
   
   Open `introduction.ipynb` to begin learning LangChain. The notebook contains how to set up the environment and 2 Ai agent examples. You can also click the "Open In Colab" badge at the top of this README to run it directly in Google Colab.

## Resources

### Official Documentation

- [LangChain Documentation](https://docs.langchain.com/oss/python/langchain/)
- [Installation Guide](https://docs.langchain.com/oss/python/langchain/install)
- [Quickstart Guide](https://docs.langchain.com/oss/python/langchain/quickstart)
- [LangChain Integrations](https://docs.langchain.com/oss/python/langchain/integrations)
- [LangSmith Documentation](https://docs.langchain.com/langsmith/) - For tracing and monitoring

### Recommended Learning Resources

- [LangChain Essentials - Python (LangChain Academy)](https://academy.langchain.com/courses/langchain-essentials-python) - Learn the core elements of LangChain including `create_agent`, messages, tools, MCP, streaming, structured outputs, and more.

- [LangChain for LLM Application Development (Coursera)](https://www.coursera.org/projects/langchain-for-llm-application-development-project) - A comprehensive course taught by Harrison Chase (CEO of LangChain) and Andrew Ng. This course covers pre-version 1 LangChain concepts and is an excellent starting point for learning LangChain fundamentals. Topics include models, prompts, parsers, memories, chains, Q&A over documents, and agents.

- [LangChain: Chat with Your Data (Coursera)](https://www.coursera.org/projects/langchain-chat-with-your-data-project) - Learn to build chatbots that interact with your own documents and data. Taught by Harrison Chase (CEO of LangChain), this course covers Retrieval Augmented Generation (RAG) and accessing various data sources using LangChain's 80+ unique loaders. This course also covers pre-version 1 concepts but provides valuable foundational knowledge.

### Additional Resources

- [LangChain GitHub Repository](https://github.com/langchain-ai/langchain)

## Notes

- **Model Variability**: LLMs do not always produce the same results. When executing code in the notebooks, you may get slightly different answers than shown in examples.
- **API Keys**: Never commit your API keys to version control. Always use environment variables or `.env` files (which should be in `.gitignore`).
- **Model Updates**: Some notebooks may reference specific model versions. Check the [OpenAI Models documentation](https://platform.openai.com/docs/models) for the latest available models.

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.

## License

This tutorial repository is for educational purposes. Please refer to LangChain's license for the framework itself.

---

**Happy Learning! 🚀**



