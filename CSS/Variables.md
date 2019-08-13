# Custom CSS Variables
CSS variables contain values that can be reused within the document.

## Declare a CSS Variable
To declare a CSS variable, prefix the name of the variable with two dashes and assign
it a value.
```css
div {
	--test-variable: gray;
}
```
To access a CSS variable, use the `var()` function by passing the variable name as the parameter.
```css
div {
	color: var(--test-variable);
}
```

## Default/Fallback Value
CSS variables support the default or fallback values, meaning that we can define a value we want to use if the custom CSS variable fails. This is done by passing a second parameter in the `var()` function.
```css
div {
	color: var(--test-variable, gray);
}
```
**Note:** This fallback is not meant to increase browser compatibility but instead is meant to give the browser a value if it can't find the variable. Fallback value can be useful when debugging.

## Browser Compatibility
Internet explorer doesn't support CSS variables so if you want to provide a browser fallback, then adding another more widely supported value immediately before the variable decaration is the way to go.
```css
.red-box {
	background: red;
	background: var(--red-color);
	height: 200px;
	width: 200px;
}
```

## Cascading
The created variable becomes available within the element it was created in. It also becomes available within any elements nested within it.

Because of this, CSS variables are usually defined in the *:root* element.

`:root` references the top most parent element in the document. In the case for HTML, it's the `<html>` element. This allows the variables be available throughout the whole document.
```css
:root {
    --penguin-skin: gray;
    --penguin-belly: pink;
    --penguin-beak: orange;
  }
  
  body {
    background: var(--penguin-belly);
  }
```
  
