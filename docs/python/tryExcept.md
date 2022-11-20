
## Four Parts of Exception Handling

- try: Lets you test a block of code for errors
- except: Lets you handle the error
- else: lets you execute the code when there isn't an error
- finally: always executes the code, regardless of any error

## Handling the Initial Error

- How can you handle an error when:
    - A user enters bad input?
    - There is an error in a calculation?

- Handle the error gracefully with exception handling!

```python
randomList = ['a', 0, 2]
for entry in randomList:
    try:
        r = 1/int(entry)
        print('The reciprocal of ', entry, ' is ', r)
    except:
        print('Oops! an exception occurred.')
        print('No reciprocal for: ', entry)
```
Since the error occurs inside the try block, the except block executes and the error message is printed.  If the code was not inside the try block, the program would crash.

[https://trinket.io/python/4742df2d3a](https://trinket.io/python/4742df2d3a)

## Using else When an Error Didn't Happen

We can use an else block to execute a block of code when there are no errors:

```python
randomList = ['a', 0, 2]
for entry in randomList:
    try:
        r = 1/int(entry)
        print('The reciprocal of ', entry, ' is ', r)
    except:
        print('Oops! an exception occurred.')
        print('No reciprocal for: ', entry)
    else:
        print('Success, we found the reciprical!')
```

# Finally, Using finally to clean up

The finally block will always execute, no matter if an error occurs or the code executes without an error

```python
randomList = ['a', 0, 2]
while randomList != []:
  entry = randomList[0]
  try:
    r = 1/int(entry)
    print('The reciprocal of ', entry, ' is ', r)
  except:
    print('Oops! an exception occurred.')
    print('No reciprocal for: ', entry)
  else:
    print('Success, we found the reciprical!')
  finally:
    randomList.pop(0)
```
[https://trinket.io/python3/7520b1fcd1](https://trinket.io/python3/7520b1fcd1)