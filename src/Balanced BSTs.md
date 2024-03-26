___
Type of [[Binary Search Trees | BST]] where the heights of the left and right [[Subtree | subtrees]] of any node differ by at most 1. 
- This property ensures that the tree remains balanced
- prevents skews which lead to poor performance

One popular type of balanced BST is the AVL Tree, named after its inventors Adel'son-Vel'skii and Landis. AVL Trees are self-balancing binary search trees that maintain the height balance property by performing rotations when necessary.

Example: Implementation of an AVL Tree in C
```c
#include <stdio.h>
#include <stdlib.h>

typedef struct Node {
    int key;
    int height;
    struct Node *left;
    struct Node *right;
} Node;

int max(int a, int b) {
    return (a > b) ? a : b;
}

int height(Node* node) {
    if (node == NULL) {
        return 0;
    }
    return node->height;
}

int getBalance(Node* node) {
    if (node == NULL) {
        return 0;
    }
    return height(node->left) - height(node->right);
}

Node* rotateRight(Node* y) {
    Node* x = y->left;
    Node* T2 = x->right;

    x->right = y;
    y->left = T2;

    y->height = max(height(y->left), height(y->right)) + 1;
    x->height = max(height(x->left), height(x->right)) + 1;

    return x;
}

Node* rotateLeft(Node* x) {
    Node* y = x->right;
    Node* T2 = y->left;

    y->left = x;
    x->right = T2;

    x->height = max(height(x->left), height(x->right)) + 1;
    y->height = max(height(y->left), height(y->right)) + 1;

    return y;
}

Node* createNode(int key) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->key = key;
    newNode->left = NULL;
    newNode->right = NULL;
    newNode->height = 1;
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
    } else {
        return root;
    }

    root->height = 1 + max(height(root->left), height(root->right));

    int balance = getBalance(root);

    if (balance > 1 && key < root->left->key) {
        return rotateRight(root);
    }

    if (balance < -1 && key > root->right->key) {
        return rotateLeft(root);
    }

    if (balance > 1 && key > root->left->key) {
        root->left = rotateLeft(root->left);
        return rotateRight(root);
    }

    if (balance < -1 && key < root->right->key) {
        root->right = rotateRight(root->right);
        return rotateLeft(root);
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
In this example, the `createNode` function creates a new node with the given key and initializes its height to 1. The `insertNode` function recursively inserts a new node with the given key into the AVL tree. After each insertion, it updates the height of the nodes and checks for balance violations. If a balance violation occurs, it performs the necessary rotations (left or right) to restore the balance.

The `getBalance` function calculates the balance factor (height difference between left and right subtrees) of a node. The `rotateRight` and `rotateLeft` functions perform right and left rotations, respectively, to rebalance the tree.

The `inorderTraversal` function traverses the AVL tree in an inorder fashion (left subtree, root, right subtree), printing the keys.