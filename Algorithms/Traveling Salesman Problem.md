# Traveling Salesman Problem
_A combinatorial optimization problem where you start and end at the same point and make the shortest path to touch each point once._
"Given a list of cities and the distances between each pair of cities, what is the shortest possible route that visits each city exactly once and returns to the origin city?"

![traveling Salesman](https://upload.wikimedia.org/wikipedia/commons/1/10/Travelling_salesman_problem_solved_with_simulated_annealing.gif)

## Nearest Neighbor Algorithm
_Jumping from one vertex to the next nearest vertex._
1. Pointer starts at a random node.
2. Pointer moves to the nearest unvisited node.
3. Repeat until all nodes are visited.
4. Return to the starting node to complete the tour.
``` ASCII 
       ┌───┐            
     ┌─┤ B │            
    10 └───┘     ┌───┐  
   ┌─┴─┐      ┌──┤ D │  
   │>A<├───100┘  └───┘  
   └─┬─┘    ┌───┐       
     └──50──┤ C │       
            └───┘       

 
       ┌───┐            
     ┌─┤>B<├───85──┐    
     │ └─┬─┘     ┌─┴─┐  
   ┌─┴─┐ │       │ D │  
   │ X │70       └───┘  
   └───┘ │  ┌───┐       
         └──┤ C │       
            └───┘       
```
## Two Point Swap
_Reverse the sequence of nodes between edges._
An operation where two edges in a Path have their endpoints swapped, this effectively creates two new edges while preserving the degree of each vertex.
``` ASCII 
┌───┐ ┌───┐    ┌───┐   ┌───┐    ┌───┐ ┌───┐ 
│ a │ │ c │    │ a ├─┐ │ c │    │ a ├─┤ c │ 
└─┬─┘ └─┬─┘    └───┘ │ └─┬─┘    └───┘ └───┘ 
  │     │        ┌─] │ [─┘                  
┌─┴─┐ ┌─┴─┐    ┌─┴─┐ │ ┌───┐    ┌───┐ ┌───┐ 
│ b │ │ d │    │ b │ └─┤ d │    │ b ├─┤ d │ 
└───┘ └───┘    └───┘   └───┘    └───┘ └───┘ 
(a,b) (c,d)     (a,d) (c,b)     (a,c) (b,d) 
                   ▲     ▲         ▲   ▲    
                   └─────┘         └───┘    
                     swap           swap    
```
