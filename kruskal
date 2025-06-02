#include <stdio.h>

#define INF 99

int cost[10][10], n, mst[10][2], sum;

void kruskal(int cost[10][10], int n);
int find(int parent[10], int i);

int main() {
    int i, j;

    printf("Enter the number of vertices: ");
    scanf("%d", &n);

    printf("Enter the cost adjacency matrix:\n");
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++) {
            scanf("%d", &cost[i][j]);
        }
    }

    kruskal(cost, n);

    printf("Edges of the minimal spanning tree:\n");
    for (i = 0; i < n - 1; i++) {
        printf("(%d, %d) ", mst[i][0], mst[i][1]);
    }
    printf("\nSum of minimal spanning tree: %d\n", sum);

    return 0;
}

void kruskal(int cost[10][10], int n) {
    int parent[10];
    int count = 0;
    sum = 0;

    // Initialize parent array
    for (int i = 0; i < n; i++) {
        parent[i] = i;
    }

    while (count < n - 1) {
        int min = INF, u = -1, v = -1;

        // Find the minimum edge
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (find(parent, i) != find(parent, j) && cost[i][j] < min) {
                    min = cost[i][j];
                    u = i;
                    v = j;
                }
            }
        }

        if (u != -1 && v != -1) {
            // Union
            int root_u = find(parent, u);
            int root_v = find(parent, v);
            parent[root_u] = root_v;

            mst[count][0] = u;
            mst[count][1] = v;
            sum += min;
            count++;

            // Mark edge as used
            cost[u][v] = cost[v][u] = INF;
        }
    }
}

int find(int parent[10], int i) {
    if (parent[i] != i)
        parent[i] = find(parent, parent[i]);  // Path compression
    return parent[i];
}





Enter the number of vertices: 4
Enter the cost adjacency matrix:
99 1 5 2
1 99 99 99
5 99 99 3
2 99 3 99
Edges of the minimal spanning tree:
(0, 1) (0, 3) (2, 3) 
Sum of minimal spanning tree: 6
