#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *left, *right;
};

struct Node* newNode(int val) {
    struct Node* n = (struct Node*)malloc(sizeof(struct Node));
    n->data = val; n->left = n->right = NULL;
    return n;
}

struct Node* insert(struct Node* root, int key) {
    if (!root) return newNode(key);
    if (key < root->data) root->left = insert(root->left, key);
    else root->right = insert(root->right, key);
    return root;
}

void inorder(struct Node* root, int* count, int k) {
    if (!root) return;
    inorder(root->left, count, k);
    (*count)++;
    if (*count == k) printf("Kth Min = %d\n", root->data);
    inorder(root->right, count, k);
}

int main() {
    struct Node* root = NULL;
    root = insert(root, 20);
    insert(root, 10);
    insert(root, 5);
    insert(root, 15);
    insert(root, 30);

    int k = 3, count = 0;
    inorder(root, &count, k);
    return 0;
}
