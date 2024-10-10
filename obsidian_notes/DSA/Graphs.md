
*Terminology*

- Graph is a combination of nodes and edges.It is used to represent a grid of connections between some nodes.Example different roads between different cities.
- ![[Pasted image 20240625233459.png]]Representation of a graph using adjacency list 
- If there are 'n' vertices and n-1 edges then that graph is a tree.
- Sparse graph => graph with n vertices and probably like nlogn edges
- Dense graph => graph with n vertices and around n$^2$ edges 
- Graph can be represented by => adjacency matrix and adjacency list 
- Which is better ? => depends for dense graphs => adjacency matrix and for sparse graphs => adjacency lists
- For graph exploration => adjacency list suits better and works better
- Space complexity for adjacency list => O(edges+vertices)
- 

*Traversals*

- **DFS(Depth First Search )** => In this the pointer first moves to an extreme end in the direction first and then changes to some new direction and continues the process recursively.Both DFS and BFS traverse through same elements or nodes but the order changes.
- ![[Pasted image 20240625233729.png]]
- **BFS(Breadth First Search)** =>  In this the pointer first traverse through all the neighbours recursively in a circular manner i.e it tends to traverse in all directions evenly rather going to extreme end like DFS .
- ![[Pasted image 20240625233955.png]]
