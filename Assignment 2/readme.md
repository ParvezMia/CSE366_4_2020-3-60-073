# Assignment 2 Report

## Introduction
The task of this assignment was to implement ***Genetic Algorithm*** to optimize the assignment of multiple robots.
### Primary Objectives
1. Minimizing the Total Producion Time.
2. Ensuring balanced workload across robots.
3. Prioritize critical tasks effectively.

## Problem Statement
Different sets of tasks with their priority and durations need to be assigned to a group of robots with different efficiency factors. The obstacle lies in effectively assigning tasks to robots in order to save production time while maintaining task prioritization and workload balance.

## Approach
***1. Representation:*** Each possible solutions was represented as vectors, where each element indicated the robot assigned to each task. Individual I is represented as a vector of N integers, where N is the number of tasks, and
each integer In (where 1≤n≤N) corresponds to the ID of the robot assigned to task n.
I=[r1,r2,...,rN]

***2. Fitness Function:***
Here two methods were needed to calculate the fitness function.
- ***Total Production Time (Ttotal)***: The total production time is determined by the robot that finishes last, taking into account the
efficiency of each robot. For each robot r, the time Tr spent on its assigned tasks is the sum of
the durations of these tasks divided by the robot's efficiency. The total production time is the
maximum time any robot takes to complete its tasks.
>Tr = ∑n∈tasks(r) (Dn*Pn/Er) <br>
>Ttotal = max(T1, T2, .., Tr)

where,
>tasks(r) is the set of tasks assigned to robot r. <br>
>Dn is the duration of task n.<br>
>Pn is the priority weight of task n.<br>
>Er is the efficiency of robor r. <br>
>R is the total number of robots.


- ***Workload Balance:*** The workload balance penalizes uneven distribution of work among robots. It can be quantified
using the standard deviation of the total times across all robots.
>B=σ(T1,T2,...,TR)

where σ is the standard deviation. <br>
- ***Fitness Function*** <br>
>F(I) = Ttotal + B

***3.Selection, Crossover, Mutation***:
- ***Selection:*** Tournament selection
- ***Crossover:*** Single-point crossover
- ***Mutation:*** Swapping tasks

## Implementation
- ***Mock Data Generation:*** Generates random mock data of tasks including duration, priorities and robot efficiencies
- ***Genetic Algorithm Implementation:*** All the necessary functions were added here in this class ***(OptimizeRobotResource_GA)*** including population generation, fitness function calculation, crossover, mutation, and running simulation
- ***Visualization:*** For visualizing the best solution with tasks duration and priorities annotations for each cell in a grid representation robots and tasks.

## Results
***Generation cycle was set to 100*** and each time the simulation was tested within this range where the GA successfully optimized tasks, minimizing total production time while ensuring workload balance and task prioritization. Each time the best solution was found in the **XXth** generation.

## Conclusion
It can be observed and concluded that the GA proved to be effective in optimizing robot tasks. It efficiently handled allocating tasks to robots, minimized production time, balanced workload and prioritized critical tasks.
