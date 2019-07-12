# Forms
Building web forms lets you submit data to a server using pure HTML. You can do this by specifying the action on the `form` element.

## &lt;form> Element
### action Attribute
Defines the action to be performed when the form is submitted. Normally it would be sent to a page on the server to process the input.
If ommited, the action is set to the current page.

```html
<form action="/url-where-you-want-to-submit-form-data"></form>
```

### target Attribute
The `target` attribute specifies if the submitted result will be open in a new browser tab, a frame, or in the current window.
Default value = `_self`, which means the current window. To open in a new browser tab the value must be `_blank`
```html
<form action="action_page.php" target="_blank"></form>
```
### method Attribute
This attribute specifies the *HTTP* method (**GET** or **POST**) to be used when submitting the form data:
```html
<form action="/action_page.php" method="get"></form>
```

## &lt;input> Element
The `<input>` element is the most important form element. It can be displayed in many ways depending on the **type** attribute.

Type | Description
--- | ---
&lt;input type="text"> | One-line text field
&lt;input type="radio"> | Radio Button
&lt;input type="submit"> | Submit Button (submit form)

### `name` Attribute
Each input must have a name attributed. If ommitted the data of that input field won't be sent.
```html
<input type="text" name="lastname" value="Mouse">
```
