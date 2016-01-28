###Relational Databases
- SQL (Structured Query Languages)
- SQLite, MySQL / MariaDB, Postgres, MSSQL, Oracle
- Big enterprises like to use MSSQL/Oracle
- sqlite data.db
- Need to be in table structure to insert data (predefine)
- Key words are ALL CAPS and case insensitive
```
sqlite> CREATE TABLE students (id INTEGER PRIMARY KEY AUTOINCREMENT,
first_name VARCHAR(50), last_name VARCHAR(50), email VARCHAR(255),
phone_number VARCHAR(25), bio TEXT);"
Quote Break
```
**Data Types**
- INTEGER, VARCHAR, TEXT, DECIMAL, FLOAT, BOOLEAN, DATETIME
- BOOLEAN: true, false, null
```
sqlite> ALTER TABLE students ADD COLUMN age INTEGER;
sqlite> DROP TABLE students;
```
- **CRUD**:Create, read, update and delete
```
sqlite> INSERT INTO students(first_name, last_name, email) VALUES ('Ryan', 'Ching', 'ryanching@hotmail.com');
```
- READ, select
```
sqlite> SELECT * FROM students;
```
- We will use READ a lot
```
sqlite> SELECT first_name, last_name FROM students;
Ryan|Ching
John|Smith
John|Smith
```
```
sqlite> SELECT * FROM students WHERE age > 25
2|John|Smith|john@smith.com|||45
3|John|Smith|john@smith.com|||45
```
- three-valued logic (3VL)
- IS NULL/IS NOT NULL
- ILIKE (case insensitive, Postgres)
```
SELECT * FROM students WHERE first_name ILIKE 'jo%';
```
- jo% partial words
- %nn% middle stirng
- Between reads nicer
```
SELECT * FROM students WHERE age BETWEEN 25 AND 35;
```

###ORDER BY
- ASC/DESC
```
SELECT * FROM students WHERE registration_date BETWEEN '2016-01-18' AND '2016-01-23' ORDER BY first_name, last_name DESC;
```

###LIMIT/OFFSET
```
SELECT * FROM students WHERE age > 30 ORDER BY first_name, last_name ASC LIMIT 10;
```
```
SELECT * FROM students WHERE first_name ILIKE 'ke%' LIMIT 10 OFFSET 10;
```

###UPDATE
```
UPDATE students set first_name="Ryan" WHERE id=48;
```

###DELETE
- DELETE FROM table_name WHERE [condition];

###Aggregate Functions
- Count
```
SELECT COUNT(*) FROM students;
```
```
SELECT COUNT(*) AS student_count FROM students WHERE age > 25;
```
- Sum
```
SELECT SUM(id) AS sum_of_ids FROM students;
```
- AVG and ROUND
```
SELECT ROUND(AVG(age)) FROM students WHERE registration_date > '2016-01-11';
```
- MAX and MIN
```
SELECT MAX(age) FROM students;
```
- GROUP BY
```
SELECT COUNT(first_name) AS first_name_count, first_name FROM students GROUP BY first_name;
```
