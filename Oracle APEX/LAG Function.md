# LAG Function
This function is considered an analytical function. `LAG` lets you query more than one row at a time without having to join the table to itself.
It returns values from a previous row in the table.

To return the value of the next row, use `LEAD` function.

## Syntax
```sql
LAG( expression [, offset [, default] ] )
OVER ( [ query_partition_clause ] order_by_clause )
```

## Parameters or Arguements
- *expression* : An expression that can contain other built-in functions, but **can't** contain analytical functions
- *offset* : Optional. Physical offset from the current row in the table. Default is 1.
- *default* : Optional. It's the value that is returned if the *offset* goes out of bounds of the table. Default is null.

## Example
`LAG` function can be used in Oracle/PLSQL.
In the example, the function will sort the result data in asc order all of the *order_date* values in the *order* table and then return
the previous *order_date* since we used an offset of 1.

We have an *orders* table:

| ORDER_DATE | PRODUCT_ID | QTY |
| --- | --- | --- |
| 2007/09/25 | 1000 | 20 | 
| 2007/09/26 | 2000 | 15 |
| 2007/09/27 | 1000 | 8 |
| 2007/09/28 | 2000 | 12 | 
| 2007/09/29 | 2000 | 2 |
| 2007/09/30 | 1000 | 4 |

```SQL
SELECT product_id, order_date,
LAG (order_date,1) OVER (ORDER BY order_date) AS prev_order_date
FROM orders;
```
Result:

| PRODUCT_ID | ORDER_DATE | PREV_ORDER_DATE |
| --- | --- | --- |
| 1000 | 2007/09/25 | NULL | 
| 2000 | 2007/09/26 | 2007/09/25 | 
| 1000 | 2007/09/27 | 2007/09/26 | 
| 2000 | 2007/09/28 | 2007/09/27 | 
| 2000 | 2007/09/29 | 2007/09/28 | 
| 1000 | 2007/09/30 | 2007/09/29 | 


