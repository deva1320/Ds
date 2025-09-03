#include <stdio.h>
int main() {
    int a[10][10], r, c, i, j;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);

    printf("Enter elements:\n");
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            scanf("%d", &a[i][j]);

    for (i = 0; i < r; i++) {
        int rowSum = 0;
        for (j = 0; j < c; j++) rowSum += a[i][j];
        printf("Row %d sum = %d\n", i, rowSum);
    }

    for (j = 0; j < c; j++) {
        int colSum = 0;
        for (i = 0; i < r; i++) colSum += a[i][j];
        printf("Column %d sum = %d\n", j, colSum);
    }
    return 0;
}
