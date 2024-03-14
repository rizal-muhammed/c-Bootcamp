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

