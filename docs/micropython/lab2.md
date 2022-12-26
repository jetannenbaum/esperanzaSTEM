# Our Second Lab: Using the Digital I/O Pins to Make Two LEDs Blink

## Solution: Blinking Two LEDs

```python
# Author: J.E. Tannenbaum
# Initial Release: 01/13/2022
# Alternating blinking leds
from machine import Pin
from time import sleep

# Define the pin for each led
led1 = Pin(16, Pin.OUT)
led2 = Pin(17, Pin.OUT)


# make sure one is off and one is on
led1.low()
led2.high()


# Toggle on for 1 second, then off for one second forever
while True:
	led1.toggle()
	led2.toggle()
	sleep(1)
```

## Solution: Challenge - Blinking Four LEDs

```python
# Author: J.E. Tannenbaum
# Initial Release: 12/26/2022
# Alternating blinking leds
from machine import Pin
from time import sleep

# Define the pin for each led
led1 = Pin(16, Pin.OUT)
led2 = Pin(17, Pin.OUT)
led3 = Pin(18, Pin.OUT)
led4 = Pin(19, Pin.OUT)

# Create a list of LEDs
leds = [led1, led2, led3, led4]

# define a function to turn on one LED and turn the others off
def toggleLeds(led, leds):
    
    # Turn one LED on
    led.high()
    
    # Loop through all of the LEDs
    for offLed in leds:
        
        # Is this the LED that is on?  If not, turn the LED off.
        if led != offLed:
            offLed.low()

# Toggle a LED on for 1 second forever
while True:
    for led in leds:
        toggleLeds(led, leds)
    	sleep(1)
```
