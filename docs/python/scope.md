
## What is Scope?

A variable is only available from inside the region it is created. This is called scope.  There are two types of scope:

- Local Scope: A variable created inside a function belongs to the local scope of that function, and can only be used inside that function.
- Global Scope: A variable created in the main body of the Python code is a global variable and belongs to the global scope.

## Local Scope

A variable that is created inside a function is only available inside that function:

```python
def localVariable():
    myLocalVariable = 12345
    print(myLocalVariable)

localVariable()
```

As explained above, the local variable is not available outside of the function.  However, it is available to any nested function:

```python
def localVariable():
    myLocalVariable = 12345

    def printLocalVariable()
        print(myLocalVariable)

    printLocalVariable()

localVariable()
```

## Global Scope

A variable created outside of a function has global scope and can be used inside or outside of a function

```python
distance = 40

def drawSquare():
    for i in range(4):
        jet.forward(distance)
        jet.right(90)

print('Draw a square with each side = ' + str(distance))
drawSquare()
```

## Reusing a variable inside of a function

```python
sum = 0
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

def sumNumbers(numbers):
    sum = 0
    for number in numbers:
        sum += number
    print(sum) # This will print 55

sumNumbers(numbers)
print(sum) # This will print 0
```

## Global Keyword

If you need to create a global variable, but are stuck in the local scope, you can use the global keyword.

```python
sum = 0
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

def sumNumbers(numbers):
    global sum
    
    for number in numbers:
        sum += number
    print(sum) # This will print 55

sumNumbers(numbers)
print(sum) # This will also print 55
```
