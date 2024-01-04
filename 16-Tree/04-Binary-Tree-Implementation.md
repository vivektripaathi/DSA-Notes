# Binary Tree Implementation

## Structure of Tree
```cpp
// Method 1: Using "struct" to make
struct node {
	int data;
	struct node* left;
	struct node* right;
	Node(int val){
		data = val;
		left = right = NULL;
	}
};

// Method 2: Using "class" to make
class Node {
public:
	int data;
	Node* left;
	Node* right;
	Node(int val){
		data = val;
		left = right = NULL;
	}
};
```

## Creating a Binary Tree
```cpp
#include<bits/stdc++.h>;
using namespace std;

struct node {
	int data;
	struct node* left;
	struct node* right;
	Node(int val){
		data = val;
		left = right = NULL;
	}
};

int main(){
	/*create root*/
	Node* root = new Node(1);
	
/* following is the tree after above statement
  1
/   \
NULL NULL
*/

	root -> left = new Node(2);
	root -> right = new Node(3);

/* 2 and 3 become left and right children of 1
       1
   /       \
  2        3
/   \     /   \
NULL NULL NULL NULL
*/

	root -> left -> left = new Node(4);

/* 4 becomes left child of 2
    1
 /     \
 2       3
/ \    /    \
4  NULL NULL NULL
/ \
NULL NULL
*/

	return 0;
}
```