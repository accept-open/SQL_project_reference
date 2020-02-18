# SQL Project Reference

## Generate unique identifier across the database

https://www.mysqltutorial.org/mysql-uuid/
```mysql
CREATE TABLE customers (
    id BINARY(16) PRIMARY KEY,
    name VARCHAR(255)
);

INSERT INTO customers(id, name)
VALUES(UUID_TO_BIN(UUID()),'John Doe'),
      (UUID_TO_BIN(UUID()),'Will Smith'),
      (UUID_TO_BIN(UUID()),'Mary Jane');

SELECT 
    BIN_TO_UUID(id) id, 
    name
FROM
    customers; 
```

![result_uuid](https://sp.mysqltutorial.org/wp-content/uploads/2017/07/MySQL-UUID.png)

## ID Auto Increment
```mysql
CREATE TABLE categories (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

```mysql
-- SQL Server
CREATE TABLE Persons (
    Personid int IDENTITY(1,1) PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

## data : Timestamp

https://www.mysqltutorial.org/mysql-timestamp.aspx
```mysql
CREATE TABLE test_timestamp (
    t1  TIMESTAMP
);

SET time_zone='+00:00';

INSERT INTO test_timestamp(t1)
VALUES('2008-01-01 00:00:01');

SELECT t1 FROM test_timestamp;
```
![](https://sp.mysqltutorial.org/wp-content/uploads/2011/03/MySQL-Timestamp-timezone-changes.jpg)

```mysql
SELECT t1 FROM test_timestamp;

CREATE TABLE categories (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO categories(name) 
VALUES ('A');

SELECT * FROM categories;

```

![](https://sp.mysqltutorial.org/wp-content/uploads/2011/03/MySQL-TIMESTAMP-Automatic-Initialization.png)
