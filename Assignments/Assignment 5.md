1. Write a program to print MySirG N times on the screen
```
#include <stdio.h>

int main()
{
    int N;
    printf("Program to MySirG N times...\n");
    printf("Enter N : \n");
    scanf("%d", &N);

    for (int i = 0; i < N; i++)
        printf("MySirG\n");

    return 0;
}
```
2. Write a program to print the first N natural numbers.
```
#include <stdio.h>

int main()
{
    int N;
    printf("Program to print first N natural numbers...\n");

    printf("Enter N\n");
    scanf("%d", &N);

    printf("-------\n");

    for (int i = 1; i <= N; i++)
        printf("%d\n", i);
    return 0;
}
```
3. Write a program to print the first N natural numbers in reverse order
```
#include <stdio.h>

int main()
{
    int N;
    printf("Program to print first N natural numbers in reverse order...\n");

    printf("Enter N\n");
    scanf("%d", &N);

    printf("First %d natural numbers in reverse order\n", N);
    printf("-----------------------------------------\n");
    for (int i = N; i >= 1; i--)
        printf("%d\n", i);
    return 0;
}
```
4. Write a program to print the first N odd natural numbers
```
#include <stdio.h>

int main()
{
    int N;
    printf("Program to print first N odd natural numbers...\n");

    printf("Enter N\n");
    scanf("%d", &N);

    printf("First %d natural numbers\n", N);
    printf("------------------------\n");
    for (int i = 1; i <= 2 * N; i = i+2)
        printf("%d\n", i);
    return 0;
}
```
5. Write a program to print the first N odd natural numbers in reverse order.
```
#include <stdio.h>

int main()
{
    int N;
    printf("Program to print first N odd natural numbers in reverse order...\n");

    printf("Enter N\n");
    scanf("%d", &N);

    printf("First %d odd natural numbers in reverse order\n", N);
    printf("-----------------------------------------\n");
    for (int i = 2*N - 1; i >= 1; i = i-2)
        printf("%d\n", i);
    return 0;
}
```
6. Write a program to print the first N even natural numbers
```
#include <stdio.h>

int main()
{
    int N;
    printf("Program to print first N even natural numbers...\n");

    printf("Enter N\n");
    scanf("%d", &N);

    printf("First %d even natural numbers\n", N);
    printf("-----------------------------\n");
    for (int i = 2; i <= 2 * N; i = i+2)
        printf("%d\n", i);
    return 0;
}
```
7. Write a program to print the first N even natural numbers in reverse order
```
#include <stdio.h>

int main()
{
    int N;
    printf("Program to print first N even natural numbers in reverse order...\n");

    printf("Enter N\n");
    scanf("%d", &N);

    printf("First %d even natural numbers in reverse order\n", N);
    printf("----------------------------------------------\n");
    for (int i = 2 * N; i >= 2; i = i-2)
        printf("%d\n", i);
    return 0;
}
```
8. Write a program to print squares of the first N natural numbers
```
#include <stdio.h>
#include <math.h>

int main()
{
    int N;
    printf("Program to print square of first N natural numbers...\n");

    printf("Enter N\n");
    scanf("%d", &N);

    printf("\nSquares of first %d natural numbers\n", N);
    printf("-----------------------------------\n");
    for (int i = 1; i <= N; i++)
        printf("%d\n", (int)powf(i, 2));
    return 0;
}
```
9. Write a program to print cubes of the first N natural numbers
```
#include <stdio.h>
#include <math.h>

int main()
{
    int N;
    printf("Program to print cubes of first N natural numbers...\n");

    printf("Enter N\n");
    scanf("%d", &N);

    printf("\nCubes of first %d natural numbers\n", N);
    printf("-----------------------------------\n");
    for (int i = 1; i <= N; i++)
        printf("%d\n", (int)powf(i, 3));
    return 0;
}
```
10. Write a program to print a table of N.
```
#include <stdio.h>

int main()
{
    int N;
    printf("Program to print Table of N\n");
    printf("Enter N : \n");
    scanf("%d", &N);
    
    printf("\nThe table of %d\n", N);
    printf("---------------\n");

    for (int i = 1; i <= 10; i++)
        printf("%d x %d = %d\n", i, N, i * N);
    return 0;
}
```
