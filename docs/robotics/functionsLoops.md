# Functions and Loops

## What is a Function?

- A function is a way to organize code into reusable sections. 
- It is a group of related statements that perform a specific task.  
- You can pass data, known as parameters, into a function. 
- A function can return data as a result.

### Defining a Function

```python
def forward():
    right_reverse.duty_u16(0)
    left_reverse.duty_u16(0)
    right_forward.duty_u16(32768)
    left_forward.duty_u16(32768)
```

### Passing Variables into a Function

```python
def forward(speed, delay):
    right_reverse.duty_u16(0)
    left_reverse.duty_u16(0)
    right_forward.duty_u16(speed)
    left_forward.duty_u16(speed)
    sleep(delay)
```

### Returning a Result From a Function

```python
def distanceToObject():
    # Some code
    return distance_cm
```

### Calling a Function

```python
forward(SPEED, DELAY)
distance_cm = distanceToObject()
```

## Using a Loop

A loop is a way to repeat the same action.

### We can use a loop to have our car move in a square

```python
for i in range(4):
    forward(SPEED, DELAY)
    right(HALF_SPEED, DELAY_90_DEGREES)
stop()
```

### Let's examine the pieces of the for statement:

1. Starts with the reserved word _for_
1. Uses a variable that iterates
1. Next is the reserved word _in_ 
1. Finally, there is the data that is iterated over.  In this example, we have a set (or _range_) of numbers. Note: a _range_ is defined (by default) as starting at zero, so range(4) means that we are counting 0, 1, 2, 3. 

!!! Challenge
    Rewrite the main.py code to use functions for forward, reverse, left, right, and stop

    Use a loop so you don't "cut and paste" code

    After your robot successfully moves in a square, can you make it move in an octogon route?