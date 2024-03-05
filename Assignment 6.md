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
```
#include <stdio.h>

int main()
{
    int N, sum = 0;
    printf("Program to print sum of first N odd natural numbers...\n");

    printf("Enter N\n");
    scanf("%d", &N);

    for (int i = 1; i <= 2 * N; i = i+2)
        sum += i;
    
    printf("\nThe sum of first %d odd natural numbers = %d\n", N, sum);

    return 0;
}
```
4. Write a program to calculate sum of squares of first N natural numbers
```
#include <stdio.h>
#include <math.h>

int main()
{
    int N, sum = 0;
    printf("Program to calculate the sum of square of first N natural numbers\n");
    printf("Enter N\n");
    scanf("%d", &N);

    for (int i = 1; i <= N; i++)
        sum += (int)(powf(i, 2));

    printf("The sum of squares of first %d natural numbers = %d\n", N, sum);
    return 0;
}
```
5. Write a program to calculate sum of cubes of first N natural numbers
```
#include <stdio.h>
#include <math.h>

int main()
{
    int N, sum = 0;
    printf("Program to calculate the sum of cubes of first N natural numbers\n");
    printf("Enter N\n");
    scanf("%d", &N);

    for (int i = 1; i <= N; i++)
        sum += (int)(powf(i, 3));

    printf("The sum of cubes of first %d natural numbers = %d\n", N, sum);
    return 0;
}
```
6. Write a program to calculate factorial of a number
```
#include <stdio.h>

int main()
{
    int n;
    printf("Program to calculate factorial of a number\n");
    printf("Enter number\n");
    scanf("%d", &n);

    if (n < 0)
        printf("%d is a negative number. factorial doesn't exists.\n", n);
    else
    {
        int result = 1;
        if (n == 0 || n == 1)
            printf("%d! = 1\n", n);
        else
        {
            for (int i = 1; i <= n; i++)
                result *= i;
            printf("%d! = %d\n", n, result);
        }
    }
    return 0;
}
```
7. Write a program to count digits in a given number
```
# include <stdio.h>

int main()
{
    int num, cp, count = 0;
    printf("Program to count digits in a number\n");
    printf("Enter your number\n");
    scanf("%d", &num);
    cp = num;

    do
    {
        num /= 10;
        count++;
    } while (num != 0);

    printf("\n%d contains %d digit(s)\n", cp, count);
    return 0;
}

```
8. Write a program to check whether a given number is a Prime number or not
```
#include <stdio.h>

int main()
{
    int num, not_prime = 0;
    printf("Program to check whether a number is prime?\n");
    printf("Enter your number\n");
    scanf("%d", &num);

    if (num < 0)
        printf("%d is negative. ie; not prime\n", num);
    else if (num == 0 || num == 1)
        printf("%d is not prime\n", num);
    else
    {
        for (int i = 2; i <= num-1; i++)
        {
            if (num % i == 0)
            {
                not_prime = 1;
                break;
            }
        }
        if (not_prime)
            printf("%d is not prime\n", num);
        else 
            printf("%d is prime\n", num);
    }


    return 0;
}
```
9. Write a program to calculate LCM of two numbers
```
#include <stdio.h>

int main()
{
    int a, b, max, min, step = 1, lcm;

    printf("Program to calculate LCM of two numbers\n");
    printf("Enter two numbers(separated by space)\n");
    scanf("%d %d", &a, &b);

    max = a > b ? a : b; // finding the maximum
    min = a > b ? b : a; // finding the minimum

    do
    {
        lcm = max * step;
        step++;
    } while (lcm % min); // stops when max % min == 0

    printf("LCM of %d and %d = %d\n", a, b, lcm);
    
}
```


10. Write a program to reverse a given number
```
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int num, reversed_num = 0, cp, is_negative = 0;
    printf("Program to reverse a given number\n");
    printf("Enter your number\n");
    scanf("%d", &num);
    cp = num;

    if (num < 0) // dealing with negative numbers
    {
        num = abs(num);
        is_negative = 1;
    }

    while (1)
    {
        if (num < 10)
        {
            reversed_num = reversed_num * 10 + num;
            break;
        }
        else
        {
            reversed_num = reversed_num * 10 + (num % 10);
            num = num / 10;
        }
    }

    if (is_negative)
        reversed_num = -1 * reversed_num;

    printf("The reverse of %d is %d\n", cp, reversed_num);
    return 0;
}
```
