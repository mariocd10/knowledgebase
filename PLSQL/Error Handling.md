# Error Handling

In PL/SQL, an error condition is called an *exception*. Exceptions can be **internally defined** or **user defined**.
Some internal exceptions have predefined names such as *no_data_found* or *division_by_zero*. User defined exceptions, like the name says, are given a name by the user.

When an error happens, an exception is *raised*. Which means, execution is stopped and the exception-handling block then executes.

## Example
The following example calculates and stores a price-to-earning ratio for a company. 
If the company has zero earnings, the predefined exception will be raised and the exception handler block will then execute.
The *Others* handler catches any exceptions that were not explicitly named.

```sql
DECLARE
   pe_ratio NUMBER(3,1);
BEGIN
   SELECT price / earnings INTO pe_ratio FROM stocks
      WHERE symbol = 'XYZ';  -- might cause division-by-zero error
   INSERT INTO stats (symbol, ratio) VALUES ('XYZ', pe_ratio);
   COMMIT;
EXCEPTION  -- exception handlers begin
   WHEN ZERO_DIVIDE THEN  -- handles 'division by zero' error
      INSERT INTO stats (symbol, ratio) VALUES ('XYZ', NULL);
      COMMIT;
   ...
   WHEN OTHERS THEN  -- handles all other errors
      ROLLBACK;
END;  -- exception handlers and block end here
```
