# REF CURSOR
## Example
```sql
DECLARE
  c1 sys_refcursor;
  ename VARCHAR2(10);
  sal NUMBER;
BEGIN
  OPEN c1 FOR SELECT ename, sal FROM emp;
  LOOP
    FETCH c1 INTO ename, sal;
    EXIT WHEN c1%notfound;
    dbms_output.put_line('Ename: ' || ename || ', Salary: ' || sal);
  END LOOP;
  CLOSE c1;
END;
```

## Differences between a CURSOR
1) A ref cursor can not be used in `CURSOR FOR LOOP`, it must be used in simple `CURSOR LOOP` statement as in example.
2) A ref cursor is defined at **runtime and can be opened dynamically** but a regular cursor is static and defined at compile time.
3) A ref cursor can be passed to another PL/SQL routine (function or procedure) or **returned to a client**. A regular cursor cannot be returned to a client application and must be consumed within same routine.
4) A ref cursor incurs a parsing penalty because it **cannot cached** but regular cursor will be cached by PL/SQL which can lead to a significant reduction in CPU utilization.
5) A regular cursor can be defined outside of a procedure or a function as a global package variable. A ref cursor cannot be; it must be **local in scope to a block of PL/SQL code**.
6) A regular cursor can more efficiently retrieve data than ref cursor. A regular cursor can implicitly fetch 100 rows at a time if used with `CURSOR FOR LOOP`. A ref cursor **must use explicit array fetching**.

My recommendation on ref cursors:
Use of ref cursors should be limited to only when you have a requirement of returning result sets to clients and when there is NO other efficient/effective means of achieving the goal.
