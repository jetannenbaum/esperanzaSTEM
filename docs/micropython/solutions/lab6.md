# Our Sixth Lab: Photo-Resistor

## Solution: Using a Photo-Resistor to Turn On and Off an LED

```python
# Author: J.E. Tannenbaum
# Initial Release: 01/22/2022
# Night Light LED

from machine import Pin, ADC
from time import sleep

# Define the pin for the A/D Converter
photo = machine.ADC(26)

# Define the pin for the led
led = Pin(16, Pin.OUT)

while True:
    if photo.read_u16() > 30000:
        led.on()
    else:
        led.off()
    sleep(.5)
```