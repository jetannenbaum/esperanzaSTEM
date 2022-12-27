# Our Sixth Lab: Using a Photo Resistor 

## Parts for this Lab are in Bag **2** and Bag **6**

1. We need a single LED for this lab from bag 2.  As a reminder for the setup:

    ```Insert the Anode(+) lead into j20```

    ```Insert the Cathode(-) lead into the Ground(-) rail```

    ```Insert the resistor leads into j3 and into the Ground(-) rail``` 

1. We will also use one of the resistors and one of the photo resistors from Bag 6.

    - Insert the pins of the resistor into ```j6 and j10```
    - Insert the pins of the photo resistor into ```j8 and i10`` 

1. When you are finished, your breadboard should look similar to the image below (Note: your LED and wires may be different colors)

![Lab 6](./img/lab6.jpg)

## Building a Night Light With a Photo Resistor

- A photoresistor is a sensor that decreases resistance when light is shined on its surface. With no light a photoresistor has high resistance in the range of megaohms. As light shines on the surface the resistance drops to kiloohms. We can use this effect as a light sensor.

- To convert the variable resistance of a photoresistor to something we can measure with our microcontroller we will need to build a small circuit that includes a 10K ohm resistor. We then measure the voltage between the photoresistor and the 10K resistor as light falls on the sensor. The top and bottom of the circuit are tied to analog ground (AGND) and reference power(ADC_REF). This will move the voltage of the midpoint of the circuit.

- From our previous lab, we know that the Pico has the ability to convert an analog voltage (a voltage anywhere between 0 and ADC_REF volts) to a corresponding digital (0 to 65535) reading.  We can then use that reading to determine when to turn the LED on or off


!!! Challenge
    Use the readings from the analog to digital converter pin to determine when to turn the LED on and off.

    You may need a bright overhead light to see the change in resistance as you cover and uncover the photo resistor.

     - Don't forget to comment your code!
     
