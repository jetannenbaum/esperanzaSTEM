# Our Third Lab: Reading a Button Press

## Solution: Interrupt Method

```python
# Author: J.E. Tannenbaum
# Initial Release: 01/13/2022
# Alternating blinking leds
from machine import Pin
import utime
from time import sleep

# define the last time a button was pressed
lastTime = 0

# Define the pin for each led
led1 = Pin(16, Pin.OUT)
led2 = Pin(17, Pin.OUT)

# define the pin for the button
button = Pin(15, Pin.IN, Pin.PULL_DOWN)

# make sure one is off and one is on
led1.low()
led2.high()

# handle the button press
def buttonPressed(pin):
    global lastTime, led1, led2
    
    # get the time the button was pressed and compare it with the last time
    newTime = utime.ticks_ms()
    if newTime - lastTime > 200:
        led1.toggle()
        led2.toggle()
        lastTime = newTime
        
# register the interrupt handler for the button
button.irq(trigger=Pin.IRQ_FALLING, handler=buttonPressed)

# Do nothing loop
while True:
    sleep(10)
```
