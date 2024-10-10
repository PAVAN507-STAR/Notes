- **Why Trees ? =>** O(logN) for basic operations(insertion,deletion..etc),elements are stored in order in both sides,Cost Efficient(no reconstruction of tree happens every time a new data is entered to data base) 
- **Level of a tree** = height of root node - height of node. Level of root node is zero.
- **Limitations** => not efficient for unbalanced Binary Tree (Solution :Use self balancing Binary trees) & Inefficient for sorted Data
- **Applications** => Filesystems,Databases,Network Routing,solving mathematical equations,decision tress(ML),Compression of images.

- *Types of Binary Trees* => 

- **Complete Binary Trees** => All levels must be full except last level,last level is filled from left -> right .
- **Full/Strict Binary Tress** => Each node has 0 or 2 children.(Used in compression,segment tress)
- **Perfect Binary Trees=> All levels are filled,all leaf nodes are on same level.
- **Height Balanced Binary Trees** => average height of tree O(logN)
- **Skewed Binary Trees** => every node has only one child .(like linked list not very useful )
- **Ordered Binary Tree** => every node has a property.

*Properties of Perfect Binary Trees*
- **Total no of nodes** in a perfect binary tree of height h  =   **2$^{(h+1)}$ - 1**
- **No of leaf nodes** in perfect binary tree of height h  =   **2$^h$**
- If there are N no of leaf nodes then the minimum no of levels =   **log(N+1)**
- 