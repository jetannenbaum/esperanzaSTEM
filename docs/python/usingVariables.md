
In the simple square program we repeated the numbers for the distance and turning angle four times in four different places.  If we wanted to change the size of our box we would have to change the code in four different places.  By using variables we can make our program easier to change.

Modifying the previous example program, we will still make the turtle go forward 40 steps and then make a right turn of 90 degrees.  However, we will use variables to make our life easier.  Note the inclusion of a set of comments before the code, identifying the author, when the code was created, and any changes to the code

## Sample Code
```python
# J.E. Tannenbaum
# Released: 11/10/2021 - Initial release
# 11/10/2022 - Cleaned up and added comments

import turtle		      # Load the library
jet = turtle.Turtle()	  # Create the turtle object and name it
jet.shape("turtle")	      # Set the shape

# Set the distance and angle variables
distance = 40
angle = 90

# Draw the square
jet.forward(distance)
jet.right(angle)
jet.forward(distance)
jet.right(angle)
jet.forward(distance)
jet.right(angle)
jet.forward(distance)
jet.right(angle)
```

Run Square With Variables: [https://trinket.io/python/94326b4743](https://trinket.io/python/94326b4743)

!!! Experiments
Can you make the turtle draw a larger square? 

- Hint: Set the distance variable to 100 instead of 40