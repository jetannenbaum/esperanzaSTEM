
## What is a Function?

- A function is a way to organize code into reusable sections. 
- It is a group of related statements that perform a specific task.  
- You can pass data, known as parameters, into a function. 
- A function can return data as a result.

## Defining a Function

```python
def drawSquare():
    for i in range(4):
        jet.forward(40)
        jet.right(90)
```

## Passing Variables into a Function

```python
def drawPolygon(sides, distance, angle):
    for i in range(sides):
        jet.forward(distance)
        jet.right(angle)
```

## Returning a Result From a Function

```python
def sumNumbers(numbers):
    sum = 0
    for number in numbers:
        sum += number
    return sum
```

## Calling a Function

```python
def sumNumbers(numbers):
    sum = 0
    for number in numbers:
        sum += number
    return sum

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print('The sum of the numbers from 1 to 10 is: ' + str(sumNumbers(numbers)))
```

!!! Challenge
    Can you create a function that draws a polygon in a color?  Once you have the function, try calling it.

    Using a function: [https://trinket.io/python/550d2a8530](https://trinket.io/python/550d2a8530)