# ChatDB: Natural Language Interface for SQL and NoSQL Databases

ChatDB is an interactive database query assistant that helps users explore SQL and NoSQL databases through natural language inputs.

The system supports dataset upload, example query generation, simple natural-language-to-query matching, and query execution against MySQL and MongoDB backends. It was originally developed as a USC database systems final project and later refined as an AI / data systems portfolio project.

## Overview

Traditional database systems require users to understand query languages such as SQL or MongoDB aggregation syntax. ChatDB reduces this barrier by providing a command-line workflow where users can select a database backend, inspect available datasets, ask query-like natural language questions, and view generated query results.

The application supports two database workflows:

- **SQL workflow:** CSV upload, MySQL database setup, sample SQL query generation, and natural language query matching.
- **NoSQL workflow:** MongoDB database and collection management, JSON upload, natural language intent parsing, and aggregation pipeline construction.

This project demonstrates how natural language processing techniques can be integrated with database systems to make structured and semi-structured data easier to query.

## Key Features

- Natural language interface for SQL and NoSQL query generation
- MySQL integration for relational datasets
- MongoDB integration for document-based datasets
- CSV and JSON dataset upload support
- Template-based example query generation
- Intent and keyword matching for query interpretation
- MongoDB aggregation pipeline construction
- Interactive command-line workflow
- Modular components for database setup, NLP processing, query generation, and execution

## Tech Stack

- **Language:** Python
- **Databases:** MySQL, MongoDB
- **Libraries:** PyMySQL, PyMongo, Pandas
- **Concepts:** natural language processing, query generation, database systems, SQL, NoSQL, aggregation pipelines

## System Architecture

```text
User Natural Language Input
        |
        v
NLP Processing / Intent Matching
        |
        v
Query Generation Layer
        |
        +--------------------+
        |                    |
        v                    v
   SQL Workflow          NoSQL Workflow
   MySQL                 MongoDB
        |                    |
        v                    v
Query Execution        Aggregation / Query Execution
        |                    |
        v                    v
Formatted Results      Formatted Results
```

## Project Structure

```text
ChatDB/
|-- main.py                  # Entry point and application workflow
|-- set_up_db.py             # MySQL setup, connection, and CSV upload
|-- sample_queries.py        # SQL sample query generation and execution helpers
|-- nlp_matching.py          # SQL-side natural language matching
|-- database_layer.py        # MongoDB database-level interface
|-- collection_layer.py      # MongoDB collection-level interface
|-- operation_layer.py       # NoSQL operation workflow and user interaction
|-- nosql_functions.py       # MongoDB utility operations
|-- keywords.py              # MongoDB aggregation stage helpers
|-- nlp_processor.py         # NoSQL natural language intent parsing
|-- example_generator.py     # NoSQL example query generation
|-- utils.py                 # Field type and collection analysis utilities
|-- requirements.txt         # Python dependencies
`-- datasets/                # Sample CSV and JSON datasets
```

## Workflows

### SQL Workflow

The SQL component supports relational data exploration through MySQL.

Main capabilities:

- Connect to a MySQL server
- Create or select databases
- Upload CSV datasets into SQL tables
- Generate sample SQL queries
- Match natural language inputs to SQL query patterns
- Execute generated SQL queries and display results

Supported SQL-style operations include:

- `SELECT`
- `WHERE`
- `GROUP BY`
- `HAVING`
- `ORDER BY`
- Basic aggregation queries

### NoSQL Workflow

The NoSQL component supports document-based data exploration through MongoDB.

Main capabilities:

- Create or select MongoDB databases
- Create or select collections
- Upload JSON datasets
- Generate example MongoDB queries
- Parse natural language input into query intent
- Build MongoDB query or aggregation pipelines
- Execute generated queries and display results

Supported MongoDB-style operations include:

- `find`
- `match`
- `group`
- `sort`
- `lookup`
- `project`

## Datasets

The repository includes sample datasets for both SQL and NoSQL workflows.

### SQL / CSV

- `coffee_shop_sales.csv`
- `pizza_sales.csv`
- `grape_quality.csv`
- `banana_quality.csv`

### NoSQL / JSON

Retail order dataset:

- `products.json`
- `users.json`
- `orders.json`
- `reviews.json`
- `categories.json`

Additional datasets:

- `countries-table.json`
- `property_level.json`
- `iris.json`

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/BrianChen29/ChatDB.git
cd ChatDB
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure database connections

ChatDB reads database connection settings from environment variables. The repository includes `.env.example` as a reference.

```bash
export MYSQL_HOST=localhost
export MYSQL_PORT=3306
export MYSQL_USER=root
export MYSQL_PASSWORD="your-mysql-password"
export MONGODB_URI="mongodb://localhost:27017/"
```

### 4. Start MySQL

On Linux:

```bash
sudo service mysql start
```

On other platforms, follow the official MySQL setup guide.

### 5. Start MongoDB

On Ubuntu:

```bash
sudo service mongod start
```

On macOS with Homebrew:

```bash
brew services start mongodb-community
```

### 6. Run ChatDB

```bash
python main.py
```

or:

```bash
python3 main.py
```

## Example User Flow

```text
1. Start ChatDB.
2. Choose SQL or NoSQL mode.
3. Select or create a database.
4. Select, create, or upload a table / collection.
5. Enter a natural language query or ask for example queries.
6. ChatDB maps the input to a SQL query or MongoDB operation.
7. The query executes against MySQL or MongoDB.
8. Results are displayed in the terminal.
```

Example requests:

```text
example of SQL query
example of GROUP BY
where price greater than 50
find all data
find price where rating > 4
total sales by category
average price by category
sort products by price descending
```

## What I Learned

Through this project, I gained hands-on experience in:

- Designing an interactive database application
- Connecting Python applications with MySQL and MongoDB
- Translating natural language patterns into structured database operations
- Building query-generation logic for SQL and NoSQL systems
- Working with CSV and JSON datasets
- Structuring command-line workflows for data exploration

## Future Improvements

Potential improvements include:

- Add a web-based interface with Streamlit or FastAPI
- Improve natural language understanding with LLM-based query generation
- Add schema-aware query validation
- Support more complex SQL joins and nested MongoDB queries
- Add query explanations to help users learn SQL and NoSQL syntax
- Add automated tests for query generation and database operations
- Containerize the application with Docker
