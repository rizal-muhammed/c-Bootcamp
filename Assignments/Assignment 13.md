# More on Recursion in C Language

1. Write a recursive function to calculate sum of first N natural numbers
```
#include <stdio.h>

int sumN(int);

int main()
{
    int N, sum;

    printf("Program to calculate sum of first N natural numbers\n");
    printf("Enter N: ");
    scanf("%d", &N);

    sum = sumN(N);
    printf("Sum of first %d natural numbers = %d\n", N, sum);

    return 0;
}

int sumN(int n)
{
    int sum = 0;
    if (n > 0)
    {
        return sum += sumN(n-1) + n;
    }
    return 0;
}
```
<br>

2. Write a recursive function to calculate sum of first N odd natural numbers
```
#include <stdio.h>

int sum_odd_N(int, int);

int main()
{
    int N, sum;

    printf("Program to calculate sum of first N natural numbers\n");
    printf("Enter n: ");
    scanf("%d", &N);

    sum = sum_odd_N(N, 1);
    printf("The sum of first %d odd natural numbers = %d\n", N, sum);
    return 0;
}

int sum_odd_N(int n, int c)
{
    int sum = 0;

    if (n > 0)
    {
        return sum += sum_odd_N(n-1, c+2) + c;
    }
    return 0;
}
```
<br>

