#include <stdio.h>
#define MAX 30

int parent[MAX];

int find(int i) {
    while (parent[i]) i = parent[i];
    return i;
}

int uni(int i, int j) {
    if (i != j) {
        parent[j] = i;
        return 1;
    }
    return 0;
}

int main() {
    int n, G[MAX][MAX];
    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter adjacency matrix (0 if no edge):\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &G[i][j]);

    int ne = 1, mincost = 0;
    while (ne < n) {
        int min = 9999, a = -1, b = -1;
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                if (G[i][j] && G[i][j] < min) {
                    min = G[i][j];
                    a = i; b = j;
                }
        int u = find(a);
        int v = find(b);
        if (uni(u, v)) {
            printf("%d - %d : %d\n", a, b, min);
            mincost += min;
            ne++;
        }
        G[a][b] = G[b][a] = 9999;
    }
    printf("Minimum Cost = %d\n", mincost);
    return 0;
}
