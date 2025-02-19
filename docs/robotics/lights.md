# Adding Lights

The Maker Pi RP2040 board has two Neopixel LEDs.  We can use them to tell us what the robot is doing.

## Learn About Neopixel LEDs

- Controlling NeoPixel LEDs is challenging since the timing of data being sent must be very precise. Python alone is not fast enough to send bits out of a serial port. So a small function that uses assembly code is used. This code can be called directly from a neopixel driver library that is built into Micropython so that the users don't need to see this code.

- Neopixel colors are set as a triplet of red, green, and blue intensities (0-255).  For example:
    - Red (255, 0, 0)
    - Green (0, 255, 0)
    - Blue (0, 0, 255)
    - Yellow (255, 255, 0)
    - White (255, 255, 255)
    - Black (0, 0, 0)

### Using Neopixel LEDs

```python
from machine import Pin
from neopixel import NeoPixel
from time import sleep

# Define the GPIO pin connected to the RGB LEDs
LED_PIN = 18 

# Initialize the NeoPixel object
np = NeoPixel(Pin(LED_PIN), 2)  # '2' indicates a two LEDs

YELLOW = (255, 255, 0)
BLACK = (0, 0, 0)

colorList = (YELLOW, BLACK)

def setColor(color):
    # Set the color of the RGB LEDs
    for id in range(2):
        np[id] = color
    np.write()

while True:
    for color in colorList:
        setColor(color)
        sleep(1)
```

The code above adds a list object to make alternating the colors easier to manage.

!!! Challenge
    Rewrite the main.py code to use the Neopixel LEDs to signal the start of your car.  You should use a "count down" of colors: Blinking Red, then Blinking Yellow, then Blinking Green before the car starts to move.

    Once the car is in motion, use the Neopixel LEDs to signal when the car is in forward motion (Green), Turning (blinking left or right LED), Slowing (Yellow), or Stopping (Red)
