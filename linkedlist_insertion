#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* insert(struct Node* head, int data) {
    struct Node* n = (struct Node*)malloc(sizeof(struct Node));
    n->data = data;
    n->next = head;
    return n;
}

void display(struct Node* h) {
    while (h) { printf("%d ", h->data); h = h->next; }
}

int main() {
    struct Node* head = NULL;
    head = insert(head, 10);
    head = insert(head, 20);
    head = insert(head, 30);

    printf("List: ");
    display(head);
    return 0;
}
