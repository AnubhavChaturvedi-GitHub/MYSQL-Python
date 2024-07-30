# Common SQL Commands

## Create Table
```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
    ...
);
```

## Insert Into Table
```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

## Select Data
```sql
SELECT column1, column2, ...
FROM table_name;
```

## Select with Conditions
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

## Update Data
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

## Delete Data
```sql
DELETE FROM table_name
WHERE condition;
```

## Join Tables
### Inner Join
```sql
SELECT column1, column2, ...
FROM table1
INNER JOIN table2
ON table1.common_column = table2.common_column;
```

### Left Join
```sql
SELECT column1, column2, ...
FROM table1
LEFT JOIN table2
ON table1.common_column = table2.common_column;
```

### Right Join
```sql
SELECT column1, column2, ...
FROM table1
RIGHT JOIN table2
ON table1.common_column = table2.common_column;
```

### Full Outer Join
```sql
SELECT column1, column2, ...
FROM table1
FULL OUTER JOIN table2
ON table1.common_column = table2.common_column;
```

## Group By
```sql
SELECT column1, COUNT(*)
FROM table_name
GROUP BY column1;
```

## Order By
```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC|DESC];
```

## Aggregate Functions
### COUNT
```sql
SELECT COUNT(column_name)
FROM table_name
WHERE condition;
```

### SUM
```sql
SELECT SUM(column_name)
FROM table_name
WHERE condition;
```

### AVG
```sql
SELECT AVG(column_name)
FROM table_name
WHERE condition;
```

### MIN
```sql
SELECT MIN(column_name)
FROM table_name
WHERE condition;
```

### MAX
```sql
SELECT MAX(column_name)
FROM table_name
WHERE condition;
```

## Alter Table
### Add Column
```sql
ALTER TABLE table_name
ADD column_name datatype;
```

### Drop Column
```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

### Modify Column
```sql
ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```

## Drop Table
```sql
DROP TABLE table_name;
```

