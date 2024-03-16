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
<br>

2. Write a program to calculate the product of two matrices each of order 3x3.
```
#include <stdio.h>

int main()
{
    printf("program to calculate the product of two matrices each of order 3x3\n");
    int a[3][3] = {{1, 2, 3},
                   {4, 5, 6},
                   {7, 8, 9}};
    int b[3][3] = {{1, 2, 1},
                   {2, 1, 2},
                   {3, 2, 1}};
    int c[3][3];
    int rows = 3, cols = 3;
    int k = 0;

    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < cols; j++)
        {
            c[i][j] = a[i][k] * b[k][j] + a[i][k+1] * b[k+1][j] + a[i][k+2] * b[k+2][j];
        }
    }

    printf("The resultant matrix is: \n");
    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < cols; j++)
        {
            printf("%d\t", c[i][j]);
        }
        printf("\n");
    }
    
    
    return 0;
}
```


