# ChatDB — Natural Language Interface for SQL and NoSQL Databases

ChatDB is an interactive database query assistant that helps users explore SQL and NoSQL databases through natural language inputs.

The system allows users to upload datasets, generate example queries, translate simple natural language requests into database queries, and execute them against MySQL or MongoDB backends. It was developed as a database systems project with a focus on query generation, database integration, and user-friendly data exploration.

---

## Overview

Traditional database systems require users to understand query languages such as SQL or MongoDB aggregation syntax. ChatDB reduces this barrier by providing a natural-language-driven interface for querying structured and semi-structured data.

The application supports two major database workflows:

- **SQL Workflow:** Dataset upload, MySQL database setup, sample SQL query generation, and natural language query matching.
- **NoSQL Workflow:** MongoDB database / collection management, JSON dataset upload, natural language intent parsing, and aggregation pipeline construction.

This project demonstrates how natural language processing techniques can be integrated with database systems to improve data accessibility.

---

## Key Features

- Natural language interface for SQL and NoSQL query generation
- MySQL integration for relational datasets
- MongoDB integration for document-based datasets
- Dataset upload support for CSV and JSON files
- Template-based example query generation
- Intent and keyword matching for query interpretation
- MongoDB aggregation pipeline construction
- Interactive command-line workflow
- Modular architecture separating SQL, NoSQL, NLP, and utility components

---

## Tech Stack

- **Language:** Python
- **Databases:** MySQL, MongoDB
- **Libraries:** PyMySQL, PyMongo, Pandas, NLTK, BSON, Requests
- **Concepts:** Natural language processing, query generation, database systems, SQL, NoSQL, aggregation pipelines

---

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
        |
        v
Formatted Results

---

## Project Structure

```text
ChatDB/
├── main.py                  # Entry point and application workflow
├── set_up_db.py             # MySQL setup, connection, and dataset upload
├── sample_queries.py        # SQL sample query generation
├── nlp_matching.py          # SQL-side natural language matching
├── database_layer.py        # MongoDB database-level interface
├── collection_layer.py      # MongoDB collection-level interface
├── operation_layer.py       # NoSQL operation workflow and user interaction
├── nosql_functions.py       # MongoDB utility operations
├── keywords.py              # MongoDB aggregation keyword / stage handling
├── nlp_processor.py         # NoSQL natural language processing logic
├── example_generator.py     # NoSQL example query generation
├── utils.py                 # Utility functions for type and column analysis
└── datasets/                # Sample CSV and JSON datasets
```

---

## SQL Workflow

The SQL component supports relational data exploration through MySQL.

Main capabilities:

* Connect to a MySQL server
* Upload CSV datasets into SQL tables
* Generate sample SQL queries
* Match natural language input to predefined SQL query patterns
* Execute SQL queries and return results

Example use cases:

* Query sales records from a coffee shop dataset
* Explore product or quality-related CSV datasets
* Generate simple `SELECT`, `WHERE`, and aggregation-style queries

---

## NoSQL Workflow

The NoSQL component supports document-based data exploration through MongoDB.

Main capabilities:

* Create and select MongoDB databases
* Create and select collections
* Upload JSON datasets
* Generate example MongoDB queries
* Parse natural language input into query intent
* Build MongoDB query or aggregation pipelines
* Execute queries and return results

Supported MongoDB-style operations include:

* `find`
* `match`
* `group`
* `sort`
* `lookup`
* `project`

---

## Datasets

The project includes sample datasets for both SQL and NoSQL workflows.

### SQL / CSV datasets

* `coffee_shop_sale.csv`
* `grape_quality.csv`
* `banana_quality.csv`

### NoSQL / JSON datasets

Retail order dataset:

* `products.json`
* `users.json`
* `orders.json`
* `reviews.json`
* `categories.json`

Additional datasets:

* `countries-table.json`
* `property_level.json`

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/BrianChen29/ChatDB.git
cd ChatDB
```

---

### 2. Install dependencies

```bash
pip install pymysql pymongo pandas nltk bson requests
```

Depending on your environment, you may also need:

```bash
pip install mysql-connector-python
```

---

### 3. Start MySQL

On Linux:

```bash
sudo service mysql start
```

On other platforms, follow the official MySQL setup guide.

---

### 4. Start MongoDB

On Ubuntu:

```bash
sudo service mongod start
```

On macOS with Homebrew:

```bash
brew services start mongodb-community
```

---

### 5. Run ChatDB

```bash
python main.py
```

or

```bash
python3 main.py
```

---

## Example User Flow

```text
1. Start the ChatDB application.
2. Choose SQL or NoSQL mode.
3. Upload or select a dataset.
4. Enter a natural language query.
5. ChatDB matches the intent and generates a database query.
6. The query is executed against MySQL or MongoDB.
7. Results are displayed to the user.
```

Example natural language requests:

```text
Show me all coffee sales in January.
Find products with high review ratings.
Group orders by customer.
Sort countries by population.
Find properties above a certain price level.
```

---

## What I Learned

Through this project, I gained hands-on experience in:

* Designing a modular database application
* Connecting Python applications with MySQL and MongoDB
* Translating natural language patterns into structured database operations
* Building query-generation logic for both SQL and NoSQL systems
* Working with CSV and JSON datasets
* Structuring a command-line workflow for interactive data exploration

---

## Future Improvements

Potential improvements include:

* Add a web-based interface with Streamlit or FastAPI
* Improve natural language understanding with LLM-based query generation
* Add schema-aware query validation
* Support more complex SQL joins and nested MongoDB queries
* Add query explanation to help users learn SQL and NoSQL syntax
* Add automated tests for query generation and database operations
* Containerize the application with Docker

---

## Repository Context

This project was originally developed as a USC database systems final project and later refined as part of my AI / data systems portfolio.

Its main focus is on combining natural language processing, database systems, and query-generation workflows to make structured data more accessible.
