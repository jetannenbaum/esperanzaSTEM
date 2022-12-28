# Our Eigth Lab: Using an SSD1306 Digital Display

## Solution: Moving Your Name Around the Display

```python
# Author: J.E. Tannenbaum
# Initial Release: 01/29/2022
# Writing text to a I2C SSD1306 display
from machine import Pin, I2C
from ssd1306 import SSD1306_I2C
import time

# Instantiate the I2C & SSD1306 classes
i2c=I2C(0,sda=Pin(0), scl=Pin(1), freq=400000)
display = SSD1306_I2C(128, 64, i2c)
 
# Setup the initial position & direction
xPos = 0
yPos = 0
xDir = 1
yDir = 1

# Guess at the edge cases
xEdge = 57
yEdge = 56

# Loop forever
while True:
    
   # Clear the old framebuffer, write the new text, then push it to the display
   display.fill(0)
   display.text("Hello Jet", xPos, yPos)
   display.show()
   
   # Update the x position, then check for edge cases
   xPos += xDir
   if xPos < 0:
       xPos = 0
       xDir = 1
   elif xPos > xEdge:
       xPos = xEdge
       xDir = -1
        
   # Update the y position, then check for edge cases
   yPos += yDir
   if yPos < 0:
       yPos = 0
       yDir = 1
   elif yPos > yEdge:
       yPos = yEdge
       yDir = -1
       
   # delay
   time.sleep(.25)
```
