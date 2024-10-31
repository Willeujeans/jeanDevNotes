# Graph Theory
_Models using vertices and edges to represent relationships between objects._
Graph theory is useful to model relationships found in the real world that can be easily understood by humans and easily transferred to computer language.
Proper Definition:
A Graph $G=(V,E)$ is a set of Vertices ($V$) and edges ($E$) where each Edge $(u,v)$ is a connection between Vertices. $u,v \epsilon V$
``` ASCII
                      
 ┌────┐        ┌────┐ 
 │Node├──Edge──┤Node│ 
 └────┘        └────┘ 
                      
```
- **Neighbors**: Vertices that are connected by an edge, nodes can have many Neighbors.
- **Degree**: Number of edges connected to the Vertex.
- **Connected Component**: A subset of Vertices within a Graph that are connected.
- **Connectivity**: Graphs are connected when all Vertices are connected, Vertices are connected if an edge exists between them. A Vertex is _incident_ to another Vertex if its connected to another Vertex.
- **Path**: The order in which Vertices are visited. Node1 -> Node2 -> Node3
- **Cycle**: A path that starts and ends at the same Vertex.
- **Hamiltonian circuit**: A closed loop that starts and ends at the same node touching each node once.

---
# Graphs
## Undirected Graph
_Edges between Vertices have no directionality._
``` ASCII 
      ┌───┐       
      │ D │       
      └─┬─┘       
        │         
        │         
┌───┐ ┌─┴─┐  ┌───┐
│ A ├─┤ B ├──┤ C │
└───┘ └───┘  └───┘     
```

## Directed Graph
_A Graph where all Edges are a singular direction, represented by an arrow._
``` ASCII
 ┌───┐        ┌───┐ 
 │ A ├──Edge─►│ B │ 
 └───┘        └───┘ 
 
NodeA Neighbors: {NodeB}
NodeB Neighbors: {Empty}
```
- **Directed Cyclic Graph**: A Directed Graph that contains at least one Cycle.
- **Directed Acyclic Graph**: A Directed Graph that does not contain any Cycles.

## Weighted Graph
_A Graph where Edges hold values, which influences Path distances._
```ASCII
       ┌───┐        
       │ D │        
       └─┬─┘        
         3          
         │          
 ┌───┐ ┌─┴─┐  ┌───┐ 
 │ A ├1┤ B ├─2┤ C │ 
 └───┘ └───┘  └───┘ 
                    
```

## Trees
1. Connected and Acyclic
2. Removing an Edge disconnects the entire Graph
3. Adding an Edge creates a Cycle
**Forest**: Collection of trees in the same graph that are disconnected.
``` ASCII
         ┌───┐              
     ┌───┤ 0 ├───┐          
     │   └───┘   │          
     │           │          
   ┌─┴─┐       ┌─┴─┐        
  ┌┤ 1 ├┐     ┌┤ 2 ├┐       
  │└───┘│     │└───┘│       
  │     │     │     │       
┌─┴─┐ ┌─┴─┐ ┌─┴─┐ ┌─┴─┐     
│ 3 │ │ 4 │ │ 5 │ │ 6 │     
└───┘ └───┘ └───┘ └───┘     
```

---
# Representations of Graphs
## Adjacency Matrix
_A table where the axis are Vertices and the cells are either 0 or 1 based on Edges._

|     | *0* | *1* | *2* | *3* | *4* |
| --- | --- | --- | --- | --- | --- |
| *0* | 0   | 1   | 1   | 1   | 0   |
| *1* | 1   | 0   | 0   | 1   | 0   |
| *2* | 1   | 0   | 0   | 1   | 0   |
| *3* | 1   | 1   | 1   | 0   | 1   |
| *4* | 0   | 0   | 0   | 1   | 0   |
Using the table we can see in the Row for `Node0` the cell that intersects with `Node1` is `1` which means `Node0` has an Edge with `Node1`.
```ASCII
        ┌───┐                   
  ┌─────┤ 1 ├─────┐             
  │     └───┘     │             
┌─┴─┐           ┌─┴─┐     ┌───┐ 
│ 0 ├───────────┤ 3 ├─────┤ 4 │ 
└─┬─┘           └─┬─┘     └───┘ 
  │     ┌───┐     │             
  └─────┤ 2 ├─────┘             
        └───┘                   
```

## Edge Set
_A set of Edges written as tuples of Vertices._
```ASCII
{(0,1),(0,2),(0,3),(1,3),(2,3),(3,4)}
        ┌───┐                   
  ┌─────┤ 1 ├─────┐             
  │     └───┘     │             
┌─┴─┐           ┌─┴─┐     ┌───┐ 
│ 0 ├───────────┤ 3 ├─────┤ 4 │ 
└─┬─┘           └─┬─┘     └───┘ 
  │     ┌───┐     │             
  └─────┤ 2 ├─────┘             
        └───┘                   
```

## Adjacency List
_A list where each node has a map of its neighbors._
``` ASCII
0[1,2,3]
1[0,3]
2[0,3]
3[0,1,2,4]
4[3]
        ┌───┐                   
  ┌─────┤ 1 ├─────┐             
  │     └───┘     │             
┌─┴─┐           ┌─┴─┐     ┌───┐ 
│ 0 ├───────────┤ 3 ├─────┤ 4 │ 
└─┬─┘           └─┬─┘     └───┘ 
  │     ┌───┐     │             
  └─────┤ 2 ├─────┘             
        └───┘                   
```