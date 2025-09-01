#include <stdio.h>
#define MAX 100

int queue[MAX], front = -1, rear = -1;

void enqueue(int x) {
    if (rear == MAX - 1)
        printf("Queue Overflow!\n");
    else {
        if (front == -1) front = 0;
        queue[++rear] = x;
    }
}

void dequeue() {
    if (front == -1 || front > rear)
        printf("Queue Underflow!\n");
    else
        printf("Dequeued: %d\n", queue[front++]);
}

void display() {
    if (front == -1 || front > rear)
        printf("Queue is Empty!\n");
    else {
        printf("Queue: ");
        for (int i = front; i <= rear; i++)
            printf("%d ", queue[i]);
        printf("\n");
    }
}

int main() {
    int choice, val;
    do {
        printf("\n1.Enqueue  2.Dequeue  3.Display  4.Exit\n");
        printf("Enter choice: ");
        scanf("%d", &choice);

        if (choice == 1) {
            printf("Enter value: ");
            scanf("%d", &val);
            enqueue(val);
        }
        else if (choice == 2) dequeue();
        else if (choice == 3) display();
    } while (choice != 4);

    return 0;
}
