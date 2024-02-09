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










## Procedural and Non Procedural DML

Procedural DML- Procedural DML require a user to specify what data are needed and how to get the data at what time.

1. Stored Procedures, Functions, Triggers
2. Control Flow and Logic

```sql
CREATE PROCEDURE updateSalary(employee_id INT, new_salary DECIMAL)
BEGIN
    UPDATE employees SET salary = new_salary WHERE id = employee_id;
END;
```

Non Procedural DML-  Non Procedural DML requires a user to specify what data are needed without specifying how to get the data.

1. SQL queries
2. Set Based Operations

```sql
SELECT * FROM employees WHERE department_id = 10;
INSERT INTO employees (name, salary) VALUES ('John', 50000);
UPDATE employees SET salary = salary * 1.1 WHERE department_id = 20;
DELETE FROM employees WHERE id = 100;
```





## Types of DBMS Users

1. Naive Users: Naive users are those that don't have prior knowledge about DBMS. They directly use the application software interface to interact with the database.

2. Application Programmers: Application Programmers are those that have prior knowledge about DBMS and how it works. They write code to develop their own DBMS applications.
Programs are written in C++,JAVA,Python etc.

3. Sophisticated Users: Sophisticated users are those users who have prior knowledge about database and DBMS. But they don't write code , but able to manage using queries.
eg. Business Analyst, Researchers

4. Native Users: Native users are those who use the existing database applications. They don't write code or queries.
eg. Library management system.

5. Specialized Users: Specialized users are those who write the code for DBMS applications. They are the developers who develop the complex programs to the requirement.

6. Stand-Alone Users: Stand-Alone Users are those who have the ability to develop their own database for their own use.
