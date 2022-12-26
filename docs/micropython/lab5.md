# Our Fifth Lab: Analog to Digital Converter

## Solution: Using a potentiometer to control PWM

```python
# Author: J.E. Tannenbaum
# Initial Release: 01/17/2022
# Using Pulse Width Modulation to control LED
# Read from the Potentiometer for the Duty Cycle
from machine import Pin, PWM, ADC
from time import sleep

# Define the pwm for the led
led = PWM(Pin(16))

# Connect to GP26, which is channel 0
potentiometer = ADC(Pin(26))

# define the pwm frequency
led.freq(1000)

# Read the potentiometer, set the duty cycle
oldDutyCycle = 0
dutyCycle = potentiometer.read_u16()
while True:
    if oldDutyCycle != dutyCycle:
        led.duty_u16(dutyCycle)
        oldDutyCycle = dutyCycle
    dutyCycle = potentiometer.read_u16()
    sleep(0.05)

```