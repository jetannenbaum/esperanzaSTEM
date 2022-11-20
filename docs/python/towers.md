
## A recursive problem

The Towers of Hanoi is a classic problem to solve with recursion.  There are three towers.  The first tower has a set of rings, starting at the bottom with the largest ring, and moving up to a smaller ring at ech new level, until we get to the top.  The object is to move the rings from the left most tower, where the rings start, to the right most stack, always making sure that a smaller ring is above a larger ring.

## Example

Here is an example, using a tower with three rings:

![Three Rings](./img/hanoi.png)
Image from: https://www.geeksforgeeks.org/c-program-for-tower-of-hanoi/

## The Steps

1. Disk 1 moved from A to C 
1. Disk 2 moved from A to B 
1. Disk 1 moved from C to B 
1. Disk 3 moved from A to C 
1. Disk 1 moved from B to A 
1. Disk 2 moved from B to C 
1. Disk 1 moved from A to C 

!!! Challenge
Can you write a recursive program to solve the towers of hanoi?

A solution: [https://trinket.io/python/d425c2e31e]https://trinket.io/python/d425c2e31e