# Color Theory
Color theory and its impact on design is a deep topic and only the basics are covered in the following challenges. 
On a website, color can draw attention to content, evoke emotions, or create visual harmony. 
Using different combinations of colors can really change the look of a website, and a lot of thought can go into picking a 
color palette that works with your content.

The color wheel is a useful tool to visualize how colors relate to each other - 
it's a circle where similar hues are neighbors and different hues are farther apart. 
When two colors are opposite each other on the wheel, they are called complementary colors. 
They have the characteristic that if they are combined, they "cancel" each other out and create a gray color. 
However, when placed side-by-side, these colors appear more vibrant and produce a strong visual contrast.

Some examples of complementary colors with their hex codes are:
```
red (#FF0000) and cyan (#00FFFF)
green (#00FF00) and magenta (#FF00FF)
blue (#0000FF) and yellow (#FFFF00)
```
This is different than the outdated RYB color model that many of us were taught in school, which has different primary and complementary colors. 
Modern color theory uses the additive RGB model (like on a computer screen) and the subtractive CMY(K) model (like in printing). 
Read here for more information on this complex subject.
There are many color picking tools available online that have an option to find the complement of a color.

**Note**: For all color challenges: Using color can be a powerful way to add visual interest to a page. 
However, color alone should not be used as the only way to convey important information because users with 
visual impairments may not understand that content. This issue will be covered in more detail in the Applied Accessibility challenges.

## Complementary Colors
The Complementary Colors challenge showed that opposite colors on the color wheel can make each other appear more vibrant when placed side-by-side. However, the strong visual contrast can be jarring if it's overused on a website, and can sometimes make text harder to read if it's placed on a complementary-colored background. In practice, one of the colors is usually dominant and the complement is used to bring visual attention to certain content on the page.

## Color Hue
Colors have several characteristics including hue, saturation, and lightness. CSS3 introduced the hsl() property as an alternative way to pick a color by directly stating these characteristics.

Hue is what people generally think of as 'color'. If you picture a spectrum of colors starting with red on the left, moving through green in the middle, and blue on right, the hue is where a color fits along this line. In hsl(), hue uses a color wheel concept instead of the spectrum, where the angle of the color on the circle is given as a value between 0 and 360.

Saturation is the amount of gray in a color. A fully saturated color has no gray in it, and a minimally saturated color is almost completely gray. This is given as a percentage with 100% being fully saturated.

Lightness is the amount of white or black in a color. A percentage is given ranging from 0% (black) to 100% (white), where 50% is the normal color.

Here are a few examples of using hsl() with fully-saturated, normal lightness colors:

Color	HSL

| Color | HSL() |
| --- | --- |
| red |	hsl(0, 100%, 50%) |
| yellow | hsl(60, 100%, 50%) |
| green	| hsl(120, 100%, 50%) |
| cyan	| hsl(180, 100%, 50%) |
| blue	| hsl(240, 100%, 50%) |
| magenta	| hsl(300, 100%, 50%) |

## Color Gradient
Applying a color on HTML elements is not limited to one flat hue. CSS provides the ability to use color transitions, otherwise known as gradients, on elements. This is accessed through the background property's linear-gradient() function. Here is the general syntax:

background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);

The first argument specifies the direction from which color transition starts - it can be stated as a degree, where 90deg makes a vertical gradient and 45deg is angled like a backslash. The following arguments specify the order of colors used in the gradient.

Example:
`background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));`
