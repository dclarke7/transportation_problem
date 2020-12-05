# Transportation Problem
This repository contains a short script solving a transportation problem in Julia using JuMP.
Upon searching for an implementation of a transportation problem in Julia, I found a [deprecated minimum working example](https://rosettacode.org/wiki/Transportation_problem#Julia) on [Rosetta Code](https://rosettacode.org/wiki/Rosetta_Code),
so I thought I ought to re-write it.
The optimization problem solved in the script `JuMP_solve.jl` can be written as follows
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
where `c` is the vector of cost of shipping each of the elements in `x` the vector of traded quantities from suppliers to customers.
The constraints are represented in matrix form as `Ax <= b`.
The solution for the vector of traded quantities is
```
x* = [20 0 5
      0 30 5]
```
More details on the formulation of this exact problem (where I first looked and found the deprecated MWE) can be found [here](https://rosettacode.org/wiki/Transportation_problem) on Rosetta Code.
The problem is to find the minimum cost quantities shipped from two suppliers to three customers subject to capacity and demand constraints.
This is sometimes called a [minimal-cost network-flow problem](https://en.wikipedia.org/wiki/Minimum-cost_flow_problem).
My goal is that this short minimum working example helps demonstrate how Julia's [JuMP](https://jump.dev/JuMP.jl/stable/) mathematical programming language works through an MWE of this classic transport LP problem.

I've since edited the [Julia section of the Transportation Problem page on Rosetta Code](https://rosettacode.org/wiki/Transportation_problem#Julia) with this example.
I also took the liberty of adding [an MWE in R to Rosetta Code](https://rosettacode.org/wiki/Transportation_problem#R) and this repository, which I adopted from [someone else's code](https://gist.github.com/rsalaza4/ef68b1dee9b7334bd4913985850d8566).
The code uses `lpSolve::lp.transport`.
