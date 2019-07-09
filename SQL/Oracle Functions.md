# Oracle Functions

## TO_CHAR

### Syntax
```sql
TO_CHAR( value [, format_mask] [, nls_language])
```

### Parameters
**value**: number or date
**format_mask**: optional. Format used to convert *value* to a string
**nls_language**: optional. nls language used to convert *value* to a string
*RETURN VARCHAR2*

### Example:
Get current Month full name
```sql
SELECT TO_CHAR(sysdate, 'Month');
```

## EXTRACT
The function extracts a value from a date or internal value.
Returns type NUMBER.
**Note**: You can only extract a year, month, and day from a DATE. You can only extract a timezone_hour, timezone_minute from timestamp.

### Syntax:
```sql
EXTRACT (
{ YEAR | MONTH | DAY | HOUR | MINUTE | SECOND }
| { TIMEZONE_HOUR | TIMEZONE_MINUTE }
| { TIMEZONE_REGION | TIMEZONE_ABBR }
FROM { date_value | interval_value } )
```

### Example: 
``` sql
SELECT EXTRACT(month FROM sysdate) FROM dual;
SELECT EXTRACT (year FROM sysdate) FROM dual;
```
## DECODE
Similar to an IF-THEN-ELSE statement.
### Syntax
```sql
DECODE( expression , search , result [, search , result]... [, default] )
```
### Parameters
**expression**: value to compare. Converted to the data type of the first *search* value before comparing.

**search**: value compared to expression. all search values converted to data type of first *search* value before comparing.

**result**: value returned, if *expression* is = to *search*.

**default**: optional. If no match found, it will return *default*. If omitted, function will return NULL if no match found.

### Example
```sql
DECODE(supplier_id, 10000, 'IBM',
                    10001, 'Microsoft',
                    10002, 'Hewlett Packard',
                    'Gateway') result
```
