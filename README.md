# Natural Language to SQL using Local LLM and Agents

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![Ollama](https://img.shields.io/badge/Ollama-FF6F00?style=for-the-badge&logoColor=white) ![LLM](https://img.shields.io/badge/LLM-Powered-blue?style=for-the-badge) ![LangChain](https://img.shields.io/badge/LangChain-Agent-green?style=for-the-badge)

This project demonstrates how to leverage Large Language Models (LLMs) to convert natural language queries into SQL statements and execute them on a MySQL database. It showcases the power of LLMs combined with an agent-based decision-making system and toolkits to provide an end-to-end solution for natural language interaction with databases.

## Key Features

- **Local LLM Inference**: This project runs on a local instance of the Llama 3.2 model using [Ollama](https://ollama.ai/), ensuring privacy and control over the AI model.
- **Agent-based Decision Making**: An agent is responsible for understanding user queries, selecting the appropriate actions, and deciding how to interact with the database. The agent brings logic, reasoning, and decision-making capabilities, enabling the use of a simpler LLM like Llama 3.2 without requiring a more advanced reasoning-focused LLM like DeepSeek.
- **SQL Toolkit**: The toolkit bridges the gap between the agent and the database, enabling query execution while ensuring security and efficiency.
- **Template Prompt with Guardrails**: A structured prompt template ensures that the agent is restricted to read-only access. The agent can only retrieve information and is explicitly prevented from modifying, deleting, or altering any database records.
- **Prompt Engineering**: A section of the notebook is dedicated to prompt engineering techniques, optimizing interactions between the user and the LLM for accurate SQL generation.
![image](https://github.com/user-attachments/assets/5f9b5cf9-3c67-4ed6-a9f5-bcb1477d0cdd)

## The Role of the Agent

The agent is the core component that enables this project to function effectively with a simpler LLM like Llama 3.2. Here's how it works:

1. **Logic and Reasoning**: The agent handles the complex task of interpreting natural language queries and translating them into structured SQL commands. This removes the need for the LLM itself to have advanced reasoning capabilities.
2. **Decision Making**: The agent decides which actions to take based on the user's query, such as selecting the appropriate database table or column, and ensures the generated SQL query is accurate and efficient.
3. **Tool Integration**: The agent interacts with the SQL toolkit to execute queries and retrieve results, ensuring a seamless flow from natural language input to database output. Effectively, rendering expensive "Reasoning" models (e.g: Chat-GPT o1, Deepseek-R1, etc) useless. More bang for your buck!

By leveraging the agent's capabilities, this project demonstrates that even a simpler LLM like Llama 3.2 can be used effectively for complex tasks like natural language to SQL conversion, without requiring a more advanced reasoning-focused LLM.

## Getting Started

### Prerequisites
Ensure you have the following installed:
- [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/)
- [Ollama](https://ollama.ai/)
- Python 3.x (recommended: latest stable version)

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Nirerp/SQL_Agent.git
   cd SQL_Agent
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Start MySQL using Docker Compose:
   ```bash
   docker-compose up -d
   ```

4. Run the Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
   Open `mysql_agent.ipynb` and follow the steps in the notebook.

## How It Works

1. **User Input**: The user provides a natural language question, e.g., *"How many employees are there in the company?"*.
2. **LLM Processing**: The local Llama 3.2 model, running on Ollama, interprets the query.
3. **Agent Decision Making**: The agent determines the appropriate SQL query required to answer the question.
4. **SQL Toolkit Execution**: The SQL toolkit converts the structured query into an actual SQL command and executes it on the MySQL database.
5. **Response Generation**: The results are returned to the user in a readable format.
   ![image](https://github.com/user-attachments/assets/3e0e6086-d7bc-47ea-b2f4-55604c1810bf)


## SQL Toolkit

The SQL toolkit serves as the intermediary between the agent and the database. It ensures the following:
- Query validation and sanitization to prevent SQL injection.
- Read-only enforcement through a template prompt guardrail that restricts any modification, deletion, or alteration of data.
- Efficient execution of database queries.
- Proper formatting of query results for readability.

## Example Usage

### Input:
```
User: "What is the average salary of employees in the company?"
```

### LLM + Agent Output:
```
Generated SQL Query:
SELECT AVG(salary) FROM employees;
```

### Database Response:
```
The average salary of employees is $75,000.
```

## Future Enhancements
- Support for additional databases (e.g., PostgreSQL, SQLite).
- Integration with a web-based UI for ease of use.
- Advanced error handling and query optimization.

## Contributing
Contributions are welcome! Feel free to submit issues or pull requests to improve this project.

## License
This project is licensed under the MIT License.

---

For any inquiries or support, please reach out via GitHub Issues.

---

This version emphasizes the agent's role in enabling the use of a simpler LLM and highlights how it handles logic, reasoning, and decision-making. Let me know if you'd like further adjustments!
