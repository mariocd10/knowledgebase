# Forms
Building web forms lets you submit data to a server using pure HTML. You can do this by specifying the action on the `form` element.

Form fields can be set as required and will not let user submit form unless there those fields are filled out.
```html
<input type="text" required>
```
## &lt;form> Element
### action Attribute
Defines the action to be performed when the form is submitted. Normally it would be sent to a page on the server to process the input.
If ommited, the action is set to the current page.

```html
<form action="/url-where-you-want-to-submit-form-data"></form>
```

### `target` Attribute
The `target` attribute specifies if the submitted result will be open in a new browser tab, a frame, or in the current window.
Default value = `_self`, which means the current window. To open in a new browser tab the value must be `_blank`
```html
<form action="action_page.php" target="_blank"></form>
```
### `method` Attribute
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
&ltinput type="checkbox"> | Check Box

By surrounding an `input` element with a `label` element it wil automatically associate the input field with the label surrounding it.
All related radio button and checkbox elements must have the same `name` attribute. 

It is considered best practice to explicitly define a relationship between a checkbox `input` and its corresponding `label` by setting the `for` attribute on the `label` element to match the `id` attribute of the associated `input` element:
```html
<label for="indoor">
  <input id="indoor" type="radio" name="indoor-outdoor">
  Indoor
</label>
<label for="outdoor">
  <input id="outdoor" type="radio" name="indoor-outdoor"> 
  Outdoor
</label>
```

### `name` Attribute
Each input must have a name attributed. If ommitted the data of that input field won't be sent.
```html
<input type="text" name="lastname" value="Mouse">
```

### `placeholder` Attribute
Placeholder text is displayed in the `input` element before the user has inputted anything.
```html
<input type="text" placeholder="this is placeholder text">
```

### `checked` Attribute
Set a checkbox or radiobutton to be checked by default.
```html
<input type="radio" name="test-name" checked>
```
