# Turtle

Turtle is a Python library that allows us to create drawings. Imagine it like a little robot turtle on a piece of paper that has a pen and follows our instructions.

## Getting started with Turtle

Lets start by creating a new script called `Turtle.py`. In order to use Turtle we need to tell our script we want to use all the functions that come with Turtle. We do this by starting our script with:
```
import turtle as t
```
Now we can start using Turtle!

## Moving the turtle

### Forward and backwards

The most simple way of getting the turtle to move is with the `forward` and `backward` functions. Both of these functions take one argument: the amount of pixels the turtle should move by.

```
t.forward(100) # Move the turtle forward 100 pixels in the direction it is facing 
t.backward(50) # Move the turtle backwards 50 pixels from the direction it is facing 
```

### Left and right

You may noticed with the forwards and backwards commands, the turtle only moves in the direction it is faces. However, we can change which direction it is facing! We do this with the `left` and `right` functions. Both of these functions have one argument: the angle in degrees the turtle will turn.

```
t.left(45) # Turn the turtle 45 degrees to the left
t.right(30) # Turn the turtle 30 degrees to the right
```
This functions will not move the turtle anywhere, just turn it on the spot.

> 💡 Exercise: Try using the `forward`, `backward`, `left` and `right` functions to draw a square.

You might notice that the turtle window closes when the script has finished running. This doesn't give you time to admire your art work! If you would like to stop this you can add the line `t.done()`at the end of your script. This will tell the script that you have finished with Turtle but not close the window automatically.

<details> <summary> <b> Additional movement functions </b> </summary>

While you can create all kinds of drawings with the four functions mentioned above, there are many other ways of controlling the turtle. There are some listed here or you can read about them in the [Python Turtle library documentation](https://docs.python.org/3/library/turtle.html#turtle-motion). If you can think of way you want to move the turtle, there is probably way to do it!

#### Goto

Another way of controlling the turtle movement is by telling it directly what coordinate you want it to go to. It will move in a straight line from where it is to the coordinate you have told it to go to, regardless of which direction it is facing.

```
t.goto(100, 50) # Move turtle from where is it to the coordinate (100, 50) in a straight line
```

#### Teleport

You can also move the turtle to any position without drawing anything.
```
t.teleport(35, 75) # Move turtle from where it is to the coordinate (35, 75) without drawing anything
```

#### Home

The turtle's home is the coordinates (0, 0) and by calling the home function you can move it from where it is to those coordinates in a straight line.
```
t.home() # Move turtle from where it is to (0, 0) in a straight line
```
</details>

## Controlling the pen

In the introduction to Turtle, we mentioned that our robot turtle was holding a little pen. We can control when that pen will draw a line when the turtle moves with the following functions.

### Pen down

`pendown()` will put the pen 'down' to the digital 'paper' so that when the turtle moves, it will draw.

```
t.pendown() # Continue drawing
```
This function doesn't do anything if the pen is already down.

### Pen up

`penup()` will take the pen off the digital 'paper' so that when the turtle moves, it will not draw.

```
t.penup() # Stop drawing
```
This function doesn't do anything if the pen is already up.

> 💡 Exercise: Try using the previous two functions to create a dashed line.

### Clear

Sometimes we may want to delete all the drawings we have made with the turtle. We can do this with the `clear()` function:
```
t.clear() # Remove all drawings
```

## Customising

You will have noticed that so far, our turtle has only been using a small black pen. The Turtle library has functions that allow us to control what kind of line the turtle draws with its pen. We are able to control the size, colour, speed and fill.

> 💡 Exercise: Try drawing a square where each side changes pen size, pen colour, fill colour and speed using these functions.

### Pen size

The default pen size is 1 pixel. We can change what size it is with the function `pensize()`, for example:

```
t.pensize(5) # Set the pen to be 5 pixels thick
```

### Pen colour

The default pen colour is black. We can change what colour it is in a handful of different ways.

```
t.color("pink") # Change the pen colour to pink
t.color("#ffc0cb") # Change the pen colour to the colour with HEX value #ffc0cb
t.color(255, 192, 203) # Change the pen colour to the colour with RGB values 255, 192 and 203
```
You can find the name, hex value or RGB value of a colour by using a online [colour picker](https://www.google.co.uk/search?q=colour+picker).

**Note:** to use the RGB values you need to set the colour mode turtle uses by adding `t.colormode(255)` before you call `t.color()`.

### Fill

When drawing a closed shape (all lines join up) you can choose what colour to fill the shape in with.

First set the colour with `fillcolor()`. Here are three different ways of doing this.

```
t.fillcolor("pink") # Change the fill colour to pink
t.fillcolor("#ffc0cb") # Change the fill colour to the colour with HEX value #ffc0cb
t.fillcolor(255, 192, 203) # Change the fill colour to the colour with RGB values 255, 192 and 203
```

The fill colour does not have to be the same as the pen colour.

Then before you draw a closed shape call `begin_fill()`

```
t.begin_fill() # Tell Turtle to fill in the shape drawn after this
```

Once you have finished drawing the shape you need to call `end_fill()`

```
t.end_fill() # Tell Turtle you have finished drawing the shape you want to fill
```

The shape will only be filled once `end_fill()` has been called.

### Speed

You can get the speed the turtle moves at using `speed()`.

```
t.speed(5) # Sets the turtle to move at speed 5
t.speed("fastest") # Sets the turtle to move at its fastest speed
```

The turtle has speeds 0 to 10 so you can use any number between 0 and 10 or you can use some set speed strings:

|string|value|code|
|---|---|---|
|fastest|0|`t.speed(“fastest”)`|
|fast|10|`t.speed(“fast”)`|
|normal|6|`t.speed(“normal”)`|
|slow|3|`t.speed(“slow”)`|
|slowest|1|`t.speed(“slowest”)`|

## Screen

### Screen colour

The default screen colour is white but we can change what colour it is with `bgcolor()`. First you need to 'get' the screen:

```
screen = t.getscreen()
```

Then here are three different ways you can change the colour of the screen:
```
screen.bgcolor("pink") # Change the background to be pink
screen.bgcolor("#ffc0cb") # Change the background colour to the colour with HEX value #ffc0cb
screen.bgcolor(255, 192, 203) # Change the background colour to the colour with RGB values 255, 192 and 203
```

> 💡 Exercise: Try setting the background colour to green.

There are many other functions you can call on the screen which you can read about in the [Python Turtle library documentation](https://docs.python.org/3/library/turtle.html#methods-of-turtlescreen-screen-and-corresponding-functions).

## Inputs

Turtle is able to take some inputs from the user which you can then use in your script.

> 💡 Exercise: Try drawing a squares whose sides have the length the user gives.

### Number input

```
num = screen.numinput("Favourite number", "Please enter your favourite number") # Ask the user to enter their favourite number
```

### Text input

```
name = screen.textinput("Name", "Please enter your name") # Ask the user to enter their name
```

## Next

Next up: [Challenge](03-challenge.md)