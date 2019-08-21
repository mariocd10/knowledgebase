# Cursors

## What is a Cursor?
Oracle creates a memory area, known as the context area, for processing an SQL statement, which contains all the information needed for processing the statement; for example, the number of rows processed, etc. A cursor is a pointer to this context area. PL/SQL controls the context area through a cursor. A cursor holds the rows (one or more) returned by a SQL statement. The set of rows the cursor holds is referred to as the active set. You can name a cursor so that it could be referred to in a program to fetch and process the rows returned by the SQL statement, one at a time. There are two types of cursors −

* Implicit cursors
* Explicit cursors

## Implicit Cursor
Implicit cursors are automatically created by Oracle whenever an SQL statement is executed, 
when there is no explicit cursor for the statement. Programmers cannot control the implicit cursors and the information in it.

Whenever a DML statement (INSERT, UPDATE and DELETE) is issued, an implicit cursor is associated with this statement. 
For INSERT operations, the cursor holds the data that needs to be inserted. 
For UPDATE and DELETE operations, the cursor identifies the rows that would be affected.

## Explicit Cursor
Explicit cursors are programmer-defined cursors for gaining more control over the context area. 
An explicit cursor should be defined in the declaration section of the PL/SQL Block. 
It is created on a SELECT Statement which returns more than one row.

### Example
```plsql
CURSOR cursor_name IS select_statement;
```

When using a explicit cursor, the following steps also have to be done...
- Declare the cursor (initialize the memory)
- Open the cursor (allocate the memory)
- Fetch the cursor (retrieve the data)
- Close the cursor (release allocated memory)

### Example
```plsql
DECLARE 
   c_id customers.id%type; 
   c_name customerS.No.ame%type; 
   c_addr customers.address%type; 
   CURSOR c_customers is 
      SELECT id, name, address FROM customers; 
BEGIN 
   OPEN c_customers; 
   LOOP 
   FETCH c_customers into c_id, c_name, c_addr; 
      EXIT WHEN c_customers%notfound; 
      dbms_output.put_line(c_id || ' ' || c_name || ' ' || c_addr); 
   END LOOP; 
   CLOSE c_customers; 
END; 
/
```
