#include <stdio.h>

int main() {
    int arr[100], n, choice, pos, value, i;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter elements: ");
    for (i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    do {
        printf("\n1.Insert  2.Delete  3.Display  4.Exit\n");
        printf("Enter choice: ");
        scanf("%d", &choice);

        if (choice == 1) {
            printf("Enter position (0-%d): ", n);
            scanf("%d", &pos);
            printf("Enter value: ");
            scanf("%d", &value);
            for (i = n; i > pos; i--)
                arr[i] = arr[i - 1];
            arr[pos] = value;
            n++;
        }
        else if (choice == 2) {
            printf("Enter position (0-%d): ", n - 1);
            scanf("%d", &pos);
            for (i = pos; i < n - 1; i++)
                arr[i] = arr[i + 1];
            n--;
        }
        else if (choice == 3) {
            printf("Array: ");
            for (i = 0; i < n; i++)
                printf("%d ", arr[i]);
            printf("\n");
        }
    } while (choice != 4);

    return 0;
}
