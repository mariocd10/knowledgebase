# Visual Design

## HTML Elements
`<strong>` tag applies the css `font-weight: strong`

`<u>` tag applies the css `decoration: underline;` note: try to avoid it bcuz it can be confused as a link

`<em>` tag applies the css `font-style: italic;`

`<s>` tag applies the css `text-decoration: line-through`. it's a strikethough line.

`<hr>` tag applies a horizontal line across the width of its containing element. This can be used to define a change in topic or to visually separate groups of content.

## CSS
`text-align`: [*justify, center, right, left*]

`width`: [*em, px, %*]

`height`: [*em, px, %*]

`background-color`: Changes the color of the element holding the text.

`font-size`: Change the size of the text font

`text-transform`: Change how the text is displayed without modifying the actual content

|Value |	Result|
|--- | --- |
|lowercase|	"transform me"|
|uppercase	|"TRANSFORM ME"|
|capitalize	|"Transform Me"|
|initial|	Use the default value|
|inherit|	Use the text-transform value from the parent element|
|none|	Default: Use the original text|

### Box-shadow
`box-shadow`: Property applies one or more shadows to an element.

The `box-shadow` property takes values for `offset-x` (how far to push the shadow horizontally from the element), `offset-y` (how far to push the shadow vertically from the element), `blur-radius`, `spread-radius` and a `color` value, in that order. The `blur-radius` and `spread-radius` values are optional.

Here's an example of the CSS to create multiple shadows with some blur, at mostly-transparent black colors:
```css
box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
```
### Opacity
`opacity` : The opacity property in CSS is used to adjust the opacity, or conversely, the transparency for an item.
- A value of *1* is opaque, which isn't transparent at all.
- A value of *0.5* is half see-through.
- A value of *0* is completely transparent.
`opacity: 0.7;`

## Color
```
rgba stands for: 
  r = red
  g = green
  b = blue
  a = alpha/level of opacity
  ```
  
  The RGB value can range from 0 to 255. The alpha value can range from 0 - 1. 0 being transparent and 1 being opaque or a solid color.
  
