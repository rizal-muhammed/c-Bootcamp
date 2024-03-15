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

7. Write a recursive function to calculate HCF of two numbers
```
#include <stdio.h>

int find_hcf(int, int);
int abs(int);
int maxf(int, int);

int main()
{
    int a, b, hcf;

    printf("Program to find HCF(Highest Common Factor) of two numbers\n");
    printf("Enter two numbers(separated by space)\n");
    scanf("%d %d", &a, &b);

    hcf = find_hcf(a, b);
    printf("HCF(%d, %d) = %d\n", a, b, hcf);

    return 0;
}

int find_hcf(int a, int b)
{
    int abs_a, abs_b, max, hcf = 1;

    abs_a = abs(a);
    abs_b = abs(b);
    max = maxf(a, b);

    /* Factor method to compute HCF of two numbers */
    if (abs_a == abs_b)
        return abs_a;
    else
    {
        for (int i = 2; i <= max/2 + 1; i++)
        {
            if (abs_a % i == 0 && abs_b % i == 0)
                hcf = i * find_hcf(abs_a/i, abs_b/i);
        }
        return hcf;
    }
    return 1;
}

int abs(int n)
{
   return n < 0? -1 * n : n;
}

int maxf(int a, int b)
{
    return a > b? a : b;
}
```
<br>

8. Write a recursive function to print first N terms of Fibonacci series
```
#include <stdio.h>

int fib_n(int);
void print_fib(int);

int main()
{
    int n, a;

    printf("Program to print first N elements of fibonacii series\n");
    printf("Enter N: ");
    scanf("%d", &n);

    print_fib(n);
    return 0;
}

void print_fib(int n)
{
    for (int i = 0; i < n; i++)
    {
        printf("%d\t", fib_n(i));
    }
    
}

int fib_n(int n)
{
    if (n == 0 || n == 1)
        return n;
    if (n > 1)
        return fib_n(n - 1) + fib_n(n - 2);
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

10. Write a program in C to calculate the power of any number using recursion.
```
#include <stdio.h>

int powerf(int, int);

int main()
{
    int b, e, result;

    printf("Program to compute the value of base raised to the power exponent(b^r).\n");
    printf("Enter base: ");
    scanf("%d", &b);
    printf("Enter exponent: ");
    scanf("%d", &e);

    result = powerf(b, e);
    printf("%d^%d = %d\n", b, e, result);

    return 0;

}

int powerf(int base, int exponent)
{
    if (exponent > 0)
    {
        return powerf(base, exponent - 1) * base;
    }
    return 1;
}
```
<br>

