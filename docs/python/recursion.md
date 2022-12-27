
## What is Recursion?

Recursion means "defining a problem in terms of itself". This can be a very powerful tool in writing algorithms. Recursion comes directly from Mathematics, where there are many examples of expressions written in terms of themselves.

## A Simple Example - Walk Home

```python
def walkHome(stepsFromHome):
    if stepsFromHome == 0:
        print('You are home')
    else:
        print('Steps from home:' + str(stepsFromHome))
        walkHome(stepsFromHome - 1)

walkHome(10)
```

Here the solution to finding your way home is two steps (three steps). First, we don't go home if we are already home. Secondly, we do a very simple action that makes our situation simpler to solve. Finally, we redo the entire algorithm.

!!! Challenge
    1. Summing a list of numbers:
        - What is a recursive solution to summing up a list of numbers?
            - Note that the sum of [1 2 3 4 5 6 7 8 9] is equal to 1 + sum of [2 3 4 5 6 7 8 9]
    1. Sum counting numbers:
        - What are counting numbers?
            - Positive inters from 1 to infinity (and beyond)
        - If we count backwards, the solution becomes:
            - sum(1) = 1
            - sum(n) - n + sum(n - 1)
        - What is sum(20)?
    3. Factorial:
        - What is the definition of a factorial?
            - factorial(x) = x * factorial(x - 1)
            - Note: we only use counting numbers, so we will stop at factorial(1)
                - What is factorial(10)?
    4. Fibonacci Sequence:
        - What is a Fibonacci Sequence?
            - The sequence is defined as follows:
                - 1, 1, 2, 3, 5, 8, ...
                - fib(x) = fib(x - 1) + fib(x - 2)
            - Using this equation, we can determine the nth number in the Fibonacci sequence
            - What is the next number in the sequence where fib(0) and fib(1) = 1, fib(2) = 2, etc.?

## Solutions

 1. Summing a list of numbers: [https://trinket.io/python3/3fc6942d2f](https://trinket.io/python3/3fc6942d2f)

 1. Sum the counting numbers up to 20: [https://trinket.io/python/2e8cf2b456](https://trinket.io/python/2e8cf2b456)

 1. Factorial: [https://trinket.io/python3/ab3e92b2d1](https://trinket.io/python3/ab3e92b2d1)

 1. Fibonacci: [https://trinket.io/python3/dce6382d1f](https://trinket.io/python3/dce6382d1f)         
