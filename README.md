# Specification for Project 5 SQL Module

## Overview

Project 5 integrates Python and SQL,
focusing on database interactions using SQLite.
This project introduces logging,
a useful tool for debugging and monitoring projects,
and involves creating and managing a database, building a schema, and performing various SQL operations,
including queries with joins, filters, and aggregations.

## Deliverable Names

- GitHub Repository:  **datafun-05-sql**
- Documentation:      README.md
- Script:             yourname_sql.py

Create a new GitHub repository with a README.md and a Python script with the specified name.

## Version Control with Git

Use Git for version control.
Document your workflow for managing the project in your README.md.

## Objective

Create a Python script that demonstrates the ability to interact with a SQL database,
including creating a database, defining a schema, and executing various SQL commands.
Incorporate logging to document the process and provide user feedback.

### 1. Environment Setup

1. Create and activate a project virtual environment.
1. Install all required packages into your local project virtual environment.
1. After installing the required dependencies, generate a requirements.txt file.
1. Document the process and commands you used in your README.md.
1. Add a .gitignore file to your project with useful entries.

### 2. Project Start

Create a docstring with a brief introduction to your project.

### 3. Import Dependencies

Import the required dependencies, following the conventional order.

### 4. Logging

Logging is recommended for all script and notebook projects.
Implement logging to enhance debugging and maintain a record of program execution.

1. Configure logging to write to a file named log.txt.
1. Log the start of the program using logging.info().
1. Log the end of the program using logging.info().
1. Log exceptions using logging.exception().
1. Log other major events using logging.info().
1. Log the start and end of major functions using logging.debug().

For example:

```python
import logging

# Configure logging to write to a file, appending new logs to the existing file
logging.basicConfig(filename='log.txt', level=logging.DEBUG, filemode='a', format='%(asctime)s - %(levelname)s - %(message)s')

logging.info("Program started")
logging.info("Program ended")
```

### 5. Database Creation and Schema Design

Create a new SQLite database file.
Design a schema with at least two related tables, including foreign key constraints.
Document the schema design in your README.md.
Keep each SQL statement in a separate file.

### 6. SQL Operations

Implement SQL statements and queries to perform table creation, data insertion,
data querying (with filters, sorting, and joining tables),
data aggregation, and record update and deletion.

Include the following SQL files:

1. create_tables.sql - create your database schema.
2. insert_records.sql - insert at least 10 records into each table.
3. update_records.sql - update 1 or more records in a table.
4. delete_records.sql - delete 1 or more records from a table.
5. query_aggregation.sql - use aggregation functions including COUNT, AVG, SUM.
6. query_filter.sql - use WHERE to filter data based on conditions.
7. query_sorting.sql - use ORDER BY to sort data.
8. query_group_by.sql - use GROUP BY clause (and optionally with aggregation)
9. query_join.sql - use INNER JOIN operation and optionally include LEFT JOIN, RIGHT JOIN, etc.

### 7. Python and SQL Integration

Use Python to interact with the SQL database and execute SQL commands:

```python
import sqlite3

def execute_sql_from_file(db_filepath, sql_file):
    with sqlite3.connect(db_filepath) as conn:
        with open(sql_file, 'r') as file:
            sql_script = file.read()
        conn.executescript(sql_script)
        print(f"Executed SQL from {sql_file}")

```

### 8. Define Main Function

Implement a main() function to execute the project logic.

```python
def main():
    db_filepath = 'your_database.db'

    # Create database schema and populate with data
    execute_sql_from_file(db_filepath, 'create_tables.sql')
    execute_sql_from_file(db_filepath, 'insert_records.sql')
    execute_sql_from_file(db_filepath, 'update_records.sql')
    execute_sql_from_file(db_filepath, 'delete_records.sql')
    execute_sql_from_file(db_filepath, 'query_aggregation.sql')
    execute_sql_from_file(db_filepath, 'query_filter.sql')
    execute_sql_from_file(db_filepath, 'query_sorting.sql')
    execute_sql_from_file(db_filepath, 'query_group_by.sql')
    execute_sql_from_file(db_filepath, 'query_join.sql')

    logging.info("All SQL operations completed successfully")

```

### 9. Conditional Script Execution

Ensure the main function only executes when the script is run directly,
not when imported as a module by using standard boilerplate code.

## Module Design

- Include a docstring at the top of the file describing its purpose.
- The code should be clear, well-organized, and demonstrate good practices.
- Include comments and docstrings for clarity.

## Evaluation Criteria

- Functionality: The project should be functional and meet all requirements.
- Documentation: The project should be well-written and well-documented.
- Presentation: The project should be presented in a clear and organized manner.
- Professionalism: The project should be submitted on-time and reflect an original, creative effort.

See rubric for additional information.
