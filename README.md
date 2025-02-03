# Natural Language to SQL using Local LLM and Agents

This project demonstrates how to leverage Large Language Models (LLMs) to convert natural language queries into SQL statements and execute them on a MySQL database. It showcases the power of LLMs combined with an agent-based decision-making system and toolkits to provide an end-to-end solution for natural language interaction with databases.

## Key Features

- **Local LLM Inference**: This project runs on a local instance of the Llama 3.2 model using [Ollama](https://ollama.ai/), ensuring privacy and control over the AI model.
- **Agent-based Decision Making**: An agent is responsible for understanding user queries, selecting the appropriate actions, and deciding how to interact with the database.
- **SQL Toolkit**: The toolkit bridges the gap between the agent and the database, enabling query execution while ensuring security and efficiency.
- **Prompt Engineering**: A section of the notebook is dedicated to prompt engineering techniques, optimizing interactions between the user and the LLM for accurate SQL generation.

## Getting Started

### Prerequisites

Ensure you have the following installed:

- [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/)
- [Ollama](https://ollama.ai/)
- Python 3.x (recommended: latest stable version)

### Setup

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd <repository-name>
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

1. **User Input**: The user provides a natural language question, e.g., _"How many employees are there in the company?"_.
2. **LLM Processing**: The local Llama 3.2 model, running on Ollama, interprets the query.
3. **Agent Decision Making**: The agent determines the appropriate SQL query required to answer the question.
4. **SQL Toolkit Execution**: The SQL toolkit converts the structured query into an actual SQL command and executes it on the MySQL database.
5. **Response Generation**: The results are returned to the user in a readable format.

## SQL Toolkit

The SQL toolkit serves as the intermediary between the agent and the database. It ensures the following:

- Query validation and sanitization to prevent SQL injection.
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
