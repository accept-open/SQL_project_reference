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
