# SOVEREREIGN-chain Copilot Instructions

## Project Overview
This is a LangChain experimentation template providing Jupyter notebook examples for core LangChain concepts. The project demonstrates building LLM-powered applications using OpenAI/Azure OpenAI APIs.

## Architecture
- **Framework**: LangChain for orchestrating LLM interactions
- **LLM Providers**: OpenAI API and Azure OpenAI Service
- **Vector Storage**: FAISS for document embeddings and similarity search
- **Tools**: Custom tools for agents (e.g., web search via SerpAPI)
- **Execution Environment**: Jupyter notebooks in Python 3.11 dev container

## Key Components
- `demo.ipynb`: Basic LLM API verification and simple prompts
- `chains.ipynb`: Prompt templates and LLMChain composition
- `embeddings.ipynb`: Text embedding generation and usage
- `agents.ipynb`: ReAct agents with tools and memory
- `faissdemo.ipynb`: Document loading, chunking, and vector similarity search
- `azure-oai.ipynb`: Direct Azure OpenAI API usage examples

## Setup Workflow
1. Create `.env` file in project root
2. For OpenAI: `OPENAI_API_KEY="<your-key>"`
3. For Azure: Add `OPENAI_API_BASE`, `OPENAI_API_TYPE="azure"`, `OPENAI_API_VERSION="2023-05-15"`
4. Run `pip install -r requirements.txt` (handled by dev container postCreateCommand)
5. Execute notebooks in order: demo → chains → embeddings → agents → faissdemo

## Coding Patterns
- **Environment Loading**: Always start cells with `from dotenv import load_dotenv; load_dotenv('.env', override=True)`
- **LLM Initialization**: Use `OpenAI(temperature=0.9)` for basic calls, `AzureChatOpenAI(deployment_name="gpt-35-turbo-16k", model_name="gpt-35-turbo-16k")` for Azure
- **Embeddings**: `OpenAIEmbeddings()` for generating vector representations
- **Chains**: Combine prompts via `PromptTemplate.from_template()` and `LLMChain(llm=llm, prompt=prompt)`
- **Agents**: Use `hub.pull("hwchase17/react")` for ReAct prompts, `AgentExecutor` with tools and memory
- **Vector Stores**: Load documents with `TextLoader`, split with `CharacterTextSplitter(chunk_size=1000)`, create FAISS index with `FAISS.from_documents()`

## Integration Points
- **Azure OpenAI**: Requires specific deployment names and API versions in .env
- **SerpAPI**: For web search tools in agents (needs SERPAPI_API_KEY)
- **FAISS**: Local vector storage, persists to disk as index files
- **LangChain Hub**: Pulls prompt templates like "hwchase17/react" for agents

## Development Workflow
- Work in Jupyter notebooks for experimentation
- Test API connectivity first with demo.ipynb
- Use `state_of_the_union.txt` as sample document for vector store demos
- Debug API issues by checking .env configuration and Azure deployment settings
- For production, convert notebook logic to Python scripts/modules

## Common Issues
- "Resource not found": Check Azure deployment name and API version in .env
- Import errors: Ensure all packages from requirements.txt are installed
- API key errors: Verify .env file exists and keys are valid
- FAISS errors: Confirm embeddings model is available (especially for Azure)</content>
<parameter name="filePath">/workspaces/SOVEREREIGN-chain/.github/copilot-instructions.md