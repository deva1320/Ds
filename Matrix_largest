#include <stdio.h>
int main() {
    int a[10][10], r, c, i, j, max;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);

    printf("Enter elements:\n");
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            scanf("%d", &a[i][j]);

    max = a[0][0];
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            if (a[i][j] > max) max = a[i][j];

    printf("Largest element = %d\n", max);
    return 0;
}
