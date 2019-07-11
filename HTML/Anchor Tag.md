# Anchor Tag
Anchor elements can link to external and internal web pages.

## Link to External Page

## Link to Internal Page/Section
Anchor elements can be used to create internal links to jump to different sections within a webpage. To do this, you assign the `href`
attribute with a `#` symbol followed by the `id` attribute of the element you want to internally link to. If not done so already, the interested element
must have the same `id` attribute value.

**Note**: an `id` is an attribute that uniquely describes an element.

```html
<a href="#contacts-header">Contacts</a>
...
<h2 id="contacts-header">Contacts</h2>
```

When the user clicks on the Contacts link, they'll be taken to the section of the webpage with the Contacts header element.

## Create a Dead Link
This is useful when you want to add an `a` element but not sure where it will link to yet. Also, when changing the behavior of a link using JavaScript.
```html
<a href="#"></a>
```
