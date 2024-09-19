# Binary Tree Traversals

![Binary Tree Traversal Example](/assets/images/Binary-Tree-Traversal.png)

# Inorder Traversal
In Inorder Traversal, a node is processed after processing all the nodes in its left subtree. The right subtree of the node is processed after processing the node itself.
- <mark class="hltr-yellow">Left, Root, Left</mark>
- **Example**: Inorder traversal for the above-given tree is 4 2 5 1 3.
```pseudocode
Algorithm Inorder(tree)
	1. Traverse the left subtree, i.e., call Inorder(left->subtree)
	2. Visit the root.
	3. Traverse the right subtree, i.e., call Inorder(right->subtree)
```

```cpp
void printInorder(struct Node* node)
{
    if (node == NULL) return;
    printInorder(node->left);
    cout << node->data << " ";
    printInorder(node->right);
}
```

## Preorder Traversal
In preorder traversal, a node is processed before processing any of the nodes in its subtree.
- <mark class="hltr-yellow">Root, Left, Right</mark>
- **Example**: Preorder traversal for the above-given tree is 1 2 4 5 3.
```pseudocode
Algorithm Preorder(tree)
	1. Visit the root.
	2. Traverse the left subtree, i.e., call Preorder(left-subtree)
	3. Traverse the right subtree, i.e., call Preorder(right-subtree)
```

```cpp
void printPreorder(struct Node* node)
{
    if (node == NULL) return;
    cout << node->data << " ";
    printPreorder(node->left); 
    printPreorder(node->right);
} 
```

## Postorder Traversal
In post order traversal, a node is processed after processing all the nodes in its subtrees.
- Left, Right, Root.
- **Example**: Postorder traversal for the above-given Tree is 4 5 2 3 1.
```pseudocode
Algorithm Postorder(tree)
    1. Traverse the left subtree, i.e., call Postorder(left-subtree)
    2. Traverse the right subtree, i.e., call Postorder(right-subtree)
    3. Visit the root.
```

```cpp
void printPostorder(struct Node* node)
{
    if (node == NULL) return;
    printPostorder(node->left);
    printPostorder(node->right);
    cout << node->data << " ";
}
```
