#include <stdio.h>

void main() {
    int a[10][10], m, n, b[50][3], k = 1, i, j;

    printf("Enter the number of rows and columns: ");
    scanf("%d%d", &m, &n);

    printf("Enter the matrix elements:\n");
    for (i = 0; i < m; i++) {
        for (j = 0; j < n; j++) {
            scanf("%d", &a[i][j]);
        }
    }

    b[0][0] = m;
    b[0][1] = n;

    for (i = 0; i < m; i++) {
        for (j = 0; j < n; j++) {
            if (a[i][j] != 0) {
                b[k][0] = i;
                b[k][1] = j;
                b[k][2] = a[i][j];
                k++;
            }
        }
    }

    b[0][2] = k - 1;

    // Optional: Print sparse matrix
    printf("Sparse Matrix Representation:\n");
    for (i = 0; i < k; i++) {
        printf("%d %d %d\n", b[i][0], b[i][1], b[i][2]);
    }
}
