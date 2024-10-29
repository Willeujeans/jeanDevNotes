# Search Algorithms
_Programs designed to find specific elements._
# Depth First Search
_A way of searching that prioritizes searching down the entire length of each path._
``` ASCII
              ┌───┐                   
     ┌────────┤ 1 ├─────────┐         
     │        └─┬─┘         │         
     │          │           │         
   ┌─┴─┐      ┌─┴─┐       ┌─┴─┐       
   │ 2 │     ┌┤ 5 ├┐      │ 9 │       
   └─┬─┘     │└───┘│      └───┘       
     │       │     │                  
   ┌─┴─┐   ┌─┴─┐ ┌─┴─┐                
   │ 3 │   │ 6 │ │ 8 │                
   └─┬─┘   └─┬─┘ └───┘                
     │       │                        
   ┌─┴─┐   ┌─┴─┐                      
   │ 4 │   │ 7 │                      
   └───┘   └───┘  
```

``` ASCII
Stack after each pop
|1| > |2| > |3| > |4| > |5| > |6| > |7| > |8| > |9| > DONE!
      |5|   |5|   |5|   |9|   |8|   |8|   |9|
      |9|   |9|   |9|         |9|   |9|

```
This approach will use a Stack, adding nodes will store them and popping them will remove them and store their children.