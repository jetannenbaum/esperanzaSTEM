# Getting the Robot Car to Move

## Connect the Computer to the Maker Pi RP2040

Use the USB cable to connect your laptop to the Maker Pi RP2040.  Once connected, move the switch to the the ON position.  You should see the green light turn on.

![Connected board](./img/boardConnected.jpg)

## Loading the MicroPython interpreter onto the Maker Pi RP2040 using Thonny

Now that your board is connected, you need to download the MicroPython interpreter using the Thonny application.  Start Thonny, then select Install MicroPython... from the bottom right corner of the main window.

![MicroPython Install](./img/thonnyMicroPythonInstall.jpg)

Select the Raspberry Pi Pico / Pico H from the variant pulldown and use the latest version.

![MicroPython Selection](./img/microPythonSelection.jpg)

Close the Install window after the the install is done.  Click on the red STOP icon at the top of the main window once the install window closes.  You should see the latest version of MicroPython in the bottom window.

## Using Digital I/O

Our board has digital input and output ports.  They are either on or off.  You can see that by typing the following in the main window, then clicking on the GREEN icon.  You will see one of the Digital IO Status leds turn on then off after 5 seconds:

```python
from machine import Pin
from time import sleep
led = Pin(0, Pin.OUT)
led.value(1)
sleep(5)
led.value(0)
```

## Using Pulse Width Modulation (PWM) to Control the Speed of the Motors

### PWM - How Does It Work?

- PWM is controlled by two factors:
    - How fast does the power turn on and off (frequency)
    - How long is the power on, relative to the power being off (duty cycle)

    ![PWM](./img/pwm.png)

- We can declare that an output pin is a PWM pin as follows:

    ```python
    from machine import Pin, PWM
    from time import sleep

    pwmPin = PWM(Pin(1))
    ```

- Now set the frequency and the duty cycle:

    ```python
    # Apply and remove power 1000 times/second (too fast to see)
    pwmPin.freq(1000)

    # Apply voltage 25% of the time for 5 seconds
    # Range is 0 - 65535
    pwmPin.duty_u16(65535 // 4)
    sleep(5)
    pwmPin.duty_u16(0)
    ```

### Controlling the Motors

Now that we know some basic MicroPython, let's use it to control the motors.  First, we need some code to allow the Maker Pi RP2040 board to control the motors:

```python
from machine import Pin, PWM
from time import sleep

def forward():
    right_reverse.duty_u16(0)
    left_reverse.duty_u16(0)
    right_forward.duty_u16(FULL_POWER_LEVEL)
    left_forward.duty_u16(FULL_POWER_LEVEL)

def stop():
    right_forward.duty_u16(0)
    right_reverse.duty_u16(0)
    left_forward.duty_u16(0)
    left_reverse.duty_u16(0)

# Motor definitions
FULL_POWER_LEVEL = 65024
right_forward = PWM(Pin(11))
right_forward.freq(1000)
right_reverse = PWM(Pin(10))
right_reverse.freq(1000)
left_forward = PWM(Pin(9))
left_forward.freq(1000)
left_reverse = PWM(Pin(8))
left_reverse.freq(1000)

forward()
sleep(2)
stop()
```

## What's Next?

We need to install batteries and download code to the Maker PI RP2040 board in order to have the robot move on it's own.  Use Thonny's SAVE icon to save the code to the board by selecting Rasperry Pi Pico and saving the file as main.py.

![File save](./img/saveToBoard.jpg)

!!! Challenge
    Can you have the robot autonomously drive halfway around your table, turn around 180 degrees, and return to it's starting spot?

    What additional methods would be helpful?

    Is it easier if the robot changes speeds?
