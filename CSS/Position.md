# Position
CSS treats each HTML element as its own box, which is usually referred to as the **CSS Box Model**. 
*Block-level* items automatically start on a new line (think headings, paragraphs, and divs) while inline items sit within surrounding content (like images or spans). 
The default layout of elements in this way is called the **normal flow** of a document, 
but CSS offers the `position` property to override it.

## Relative
When the position of an element is set to **relative**, 
it allows you to specify how CSS should move it relative to its **current position** in the normal flow of the page. 
It pairs with the CSS offset properties of `left` or `right`, and `top` or `bottom`. 
These say how many *pixels*, *percentages*, or *ems* to move the item away from where it is normally positioned. 
The following example moves the paragraph 10 pixels away from the bottom:
```css
p {
  position: relative;
  bottom: 10px;
  }
```
