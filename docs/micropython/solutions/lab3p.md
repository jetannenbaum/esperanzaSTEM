# Our Third Lab: Reading a Button Press

## Solution: Polling Method

```python
# Author: J.E. Tannenbaum
# Initial Release: 01/13/2022
# Alternating blinking leds
from machine import Pin
from time import sleep

# Define the pin for each led
led1 = Pin(16, Pin.OUT)
led2 = Pin(17, Pin.OUT)

# define the pin for the button
button = Pin(15, Pin.IN, Pin.PULL_DOWN)

# make sure one is off and one is on
led1.low()
led2.high()

# Toggle when the button is pressed
while True:

    # Was the button pressed?
    if button.value():
        led1.toggle()
        led2.toggle()

        # This is delay to give time to get finger off the button.  
        sleep(0.5)
```
