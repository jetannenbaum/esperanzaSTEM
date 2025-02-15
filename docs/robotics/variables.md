# Using Variables

## Variable Naming Rules
- Must start with a letter or an underscore
- Can only contain alpha-numeric characters and underscores (A-z, 0-9, and _)
- Case sensitive (Delay is _not_ the same as delay)

    !!! Challenge
        Which Variable Names Are Legal?

        1. MrRoberts
        2. _goodbye!
        3. 2For1
        4. Mr.Tannenbaum
        5. X
        6. _wait
        7. _2

## Python is both a Strongly Type and Dynamically Type Language
- **Strong** typing means that the type of a value doesn't change in unexpected ways. A string containing only digits doesn't magically become a number. Every change of type requires an explicit conversion.
- **Dynamic** typing means that runtime objects (values) have a type, as opposed to static typing where variables have a type.

## What Does That Mean?
- **Text (string):** wait = "two"
- **Number with a decimal point (float):** wait = 2.0
- **Number without a decimal point (int):** wait = 2
- **A Collection (list):** wait = ["Two", 2.0, 2]

For example, the duty_u16 method from the PWM library only accepts a positive integer.

## So?

We can use variables to make driving the robot car simpler.  For example, we can create the following variables (use upper case to denote constants):

- SPEED = 32768
- DELAY = 2
- FREQUENCY = 1000

Now we can have the robot car easily move faster or further without changing the numbers in multiple places.  The simple code we had last time becomes:

```python
from machine import Pin, PWM
from time import sleep

DELAY = 2
SPEED = 32768
FREQUENCY = 1000

# Motor definitions
right_forward = PWM(Pin(11))
right_forward.freq(FREQUENCY)
right_reverse = PWM(Pin(10))
right_reverse.freq(FREQUENCY)
left_forward = PWM(Pin(9))
left_forward.freq(FREQUENCY)
left_reverse = PWM(Pin(8))
left_reverse.freq(FREQUENCY)

# Wait before moving
sleep(DELAY)

# Move Forward
right_reverse.duty_u16(0)
left_reverse.duty_u16(0)
right_forward.duty_u16(SPEED)
left_forward.duty_u16(SPEED)
sleep(DELAY)

# Move Backwards
right_forward.duty_u16(0)
left_forward.duty_u16(0)
right_reverse.duty_u16(SPEED)
left_reverse.duty_u16(SPEED)
sleep(DELAY)

# Stop Moving
right_forward.duty_u16(0)
right_reverse.duty_u16(0)
left_forward.duty_u16(0)
left_reverse.duty_u16(0)
```

If we want to move further or change the speed we can simply change the value of the variables.

!!! Challenge
    Rewrite the main.py code to use variables

    Make a larger square

    Move at a different speed