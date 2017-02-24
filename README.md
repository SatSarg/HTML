# HTML
HTML5

When writing HTML5 documents, one of the first new features that you'll notice is the doc type declaration:
<!DOCTYPE HTML> 

The character encoding (charset) declaration is also simplified:
<meta charset="UTF-8">

New Elements in HTML5
<article>, <aside>, <audio>, <canvas>, <datalist>, <details>, <embed>, <footer>, <header>, <nav>, <output>, <progress>, <section>, <video>, and even more!
The default character encoding in HTML5 is UTF-8.

New in HTML5

Forms
- The Web Forms 2.0 specification allows for creation of more powerful forms and more compelling user experiences.
- Date pickers, color pickers, and numeric stepper controls have been added.
- Input field types now include email, search, and URL.
- PUT and DELETE form methods are now supported.

Integrated API (Application Programming Interfaces) 
- Drag and Drop
- Audio and Video
- Offline Web Applications
- History
- Local Storage
- Geolocation
- Web Messaging
You will learn more about these new features in the upcoming lessons.
Tap the Continue button to begin!

The scale() Method

The scale() method scales the current drawing. It takes two parameters:
- The number of times by which the image should be scaled in the X-direction.
- The number of times by which the image should be scaled in the Y-direction.
var canvas = document.getElementById('canvas1');
ctx =canvas.getContext('2d');
ctx.font="bold 22px Tahoma";
ctx.textAlign="start";
ctx.fillText("start", 10, 30);
ctx.translate(100, 150);
ctx.fillText("after translate", 0, 0);
ctx.rotate(1);
ctx.fillText("after rotate", 0, 0);
ctx.scale(1.5, 4);
ctx.fillText("after scale", 0,20);
Try It Yourself

This will scale the canvas 1.5 times in the X-direction, and 4 times in Y-direction:


Shape Animations

SVG animations can be created using the <animate> element. 

The example below creates a rectangle that will change its position in 3 seconds and will then repeat the animation twice:
<svg width="1000" height="250">
<rect width="150" height="150" fill="orange">
  <animate attributeName="x" from="0" to="300"
    dur="3s" fill="freeze" repeatCount="2"/> 
</rect>
</svg>
Try It Yourself

attributeName: Specifies which attribute will be affected by the animation
from: Specifies the starting value of the attribute
to: Specifies the ending value of the attribute
dur: Specifies how long the animation runs (duration)
fill: Specifies whether or not the attribute's value should return to its initial value when the animation is finished (Values: "remove" resets the value; "freeze" keeps the “to value”)
repeatCount: Specifies the repeat count of the animation

In the example above, the rectangle changes its x attribute from 0 to 300 in 3 seconds.
To repeat the animation indefinitely, use the value "indefinite" for the repeatCount attribute.

Paths

The <path> element is used to define a path.

The following commands are available for path data:
M: moveto
L: lineto
H: horizontal lineto
V: vertical lineto
C: curveto
S: smooth curveto
Q: quadratic Bézier curve
T: smooth quadratic Bézier curveto
A: elliptical Arc
Z: closepath

Define a path using the d attribute:
<svg width="500" height="500">
<path d="M 0 0 L200 200 L200 0 Z" style="stroke:#000;  fill:none;" />
</svg>

M places our "virtual pen" down at the position 0, 0. It then moves 200px down and to the right, then moves up to the position 200, 0. The Z command closes the shape, which results in a hypotenuse:

All of the above commands can also be expressed with lower case letters. When capital letters are used, it indicates absolute position; lower case indicates relative position.

The <canvas> Element

The HTML canvas is used to draw graphics that include everything from simple lines to complex graphic objects.

The <canvas> element is defined by:
<canvas id="canvas1" width="200" height="100">
</canvas>

The <canvas> element is only a container for graphics. You must use a script to actually draw the graphics (usually JavaScript).

The <canvas> element must have an id attribute so it can be referred to by JavaScript:
<html>
   <head></head>
   <body>
     <canvas id="canvas1" 
   width="400" height="300"></canvas> 

   <script>
      var can = document.getElementById("canvas1"); 
      var ctx = can.getContext("2d");
   </script>

   </body>
</html>

getContext() returns a drawing context on the canvas.
Basic knowledge of JavaScript is required to understand and use the Canvas.


Canvas Coordinates

The HTML canvas is a two-dimensional grid.
The upper-left corner of the canvas has the coordinates (0,0).

X coordinate increases to the right.
Y coordinate increases toward the bottom of the canvas.


Drawing Shapes

The fillRect(x, y, w, h) method draws a "filled" rectangle, in which w indicates width and h indicates height. The default fill color is black. 

A black 100*100 pixel rectangle is drawn on the canvas at the position (20, 20):
var c=document.getElementById("canvas1");
var ctx=c.getContext("2d");
ctx.fillRect(20,20,100,100);

The fillStyle property is used to set a color, gradient, or pattern to fill the drawing.
Using this property allows you to draw a green-filled rectangle.
var canvas=document.getElementById("canvas1");
var ctx=canvas.getContext("2d");
ctx.fillStyle ="rgba(0, 200, 0, 1)";
ctx.fillRect (36, 10, 22, 22);

The canvas supports various other methods for drawing:

Draw a Line
moveTo(x,y): Defines the starting point of the line.
lineTo(x,y): Defines the ending point of the line.

Draw a Circle
beginPath(): Starts the drawing.
arc(x,y,r,start,stop): Sets the parameters of the circle.
stroke(): Ends the drawing.

Gradients
createLinearGradient(x,y,x1,y1): Creates a linear gradient.
createRadialGradient(x,y,r,x1,y1,r1): Creates a radial/circular gradient.

Drawing Text on the Canvas
Font: Defines the font properties for the text.
fillText(text,x,y): Draws "filled" text on the canvas.
strokeText(text,x,y): Draws text on the canvas (no fill).
There are many other methods aimed at helping to draw shapes and images on the canvas.


Canvas vs. SVG

Canvas
- Elements are drawn programmatically
- Drawing is done with pixels
- Animations are not built in
- High performance for pixels-based drawing operations
- Resolution dependent
- No support for event handlers
- You can save the resulting image as .png or .jpg
- Well suited for graphic-intensive games

SVG
- Elements are part of the page's DOM (Document object model)
- Drawing is done with vectors
- Effects, such as animations are built in
- Based on standard XML syntax, which provides better accessibility
- Resolution independent
- Support for event handlers
- Not suited for game applications
- Best suited for applications with large rendering areas (for example, Google Maps)

You can actually use both SVG and canvas on the same page, if needed.
However, you cannot just draw SVG onto a canvas, or vice-versa.

Working with Canvas

The Canvas element can be transformed. As an example, a text is written on the canvas at the coordinates (20, 10).
ctx.font="bold 22px Tahoma";
ctx.textAlign="start";
ctx.fillText("start", 10, 30);

The translate(x,y) method is used to move the Canvas.
x indicates how far to move the grid horizontally, and y indicates how far to move the grid vertically.
ctx.translate(100, 150);
ctx.fillText("after translate", 10, 30);
Try It Yourself

In this example, the canvas is moved 100px to the right, and 150px down.
Result:

The rotate() Method

The rotate() method is used to rotate the HTML5 Canvas. The value must be in radians, not degrees.

Here is an example that draws the same rectangle before and after rotation is set:
ctx.fillStyle = "#FF0000";
ctx.fillRect(10,10, 100, 100);

ctx.rotate( (Math.PI / 180) * 25);  //rotate 25 degrees.

ctx.fillStyle = "#0000FF";
ctx.fillRect(10,10, 100, 100);

HTML5 Forms

HTML5 brings many features and improvements to web form creation. There are new attributes and input types that were introduced to help create better experiences for web users.

Form creation is done in HTML5 the same way as it was in HTML4:
<form>
   <label>Your name:</label>
   <input id="user" name="username" type="text" />
</form>


New Attributes

HTML5 has introduced a new attribute called placeholder. On <input> and <textarea> elements, this attribute provides a hint to the user of what information can be entered into the field.
<form>
   <label for="email">Your e-mail address: </label> 
   <input type="text" name="email" placeholder="email@example.com" /> 
</form>


The autofocus attribute makes the desired input focus when the form loads:
<form>
   <label for="e-mail">Your e-mail address: </label> 
   <input type="text" name="email" autofocus/>
</form>



Forms with Required Fields

The "required" attribute is used to make the input elements required.
<form autocomplete="off">
   <label for="e-mail">Your e-mail address: </label>
   <input name="Email" type="text" required />
   <input type="submit" value="Submit"/>
</form>

The form will not be submitted without filling in the required fields.

The autocomplete attribute specifies whether a form or input field should have autocomplete turned on or off.
When autocomplete is on, the browser automatically complete values based on values that the user has entered before.


HTML5 added several new input types:
- color
- date
- datetime
- datetime-local
- email
- month
- number
- range
- search
- tel
- time
- url
- week

New input attributes in HTML5:
- autofocus
- form
- formaction
- formenctype
- formmethod
- formnovalidate
- formtarget
- height and width
- list
- min and max
- multiple
- pattern (regexp)
- placeholder
- required
- step
Input types that are not supported by old web browsers, will behave as input type text.

Creating a Search Box

The new search input type can be used to create a search box:
<input id="mysearch" name="searchitem" type="search" />


Search Options

The <datalist> tag can be used to define a list of pre-defined options for the search field:
<input id="car" type="text" list="colors" />
<datalist id="colors">
   <option value="Red">
   <option value="Green">
   <option value="Yellow">
</datalist>


<option> defines the options in a drop-down list for the user to select. 
The ID of the datalist element must match with the list attribute of the input box.



Creating More Fields

Some other new input types include email, url, and tel:
<input id="email" name="email" type="email" placeholder="example@example.com" />
<br />
<input id="url" name="url" type="url" placeholder="example.com" />
<br />
<input id="tel" name="tel" type="tel" placeholder="555.555.1211" />

These are especially useful when opening a page on a modern mobile device, which recognizes the input types and opens a corresponding keyboard matching the field's type:

nkar html2
These new types make it easier to structure and validate HTML forms.
