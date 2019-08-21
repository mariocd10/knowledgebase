# REF CURSOR / Cursor Variable
A `REF CURSOR` is a **variable** that references a **cursor**.

A `REF CURSOR` is a PL/SQL data type whose value is the memory address of a query work area on the database. Meaning, a `REF CURSOR` is a pointer or a handle to a result set on the database. 

## Creating a REF CURSOR
```sql
CREATE OR REPLACE FUNCTION get_dept_emps(p_deptno IN NUMBER) RETURN sys_refcursor IS
  v_rc sys_refcursor;
  BEGIN
    OPEN v_rc FOR 'select empno, ename, mgr, sal from emp where deptno = :deptno' using p_deptno;
    RETURN v_rc;
  END;
```

## FETCH DATA from REF CURSOR
```sql
DECLARE
  v_rc    sys_refcursor;
  v_empno NUMBER;
  v_ename VARCHAR2(10);
  v_mgr   NUMBER;
  v_sal   NUMBER;
BEGIN
  v_rc := get_dept_emps(10);  -- This returns an open cursor
  LOOP
    FETCH v_rc into v_empno, v_ename, v_mgr, v_sal;
    EXIT WHEN v_rc%NOTFOUND;  -- Exit the loop when we've run out of data
    dbms_output.put_line('Row: '||v_rc%ROWCOUNT||' # '||v_empno||','||v_ename||','||v_mgr||','||v_sal);
  END LOOP;
  CLOSE v_rc;
  FETCH v_rc into v_empno, v_ename, v_mgr, v_sal;
END;
```

## REF CURSOR vs CURSOR
1) A ref cursor can not be used in `CURSOR FOR LOOP`, it must be used in simple `CURSOR LOOP` statement as in example.
2) A ref cursor is defined at **runtime and can be opened dynamically** but a regular cursor is static and defined at compile time.
3) A ref cursor can be passed to another PL/SQL routine (function or procedure) or **returned to a client**. A regular cursor cannot be returned to a client application and must be consumed within same routine.
4) A ref cursor incurs a parsing penalty because it **cannot cached** but regular cursor will be cached by PL/SQL which can lead to a significant reduction in CPU utilization.
5) A regular cursor can be defined outside of a procedure or a function as a global package variable. A ref cursor cannot be; it must be **local in scope to a block of PL/SQL code**.
6) A regular cursor can more efficiently retrieve data than ref cursor. A regular cursor can implicitly fetch 100 rows at a time if used with `CURSOR FOR LOOP`. A ref cursor **must use explicit array fetching**.

My recommendation on ref cursors:
Use of ref cursors should be limited to only when you have a requirement of returning result sets to clients and when there is NO other efficient/effective means of achieving the goal.
