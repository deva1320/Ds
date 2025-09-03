#include <stdio.h>
int main() {
    int arr[50], n, count, maxCount = 0, mostFreq;
    printf("Enter size: ");
    scanf("%d", &n);

    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    for (int i = 0; i < n; i++) {
        count = 1;
        for (int j = i + 1; j < n; j++)
            if (arr[i] == arr[j]) count++;

        if (count > maxCount) {
            maxCount = count;
            mostFreq = arr[i];
        }
    }

    printf("Most frequent number = %d (count = %d)\n", mostFreq, maxCount);
    return 0;
}
