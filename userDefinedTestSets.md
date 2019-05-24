## User-defined test sets

A user-defined test set consists of the following:

- The height and width of the container
- A set of test pieces (values and grid pattern)
- a drop pattern that places a subset of the given pieces in the container
- The optimal solution value

![User-defined test set](https://github.com/tevye/Tetris-inspired-knapsack-problem-testing-facility/blob/master/userDefinedxcf.png)

The above image shows a trivial test set with a 5 x 5 container and an optimal value of [42](https://www.youtube.com/watch?v=aboZctrHfK8). It's a useful training set because the optimal solution is only achieved by foregoing selection of the highest-value piece and applying some rotations of the pieces.

{TO BE ADDED - EXAMPLE OF THE USER TEST SET DEFINITION PER OpenAPI}

## Errors

If the single, red piece at the bottom-right of the figure above were 3 and some other piece above it were decreased in value by 2; then the solution would include the black plus-sign shaped piece on the left and the optimal solution would be 43. All that to say that there is a chance that a particular user-defined test set may contain errors.

Several straight-forward validations are:

- Drops mustn't have segments of a piece drop outside the container
- The sum of the value of the dropped pieces must equal the given optimal solution value
- Segment out the unused pieces. Check for any voids in the container after all the drops are made. If a revised drop order would get one or more of the unused pieces to fill one or more voids, then the set is in error. (Assumes all pieces have a positive value greater than zero).
- If the container has no voids, the drop sum equals the given optimal value, and the unused pieces are all of lower value density than any combination of the used pieces; then set is proven correct.
- If testing a contestant developer's solution (itself without error) finds a value larger than the one given, the test set is in error.

{TO DO - Should be able to find a brute force way to prove any reasonably sized test set. Have to consider how to cover the computational expense if implemented.}

## Life-cycle ramification

The last validation points to the iterative learning that can occur in the interactions between test makers and takers. In turn, that offers two more ways to gamify the system. One, reward test takers for finding test set mistakes. Two, reward test makers for submitting test sets that are proven correct.

