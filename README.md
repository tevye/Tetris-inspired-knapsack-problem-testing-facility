# Tetris-inspired-knapsack-problem-testing-facility
Design of a Tetris-inspired, gamified knapsack algorithm testing facility.

## Motivation
The knapsack problem (see [https://en.wikipedia.org/wiki/Knapsack_problem](https://en.wikipedia.org/wiki/Knapsack_problem)) is accessible. Its description relates to a common idea to which many people can relate. On the other hand, with the unbounded form proven to be NP-Complete; study of the problem (and algorithmic improvements in estimating or solving) different forms the problem offers a rich vein of intellectual challenge to explore.

I've been looking for something interesting to do with the $300 credit you get when you sign up for a [Google Cloud Platform free trial](https://console.cloud.google.com/freetrial/signup/tos). This may well be it.

## Design

![Basic system diagram](https://github.com/tevye/Tetris-inspired-knapsack-problem-testing-facility/blob/master/systemDiagram.png)

Since the primary intent of the system is to foster learning, it's distributed and requires developers ('contestants') to provide a hosted set of endpoints for their entry on their own server. (Shameless monetization idea...I might provide a virtual host in my GCP instance for a nominal rent). In the diagram, each developer's server is denoted on the left side as one of the Dev N Servers.

## The endpoints the developer will need to provide

The safe-source reference for the endpoint definition is given as the OpenAPI specification {TO BE ADDED AND LINKED} given in this project. Thus, this description is just the light conceptual overview.

GET /solvers

The 'solvers' endpoint will return a list of names of the different solvers that the developer has implemented

GET /solution/{solver_name}/set/{id}/height/{h}/width/{w}/{pieces}

The solution passes back one the names of the solvers as 'solver_name', an identifier 'id' of given problem set, the height 'h' of the Tetris container, the width 'w' of the Tetris container, and a JSON array of 'pieces'.

## A piece

A piece will fit in a 5 x 5 grid. An example is...

![An example Tetris piece](https://github.com/tevye/Tetris-inspired-knapsack-problem-testing-facility/blob/master/tetrisExamplePiece.png)

By designating each cell in the grid to correspond to a binary place value as...

![An example Tetris piece](https://github.com/tevye/Tetris-inspired-knapsack-problem-testing-facility/blob/master/tetrisBitMap.png)

The above piece in hexadecimal is...

1 0100 1110 0001 0000 1110 0100 --> **0x14E10E4**
