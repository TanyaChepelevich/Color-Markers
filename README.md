# Color-Markers
CSS colors by building a Set of Colored Markers

![Colored Markers](https://user-images.githubusercontent.com/77103357/199968579-da597ff5-2f93-44fe-bdf1-48387689d896.png)

## Colors in CSS
One way to add color to an element is to use a color keyword like black, cyan, or yellow.
There are two main color models: the **additive RGB (red, green, blue) model** used in electronic devices, and the **subtractive CMYK (cyan, magenta, yellow, black) model** used in print.

### RGB Model
In this project I use the RGB model. This means that colors begin as black, and change as different levels of red, green, and blue are introduced. An easy way to see this is with the CSS rgb function.

A function is a piece of code that can take an input and perform a specific action. The CSS rgb function accepts values, or arguments, for red, green, and blue, and produces a color:
```
rgb(red, green, blue);
```
Each red, green, and blue value is a number from 0 to 255. 
- 0 means that there's 0% of that color, and is black. 
- 255 means that there's 100% of that color.

In the additive RGB color model, _primary colors_ are colors that, when combined, create pure white. But for this to happen, each color needs to be at its highest intensity.

![ColorMarkers](https://user-images.githubusercontent.com/77103357/199969151-3d722498-2b91-4b3d-b433-3fe9aa4aff0d.png)
1. RED rgb(255, 0, 0)
1. GREEN rgb(0, 255, 0)
1. BLUE rgb(0, 0, 255)

_Secondary colors_ are the colors you get when you combine primary colors. 

![secondary colors](https://user-images.githubusercontent.com/77103357/199969237-c93d8c1e-8897-4a05-8e0e-2c7c79a409f0.png)
1. YELLOW rgb(255, 255, 0)
1. CYAN rgb(0, 255, 255)
1. MAGENTA rgb(255, 0, 255)

_Tertiary colors_ are created by combining a primary with a nearby secondary color.

![Tertiary colors1](https://user-images.githubusercontent.com/77103357/199969494-8c3dec11-ed79-4af1-ab58-82f9167ac1ee.png)
1. ORANGE rgb(255, 127, 0)
1. SPRING GREEN rgb(0, 255, 127)
1. VIOLET rgb(127, 0, 255)

There are three more tertiary colors: chartreuse green (green + yellow), azure (blue + cyan), and rose (red + magenta). 

![tertiary colors2](https://user-images.githubusercontent.com/77103357/199969572-fe2aec60-fdfd-4c1c-bfe1-8f7cd8e8e6c3.png)
1. CHARTREUSE GREEN rgb(127, 255, 0)
1. AZURE rgb(0, 127, 255)
1. ROSE rgb(255, 0, 127)

A color wheel is a circle where similar colors, or hues, are near each other, and different ones are further apart. For example, pure red is between the hues rose and orange.

Two colors that are opposite from each other on the color wheel are called complementary colors. If two complementary colors are combined, they produce gray. But when they are placed side-by-side, these colors produce strong visual contrast and appear brighter.

It's better practice to choose one color as the dominant color, and use its complementary color as an accent to bring attention to certain content on the page.

### Hexadecimal values
A very common way to apply color to an element with CSS is with **hexadecimal** or hex values. While hex values sound complicated, they're really just another form of RGB values.

Hex color values start with a `#` character and take six characters from 0-9 and A-F. The first pair of characters represent red, the second pair represent green, and the third pair represent blue. For example, `#4B5320`.
You may already be familiar with decimal, or base 10 values, which go from 0 - 9. Hexadecimal, or base 16 values, go from 0 - 9, then A - F:
```
0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F
```
With hex colors, 00 is 0% of that color, and FF is 100%. So #00FF00 translates to 0% red, 100% green, and 0% blue, and is the same as rgb(0, 255, 0).

### HSL color model

The HSL color model, or hue, saturation, and lightness, is another way to represent colors.

The CSS hsl function accepts 3 values: 
- a number from 0 to 360 for hue, 
  - If you imagine a color wheel, the hue red is at 0 degrees, green is at 120 degrees, and blue is at 240 degrees.
- a percentage from 0 to 100 for saturation
  - _Saturation_ is the intensity of a color from 0%, or gray, to 100% for pure color.
- a percentage from 0 to 100 for lightness
  - _Lightness_ is how bright a color appears, from 0%, or complete black, to 100%, complete white, with 50% being neutral.

### Color Transition or _Gradient_
You've learned a few ways to set flat colors in CSS, but you can also use a color transition, or gradient, on an element.

A gradient is when one color transitions into another. The CSS `linear-gradient` function lets you control the direction of the transition along a line, and which colors are used.

One thing to remember is that the _linear-gradient function actually creates an image element_, and is usually paired with the `background` property which can accept an image as a value.

The linear-gradient function is very flexible -- here is the basic syntax you'll use in this tutorial:
```
linear-gradient(gradientDirection, color1, color2, ...);
```
`gradientDirection` is the direction of the line used for the transition.
If no gradientDirection argument is provided to the linear-gradient function, it arranges colors from top to bottom, or along a 180 degree line, by default.
 `Color1` and `Color2` are color arguments, which are the colors that will be used in the transition itself. These can be any type of color, including color keywords, hex, rgb, or hsl.
While the linear-gradient function needs a minimum of two color arguments to work, it can accept many color arguments.

**Color-stops** allow you to fine-tune where colors are placed along the gradient line. They are a length unit like px or percentages that follow a color in the linear-gradient function.

For example, in this red-black gradient, the transition from red to black takes place at the 90% point along the gradient line, so red takes up most of the available space:
```
linear-gradient(90deg, red 90%, black);
```
Even without the color-stops the linear-gradient function automatically calculates these values for you, and places colors evenly along the gradient line by default.

### Opacity

Opacity describes how opaque, or non-transparent, something is. For example, a solid wall is opaque, and no light can pass through. But a drinking glass is much more transparent, and you can see through the glass to the other side.

With the CSS `opacity` property, you can control how opaque or transparent an element is. With the value 0, or 0%, the element will be completely transparent, and at 1.0, or 100%, the element will be completely opaque like it is by default.

Another way to set the opacity for an element is with the **alpha channel**. Similar to the opacity property, the alpha channel controls how transparent or opaque a color is.

To add an alpha channel to an rgb color, use the rgba function instead.

The rgba function works just like the rgb function, but takes one more number from 0 to 1.0 for the alpha channel:
```
rgba(redValue, greenValue, blueValue, alphaValue);

```
### Shadows
The `box-shadow` property lets you apply one or more shadows around an element. Here is basic syntax:
```
box-shadow: offsetX offsetY color;
```
f you wanted to position your shadow on the opposite side? You can do that by using _negative values_ for offsetX and offsetY.

Whith the basic sintacs the edges of the shadow are sharp. This is because there is an optional `blurRadius` value for the box-shadow property:
```
box-shadow: offsetX offsetY blurRadius color;
```
If a **blurRadius** value isn't included, it defaults to 0 and produces sharp edges. The higher the value of blurRadius, the greater the blurring effect is.
If you wanted to expand the shadow out further, you can do that with the optional `spreadRadius` value:
```
box-shadow: offsetX offsetY blurRadius spreadRadius color;
```
Like blurRadius, spreadRadius defaults to 0 if it isn't included.

