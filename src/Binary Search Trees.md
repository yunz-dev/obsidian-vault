___
a BST is a [[Node | node]] based [[Binary Tree | binary tree]] [[Data Structures | data structure]] where each node contains a key (or value) and the keys in the left of the subtree are less that then key in the root, while keys in right will be greater than the root. 
- This allows for efficient [[Searching | searching]], [[Insertion | insertion]] and [[Deletion | deletion]] operations
Example: Implementation in C
```c
#include <stdio.h>
#include <stdlib.h>

typedef struct Node {
    int key;
    struct Node *left;
    struct Node *right;
} Node;

Node* createNode(int key) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->key = key;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}

Node* insertNode(Node* root, int key) {
    if (root == NULL) {
        return createNode(key);
    }

    if (key < root->key) {
        root->left = insertNode(root->left, key);
    } else if (key > root->key) {
        root->right = insertNode(root->right, key);
    }

    return root;
}

void inorderTraversal(Node* root) {
    if (root != NULL) {
        inorderTraversal(root->left);
        printf("%d ", root->key);
        inorderTraversal(root->right);
    }
}

int main() {
    Node* root = NULL;
    root = insertNode(root, 50);
    insertNode(root, 30);
    insertNode(root, 20);
    insertNode(root, 40);
    insertNode(root, 70);
    insertNode(root, 60);
    insertNode(root, 80);

    printf("Inorder traversal: ");
    inorderTraversal(root);

    return 0;
}
```
In this example, the `createNode` function creates a new node with the given key. The `insertNode` function recursively inserts a new node with the given key into the BST, following the BST property. The `inorderTraversal` function traverses the BST in an inorder fashion (left subtree, root, right subtree), printing the keys.