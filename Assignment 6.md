1. Write a program to calculate sum of first N natural numbers
```
#include <stdio.h>

int main()
{
    int N, sum = 0;

    printf("Program to calculate sum of first N natural numbers\n");
    printf("Enter N : \n");
    scanf("%d", &N);

    for (int i = 1; i <= N; i++)
        sum += i;
    
    printf("\nThe sum of first %d natural numbers is %d\n", N, sum);
    return 0;
}
```
2. Write a program to calculate sum of first N even natural numbers
```
#include <stdio.h>

int main()
{
    int N, sum = 0;

    printf("Program to calculate sum of first N even natural numbers\n");
    printf("Enter N : \n");
    scanf("%d", &N);

    for (int i = 2; i <= 2 * N; i = i+2)
        sum += i;
    
    printf("\nThe sum of first %d even natural numbers is %d\n", N, sum);
    return 0;
}
```
3. Write a program to calculate sum of first N odd natural numbers
