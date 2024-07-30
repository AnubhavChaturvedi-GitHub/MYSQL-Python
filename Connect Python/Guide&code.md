# Connecting Python to SQL Databases

## Prerequisites

Before proceeding, ensure you have the necessary modules installed:

### Install `sqlite3`
```bash
pip install db-sqlite3
```

### Install `pyodbc`
```bash
pip install pyodbc
```

### Install `pymysql`
```bash
pip install pysql
```

---

## 1. Using `sqlite3` for SQLite

### Code Example

```python
import sqlite3

# Connect to the SQLite database
conn = sqlite3.connect('example.db')

# Create a cursor object
cursor = conn.cursor()

# Execute a simple query
cursor.execute('''CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, name TEXT)''')

# Insert a record
cursor.execute('''INSERT INTO users (name) VALUES (?)''', ('Anubhav',))

# Commit the changes
conn.commit()

# Fetch all records
cursor.execute('''SELECT * FROM users''')
rows = cursor.fetchall()
for row in rows:
    print(row)

# Close the connection
conn.close()
```

---

## 2. Using `pyodbc` for SQL Server

### Code Example

```python
import pyodbc

# Define the connection string
conn_str = (
    r'DRIVER={ODBC Driver 17 for SQL Server};'
    r'SERVER=server_name;'
    r'DATABASE=database_name;'
    r'UID=username;'
    r'PWD=password'
)

# Connect to the SQL Server database
conn = pyodbc.connect(conn_str)

# Create a cursor object
cursor = conn.cursor()

# Execute a simple query
cursor.execute('CREATE TABLE IF NOT EXISTS users (id INT PRIMARY KEY, name NVARCHAR(50))')

# Insert a record
cursor.execute('INSERT INTO users (id, name) VALUES (?, ?)', (1, 'Anubhav'))

# Commit the changes
conn.commit()

# Fetch all records
cursor.execute('SELECT * FROM users')
rows = cursor.fetchall()
for row in rows:
    print(row)

# Close the connection
conn.close()
```

---

## 3. Using `pymysql` for MySQL

### Code Example

```python
import pymysql

# Connect to the MySQL database
conn = pymysql.connect(
    host='localhost',
    user='username',
    password='password',
    database='database_name'
)

# Create a cursor object
cursor = conn.cursor()

# Execute a simple query
cursor.execute('CREATE TABLE IF NOT EXISTS users (id INT PRIMARY KEY, name VARCHAR(50))')

# Insert a record
cursor.execute('INSERT INTO users (id, name) VALUES (%s, %s)', (1, 'Anubhav'))

# Commit the changes
conn.commit()

# Fetch all records
cursor.execute('SELECT * FROM users')
rows = cursor.fetchall()
for row in rows:
    print(row)

# Close the connection
conn.close()
```
