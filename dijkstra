#include <stdio.h>
#define INF 9999
#define MAX 20

void dijkstra(int G[MAX][MAX], int n, int start) {
    int cost[MAX][MAX], dist[MAX], visited[MAX], pred[MAX];
    int count, mindist, nextnode;

    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            cost[i][j] = (G[i][j] == 0) ? INF : G[i][j];

    for (int i = 0; i < n; i++) {
        dist[i] = cost[start][i];
        pred[i] = start;
        visited[i] = 0;
    }
    dist[start] = 0;
    visited[start] = 1;
    count = 1;

    while (count < n - 1) {
        mindist = INF;
        for (int i = 0; i < n; i++)
            if (dist[i] < mindist && !visited[i]) {
                mindist = dist[i];
                nextnode = i;
            }

        visited[nextnode] = 1;
        for (int i = 0; i < n; i++)
            if (!visited[i] && mindist + cost[nextnode][i] < dist[i]) {
                dist[i] = mindist + cost[nextnode][i];
                pred[i] = nextnode;
            }
        count++;
    }

    printf("Vertex\tDistance from %d\n", start);
    for (int i = 0; i < n; i++)
        printf("%d\t%d\n", i, dist[i]);
}

int main() {
    int G[MAX][MAX], n, start;
    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter adjacency matrix (0 if no edge):\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &G[i][j]);

    printf("Enter starting vertex: ");
    scanf("%d", &start);

    dijkstra(G, n, start);
    return 0;
}
