CanvasTextWrapper
=================

##Syntax
```
new CanvasTextWrapper(HTMLCanvasElement, String [, options]);
```

```options``` - is a JavaScript object with the following available properties and values:

- ```font: String``` - text style that includes font size (in px), weight and family, similarly to CSS font shorthand property
- ```textAlign: "left" | "center" | "right"``` - horizontal alignment for each line
- ```verticalAlign: "top" | "middle" | "bottom"``` - vertical alignment for the whole text block
- ```paddingX: Number``` - horizontal padding in pixels set equally on both, left and right sides of the element
- ```paddingY: Number``` - vertical padding in pixels set equally on both, top and bottom sides of the element
- ```fitParent: Boolean``` - parameter that controls which element to fit where ```true``` means fit canvas parent's width instead of canvas own width
- ```lineBreak: "auto" | "word"``` - text split rule. When using ```"auto"```, text fills the element's width, going to a new line on a whole word when there's no more room. If ```"word"``` is set as value, each next word will be placed on a new line.
- ```sizeToFill: Boolean``` - ignore given font size and resize text to fill its padded container
- ```strokeText: Boolean``` - add text outline based on context configuration (make sure it doesn't contradict with other context settings such as globalCompositeOperation, etc)

NOTE: if a single word is too long to fit the width with specified font size, it will be broken into as many lines as required on any letter of the word unless ```sizeToFill``` option is used.

##Defaults

The default options object which values will be used if a property is not specified or no object is passed:

``` 
   { 
       font:          "18px Arial, sans-serif",
       textAlign:     "left",
       verticalAlign: "top",
       paddingX:       0,
       paddingY:       0,
       fitParent:      false,
       lineBreak:     "auto",
       sizeToFill:     false,
       strokeText:     false
    } 
```

##Usage
Use standard canvas text drawing сщташпгкфешщты such as "fillStyle" and "globalCompositeOperation" when needed before using CanvasTextWrapper like so:
``` 
var canvas = document.createElement('canvas');
canvas.width = 300;
canvas.height = 250;
context = canvas.getContext("2d");
context.fillStyle = "rgb(255, 255, 255)";
context.fillRect(0, 0, canvas.width, canvas.height);

new CanvasTextWrapper(canvas, "Hi there", {
      font:          "normal 40px Open Sans, sans-serif",
      textAlign:     "center",
      verticalAlign: "bottom",
      paddingY:      10,
      lineBreak:     "word",
});
```

##Examples
http://namniak.github.io/CanvasTextWrapper/

##Installation

```
bower install canvas-text-wrapper

npm install canvas-text-wrapper
```
