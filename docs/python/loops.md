
## Using a Loop

A loop is a way to repeat the same action.

Instead of writing:

```python
# Draw a square:
jet.forward(distance)
jet.right(angle)
jet.forward(distance)
jet.right(angle)
jet.forward(distance)
jet.right(angle)
jet.forward(distance)
jet.right(angle)
```

We can use a loop:
```python
# Draw a square:
for i in range(4):
    jet.forward(distance)
    jet.right(angle)
```

Let's examine the pieces of the for statement:

1. Starts with the reserved word _for_
1. Uses a variable that iterates
1. Next is the reserved word _in_ 
1. Finally, there is the data that is iterated over.  In this example, we have a set (or _range_) of numbers. Note: a _range_ is defined (by default) as starting at zero, so range(4) means that we are counting 0, 1, 2, 3. 

See a loop in action: [https://trinket.io/python/11386c7fa2](https://trinket.io/python/11386c7fa2)

!!! Experiments
1. Can you make the turtle draw a larger square?  Hint: change the distance to be 80.  How big can you make the square before the turtle goes off the screen?
1. A polygon's internal angle can be calculated as: angle = 360 / Number of sides.  A square is a type of polygon.  It has four sides, so the internal angle = 360 / 4 = 90 degrees!
1. Can you make a hexagon?  This is a figure with six sides.  Hint: Use the equation above to calculate the internal angle.
1. Can you make an octagon?  An Octagon has eight sides.
1. Can you make a stop sign?  You will need to use a jet.color('red'). a jet.beginfill() and a jet.endfill().  You can add the text of the word "stop" by using jet.moveto(x,y) and jet.write("STOP",None,None, "30pt bold").  You can also use the jet.hideturtle() so that the outline of the turtle is not displayed at the end.
