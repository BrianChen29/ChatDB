# ChatDB

Final project for USC DSCI551

## Introduction

ChatDB is an interactive application designed to teach users how to query database systems (both SQL and NoSQL) using natural language inputs. It will act as a learning tool that provides example queries, allows users to run queries, and returns results from databases like MySQL (for SQL) and MongoDB (for NoSQL). The system can handle natural language inputs, generate SQL or NoSQL queries based on predefined patterns, and execute them, displaying results to the user. Users can also upload their datasets, which the system will store in databases and make available for querying. The project will integrate NLP capabilities with database systems to allow easy query generation and execution.

## Get Started

### Environment Setup

Requirements for Python Environment:
```
re
pymysql
pymongo
pandas
datetime
nltk
json
bson
requests
```

### MySQL

#### Set up MySQL server

Instalation: <https://dev.mysql.com/doc/mysql-getting-started/en/>

* Run MySQL server on Linux

    ```$ sudo service mysql start```

* Stop MySQL server on Linux

    ```$ sudo service mysql stop```

Note: Please follow the link above to access the instruction for different platforms usage.

### NoSQL

#### Set up NoSQL-MongoDB server

Installation

* On Ubuntu:

    <https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/>

* On MacOS:

    <https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-os-x/>

* On Windows:

    <https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-windows/>

Note: Please follow the link above to access the instruction for different platforms usage.

#### Run MongoDB server

Start the mongoDB service

* Ubuntu

    ```$ sudo service mongod start```

* MacOS (if using homebrew)
  
    ```$ brew service mongod start```

## Get Started with ChatDB

### Run ChatDB:

on terminal input:

```$ <python/python3> main.py```

<br>

### File Structure

chatdb/

* main.py: Entry point of the application, main function, initial settings and handling the work flow of the chatDB

SQL part/

* set_up_db.py: Database connection, set up database, user upload function
* sample_queries.py: Sample queries generation
* nlp_matching.py: Natural language matching

NoSQL part/

* database_layer.py: NoSQL database layer interface and user input handling
* collection_layer.py: NoSQL collection layer interface and user input handling
* operation_layer.py: NoSQL operation layer interface and user input handling, this layer also calls other actions, such as example generation and nlp process.
* nosql_functions.py: Simple nosql query functions, including create database, create collection, upload, find, and etc..
* keywords.py: MongoDB-specific query stages (match, group, sort, lookup, project) and build aggregatation pipeline
* utils.py: utility functions (type detection, column type classification, etc.)
* example_generator.py: Generates example queries with templates
* nlp_processor.py: Natural language process logic for parsing user input and intent-pattern matching  

<br>

### Datasets Discription

#### CSV file for SQL

* coffee_shop_sale.csv: data of coffee sales information
* grape_qulity.csv: data of grape quality identifier information
* banana_qulity.csv: data of banana quality identifier information

#### JSON file for NoSQL

* Orders folder: data of orders and other information of a retail store
  * products.json
  * users.json
  * orders.json
  * reviews.json
  * categories.json
* countries-table.json: data of different countries information
* property_level.json: data of property information