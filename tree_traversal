#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *left, *right;
};

struct Node* newNode(int d) {
    struct Node* n = (struct Node*)malloc(sizeof(struct Node));
    n->data = d; n->left = n->right = NULL;
    return n;
}

void preorder(struct Node* r) {
    if (r) { printf("%d ", r->data); preorder(r->left); preorder(r->right); }
}
void inorder(struct Node* r) {
    if (r) { inorder(r->left); printf("%d ", r->data); inorder(r->right); }
}
void postorder(struct Node* r) {
    if (r) { postorder(r->left); postorder(r->right); printf("%d ", r->data); }
}

int main() {
    struct Node* root = newNode(1);
    root->left = newNode(2);
    root->right = newNode(3);
    root->left->left = newNode(4);

    printf("Preorder: "); preorder(root);
    printf("\nInorder: "); inorder(root);
    printf("\nPostorder: "); postorder(root);
    return 0;
}
