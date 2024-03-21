# Set

## Set Operations

There are two employee's table *emp* and *emp1*.

```sql
mysql> select * from emp;
+-----+----------------+--------+-------+--------------------------+
| EID | ENAME          | SALARY | TAX   | DESIGNATION              |
+-----+----------------+--------+-------+--------------------------+
| 101 | John Doe       |  20000 |  1000 | Manager                  |
| 102 | Alice Smith    |  60000 | 12000 | Senior Engineer          |
| 103 | Bob Johnson    |  45000 |  9000 | Software Developer       |
| 104 | Emily Davis    |  55000 | 11000 | Data Analyst             |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          |
| 106 | Emma Wilson    |  48000 |  9500 | Business Analyst         |
| 107 | David Martinez |  52000 |   104 | Systems Administrator    |
| 108 | Sophia Taylor  |   5800 |  1160 | Database Administrator   |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer |
| 110 | Olivia White   |   1000 |  1020 | Quality Assurance Tester |
| 111 | Alice Smith    |  60000 | 12000 | Senior Engineer          |
+-----+----------------+--------+-------+--------------------------+
11 rows in set (0.00 sec)
```

```sql
mysql> select * from emp1;
+-----+----------------+--------+------+--------------------------+
| EID | ENAME          | SALARY | TAX  | DESIGNATION              |
+-----+----------------+--------+------+--------------------------+
| 101 | John Doe       |  50000 | 1000 | Manager                  |
| 102 | Alice Smith    |  60000 | 1200 | Senior Engineer          |
| 103 | Bob Johnson    |  45000 |  900 | Software Developer       |
| 104 | Emily Davis    |  55000 | 1100 | Data Analyst             |
| 105 | Michael Brown  |  70000 | 1400 | Project Manager          |
| 106 | Emma Wilson    |  48000 |  950 | Business Analyst         |
| 107 | David Martinez |  52000 | 1040 | Systems Administrator    |
| 108 | Sophia Taylor  |  58000 | 1160 | Database Administrator   |
| 109 | James Clark    |  63000 | 1260 | Senior Software Engineer |
| 110 | Olivia White   |  51000 | 1020 | Quality Assurance Tester |
+-----+----------------+--------+------+--------------------------+
```

```sql
SELECT EID from emp UNION select EID from emp1;
+-----+
| EID |
+-----+
| 101 |
| 102 |
| 103 |
| 104 |
| 105 |
| 106 |
| 107 |
| 108 |
| 109 |
| 110 |
| 111 |
+-----+
11 rows in set (0.00 sec)

mysql> select ENAME from emp UNION select ENAME from emp1;
+----------------+
| ENAME          |
+----------------+
| John Doe       |
| Alice Smith    |
| Bob Johnson    |
| Emily Davis    |
| Michael Brown  |
| Emma Wilson    |
| David Martinez |
| Sophia Taylor  |
| James Clark    |
| Olivia White   |
+----------------+
10 rows in set (0.00 sec)

mysql> select EID, ENAME from emp UNION select EID,ENAME from emp1;
+-----+----------------+
| EID | ENAME          |
+-----+----------------+
| 101 | John Doe       |
| 102 | Alice Smith    |
| 103 | Bob Johnson    |
| 104 | Emily Davis    |
| 105 | Michael Brown  |
| 106 | Emma Wilson    |
| 107 | David Martinez |
| 108 | Sophia Taylor  |
| 109 | James Clark    |
| 110 | Olivia White   |
| 111 | Alice Smith    |
+-----+----------------+
11 rows in set (0.00 sec)
```

- **This is because,both the table must have equal number of columns in query as well as in database to perform set operation.**

```sql
mysql> select EID,ENAME from emp UNION select EID from emp1;
ERROR 1222 (21000): The used SELECT statements have a different number of columns
```

### UNION ALL

- **The column heading is given from the first table.**

```sql
select EID from emp UNION ALL select EID from emp1;
+-----+
| EID |
+-----+
| 101 |
| 102 |
| 103 |
| 104 |
| 105 |
| 106 |
| 107 |
| 108 |
| 109 |
| 110 |
| 111 |
| 101 |
| 102 |
| 103 |
| 104 |
| 105 |
| 106 |
| 107 |
| 108 |
| 109 |
| 110 |
+-----+
21 rows in set (0.00 sec)

mysql> select EID,ENAME from emp UNION ALL select ENAME,DESIGNATION from emp1;
+----------------+--------------------------+
| EID            | ENAME                    |
+----------------+--------------------------+
| 101            | John Doe                 |
| 102            | Alice Smith              |
| 103            | Bob Johnson              |
| 104            | Emily Davis              |
| 105            | Michael Brown            |
| 106            | Emma Wilson              |
| 107            | David Martinez           |
| 108            | Sophia Taylor            |
| 109            | James Clark              |
| 110            | Olivia White             |
| 111            | Alice Smith              |
| John Doe       | Manager                  |
| Alice Smith    | Senior Engineer          |
| Bob Johnson    | Software Developer       |
| Emily Davis    | Data Analyst             |
| Michael Brown  | Project Manager          |
| Emma Wilson    | Business Analyst         |
| David Martinez | Systems Administrator    |
| Sophia Taylor  | Database Administrator   |
| James Clark    | Senior Software Engineer |
| Olivia White   | Quality Assurance Tester |
+----------------+--------------------------+
21 rows in set (0.00 sec)

```

### INTERSECT

```sql
mysql> SELECT EID from emp WHERE EID IN (select EID from emp1);
+-----+
| EID |
+-----+
| 101 |
| 102 |
| 103 |
| 104 |
| 105 |
| 106 |
| 107 |
| 108 |
| 109 |
| 110 |
+-----+
10 rows in set (0.00 sec)
```

### MINUS

- In SQL, the MINUS operator is used to find the difference between two result sets. It returns all distinct rows from the first result set that are not present in the second result set.

- To perform the equivalent of a MINUS operation in SQL, you can use a combination of LEFT JOIN and WHERE clause to filter out the matching rows.

```sql
```

## SQL JOIN

```sql
mysql> select * from emp INNER JOIN emp1 ON emp.EID=emp1.EID;
+-----+----------------+--------+-------+--------------------------+-----+----------------+--------+------+--------------------------+
| EID | ENAME          | SALARY | TAX   | DESIGNATION              | EID | ENAME          | SALARY | TAX  | DESIGNATION              |
+-----+----------------+--------+-------+--------------------------+-----+----------------+--------+------+--------------------------+
| 101 | John Doe       |  20000 |  1000 | Manager                  | 101 | John Doe       |  50000 | 1000 | Manager                  |
| 102 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 102 | Alice Smith    |  60000 | 1200 | Senior Engineer          |
| 103 | Bob Johnson    |  45000 |  9000 | Software Developer       | 103 | Bob Johnson    |  45000 |  900 | Software Developer       |
| 104 | Emily Davis    |  55000 | 11000 | Data Analyst             | 104 | Emily Davis    |  55000 | 1100 | Data Analyst             |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 105 | Michael Brown  |  70000 | 1400 | Project Manager          |
| 106 | Emma Wilson    |  48000 |  9500 | Business Analyst         | 106 | Emma Wilson    |  48000 |  950 | Business Analyst         |
| 107 | David Martinez |  52000 |   104 | Systems Administrator    | 107 | David Martinez |  52000 | 1040 | Systems Administrator    |
| 108 | Sophia Taylor  |   5800 |  1160 | Database Administrator   | 108 | Sophia Taylor  |  58000 | 1160 | Database Administrator   |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer | 109 | James Clark    |  63000 | 1260 | Senior Software Engineer |
| 110 | Olivia White   |   1000 |  1020 | Quality Assurance Tester | 110 | Olivia White   |  51000 | 1020 | Quality Assurance Tester |
+-----+----------------+--------+-------+--------------------------+-----+----------------+--------+------+--------------------------+
```

- If we wanted to select specific column from specific table. use **emp.DESIGNATION**

```sql
mysql> select emp.DESIGNATION from emp INNER JOIN emp1 ON emp.EID=emp1.EID;
+--------------------------+
| DESIGNATION              |
+--------------------------+
| Manager                  |
| Senior Engineer          |
| Software Developer       |
| Data Analyst             |
| Project Manager          |
| Business Analyst         |
| Systems Administrator    |
| Database Administrator   |
| Senior Software Engineer |
| Quality Assurance Tester |
+--------------------------+
10 rows in set (0.01 sec)

mysql> select emp.DESIGNATION,emp1.DESIGNATION from emp1 INNER JOIN emp ON emp.EID=e
mp1.EID;
+--------------------------+--------------------------+
| DESIGNATION              | DESIGNATION              |
+--------------------------+--------------------------+
| Manager                  | Manager                  |
| Senior Engineer          | Senior Engineer          |
| Software Developer       | Software Developer       |
| Data Analyst             | Data Analyst             |
| Project Manager          | Project Manager          |
| Business Analyst         | Business Analyst         |
| Systems Administrator    | Systems Administrator    |
| Database Administrator   | Database Administrator   |
| Senior Software Engineer | Senior Software Engineer |
| Quality Assurance Tester | Quality Assurance Tester |



mysql> select emp.EID,emp1.DESIGNATION from emp INNER JOIN emp1 ON emp.EID=emp1.EID;

+-----+--------------------------+
| EID | DESIGNATION              |
+-----+--------------------------+
| 101 | Manager                  |
| 102 | Senior Engineer          |
| 103 | Software Developer       |
| 104 | Data Analyst             |
| 105 | Project Manager          |
| 106 | Business Analyst         |
| 107 | Systems Administrator    |
| 108 | Database Administrator   |
| 109 | Senior Software Engineer |
| 110 | Quality Assurance Tester |
+-----+--------------------------+
10 rows in set (0.00 sec)


```