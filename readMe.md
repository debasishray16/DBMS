#

## Data Control Language

DCL commands are used to /get back/ control the privileges of an object by the user.

-> GRANT- to give access priviledges of an object to the other user by the owner

```sql
GRANT SELECT ON my_table TO 'username'@'hostname';
```

-> REVOKE- to get back all  the privileges from the user who have been granted.

```sql
REVOKE SELECT ON my_table FROM 'username'@'hostname';
```

## Transaction Control Language

TCL are used to control the database operations.

-> COMMIT- to commit the transaction.

```sql
COMMIT;
```

-> ROLLBACK- to rollback the transaction in case if there is any errors.

```sql
ROLLBACK;
```

-> SAVEPOINT- to set a savepoint within the transaction. Rolled back from the specific savepoint.

```sql
SAVEPOINT savepoint_name;
```

```sql
ROLLBACK TO SAVEPOINT sp1;
```

## Data Manipulation Language

DML enables the user to manipulate or change the data in the databases organized by the appropriate data model.

-> INSERT- to insert the data in the table or record.

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

to insert data in CLI:

```sql
INSERT INTO my_table (column1, column2, column3)
VALUES (&value1, '&value2', &value3);
```

'' for those which have datatype declared as TEXT or VARCHAR.

-> SELECT- TO retrieve data from the table using constraints and conditions stored in database.

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

using functions

```sql
SELECT UPPER(first_name), LOWER(last_name) FROM employees;
```

```sql
SELECT employees.first_name, departments.department_name
FROM employees
JOIN departments ON employees.department_id = departments.department_id;
```