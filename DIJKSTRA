#include <stdio.h>

#define INF 99

int cost[10][10], n, result[10][2], weight[10];

void dijkstras(int [][10], int);

int main() {
    int i, j, s;

    printf("Enter the number of vertices: ");
    scanf("%d", &n);

    printf("Enter the cost adjacency matrix:\n");
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++) {
            scanf("%d", &cost[i][j]);
        }
    }

    printf("Enter the source vertex: ");
    scanf("%d", &s);

    dijkstras(cost, s);

    printf("Path:\n");
    for (i = 0; i < n; i++) {
        printf("(%d, %d) with weight %d ", result[i][0], result[i][1],
               weight[result[i][1]]);
    }

    return 0;
}

void dijkstras(int cost[][10], int s) {
    int d[10], p[10], visited[10];
    int i, j, min, u, v;

    for (i = 0; i < n; i++) {
        d[i] = INF;
        visited[i] = 0;
        p[i] = s;
    }

    d[s] = 0;

    for (i = 0; i < n - 1; i++) {
        min = INF;
        u = -1;

        for (j = 0; j < n; j++) {
            if (!visited[j] && d[j] < min) {
                min = d[j];
                u = j;
            }
        }

        if (u == -1)
            break;

        visited[u] = 1;

        for (v = 0; v < n; v++) {
            if (!visited[v] && cost[u][v] != INF && d[u] + cost[u][v] < d[v]) {
                d[v] = d[u] + cost[u][v];
                p[v] = u;
            }
        }
    }

    for (i = 0; i < n; i++) {
        result[i][0] = p[i];
        result[i][1] = i;
        weight[i] = d[i];
    }
}





O/P:
Enter the number of vertices: 4
Enter the cost adjacency matrix:
0 1 7 8
99 0 2 5
99 99 0 4
99 99 99 0
Enter the source vertex: 0
Path:
(0, 0) with weight 0 (0, 1) with weight 1 (1, 2) with weight 3 (1, 3) with weight 6
