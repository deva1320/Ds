#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* newNode(int d) {
    struct Node* n = (struct Node*)malloc(sizeof(struct Node));
    n->data = d; n->next = NULL;
    return n;
}

void findIntersection(struct Node* h1, struct Node* h2) {
    while (h1 && h2) {
        if (h1 == h2) {
            printf("Intersect at node with value %d\n", h1->data);
            return;
        }
        h1 = h1->next;
        h2 = h2->next;
    }
    printf("No intersection\n");
}

int main() {
    struct Node* common = newNode(30);
    common->next = newNode(40);

    struct Node* h1 = newNode(10);
    h1->next = newNode(20);
    h1->next->next = common;

    struct Node* h2 = newNode(15);
    h2->next = common;

    findIntersection(h1, h2);
    return 0;
}
