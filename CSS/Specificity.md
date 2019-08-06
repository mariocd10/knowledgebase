# Specificity
If multiple CSS selectors are targeting the same HTML element, and the CSS selectors are trying to assign the same property/properties
to the HTML element, the selector with the highest specificity value will "win" and apply the style.

In other words, the most specific selector gets to assign the values to the element.

The following list of selector types increases by specificity:
1. Type Selectors (e.g `h1`)
2. Class Selectors
3. ID Selectors

Inline styles added to an element always overwrite any styles in external stylesheets.

## Calculating Specificity
To calculate CSS Specificity, we use a four category system to give CSS selector a value.

![alt text](https://cdn-images-1.medium.com/max/1600/1*Z5vDhOz-hSY7GK1UI4RE5A.png "Specificity Image")
*image by Emma Wedekind*

