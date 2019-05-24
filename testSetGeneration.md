## Two ways to generate test set

There should be two ways to generate test sets:

- Automatic and random
- [User-specified](./userDefinedTestSets.md)

## Automatic and random test set generation

A facility for generating test sets with a known optimal solution is depicted in the next diagram.

![Automatic generation](https://github.com/tevye/Tetris-inspired-knapsack-problem-testing-facility/blob/master/testSetGenAutomatic.png)

Here are the process steps:

1. Pick the height and width of the container within some pre-defined range.
2. Fill the container with *segments* in each available cell. Each segment will have a randomly assigned value. (Mark the optimal solution as being the sum of the values of the segments).
3. Place a 5x5 grid overlapping the container such that the lower-righthand corner of the grid is at container position (0,0) as depicted above.
4. Randomly (or with some stipulation), "lift" a set of segments within the grid out of the container. (If the grid overlaps two segments in the same column, it must lift the top one to life the one underneath it. Any segment that ends up in the 2^24, upper-lefthand corner of the grid must be lifted). The segments included in a lift are a piece.
5. Move the grid to the right one postion at a time and repeating step 4 until the grid center is over column w + 1.
6. Once the grid center is over column w + 1 and has repeated step 4, then move the grid down one row and back so its center is over column w - 2. Do this as long as the center of the grid is above and to the left of w+1, h+1 and go back to step 4.
7. Randomly add pieces to the test set where the value of the new pieces are guaranteed to be less that the minimum of any pieces they may displace.
8. Randomly apply 0-3 rotations of pieces before including them in the test set.

[Next - user-defined test sets](./userDefinedTestSets.md)
