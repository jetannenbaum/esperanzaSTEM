
# The Turtle Graphics Library

## What is the turtle graphics library?

Turtle graphics have been around for almost 50 years. A turtle is a drawing object that has position, direction, and a pen to draw as it moves around a grid. Turtle graphics are the preferred way to teach many concepts in computer science because they give you fast feedback.

We will use the turtle python library. Although there are many different versions of the turtle library, most of the commands are similar. What you learn with the trinket python system will be useful in other systems also.

## Why use the turle graphics library?

* Fast feedback for learning programming concepts
* The “turtle” can be any shape, color, or size
* The turtle can be positioned at any coordinate on the screen
* It can be moved in any direction from its initial starting point

## Adding a turtle to your Python code
```python
import turtle           # Load the library
jet = turtle.Turtle()   # Create the turtle object and name it (use any name)
jet.shape("turtle")     # Set the shape to be a turtle
```

## Moving the turtle

There are five different ways to move a turtle:

1. jet.forward(40)
1. jet.back(40)
1. jet.left(90)
1. jet.right(90)
1. jet.goto(x, y)

!!! Challenge
    Create a trinket with your turtle and draw a square.

