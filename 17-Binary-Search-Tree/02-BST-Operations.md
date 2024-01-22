# Operations of Binary Search Tree
## Searching In BST
- **Iterative function**
```cpp
bool search(Node *root, int key){
    while(root != NULL){
        if(root->data == key) return true;
        else if(root->data < key) root = root -> right;
        else root = root -> left;
    }
    return false;
}
```

- **Recursive  function**
```cpp
bool search(Node *root, int key){
    if(root == NULL) return false;
    if(root -> data == key) return true;
    if(root -> data < key) return search(root -> right, key);
    if(root -> data > key) return search(root -> left, key);
    return false;
}
```

## Insertion in BST
- **Iterative function**
```cpp
void insert(Node *&root, int key){
    Node *node = new Node(key);
    if(root == NULL){
        root = node;
        return;
    }
    Node *temp = root;
    Node *prev = NULL;
    while(temp != NULL){
        if(temp -> data > key){
            prev = temp;
            temp = temp -> left;
        }
        else if(temp -> data < key){
            prev = temp;
            temp = temp -> right;
        }
    }
    if(prev -> data > key) prev -> left = node;
    else prev-> right = node;
}
```

- **Recursive  function**
```cpp
void insert(Node *&root, int key){
    if(root == NULL){
        root = new Node(key);
    }
    else if(root -> data < key) insert(root -> right, key);
    else if(root -> data > key) insert(root -> left, key);
}

```

## Deletion in BST
```cpp
Node * minValueNode(Node* node)
{
    Node* current = node;
    while (current->left != NULL)
        current = current->left;
    return current;
}

Node* deleteNode(Node* root, int key)
{
    if (root == NULL) return root;
    if (key < root->data)
        root->left = deleteNode(root->left, key);
    else if (key > root->data)
        root->right = deleteNode(root->right, key);
    else
    {
        if (root->left == NULL)
        {
            Node *temp = root->right;
            free(root);
            return temp;
        }
        else if (root->right == NULL)
        {
            Node *temp = root->left;
            free(root);
            return temp;
        }
        Node* temp = minValueNode(root->right);
        root->data = temp->data;
        root->right = deleteNode(root->right, temp->data);
    }
    
    return root;
}
```