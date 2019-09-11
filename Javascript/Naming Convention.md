# Naming Convention

## The `$` Identifier
The $ in the variable name is only part of the name, 
but the convention is to use it to start variable names when the variable represents a jQuery object.
```javascript
var $myHeaderDiv = $('#header');
var myHeaderDiv = document.getElementById('header');
```
Now later in your code, you know the $myHeaderDiv is already a jQuery object, so you can call jQuery functions:
```
$myHeaderDiv.fade();
```
To get from the DOM-variable to the jQuery variable:
```javascript
var $myHeaderDiv = jQuery(myHeaderDiv); //assign to another variable
jQuery(myHeaderDiv).fade(); //use directly
//or, as the $ is aliased to the jQuery object if you don't specify otherwise:
var $myHeaderDiv = jQuery(myHeaderDiv); //assign
$(myHeaderDiv).fade(); //use
```
To get from the jQuery variable to the DOM-variable.
```javascript
var myHeaderDiv = $myHeaderDiv.get(0);
```

## The Underscore `_` Identifier
A convention has also developed regarding the use of _, which is frequently used to preface the name of an object's property or method that is private. This is a quick and easy way to immediately identify a private class member, and it is so widely used, that almost every programmer will recognize it.
