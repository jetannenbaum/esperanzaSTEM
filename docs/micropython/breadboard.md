# Breadboards

![Solderless Mini Breadboard](./img/solderless-mini-breadboard.jpg)

We use standard solderless mini breadboards in our labs.  The breadboards have holes that are spaced 1/10th of an inch apart which is a standard for most electronics in the US.

Our breadboards are usually 1/2 size with 400-ties.  They have a central trough and power rails on the left and right edges.

## Breadboard Regions and Connections

Learning how a breadboard works is critical for building your projects.  In the figure above you will see that there are two types of regions of the breadboard

1. The side regions are called the power distribution rails.  They are similar to power lines that reach across our projects.
2. The central region is call the row connector region.  In this area the horizontal rows are all connected inside the breadboard.  Within any row, columns ```a, b, c, d and e``` are all electrically connected.  Within any row, columns ```f, h, i, j, and k``` are also electrically connected.  However, there is a gap between columns e and f called the center gap or component slot that parts are usually placed over.  Components like buttons and chips usually have their pins straddle the component slot.

## Pico Placement on Breadboard

For most of our labs we place the Pico board (found in **Bag 1**) so that pin 1 of the Pico is in row 1 of the breadboard as in the image below.

![Pico on Breadboard](./img/pico-on-breadboard.png)

This means that the GND connections to the Pico are always in rows 3, 8, 13 and 18 on both sides of the breadboard.  One of the ground pins is usually hooked up to the vertical blue power rails on the sides of the breadboard.

## Pico Placement Annotations

![Pico on Breadboard](./img/picoBreadBoard.jpg)

1. **GND** are the ground connections.  There are 4 on each side of the board
2. **3.3V** is the 3.3 volt power, regulated down from the 5 volts from the USB connection.

