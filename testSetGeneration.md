## Two ways to generate test set

There should be two ways to generate test sets:

- Automatic and random
- User-specified

## Automatic and random test set generation

A facility for generating test sets with a known optimal solution is depicted in the next diagram.

![Automatic generation](https://github.com/tevye/Tetris-inspired-knapsack-problem-testing-facility/blob/master/testSetGenAutomatic.png)

Here are the process steps:

1. Pick the height and width of the container within some pre-defined range.
2. Fill the container with pieces in each available cell. Each piece will have a randomly assigned value.
3. Place a 5x5 grid overlapping the container such that the lower-righthand corner of the grid is at container position (0,0) as depicted above.
4. Randomly (or with some stipulation), "lift" a set of pieces within the grid out of the container. (If the grid overlaps two pieces in the same column, it must lift the top one to life the one underneath it. Any piece that ends up in the 2^24, upper-lefthand corner of the grid must be lifted).
