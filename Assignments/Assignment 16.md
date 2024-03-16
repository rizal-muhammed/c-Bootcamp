# Multi-Dimensional Array in C Language

1. Write a program to calculate the sum of two matrices each of order 3x3.
```
#include <stdio.h>

int main()
{
    int a[3][3] = {{1, 2, 3},
                   {4, 5, 6},
                   {7, 8, 9}};
    int b[3][3] = {{1, 2, 1},
                   {2, 1, 2},
                   {3, 2, 1}};
    int c[3][3];
    printf("sum of two matrices each of order 3x3\n");
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 3; j++)
        {
            c[i][j] = a[i][j] + b[i][j];
        }
        
    }

    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 3; j++)
        {
            printf("%d\t", c[i][j]);
        }
        printf("\n");
    }
    

}
```
