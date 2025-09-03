#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

struct Node* createNode(char d) {
    struct Node* n = (struct Node*)malloc(sizeof(struct Node));
    n->data = d; n->next = NULL;
    return n;
}

int isPalindrome(struct Node* head) {
    char str[100]; int i = 0;
    while (head) { str[i++] = head->data; head = head->next; }
    str[i] = '\0';
    for (int j = 0; j < i / 2; j++)
        if (str[j] != str[i - j - 1]) return 0;
    return 1;
}

int main() {
    struct Node* head = createNode('r');
    head->next = createNode('a');
    head->next->next = createNode('d');
    head->next->next->next = createNode('a');
    head->next->next->next->next = createNode('r');

    if (isPalindrome(head)) printf("Palindrome\n");
    else printf("Not Palindrome\n");

    return 0;
}
