# Our Third Lab: Reading a Button Press (Polling)

## Parts for this Lab are in Bag **2** and Bag **3**

1. Using the setup from the last lab, we'll use two LEDs and a resistor from Bag 2.  As a reminder:

    ```Insert the Anode (long) leads into j20 and j19```

    ```Insert the Cathode (short) leads into the Ground(-) rail```

    ```Insert the resistor leads into j3 and into the Ground(-) rail``` 

1. Take one button from Bag 3 and insert it into the bottom of the board.  The pins of the switch will straddle the channel and be inserted into ```e28, e30, f28, and f30```

1. Using one of the jumper wires in Bag 3, insert one end to ```j5``` and the other end into the ```Power(+) rail``` 

1. Take the second jumper wire, insert one end into the ```Power(+) rail``` and the other into ```j28```

1. Using the third jumper wire, insert one end into ```a30``` and the other end into ```a20```

1. When you are finished, your breadboard should look similar to the image below (Note: your LEDs and wires may be different colors)

![Lab 3](./img/lab3.jpg)

## How Would You Read the Button to Make the LEDs Blink in an Alternating Pattern?

The object of this lab is to have one of the external LEDs on while the other is off.  Then switch after each button press.  Continue until you stop the program.

- We can use the second program to continue to use two GP pins to control the external LEDs.  
- We need to modify the program to have the Pico read from a GP pin in this lab.  To do so, designate GP pin 15 to be an input, with the default state to be logical 0 (pulled down):
    - button = Pin(15, Pin.IN, Pin.PULL_DOWN)
- When the button is pressed, 3.3V (logical 1) will be applied to the input.
- The state of the button can be read at any time:
    - button.value()

## What Does a Button Press Look Like to the Pico?

![Button Press](./img/buttonPress.png)

Hints:

- You will still need the setup to control GP pins connected to the LEDs and a main loop as was done in Lab 2.

- You will need to define GP pin 15 as an input as shown above.  That should be done in the same section of code that defines the GP pins that control the LEDs.

- Check the button state inside the loop to determine if the button was pressed, using a conditional.

- Once the button is pressed, sleep for a moment to make sure you get a clean press and release.

- Save the program as lab3.py

- Don't forget to comment your code!
