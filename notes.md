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
###Data Types
- INTEGER, VARCHAR, TEXT, DECIMAL, FLOAT, BOOLEAN, DATETIME
- BOOLEAN: true, false, null
