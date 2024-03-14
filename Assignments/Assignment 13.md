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

3. Write a recursive function to calculate sum of first N even natural numbers
```
#include <stdio.h>

int sum_even_N(int, int);

int main()
{
    int N, sum;
    printf("Program to calculate sum of first N even natural numbers\n");
    printf("Enter N: ");
    scanf("%d", &N);
    
    sum = sum_even_N(N, 2);
    printf("The sum of first %d even natural numbers = %d\n", N, sum);
    return 0;
}

int sum_even_N(int n, int c)
{
    int sum = 0;
     
    if (n > 0)
    {
        return sum += sum_even_N(n-1, c+2) + c;
    }
    return 0;
}
```
<br>

4. Write a recursive function to calculate sum of squares of first n natural numbers
```
#include <stdio.h>

int sum_squares_N(int);

int main()
{
    int N, sum;

    printf("Program to calculate sum of squares of first N natural numbers\n");
    printf("Enter N: ");
    scanf("%d", &N);

    sum = sum_squares_N(N);
    printf("Sum of square of first %d natural numbers = %d\n", N, sum);
    return 0;
}

int sum_squares_N(int n)
{
    int sum = 0;

    if (n > 0)
    {
        return sum += sum_squares_N(n - 1) + n * n;
    }
    return 0;
}
```
<br>

5. Write a recursive function to calculate sum of digits of a given number
```
#include <stdio.h>

int sum_digits(int);

int main()
{
    int n, sum;

    printf("Program to calculate the sum of digits of a given number\n");
    printf("Enter number: ");
    scanf("%d", &n);

    sum = sum_digits(n);
    printf("Sum of digits of %d = %d\n", n, sum);

    return 0;
}

int sum_digits(int n)
{
    int ld;

    if (n > 0)
    {
        ld = n % 10;
        return ld + sum_digits(n / 10);
    }
    return 0;
}
```
<br>

6. Write a recursive function to calculate factorial of a given number
```
#include <stdio.h>

int factorial(int);

int main()
{
    int N, fact;

    printf("Program to calculate factorial of N\n");
    printf("Enter N: ");
    scanf("%d", &N);

    fact = factorial(N);
    printf("%d! = %d\n", N, fact);

    return 0;
}

int factorial(int n)
{
    if (n > 0)
    {
        return factorial(n - 1) * n;
    }
    else if (n == 0)
        return 1;
    
    return 0;
}
```
<br>

9. Write a program in C to count the digits of a given number using recursion.
```
#include <stdio.h>

int digits_count(int);

int main()
{
    int n, digits;

    printf("Program to count the digits of a given number\n");
    printf("Enter number: ");
    scanf("%d", &n);

    digits = digits_count(n);
    printf("%d contain %d digits\n", n, digits);
    return 0;
}

int digits_count(int n)
{
    int count = 0;

    if (n > 0)
    {
        return count += digits_count(n / 10) + 1;
    }
    return 0;
}
```
<br>




