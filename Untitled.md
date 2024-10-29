# Chosen Approach:
The core of the Bellman ford approach is the updating of node values in phases. To store the best path to the node I used the last edge that was the least costly to get to the node in a dictionary. I chose a dictionary because each node must have a unique name, and that name was hash-able. I could have gone for another approach where I store the path as I generate the best values of the nodes, however I preferred this one because it broke the task into multiple steps. In my approach I create a deep copy of the provided graph, this is more costly in terms of space complexity. However in my approach I will be modifying the graph. After finding a path from the start to remote, I will take every edge that exists in that path and remove it from the graph. This new graph will now be run through the de-stressing process creating a new best path, but remote is marked as the start this time. I could mark the edges and simply skip them, but I think it is easier to understand when the edges are completely removed. When de-stressing edges I opted to destress in both directions because the graph is undirected.
# Composing Code:
## Loops
There are a lot of loops in this algorithm, the core functionality is 3 nested loops. These can quickly become difficult to read so I made sure that when there was a nested loop each variable will be named descriptively. However when there are simple loops accomplishing one task on each element I only name the variable `each` because often the list of elements I am accessing is self explanatory. 
## Infinity
I did some research and float("Inf") is something that exists in python, which I think is more descriptive than just a really high number or an arbitrary variable.
## Predecessors
This is the dictionary used to trace back the best path to the start. The reason I didn't name this previous_nodes or something similar is because 'Predecessors' speaks to a current Node being somehow connected to a past Node, which is the case.
## Vertex
I decided to stick to the vertex naming instead of node unless a variable is already named vertex in which case I would call it a node instead of saying "another_vertex" or something. When I named variables in couples I made sure not to name them one and two unless there was a sequential nature to them. Because the graph is undirected each edge is not a start and end, but when removing the edges I called them one and two because one is removed before the other in a sequence.
# Modularity Decisions:
``` python
is_valid_input()
bellman_ford()
	destress_graph()
		relax_edge()
	remove_all_edges()
	remove_undirected_edge()
	find_optimal_path()
```
I separated the logic for each piece of the Bellman-Ford algorithm into hierarchical subroutines. I wanted to keep the bellman_ford() logic in one routine however, The entire bellman_ford() routine will 1.destress the graph, 2. Return optimal paths to a from remote. Which means it was doing two different tasks that needed to be separated into their own subroutines. One of those subroutines is destress_graph() which will destress edges in both directions due to the graph being undirected. Which meant I needed to create a subroutine to call twice, which is why I made relax_edge() to remove repetition. Then the second important subroutine is find_optimal_path() which is self descriptive. 
# Implementing Bellman-Ford:
I think of implementing the Bellman-Ford algorithm as being lost in the woods without a map. However, you have a sign called 'remote' pointing to another sign, which points to another sign ect. By following these signs enough times, you will eventually find your way home or back to the 'start' sign.
To make sure the signs point correctly towards the next best direction, we calculate the cost between each pair of connected signs and update the cost if we have a new sign that makes a shorter path. The starting point always has a cost of 0, and as we move from sign to sign we will calculate the costs and "destress" the edges in-between the signs by finding shorter connections.

