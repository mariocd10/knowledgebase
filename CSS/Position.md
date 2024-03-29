# Position
CSS treats each HTML element as its own box, which is usually referred to as the **CSS Box Model**. 
*Block-level* items automatically start on a new line (think headings, paragraphs, and divs) while inline items sit within surrounding content (like images or spans). 
The default layout of elements in this way is called the **normal flow** of a document, 
but CSS offers the `position` property to override it.

**Note**
Positioning gives you a lot of flexibility and power over the visual layout of a page. It's good to remember that no matter the position of elements, the underlying HTML markup should be organized and make sense when read from top to bottom. This is how users with *visual impairments* (who rely on assistive devices like screen readers) access your content.

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
Changing an element's position to `relative` does not remove it from the normal flow - other elements around it still behave as if that item were in its default position.

## Absolute
locks the element in place relative to its parent container. Unlike the `relative` position, this removes the element from the normal flow of the document, so surrounding items ignore it. The CSS offset properties (`top` or `bottom` and `left` or `right`) are used to adjust the position.

One nuance with `absolute` positioning is that it will be locked relative to its closest positioned ancestor. If you forget to add a position rule to the parent item, (this is typically done using `position: relative;`), the browser will keep looking up the chain and ultimately default to the `body` tag.

## Fixed
The next layout scheme that CSS offers is the `fixed` position, which is a type of absolute positioning that **locks** an element **relative to the browser window**. Similar to `absolute` positioning, it's used with the **CSS offset properties** and also removes the element from the normal flow of the document. Other items no longer "realize" where it is positioned, which may require some layout adjustments elsewhere.

One key difference between the `fixed` and `absolute` positions is that an element with a `fixed` position won't move when the user scrolls.

## Offset
The CSS offsets of `top` or `bottom`, and `left` or `right` tell the browser how far to offset an item relative to where it would sit in the normal flow of the document. You're offsetting an element away from a given spot, which moves the element away from the referenced side (effectively, the opposite direction).
```css
h2 {
  top: 10px;
  bottom: 14px;
  }
```

## Z-Index
When elements are positioned to overlap, the element coming later in the HTML markup will, by default, appear on the top of the other elements. However, the `z-index` property can specify the order of how elements are **stacked on top of one another**. It must be an integer (i.e. a whole number and not a decimal), and higher values for the `z-index` property of an element move it higher in the **stack** than those with lower values.
