---
title: "Matrix multiplication algorithms on_RISC-V vector extensions"
date: 2024-10-06T13:44:49+08:00
draft: false
---

we start off with simple matrices, with both Length and complexity.

first we use 4x4 matrix to display how RVV works. To do so, we write the algorithm in C first then talk about the instructions while we are writing the assembly code.

```c
#include <stdio.h>

#define N 3  // Dimension of the matrix

int main() {
    int A[N][N] = {
        {1, 2, 3},
        {8, 9, 10},
        {15, 16, 21},
    };

    int B[N][N] = {
        {21, 20, 19},
        {14, 13, 12},
        {7, 6, 5}
    };

    int C[N][N];

    for(int i = 0; i < N; ++i) {
        for(int k = 0; k < N; ++k) {
            for(int j = 0; j < N; ++j)     {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }

    printf("Resultant Matrix C:\n");
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf("%d ", C[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```
