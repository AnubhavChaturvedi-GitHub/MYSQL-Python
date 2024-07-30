## There is three way to connect the python and SQl

## Before it must be install the modules
FOR First Code Need to install [sqlite3](https://pypi.org/project/db-sqlite3/)
```
pip install db-sqlite3
```
For second way to connect install [pyodbc](https://pypi.org/project/pyodbc/)
```
pip install pyodbc
```
for 3 and best code to connect need to install [pymysql](https://pypi.org/project/pysql/)
```
pip install pysql
```


### Using `sqlite3` for SQLite

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

### Using `pyodbc` for SQL Server

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

### Using `pymysql` for MySQL

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
