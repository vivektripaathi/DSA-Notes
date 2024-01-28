# Tree
A tree data structure is a non-linear hierarchical structure that is used to represent and organize data in a way that is easy to navigate and search. It is a collection of nodes that are connected by edges and has a hierarchical relationship between the nodes.

![Tree Data Structure](/assets/images/tree.png)

## Basic Terminologies In Tree Data Structure:
- **Parent Node:** The node which is a predecessor of a node is called the parent node of that node. **{B}** is the parent node of **{D, E}**.
- **Child Node:** The node which is the immediate successor of a node is called the child node of that node. Examples: **{D, E}** are the child nodes of **{B}.**
- **Root Node:** The topmost node of a tree or the node which does not have any parent node is called the root node. **{A}** is the root node of the tree. A non-empty tree must contain exactly one root node and exactly one path from the root to all other nodes of the tree.
- **Leaf Node or External Node:** The nodes which do not have any child nodes are called leaf nodes. **{K, L, M, N, O, P, G}** are the leaf nodes of the tree.
- **Ancestor of a Node:** Any predecessor nodes on the path of the root to that node are called Ancestors of that node. **{A,B}** are the ancestor nodes of the node **{E}**
- **Descendant:** Any successor node on the path from the leaf node to that node. **{E,I}** are the descendants of the node **{B}.**
- **Sibling:** Children of the same parent node are called siblings. **{D,E}** are called siblings.
- **Level of a node:** The count of edges on the path from the root node to that node. The root node has level **0**.
- **Internal node:** A node with at least one child is called Internal Node.
- **Neighbour of a Node:** Parent or child nodes of that node are called neighbours of that node.
- **Subtree**: Any node of the tree along with its descendant.

## Applications of Tree
1. Store hierarchical data, like folder structure, organization structure, XML/HTML data.
2. **Binary Search Tree** is a tree that allows fast search, insert, delete on a sorted data. It also allows finding closest item
3. **Heap** is a tree data structure which is implemented using arrays and used to implement priority queues.
4. **B-Tree** and **B+ Tree** : They are used to implement indexing in databases.
5. **Syntax Tree**:  Scanning, parsing , generation of code and evaluation of arithmetic expressions in Compiler design.
6. **K-D Tree**: A space partitioning tree used to organize points in K dimensional space.
7. **Trie** : Used to implement dictionaries with prefix lookup.
8. **Suffix Tree**: For quick pattern searching in a fixed text.
9. **Spanning Trees** and shortest path trees are used in routers and bridges respectively in computer networks

## Basic Operation Of Tree Data Structure:
- **Create** – create a tree in the data structure.
- **Insert** − Inserts data in a tree.
- **Search** − Searches specific data in a tree to check whether it is present or not.
- **Traversal**:
    - **Preorder Traversal** – perform Traveling a tree in a pre-order manner in the data structure.
    - **In order Traversal** – perform Traveling a tree in an in-order manner.
    - **Post-order Traversal** –perform Traveling a tree in a post-order manner.

## Types of Tree

![Types of Tree](/assets/images/tree-types.png)

1. **[Binary Tree](16-Tree/02-Binary-Tree):** A binary Tree is defined as a Tree data structure with at most 2 children. Since each element in a binary tree can have only 2 children, we typically name them the left and right child.
2. **Ternary Tree:** A Ternary Tree is a tree data structure in which each node has at most three child nodes, usually distinguished as “left”, “mid” and “right”.
3. **N-ary Tree:** Generic trees are a collection of nodes where each node is a data structure that consists of records and a list of references to its children(duplicate references are not allowed). Unlike the linked list, each node stores the address of multiple nodes.