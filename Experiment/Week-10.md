# PL/SQL Statements

## Features of PL/SQL

- PL/SQL is tightly integrated with SQL.
- It offers extensive error checking.
- It offers numerous data types.
- It offers a variety of programming structures.
- It supports structured programming through functions and procedures.
- It supports object-oriented programming.
- It supports the development of web applications and server pages

## TO display output in the screen – give the below command initially

```db
SQL> SET serveroutput ON;
```

## Q1. Print the value of a

```db
DECLARE
a integer:=10;

BEGIN
dbms_output.put_line('The value of '|| a);

END;
```

## Q2. Print the value of a in text format

```db
DECLARE
a varchar(20):='Hello World';

BEGIN
dbms_output.put_line('The text value:'|| a);

END;
```

## Q3. Print the value of PI constant

```db
DECLARE
pi CONSTANT number:=3.14;

BEGIN
dbms_output.put_line('Value of PI:' || pi);

END;

```

## Q4. Calculate the sum of variable c

```db
DECLARE
a integer:=10;
b integer:=20;

c integer;

BEGIN
c:=a+b;
dbms_output.put_line('a=' || a ||'  '|| 'b='|| b||'  '|| 'c='|| c);

END;
```

## Q5. Find the Greater than , less than

```db

DECLARE

a integer:=10;

BEGIN
IF (a<20) THEN
dbms_output.put_line('a is less than 20');
ELSE
dbms_output.put_line('a is greater than 20');
END IF;
END;

```

## Q6. CASE Statements

```db
DECLARE

grade char(1):='A';

BEGIN

CASE grade
WHEN 'A' THEN dbms_output.put_line(' Excellent');
WHEN 'B' THEN dbms_output.put_line('Good');
WHEN 'C' THEN dbms_output.put_line('Average');
WHEN 'D' THEN dbms_output.put_line('Poor');

ELSE dbms_output.put_line('Failed');

END CASE;
END;


```

## Q7. Looping Statements

```db
DECLARE
i NUMBER:=1;

BEGIN
LOOP
EXIT WHEN i>10;
dbms_output.put_line(i);
i:=i+1;
END LOOP;
END;
```

## Q8. WHILE Loop Implementation

```db
DECLARE
i integer:=1;

BEGIN

WHILE i<=10 LOOP
dbms_output.put_line(i);
i:=i+1;
END LOOP;
END;
```

## Q9. FOR Loop Implementation

```db

DECLARE
var1 number;

BEGIN
var1:=10;
FOR var2 IN 1..20
LOOP
dbms_output.put_line(var1*var2);
END LOOP;
END;



```
