# APEX_DEBUG
The `APEX_DEBUG` package provides utility functions for managing the debug message log. 
Specifically, this package provides the necessary APIs to instrument and debug PL/SQL code contained within your 
Application Express application as well as PL/SQL code in database stored procedures and functions.

## Enable
This procedure turns on debug messaging. You can specify, by level of importance, the types of debug messages that are monitored.

**Note:** You only need to call it once per page view or page accept.
```
APEX_DEBUG.ENABLE (
    p_level    IN  T_LOG_LEVEL DEFAULT C_LOG_LEVEL_INFO );
```
| Parameter | Description |
|---|---|
| p_level | Level or levels of messages to log. Must be an integer from 1 to 9, where level 1 is the most important messages and level 9 (the default) is the least important. Setting to a specific level logs messages both at that level and below that level. For example, setting p_level to 2 logs any message at level 1 and 2. |

## Example
```javascript
apex_debug.enable(
        p_level => 1);
        
apex_debug.log_message(
      p_level => 1,
      p_message => 'radio list 1: ' || :P13_DISPATCH_LIST);
apex_debug.log_message(
      p_level => 1,
      p_message => 'radio list 2: ' || :P13_DISPATCH_LIST_OFF );
apex_debug.disable();
```
