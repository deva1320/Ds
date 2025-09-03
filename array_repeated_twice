#include <stdio.h>
int main() {
    int arr[50], n;
    printf("Enter size: ");
    scanf("%d", &n);

    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Elements repeated twice:\n");
    for (int i = 0; i < n; i++) {
        int count = 0;
        for (int j = 0; j < n; j++)
            if (arr[i] == arr[j]) count++;
        if (count == 2) printf("%d ", arr[i]);
    }
    return 0;
}
