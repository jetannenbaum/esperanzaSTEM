# Our Tenth Lab: Using a Buzzer with PWM

## Solution: Using a Buzzer to Make a Sound

```python
# Author: J.E. Tannenbaum
# Initial Release: 02/03/2022
# Creating a tone
from machine import Pin, PWM
from utime import sleep

# lower right corner with USB connector on top
SPEAKER_PIN = 16

# create a Pulse Width Modulation Object on this pin
speaker = PWM(Pin(SPEAKER_PIN))

# set the duty cycle to be 50%
speaker.duty_u16(1000)

# Set the frequency
speaker.freq(1000)

sleep(5) # wait 5 seconds

# turn off the PWM circuit off with a zero duty cycle
speaker.duty_u16(0)
```
