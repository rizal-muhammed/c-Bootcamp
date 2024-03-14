1. Write a recursive function to print first N natural numbers
```
#include <stdio.h>

void printN(int);

int main()
{
    int N;
    printf("Program to print first N natural numbers\n");
    printf("Enter N: ");
    scanf("%d", &N);
    printN(N);
    return 0;
}

void printN(int n)
{
    if (n > 0)
    {
        printN(n - 1);
        printf("%d\t", n);
    }
}
```
<br>

2. Write a recursive function to print first N natural numbers in reverse order
```
#include <stdio.h>

void printN_reverse(int);

int main()
{
    int N;
    printf("Program to print first N natural numbers in reverse order\n");
    printf("Enter N: ");
    scanf("%d", &N);
    printN_reverse(N);
    return 0;
}

void printN_reverse(int n)
{
    if (n > 0)
    {
        printf("%d\t", n);
        printN_reverse(n-1);
    }
}
```
<br>

3. Write a recursive function to print first N odd natural numbers
```
#include <stdio.h>

void print_odd_N(int, int);

int main()
{
    int N ;
    printf("Program to print first N odd natural numbers\n");
    printf("Enter N: ");
    scanf("%d", &N);
    print_odd_N(N, 1);
    return 0;
}

void print_odd_N(int n, int c)
{
    if (n > 0)
    {
        printf("%d\t", c);
        print_odd_N(n - 1, c + 2);
    }
}
```
<br>



