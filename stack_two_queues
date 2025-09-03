#include <stdio.h>
#define MAX 100

int q1[MAX], q2[MAX], f1 = -1, r1 = -1, f2 = -1, r2 = -1;

void enqueue1(int x) { if (r1 == -1) f1 = 0; q1[++r1] = x; }
int dequeue1() { return q1[f1++]; }
void enqueue2(int x) { if (r2 == -1) f2 = 0; q2[++r2] = x; }
int dequeue2() { return q2[f2++]; }

void push(int x) { enqueue1(x); }
int pop() {
    while (f1 != r1) enqueue2(dequeue1());
    int val = dequeue1();
    while (f2 <= r2) enqueue1(dequeue2());
    return val;
}

int main() {
    push(10); push(20); push(30);
    printf("Popped: %d\n", pop());
    return 0;
}
