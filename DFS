#include <stdio.h>
#define MAX 20

int visited[MAX];

void dfs(int adj[MAX][MAX], int n, int v) {
    printf("%d ", v);
    visited[v] = 1;
    for (int i = 0; i < n; i++) {
        if (adj[v][i] && !visited[i])
            dfs(adj, n, i);
    }
}

int main() {
    int n, adj[MAX][MAX], start;
    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter adjacency matrix:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &adj[i][j]);

    printf("Enter starting vertex: ");
    scanf("%d", &start);

    for (int i = 0; i < n; i++) visited[i] = 0;

    printf("DFS Traversal: ");
    dfs(adj, n, start);
    return 0;
}
