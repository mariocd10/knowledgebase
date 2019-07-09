# Oracle Functions

## TO_CHAR

### Syntax
`TO_CHAR( value [, format_mask] [, nls_language])`

### Parameters
**value**: number or date
**format_mask**: optional. Format used to convert *value* to a string
**nls_language**: optional. nls language used to convert *value* to a string
*RETURN VARCHAR2*

### Example:
- Get current Month full name
```sql
SELECT TO_CHAR(sysdate, 'Month');
```

## EXTRACT
Returns type NUMBER

### Syntax:
`EXTRACT ( { DAY | MONTH | YEAR | HOUR | MINUTE | SECOND } FROM arg )`

### Example: 
``` sql
SELECT EXTRACT(month FROM sysdate) FROM dual;
SELECT EXTRACT (year FROM sysdate) FROM dual;
```
