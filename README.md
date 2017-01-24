# Canvas-Lightningtalk


##What is Canvas?
Added in HTML5, the HTML `<canvas>` element can be used to draw graphics via scripting in JavaScript. For example, it can be used to draw graphs, make photo compositions, create animations, or even do real-time video processing or rendering.

##Basic Usage
The Canvas
````
<canvas id="demo" width="150" height="150"></canvas>
````

The HTML5 `<canvas>` tag is used to draw graphics, on the fly, via scripting (usually JavaScript).
However, the `<canvas>` element has no drawing abilities of its own (it is only a container for graphics) - you must use a script to actually draw the graphics.

At first sight a `<canvas>` looks like the `<img>` element, with the only clear difference being that it doesn't have the src and alt attributes. Indeed, the `<canvas>` element has only two attributes, width and height. These are both optional and can also be set using DOM properties. When no width and height attributes are specified, the canvas will initially be 300 pixels wide and 150 pixels high. The element can be sized arbitrarily by CSS, but during rendering the image is scaled to fit its layout size: if the CSS sizing doesn't respect the ratio of the initial canvas, it will appear distorted.

The `<canvas>` element itself is a normal block element and can be styled like any other block element. The rules, however don't affect the actual drawing on the canvas.

##Support
Canvas seems to be pretty well supported for a relatively new syntax          
[http://caniuse.com/#feat=canvas]

###Note:
With that said,keep in mind that canvas displays alternative/fallback content a little differently. Providing fallback content is very straightforward: just insert the alternate content inside the `<canvas>` element. Browsers that don't support `<canvas>` will ignore the container and render the fallback content inside it. Browsers that do support `<canvas>` will ignore the content inside the container, and just render the canvas normally.

For example:
```
<canvas id="stockGraph" width="150" height="150">
  current stock price: $3.15 +0.15
</canvas>

<canvas id="clock" width="150" height="150">
  <img src="images/clock.png" width="150" height="150" alt=""/>
</canvas>
```
As a consequence of the way fallback is provided, unlike the `<img>` element, the `<canvas>` element requires the closing tag `</canvas>`. If this tag is not present, the rest of the document would be considered the fallback content and wouldn't be displayed.

##The rendering context? What's that?
The `<canvas>` element creates a fixed-size drawing surface that exposes one or more rendering contexts, which are used to create and manipulate the content shown. 

The canvas is initially blank. To display something, a script first needs to access the rendering context and draw on it. The `<canvas>` element has a method called getContext(), used to obtain the rendering context and its drawing functions. getContext() takes one parameter, the type of context. For 2D graphics, you specify "2d" to get a CanvasRenderingContext2D.

``
var canvas = document.getElementById('tutorial') 
``  

``
var ctx = canvas.getContext('2d');
``

The first line in the script retrieves the node in the DOM representing the `<canvas>` element by calling the document.getElementById() method. Once you have the element node, you can access the drawing context using its getContext() method.

##Get to the good stuff already!

