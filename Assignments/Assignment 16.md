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
<br>

3. Write a program in C to find the transpose of a given matrix.
```
#include <stdio.h>

void print_matrix(int arr[][3], int, int);
void transpose(int arr[][3], int arr_t[][3], int, int);

void transpose(int arr[][3], int arr_t[][3], int rows, int cols)
{
    if (rows == cols)
    {
        for (int i = 0; i < rows; i++)
        {
            for (int j = 0; j < cols; j++)
            {
                arr_t[i][j] = arr[j][i];
            }
            
        }
    }
    else
        printf("Not a sqaure matrix. Transpose doesn't exists\n");
}

void print_matrix(int arr[][3], int rows, int cols)
{
    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < cols; j++)
        {
            printf("%d\t", arr[i][j]);
        }
        printf("\n");
    }
}

int main()
{
    int a[3][3] = {{1, 2, 3},
                   {4, 5, 6},
                   {7, 8, 9}};

    int rows = sizeof(a) / sizeof(a[0]);
    int cols = sizeof(a[0]) / sizeof(a[0][0]);

    int a_t[3][3] = {0};

    printf("Matrix a : \n");
    print_matrix(a, rows, cols);

    transpose(a, a_t, rows, cols);

    printf("Matrix A Transpose : \n");
    print_matrix(a_t, rows, cols);

    return 0;
}
```
<br>

4. Write a program in C to find the sum of right diagonals of a matrix.
```
#include <stdio.h>

# define ROWS 3
# define COLS 3

void print_matrix(int arr[][COLS]);
float sum_diagonals(int arr[][COLS]);

void print_matrix(int arr[][COLS])
{
    for (int i = 0; i < ROWS; i++)
    {
        for (int j = 0; j < COLS; j++)
        {
            printf("%d\t", arr[i][j]);
        }
        printf("\n");
    }
}

float sum_diagonals(int arr[][COLS])
{
    float diagonals_sum = 0;

    for (int i = 0; i < ROWS; i++)
    {
        for (int j = 0; j < COLS; j++)
        {
            if (i == j)
                diagonals_sum += arr[i][j];
        }
    }
    return diagonals_sum;
}

int main()
{
    printf("Program to find the sum of right diagonal elements\n");
    int a[ROWS][COLS] = {{1, 2, 3},
                         {4, 5, 6},
                         {7, 8, 9}};

    float diagonal_sum;

    printf("Matrix A : \n");
    print_matrix(a);
    printf("\n");

    diagonal_sum = sum_diagonals(a);
    printf("The sum of diagonal elements = %.1f\n", diagonal_sum);

    return 0;
}
```
<br>

5. Write a program in C to find the sum of left diagonals of a matrix.
```
#include <stdio.h>

# define ROWS 3
# define COLS 3

void print_matrix(int arr[][COLS]);
int sum_left_diagonals(int arr[][COLS]);


void print_matrix(int arr[][COLS])
{
    for (int i = 0; i < ROWS; i++)
    {
        for (int j = 0; j < COLS; j++)
        {
            printf("%d\t", arr[i][j]);
        }
        printf("\n");
    }
}

int sum_left_diagonals(int arr[][COLS])
{
    int left_diag_sum = 0;

    if (ROWS == COLS)
    {
        for (int i = 0; i < ROWS; i++)
        {
            for (int j = 0; j < COLS; j++)
            {
                if (i + j == ROWS - 1)
                    left_diag_sum += arr[i][j];
            }
        }
        return left_diag_sum;
    }
    else
        printf("Not a square matrix\n");
    return 0;
}

int main()
{
    printf("Program to find the sum of left diagonals of a matrix\n");
    int a[ROWS][COLS] = {{11, 2, 13},
                         {4, 5, 6},
                         {7, 8, 9}};
    int left_diagonal_sum;

    printf("Matrix A : \n");
    print_matrix(a);
    printf("\n");

    left_diagonal_sum = sum_left_diagonals(a);
    printf("The sum of left diagonal elements = %d\n", left_diagonal_sum);

    return 0;
}
```
<br>

6. Write a program in C to find the sum of rows and columns of a Matrix.
```
#include <stdio.h>

void read_matrix(int n, int m, int a[n][m]);
void print_matrix(int n, int m, int a[n][m]);
void calculate_row_sums(int n, int m, int a[n][m], int row_sums[n]);
void print_row_sums(int n, int row_sums[n]);
void calculate_col_sums(int n, int m, int a[n][m], int col_sums[m]);
void print_col_sums(int m, int col_sums[m]);

void read_matrix(int n, int m, int a[n][m])
{
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            printf("Element [%d][%d]: ", i, j);
            scanf("%d", &a[i][j]);
        }
        
    }
}

void print_matrix(int n, int m, int a[n][m])
{
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            printf("%d\t", a[i][j]);
        }
        printf("\n");
    }
}

void calculate_row_sums(int n, int m, int a[n][m], int row_sums[n])
{

    for (int i = 0; i < n; i++)
    {
        int row_sum = 0;
        for (int j = 0; j < m; j++)
        {
            row_sum += a[i][j];
        }
        row_sums[i] = row_sum;
    }
    print_row_sums(n, row_sums);
}

void print_row_sums(int n, int row_sums[n])
{
    printf("------------------\n");
    printf("Row sum: \n");
    for (int i = 0; i < n; i++)
    {
        printf("|%d|\n", row_sums[i]);
    }
    printf("------------------\n");
    printf("\n"); 
}

void calculate_col_sums(int n, int m, int a[n][m], int col_sums[m])
{
    for (int i = 0; i < m; i++)
    {
        int col_sum = 0;
        for (int j = 0; j < n; j++)
        {
            col_sum += a[j][i];
        }
        col_sums[i] = col_sum;
    }
    print_col_sums(m, col_sums);
}

void print_col_sums(int m, int col_sums[m])
{
    printf("------------------\n");
    printf("Col sum: \n");
    for (int i = 0; i < m; i++)
    {
        printf("%d\t", col_sums[i]);
    }
    printf("\n------------------\n");
    printf("\n"); 
}

int main()
{
    int n, m;
    printf("Program to find the sum of rows and columns of an n x m matrix\n");
    printf("Let's read the matrix\n");
    printf("Enter number of rows n: ");
    scanf("%d", &n);
    printf("Enter number of columns m: ");
    scanf("%d", &m);

    int a[n][m];
    int row_sums[n], col_sums[m];

    read_matrix(n, m, a);
    printf("The entered matrix is: \n");
    print_matrix(n, m, a);

    calculate_row_sums(n, m, a, row_sums);
    calculate_col_sums(n, m, a, col_sums);

    return 0;
}
```
<br>

7. Write a program in C to print or display the lower triangular of a given matrix.
```
#include <stdio.h>

void read_matrix(int n, int m, int a[n][m]);
void print_matrix(int n, int m, int a[n][m]);
void print_lower_triangle(int n, int m, int a[n][m]);

void print_lower_triangle(int n, int m, int a[n][m])
{
    printf("Lower triangle\n");
    printf("--------------\n");

    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            if (i >= j)
                printf("%d\t", a[i][j]);
        }
        printf("\n");
    }
    
}

void read_matrix(int n, int m, int a[n][m])
{
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            printf("Element [%d][%d]: ", i, j);
            scanf("%d", &a[i][j]);
        }
        
    }
}

void print_matrix(int n, int m, int a[n][m])
{
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            printf("%d\t", a[i][j]);
        }
        printf("\n");
    }
}

int main()
{
    int n, m;
    printf("Program to print or display the lower triangular of a given matrix\n");
    printf("Let's read the matrix\n");
    printf("Enter number of rows n: ");
    scanf("%d", &n);
    printf("Enter number of columns m: ");
    scanf("%d", &m);

    int a[n][m];
    int row_sums[n], col_sums[m];

    read_matrix(n, m, a);
    printf("The entered matrix is: \n");
    print_matrix(n, m, a);

    print_lower_triangle(n, m, a);

    return 0;
}
```
<br>

