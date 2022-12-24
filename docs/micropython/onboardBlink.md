# Our First Lab: Making the Onboard LED Blink

## Connect the Board to Your Computer

1. Plug the small end of the USB cable to your Pico
1. Plug the other end into the USB port on your Computer
1. Open Thonny on your Computer
1. You should see the following in the Shell (Thonny's bottom window)

    ```MicroPython v1.19.1 on 2022-06-18; Raspberry Pi Pico with RP2040```

    ```Type "help()" for more information.```

    ```>>>```

Note: Your version of the MicroPython interpreter may be different

## Typing Commands in the Shell

The Shell window allows us to quickly test MicroPython commands.  Typing in the Shell window is known as typing in the REPL.  REPL stands for **Read Evaluate Print Loop**, and is the name given to the interactive MicroPython prompt that is accessible on the Pycom devices. 

Let's try a simple command to make sure everything is working.  Type the following at the prompt:

print('Hello')

The interpreter should respond with ```Hello```

## Blinking the Onboard LED

Type the following in the Thonny's top window:

```python
# Load the libraries
from machine import Pin 
from time import sleep

# Define the GPIO pin that controls the LED
led1 = Pin(25, Pin.OUT)

# Turn off the LED
led1.low()

# Loop forever, while turning the LED On and Off
while True:
    led1.toggle()
    sleep(1)
```

Once you typed in the code, be sure to save the code on your computer as lab1.py.  Then run the code by pressing the Green button.  You should see the onboard LED turn on for one second, then off for one second.

![Blinking LED](./img/blink-on-board-led.gif)

This program has two main parts.  The first part is often called the preamble or the setup code. This code gets executed only once when the program is run. In this example, the setup loads the right libraries and initializes global variables.

The second part is the main event loop.  This program continues to run until the device is powered down or the program is reset.

The ```from machine import Pin``` statement is required to define the characteristics of our physical machine.  In this case, we are loading the Pin python library.

 The ```from time import sleep``` library is required for the python sleep function.  Note that some programs use ```utime``` for MicroPython time.  These both work the same.  They are really just synonyms or alias of each other.  Although the use of ```utime``` is technically a little bit more precise - the reader knows that the code is using the actual MicroPython time library, the use of the ```time``` alias makes our code on character smaller and can make our code more portable to other systems.

Note that the text after the hash or pound characters are comments.  Comments are ignored by the Python interpreter but it is a good practice to put in comments in your code to help others understand your program.

## Changing the Blink Speed

Next, lets create a Python global variable for the delay that the LED is on and off.

```python
# Load the libraries
from machine import Pin 
from time import sleep

# Define the blink delay rate
delay = .25

# Define the GPIO pin that controls the LED
led1 = Pin(25, Pin.OUT)

# Turn off the LED
led1.low()

# Loop forever, while turning the LED On and Off
while True:
    led1.toggle()
    sleep(delay)
```

This program will blink the built-in LED on and off every 1/4 of a second.  By changing the delay variable you can make the LED blink faster and slower.

!!! Challenge
    What is the fastest you can make the LED blink and still see it changing?  What does this tell you about the human eye?
