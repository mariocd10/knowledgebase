# Colors

## Hexadecimal
Another way to represent color is Hexadecimal code or `hex code` for short.

*Hexadecimals* (or *hex*) base 16 numbers. This means it uses 16 distinct symbols.

The symbols 0-9 represent the values zero to nine. Then A,B,C,D,E,F reprsent the values ten to fifteen. Altogether, 9 to F can represent a digit in *hexadecimal*
, giving us 16 total possible values.

In CSS, we can use 6 hexadecimal digits to represent colors, two each for the red (R), green(G), and blue (B) components.

```css
body {
  color: #000000;
}
```

This gives possibility for 16 million colors which can feel overwhelming when finding a color. Fortunately, the hex code can be shortened.

**before**: `#FF0000`

**after**: `#F00`

This shortened form gives one digit for red, one digit for green, and one digit for blue. This reduces the total number of possible colors to around 4,000, But browsers interpret this as #FF0000 and #F00 as the same exact color.

### Example
|Color	|Short Hex Code|
| --- | --- |
|Cyan	|#0FF|
|Green	|#0F0|
|Red	|#F00|
|Fuchsia	|#F0F|
