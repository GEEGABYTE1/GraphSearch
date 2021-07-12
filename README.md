# Graph Search 📊🔍

Elementary version of Graph Search Algorithm 

For my version of the algorithm, there are two functions:

The first function called, `.single_direct()`, is a helper function that returns a dictionary of vertices as keys and their edges as their values. The returned dictionary helps us find if our goal node is part of some edge.

The second function is the algorithm itself called `.path_visualizer()`, which is a recursive algorithm that takes a graph and a goal value, and four other base values; path (empty list), counter (set to 0), and root_element (None). Note that all the keyword arguments are for reference for the algorithm.

There are four cases that makes this recursive algorithm work:

  1) If the graph only has one node, the algorithm will return the node itself
  2) If the graph is empty, the algorithm will return `None`
  3) If the current node has the goal node within it's edge, the algorithm will add the current node and will return the path at the end along with the goal node.
  4) If the current node does not have the node within, the algorithm will add the node to the traversal path. The root element stays the same and the algorithm will recurse making the first edge the current node. To check if there is a cycle involving the goal element, the algorithm will take all the edges and will see if the goal node appears in the list of edges at least one. If it is, we keep the root element the same for reference when we recurse, otherwise, we will recurse with the root element being the next node in the original dictionary. Do remember that the root element is needed as we use it to reference if it is apart of a cycle where the goal node lies in.
  5)  Another condition the algorithm checks under this case is if the goal node is within the path. This condition is our successive case, and which, will return the path of the cycle. If none of this sub-cases meet, the algorithm will recurse like the previous case, making the root element the next node. We do this because if none of the cases above are met, that only means that the current node (which in this case, would be the root element) was never part of a cycle in the first place where the goal node lies in.

  Additionally, if any of these cases are not met, we can conclude that the goal node was not found as there will be a `RecursionError` present.
  
 Time Complexity: `O(N^2)`
 
 # More Info
 The rest of the functions that are not stated in this file are helper functions to setup the Graph data structure itself.
 
 Made in Python 🐍
