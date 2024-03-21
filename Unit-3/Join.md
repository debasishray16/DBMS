#

## Inner Join

### Equi Inner Join

- Condition used here is (=) operator

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
10 rows in set (0.01 sec)
```

### Theeta Inner Join

- Condition used here is (<,>) comparison operator

```sql
mysql> select * from emp INNER JOIN emp1 ON emp.salary > emp1.Salary;
+-----+----------------+--------+-------+--------------------------+-----+----------------+--------+------+--------------------------+
| EID | ENAME          | SALARY | TAX   | DESIGNATION              | EID | ENAME          | SALARY | TAX  | DESIGNATION              |
+-----+----------------+--------+-------+--------------------------+-----+----------------+--------+------+--------------------------+
| 102 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 101 | John Doe       |  50000 | 1000 | Manager                  |
| 102 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 103 | Bob Johnson    |  45000 |  900 | Software Developer       |
| 102 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 104 | Emily Davis    |  55000 | 1100 | Data Analyst             |
| 102 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 106 | Emma Wilson    |  48000 |  950 | Business Analyst         |
| 102 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 107 | David Martinez |  52000 | 1040 | Systems Administrator    |
| 102 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 108 | Sophia Taylor  |  58000 | 1160 | Database Administrator   |
| 102 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 110 | Olivia White   |  51000 | 1020 | Quality Assurance Tester |
| 104 | Emily Davis    |  55000 | 11000 | Data Analyst             | 101 | John Doe       |  50000 | 1000 | Manager                  |
| 104 | Emily Davis    |  55000 | 11000 | Data Analyst             | 103 | Bob Johnson    |  45000 |  900 | Software Developer       |
| 104 | Emily Davis    |  55000 | 11000 | Data Analyst             | 106 | Emma Wilson    |  48000 |  950 | Business Analyst         |
| 104 | Emily Davis    |  55000 | 11000 | Data Analyst             | 107 | David Martinez |  52000 | 1040 | Systems Administrator    |
| 104 | Emily Davis    |  55000 | 11000 | Data Analyst             | 110 | Olivia White   |  51000 | 1020 | Quality Assurance Tester |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 101 | John Doe       |  50000 | 1000 | Manager                  |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 102 | Alice Smith    |  60000 | 1200 | Senior Engineer          |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 103 | Bob Johnson    |  45000 |  900 | Software Developer       |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 104 | Emily Davis    |  55000 | 1100 | Data Analyst             |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 105 | Michael Brown  |  70000 | 1400 | Project Manager          |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 106 | Emma Wilson    |  48000 |  950 | Business Analyst         |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 107 | David Martinez |  52000 | 1040 | Systems Administrator    |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 108 | Sophia Taylor  |  58000 | 1160 | Database Administrator   |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 109 | James Clark    |  63000 | 1260 | Senior Software Engineer |
| 105 | Michael Brown  |  70009 |  1400 | Project Manager          | 110 | Olivia White   |  51000 | 1020 | Quality Assurance Tester |
| 106 | Emma Wilson    |  48000 |  9500 | Business Analyst         | 103 | Bob Johnson    |  45000 |  900 | Software Developer       |
| 107 | David Martinez |  52000 |   104 | Systems Administrator    | 101 | John Doe       |  50000 | 1000 | Manager                  |
| 107 | David Martinez |  52000 |   104 | Systems Administrator    | 103 | Bob Johnson    |  45000 |  900 | Software Developer       |
| 107 | David Martinez |  52000 |   104 | Systems Administrator    | 106 | Emma Wilson    |  48000 |  950 | Business Analyst         |
| 107 | David Martinez |  52000 |   104 | Systems Administrator    | 110 | Olivia White   |  51000 | 1020 | Quality Assurance Tester |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer | 101 | John Doe       |  50000 | 1000 | Manager                  |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer | 102 | Alice Smith    |  60000 | 1200 | Senior Engineer          |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer | 103 | Bob Johnson    |  45000 |  900 | Software Developer       |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer | 104 | Emily Davis    |  55000 | 1100 | Data Analyst             |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer | 106 | Emma Wilson    |  48000 |  950 | Business Analyst         |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer | 107 | David Martinez |  52000 | 1040 | Systems Administrator    |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer | 108 | Sophia Taylor  |  58000 | 1160 | Database Administrator   |
| 109 | James Clark    |  63000 |   120 | Senior Software Engineer | 110 | Olivia White   |  51000 | 1020 | Quality Assurance Tester |
| 111 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 101 | John Doe       |  50000 | 1000 | Manager                  |
| 111 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 103 | Bob Johnson    |  45000 |  900 | Software Developer       |
| 111 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 104 | Emily Davis    |  55000 | 1100 | Data Analyst             |
| 111 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 106 | Emma Wilson    |  48000 |  950 | Business Analyst         |
| 111 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 107 | David Martinez |  52000 | 1040 | Systems Administrator    |
| 111 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 108 | Sophia Taylor  |  58000 | 1160 | Database Administrator   |
| 111 | Alice Smith    |  60000 | 12000 | Senior Engineer          | 110 | Olivia White   |  51000 | 1020 | Quality Assurance Tester |
+-----+----------------+--------+-------+--------------------------+-----+----------------+--------+------+--------------------------+
42 rows in set (0.01 sec)
```
