# Built In Substitution Strings
## APP_PAGE_ID
Contains the current app page id. For example, if your application was on page 3, then the result would be 3. Using this syntax is useful when writing application components that must work generically in multiple applications. 
### Example
`f?p=&APP_ID.:&APP_PAGE_ID.:&APP_SESSION.`
### Reference Type	Syntax
Bind variable: `:APP_PAGE_ID`

PL/SQL and Direct PL: `NV('APP_PAGE_ID')`

Substitution string: `&APP_PAGE_ID.`
