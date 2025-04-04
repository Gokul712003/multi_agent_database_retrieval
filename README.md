# Multi-Model SQL Database Agent

## Overview
This project implements a sophisticated SQL database agent system that leverages multiple large language models (LLMs) to execute SQL queries in parallel and compare their results. The system connects to a MySQL database and uses LangGraph to orchestrate the execution flow across different LLM providers.Scalable -> can add more models which have tool calling support.

## Features
- **Multi-Model Architecture**: Simultaneously queries the database using four different LLMs:
  - Google Gemini 2.0
  - DeepSeek
  - Meta Llama 3.3 70B
  - NVIDIA Nemotron
- **Parallel Execution**: All models process the same query simultaneously to maximize efficiency
- **Comparison Framework**: Easily compare responses from different models for evaluation
- **SQL Database Integration**: Built-in tools for querying SQL databases with natural language

## Technologies Used
- **LangGraph**: For creating the execution flow graph and managing model states
- **LangChain**: For LLM integration and SQL database toolkit functionality
- **Large Language Models**:
  - Google Generative AI (Gemini)
  - DeepSeek
  - NVIDIA AI Endpoints (Llama 3.3 and Nemotron)
- **Database**: MySQL (using SQLAlchemy and PyMySQL)

## Project Structure
- `graph.ipynb`: Main implementation of the multi-model SQL agent using LangGraph
- `database_agent_tutorial.ipynb`: Tutorial and simpler implementation of SQL database agent

## Setup Instructions

### Prerequisites
- Python 3.8+
- MySQL database
- API keys for:
  - Google AI (Gemini)
  - DeepSeek
  - NVIDIA AI Endpoints

### Installation
1. Clone this repository: 
git clone https://github.com/Gokul712003/multi_agent_database_retrieval.git cd multi-model-sql-agent


2. Install required packages:
pip install langgraph langchain-google-genai langchain-deepseek langchain-nvidia-ai-endpoints pip install langchain-community sqlalchemy pymysql python-dotenv

3. Create a `.env` file with your API keys:
GOOGLE_API_KEY=your_google_api_key 
DEEPSEEK_API_KEY=your_deepseek_api_key 
NVIDIA_API_KEY=your_nvidia_api_key

get nvidia api key from here : https://build.nvidia.com/models


4. Set up your MySQL database:
- Create a database named `retail_sales_db`
- Update the database credentials in the notebooks if needed

## Usage

### Multi-Model Agent
Run the `graph.ipynb` notebook to use the multi-model agent. Example query:
```python
response = await graph.ainvoke({'messages':"How many male and female from age 19 in the sales table"}, config=config)
```
This will execute the query using all four models in parallel and return their responses.

Single Model Agent
For simpler usage with just one model, use the database_agent_tutorial.ipynb notebook:
```python
response = gemini_agent.invoke({'messages':"Can you tell me which product is the costliest?"})
```

Database Schema
The system works with a retail sales database (retail_sales_db) containing information about products, customers, sales, etc.

Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

License
OPEN SOURCE HAVE FUN!!!!!!!!! ```
