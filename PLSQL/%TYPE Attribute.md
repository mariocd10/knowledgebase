# %TYPE Attribute

## Declare Variable with %TYPE attribute
Using the %TYPE attribute ensures that type compatibility between table columns and PL/SQL variables is maintained

### Syntax
`name [table | view ].column%TYPE`
`name variable%TYPE`

**name**: The identifier for the variable being declared
**table**: the identifier for the table whose column is to be referenced
**view:** The identifier for the view whose column is to be referenced
**column:** the identifier for the table or view column is to be referenced
**variable:** The identifier for the variable previously declared to be referenced. Does not inherit any other column attributes like nullability.

### Example
```PLSQL
CREATE OR REPLACE PROCEDURE emp_sal_query (
	p_empno	IN emp.empno%TYPE
) IS
	v_lastname	emp.lastname%TYPE;
	v_job		emp.job%TYPE;
	...
BEGIN
...
END;
```
