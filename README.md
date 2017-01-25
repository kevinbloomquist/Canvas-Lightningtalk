# Canvas-Lightningtalk
---
Think back over the last 12 weeks. Did you, at any point in time, have a thought like " I JUST WANT THAT THING TO BE THERE!!!" or "WHY CAN'T I JUST MAKE A THING! ALL I WANT TO DO IS MAKE A THING!?" or "IF MY SCREEN WERE A PIECE OF PAPER I'D BE DONE BY NOW!"

No? Good for you, shut up.

The rest of us get canvas now!

##What is Canvas?
Added in HTML5, the HTML `<canvas>` element can be used to draw graphics via scripting in JavaScript. For example, it can be used to draw graphs, make photo compositions, create animations, or even do real-time video processing or rendering.

##How do I use it?
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
[Check it out!](http://caniuse.com/#feat=canvas)

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
var canvas = document.getElementById('demo') 
``  

``
var ctx = canvas.getContext('2d');
``

The first line in the script retrieves the node in the DOM representing the `<canvas>` element by calling the document.getElementById() method. Once you have the element node, you can access the drawing context using its getContext() method.

##Get to the good stuff already!


##Alright...

###The Grid
---

If you remember from the section above our example grid is a square with a width and height of 150px. Imagine a grid painted over our canvas. Normally 1 unit in the grid corresponds to 1 pixel on the canvas. The origin of this grid is positioned in the top left corner at coordinate (0,0). All elements are placed relative to this origin. So the position of the top left corner of the blue square becomes x pixels from the left and y pixels from the top, at coordinate (x,y). You can translate the origin to a different position, rotate the grid and even scale it, but for now we'll stick to the default.

![](https://mdn.mozillademos.org/files/224/Canvas_default_grid.png)

##Drawing shapes

Canvas only inherently supports one shape... a rectangle. That is to say, the only shape you will see the code directly allude to is rect like in the code below  
```
fillRect(x, y, width, height)
Draws a filled rectangle.

strokeRect(x, y, width, height)
Draws a rectangular outline.

clearRect(x, y, width, height)
Clears the specified rectangular area, making it fully transparent.
```

Here is an example of what a draw function might look like. Note how the canvas and context are brought in. Most if not all of your canvas work will start like this.

```
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.fillRect(25, 25, 100, 100);
    ctx.clearRect(45, 45, 60, 60);
    ctx.strokeRect(50, 50, 50, 50);
  }
}
```
The fillRect() function draws a large black square 100 pixels on each side. The clearRect() function then erases a 60x60 pixel square from the center, and then strokeRect() is called to create a rectangular outline 50x50 pixels within the cleared square.

The rest the cool stuff comes through path and move methods so...

##What is a path?

A path is a list of points, that can be any shape. You can vary a path by width or color and they can be left open or closed to complete a non-rectangular shape. In other words, think like an etch-a-sketch. 

Great, so we can almost make an awesome shape but then we have to cross everything to get to another spot or start a new shape...

Nope!
We have moveTo(x,y)! The moveTo() function is how we escape the etch-a-sketch handcuffs and pick up our pencil. Which is the last piece of the "getting started" puzzle.

##So what kind of stuff can I do!?

Like most of the awesome creative tools we've seen so far ( or a pencil for that matter) canvas is pretty easy to pick up and you could be up and struggling in just a few minutes but again, like most creative tools there is a "creative curve" and it feels like it would take alot of "doodling" to get the final product to match your vision.

With just a little time spent on tutorials you could produce some fun stuff:
(Fun!)[https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes]

Given a few days...
(GA Student Project)[https://github.com/briandridge/project-1]

But canvas can do some really cool stuff so the sky's the limit!
(Legwork Studios)[http://www.legworkstudio.com/animation]










