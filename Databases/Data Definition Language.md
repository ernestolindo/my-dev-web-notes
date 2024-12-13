Data Definition Language (DDL) is a syntax used for creating, modifying, and deleting database objects like tables and indexes.

`#` or `--` is used to make a comment.

**Create database**:
```mysql
CREATE DATABASE empresa;
```

**Select database**:
```mysql
USE empresa;
```

The primary key in SQL is a column that can uniquely identify a row in a table. Putting it simply, it is a column that accepts unique values for each row.

**Create a row**:
```mysql
CREATE TABLE productos(
    id int AUTO_INCREMENT PRIMARY KEY,
    nombre varchar(255) NOT NULL,
    precio decimal(5,2) NOT NULL,
    cantidad int DEFAULT 0
);
```
