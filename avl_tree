#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data, height;
    struct Node *left, *right;
};

int height(struct Node *n) {
    return n ? n->height : 0;
}

int max(int a, int b) { return (a > b) ? a : b; }

struct Node* createNode(int key) {
    struct Node* node = (struct Node*)malloc(sizeof(struct Node));
    node->data = key;
    node->left = node->right = NULL;
    node->height = 1;
    return node;
}

struct Node* rightRotate(struct Node* y) {
    struct Node* x = y->left;
    struct Node* T2 = x->right;
    x->right = y;
    y->left = T2;
    y->height = max(height(y->left), height(y->right)) + 1;
    x->height = max(height(x->left), height(x->right)) + 1;
    return x;
}

struct Node* leftRotate(struct Node* x) {
    struct Node* y = x->right;
    struct Node* T2 = y->left;
    y->left = x;
    x->right = T2;
    x->height = max(height(x->left), height(x->right)) + 1;
    y->height = max(height(y->left), height(y->right)) + 1;
    return y;
}

int getBalance(struct Node* n) {
    return n ? height(n->left) - height(n->right) : 0;
}

struct Node* insert(struct Node* node, int key) {
    if (!node) return createNode(key);

    if (key < node->data) node->left = insert(node->left, key);
    else if (key > node->data) node->right = insert(node->right, key);
    else return node;

    node->height = 1 + max(height(node->left), height(node->right));

    int balance = getBalance(node);
    if (balance > 1 && key < node->left->data) return rightRotate(node);
    if (balance < -1 && key > node->right->data) return leftRotate(node);
    if (balance > 1 && key > node->left->data) {
        node->left = leftRotate(node->left);
        return rightRotate(node);
    }
    if (balance < -1 && key < node->right->data) {
        node->right = rightRotate(node->right);
        return leftRotate(node);
    }
    return node;
}

struct Node* minValueNode(struct Node* node) {
    struct Node* current = node;
    while (current->left) current = current->left;
    return current;
}

struct Node* deleteNode(struct Node* root, int key) {
    if (!root) return root;

    if (key < root->data) root->left = deleteNode(root->left, key);
    else if (key > root->data) root->right = deleteNode(root->right, key);
    else {
        if (!root->left || !root->right) {
            struct Node* temp = root->left ? root->left : root->right;
            if (!temp) { temp = root; root = NULL; }
            else *root = *temp;
            free(temp);
        } else {
            struct Node* temp = minValueNode(root->right);
            root->data = temp->data;
            root->right = deleteNode(root->right, temp->data);
        }
    }

    if (!root) return root;

    root->height = 1 + max(height(root->left), height(root->right));
    int balance = getBalance(root);

    if (balance > 1 && getBalance(root->left) >= 0) return rightRotate(root);
    if (balance > 1 && getBalance(root->left) < 0) {
        root->left = leftRotate(root->left);
        return rightRotate(root);
    }
    if (balance < -1 && getBalance(root->right) <= 0) return leftRotate(root);
    if (balance < -1 && getBalance(root->right) > 0) {
        root->right = rightRotate(root->right);
        return leftRotate(root);
    }
    return root;
}

int search(struct Node* root, int key) {
    if (!root) return 0;
    if (root->data == key) return 1;
    if (key < root->data) return search(root->left, key);
    return search(root->right, key);
}

void preorder(struct Node* root) {
    if (root) {
        printf("%d ", root->data);
        preorder(root->left);
        preorder(root->right);
    }
}

int main() {
    struct Node* root = NULL;
    int choice, val;
    do {
        printf("\n1.Insert  2.Delete  3.Search  4.Display(Preorder)  5.Exit\n");
        printf("Enter choice: ");
        scanf("%d", &choice);

        if (choice == 1) {
            printf("Enter value: ");
            scanf("%d", &val);
            root = insert(root, val);
        } else if (choice == 2) {
            printf("Enter value to delete: ");
            scanf("%d", &val);
            root = deleteNode(root, val);
        } else if (choice == 3) {
            printf("Enter value to search: ");
            scanf("%d", &val);
            if (search(root, val)) printf("Found!\n");
            else printf("Not Found!\n");
        } else if (choice == 4) {
            printf("Preorder Traversal: ");
            preorder(root);
            printf("\n");
        }
    } while (choice != 5);

    return 0;
}
