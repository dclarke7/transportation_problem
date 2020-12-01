# transportation_problem
The repository contains a short script solving a transportation problem in Julia.
Upon searching for an implementation of the classic transportation problem in Julia, I found various deprecated minimum working examples, so I thought I ought to create my own.
The problem solved in the script can be written as follows 
```math
min_{x} c'x
```
subject to 
```
x_1 + x_2 + x_3 <= 25 
x_4 + x_5 + x_6 <= 35
x_1 + x_4 = 20
x_2 + x_5 = 30
x_3 + x_6 = 10
```
where `c` is the vector of cost of shipping across various routes and `x` is the vector of traded quantities.
The constraints can be represented in matrix form as `Ax <= b`.
A general formulation of the problem (where I first looked and found the deprecated MWE) can be found [here](https://rosettacode.org/wiki/Transportation_problem#Julia).
My goal is that this short minimum working example helps demonstrate how Julia's JuMP mathematical programming language works through demonstrating this classic transport LP problem.
