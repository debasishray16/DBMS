#

## Data Definition Language

1. ALTER Command

Alter command are used to add and modify the columns and need to make changes in it.

```db
ALTER TABLE table_name ADD/MODIFY column_name datatype;
```

```db
ALTER TABLE table MODIFY column_name datatype;
```

2. DROP Command

Drop command are used to **remove the table with records from the database completely**.

```db
DROP TABLE table_name;
```

3. TRUNCATE Command

Truncae command are used to **delete the records completely from the base table** but **keeps the structure of the base table alone.**

```db
TRUNCATE TABLE table_name;
```

### Constraints

Constraints are used to define the intergity constriants   that establishes a rule in the database.

There are five types of constraints:

- NOT NULL constraint
- UNIQUE constraint
- PRIMARY KEY constraint
- FOREIGN KEY constraint
- CHECK constraint

1. NOT NULL Constraint: NOT NULL constraints restricts the user to enter NULL values and **permits duplicate value.**

```text
1. You cannot specify NULL or NOT NULL constraints in a view of table.
2. You cannot specify NULL or NOT NULL for an attribute of an object. 
    Instead use a CHECK constraint with IS [NOT] NULL condition.
```

2. UNIQUE constraint: UNIQUE constraints designates a column as the unique key.

```text
1. Unique Constraint allows null values and it allows more number of NULL values.
2. To satisfy the unique constraint, no two rows in the table can have the same value for the unique constraint.
3. You cannot specify a unique key when creating a subview in an inheritance hierarchy.
4. The unique key can beb specified only on the top-level (root) view.
5. A composite unique cannot have more than 32 columns.
```

```db
Create table <table_name> ( column_1 datatype Constraint <constraint_name>
<constraint_type>, column_2 datatype,
column_n datatype);
```