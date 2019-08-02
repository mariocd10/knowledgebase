# SELECT Statement

Is used to retrieve data from a database. The data retrieved is called a *result set*. 
A *result set* is comprised of rows and columns making it possible to populate a table with the *result set*.

## Syntax
```sql
SELECT <one or more things>
FROM <one or more places>
WHERE <one or more conditions apply>
```

A SELECT clause may contain:
- Literal values, such as numbers or strings
- expressions, such as `shape.diameter * 3.1415927`
- Function calls, such as `TO_DATE('01-JAN-2004','DD-MON-YYYY')`
- Pseudocolumns, such as `ROWID`, `ROWNUM`, or `LEVEL`

### Example
```sql
SELECT ROWNUM,
  cust_nbr,
  1 multiplier,
  'cust# ' || cust_nbr cust_nbr_str,
  'hello' greeting,
  TO_CHAR(last_order_dt, 'DD-MON-YYYY') last_order
FROM customer;
```

A `SELECT` clause doesn't have to reference columns from any of the tables in the `FROM` clause.

### Example
```sql
SELECT 1 num, 'abc' str
FROM customer;
```
