# removeClass
## Syntax
```javascript
$(selector).removeClass(classname,function(index,currentclass))
```
## Parameters
**classname**: optional. Specifies one or more class names to remove. Seperate with spaces.

**function(index,currentclass)**: optional. A functions that returns one or more class names to remove. 
*index* - returns index position. 
*currentclass* - returns current class name of selected elements.

## Example
```javascript
$("button").click(function(){
  $("p").removeClass("intro");
});
```
