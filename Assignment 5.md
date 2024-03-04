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
