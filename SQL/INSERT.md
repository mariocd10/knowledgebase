# INSERT

The insert statement is used to insert a single or multiple records into a table. 

When using INSERT, a value must be provided for every required (`NOT NULL`) column, otherwise it can be omitted.

## INSERT Single Record Suntax
```sql
INSERT INTO table
(column1, column2, ... , column_n)
VALUES
(expression1, expression2, ... , expression_n);
```

## INSERT Multiple Record Suntax
```sql
INSERT INTO table
(column1, column2, ... , column_n)
SELECT expression1, expression2, ... , expression_n
FROM source_table
[WHERE conditions];
```
