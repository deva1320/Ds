#include <stdio.h>
int main() {
    int arr[50], n;
    printf("Enter size: ");
    scanf("%d", &n);

    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Repeated elements and their indices:\n");
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (arr[i] == arr[j]) {
                printf("Value %d repeated at indices %d and %d\n", arr[i], i, j);
            }
        }
    }
    return 0;
}
