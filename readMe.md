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
