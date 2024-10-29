# Bellman-Ford Algorithm
_starts at a node distance is initially unknown and assumed to be infinite until calculated._
Given a graph, using this algorithm we will slowly get the shortest distance between nodes.
0: Distance using no edges (this will just be the start node)
1: Distance using 1 edge
2: Distance using 2 edges
ect...

```ASCII
              ┌───┐                 
  ┌─(8)───────┤ S ├──────(10)──┐    
  │           └───┘            │      
  │                            ▼    
┌─┴─┐        ┌(-4)──────────►┌───┐  
│ E │        │               │ A │  
└─┬─┘        │  ┌───────────►└───┘  
  │          │  │              ▲    
  │          │  │              │    
 (1)         │  │              │    
  │          │ (2)            (1)    
  ▼          │  │              │    
┌───┐        │  │            ┌─┴─┐  
│ D ├────────┘  │            │ B │  
└─┬─┘           │            └───┘  
  │             │              ▲    
  │           ┌─┴─┐            │    
  └──(-1)────►│ C ├─────(-2)───┘    
              └───┘                 

```

``` ASCII
Distances using 1 Edge
CYCLE0:
S  A  B  C  D  E
0  ∞  ∞  ∞  ∞  ∞

CYCLE1:
	S-(10)->A
	S--(8)->E
	
	S  A  B  C  D  E
	0 10  ∞  ∞  ∞  8

CYCLE2:
	A-(2)->C
	
	S  A  B  C  D  E
	0 10  ∞ 12  ∞  8
	
	S-(2+10)->C

CYCLE3:
	C-(-2)->B
	
	S  A  B  C  D  E
	0 10 10 12  ∞  8
	
	S-(12-2)->B

CYCLE4:
	E-(1)->D
	
	S  A  B  C  D  E
	0 10 10 12  9  8
	
	S-(9)->D
```

We now have an updated distances table, but now we need to be able to trace a path using the lowest costing route.
We will store the Node and the best last connection to it
This way we can start at the end, then move to its last connection. This connection will also have its best last connection stored so then we walk along that connection. Because every node has stored its best last connection to the start, every time we leave one node to another that node will point to the next best option. This will happen every time we walk to a node leading to the optimal path!

Its like walking to a sign that is pointing to another sign, we don't have a map of the entire trail but if each sign is pointing to the next best place and we will eventually complete the trail!