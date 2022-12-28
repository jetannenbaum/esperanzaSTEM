# Our Ninth Lab: Using a Joystick to Draw Lines on an SSD1306 Digital Display

## Solution: Drawing Lines on the Display

```python
# Author: J.E. Tannenbaum
# Initial Release: 01/29/2022
# Drawing lines on a I2C SSD1306 display
from machine import Pin, I2C, ADC
from ssd1306 import SSD1306_I2C
import time

# Takes an input number value and a range between low-and-high and returns it scaled to the new range
def scaled(value, istart, istop, ostart, ostop):
  return int(ostart + (ostop - ostart) * ((int(value) - istart) / (istop - istart)))

# Instantiate the I2C & SSD1306 classes
i2c=I2C(0,sda=Pin(0), scl=Pin(1), freq=400000)
display = SSD1306_I2C(128, 64, i2c)

# Turn all pixels off
display.fill(0)
display.show()

# Provide info to user
display.text('Line Drawing', 0, 0, 1)
display.text('Hit the reset', 0, 20, 1)
display.text('button to clear', 0, 30, 1)
display.text('the screen', 0, 40, 1)
display.show()

# Define the pin for the reset button
resetButton = Pin(16, Pin.IN, Pin.PULL_UP)

# Wait unti the user hits the button to clear the screen and start drawing
while resetButton.value():
    time.sleep(.25)
    
# Turn all pixels off
display.fill(0)
display.show()

# Define the Horizontal and Vertical inputs from the Rheostats
vert = ADC(26)
horiz = ADC(27)

# Calculate where to start the line
x = newX = scaled(vert.read_u16(), 0, 65535, 0, 127)
y = newY = scaled(horiz.read_u16(), 0, 65535, 0, 63)

# Loop forever
# Draw the line, look for a reset to clear the screen, and get the new end points for the line
while True:
    display.line(x, y, newX, newY, 1)
    x = newX
    y = newY
    if resetButton.value() != 1:
        display.fill(0)
    display.show()
    time.sleep(.2)
    newX = 127 - scaled(vert.read_u16(), 0, 65535, 0, 127)
    newY = scaled(horiz.read_u16(), 0, 65535, 0, 63)
```
