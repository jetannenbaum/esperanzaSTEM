# Our Seventh Lab: NeoPixel Display

## Solution: Using a NeoPixel Display to Turn One Pixel at a Time

```python
# Author: J.E. Tannenbaum
# Initial Release: 03/08/2022
# Playing with a neopixel bar

import time
from neopixel import NeoPixel
from machine import Pin

# Number of pixels in the NeoPixel Strip
NUMBER_PIXELS = 8

# Driver pin
LED_PIN = 0

# Set the delay
DELAY = .1

#Define the pin as output
pin = Pin(LED_PIN, Pin.OUT)

# Define the NeoPixel Strip
strip = NeoPixel(pin, NUMBER_PIXELS)

# set the colors from https://www.rapidtables.com/web/color/RGB_Color.html
white = (255, 255, 255)
red = (255, 0, 0)
orange = (255, 165, 0)
yellow = (255, 255, 0)
green = (0, 255, 0)
blue = (0, 0, 255)
indigo = (75, 0, 130)
violet = (148, 0,211)
black = (0, 0, 0)
grey = (64, 64, 64)
colors = (black, grey, white, red, orange, yellow, green, blue, indigo, violet, black, black)

while True:
    for color in colors:
        for i in range(NUMBER_PIXELS):
            strip[i] = color
            strip.write()
            time.sleep(DELAY)
```

## Solution: Using a NeoPixel Display to Turn All the Pixels at Once

```python
# Author: J.E. Tannenbaum
# Initial Release: 03/11/2022
# Playing with a neopixel bar

import time
from neopixel import NeoPixel
from machine import Pin

NUMBER_PIXELS = 8
LED_PIN = 0

#Define the pin as output
pin = Pin(LED_PIN, Pin.OUT)

# Define the NeoPixel Strip
strip = NeoPixel(pin, NUMBER_PIXELS)

delay = 1

# set the colors from https://www.rapidtables.com/web/color/RGB_Color.html
white = (255, 255, 255)
red = (255, 0, 0)
orange = (255, 165, 0)
yellow = (255, 255, 0)
green = (0, 255, 0)
blue = (0, 0, 255)
indigo = (75, 0, 130)
violet = (148, 0,211)
black = (0, 0, 0)
colors = (white, red, orange, yellow, green, blue, indigo, violet, black)

while True:
    for color in colors:
        strip.fill(color)
        strip.write()
        time.sleep(delay)
```