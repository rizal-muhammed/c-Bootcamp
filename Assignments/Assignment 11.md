1. Write a function to calculate LCM of two numbers. (TSRS)
```
#include <stdio.h>

int get_lcm(int, int);

int main()
{
    int a, b, max, min, step = 1, lcm;

    printf("Program to calculate LCM of two numbers\n");
    printf("Enter two numbers(separated by space)\n");
    scanf("%d %d", &a, &b);

    lcm = get_lcm(a, b);
    printf("LCM of %d and %d = %d\n", a, b, lcm);
    return 0;
}

int get_lcm(int a, int b)
{
    int max, min, lcm, step = 1;

    max = a > b ? a : b; // finding the maximum
    min = a > b ? b : a; // finding the minimum

    do
    {
        lcm = max * step;
        step++;
    } while (lcm % min); // stops when max % min == 0

    return lcm;
}
```
<br>

2. Write a function to calculate HCF of two numbers. (TSRS)
```
#include <stdio.h>

int get_hcf(int, int);

int main()
{
    int a, b, hcf = 1;
    int abs_a, abs_b, max;

    printf("Program to calculate the HCF(Highest Common Factor) of two numbers\n");
    printf("Enter two numbers(separated by space)\n");
    scanf("%d %d", &a, &b);

    hcf = get_hcf(a, b);

    printf("HCF of %d and %d = %d\n", a, b, hcf);

    return 0;
}

int get_hcf(int a, int b)
{
    int abs_a, abs_b, max, hcf = 1;;

    abs_a = a < 0? -1 * a : a; // Absolute value of a
    abs_b = b < 0? -1 * b : b; // Absolute value of b
    max = abs_a > abs_b? abs_a : abs_b; // Maximum

    /* factor method to computed the highest common factor of two numbers */
    if (abs_a == abs_b)
        return abs_a;
    else
    {
        for (int i = 2; i <= max/2 + 1; i++)
        {
            if (abs_a % i == 0 && abs_b % i == 0)
                hcf = i;
        }
    }
    return hcf;
}
```
<br>

3. Write a function to check whether a given number is Prime or not. (TSRS)
```
#include <stdio.h>
#include <stdbool.h>

bool is_prime(int);

int main()
{
    int num;
    printf("Program to check whether a number is prime?\n");
    printf("Enter your number\n");
    scanf("%d", &num);

    if (is_prime(num))
        printf("%d is prime\n", num);
    else
        printf("%d is not prime\n", num);


    return 0;
}


bool is_prime(int num)
{
    if (num <= 1)
        return false;
    
    for (int i = 2; i * i <= num; i++)
    {
        if (num % i == 0)
            return false;
    }
    return true;
}
```
<br>

4. Write a function to find the next prime number of a given number. (TSRS)
```
#include <stdio.h>
#include <stdbool.h>

int next_prime(int);
bool is_prime(int);

int main()
{
    int num, np;
    printf("Program to find next prime number of a given number\n");
    printf("Enter number: \n");
    scanf("%d", &num);
    np = next_prime(num);

    printf("Next prime number after %d is %d\n", num, np);
}

int next_prime(int n)
{
    int np = n;
    do
    {
        np++;
    } while (!is_prime(np));
    
    return np;
}

bool is_prime(int num)
{
    if (num <= 1)
        return false;
    
    for (int i = 2; i * i <= num; i++)
    {
        if (num % i == 0)
            return false;
    }
    return true;
}
```
<br>

5. Write a function to print first N prime numbers (TSRN)
```
#include <stdio.h>
#include <stdbool.h>

void print_first_N_primes(int);
bool is_prime(int);

int main()
{
    int N;
    printf("Program to print first N prime numbers\n");
    printf("Enter N: \n");
    scanf("%d", &N);

    print_first_N_primes(N);
    return 0;
}

void print_first_N_primes(int n)
{
    int count;
    printf("First %d prime numbers are: \n", n);

    for (int i = 2; n >= 1; i++)
    {
        if (is_prime(i))
        {
            printf("%d\n", i);
            n--;
        }
    }
    
    
}

bool is_prime(int num)
{
    if (num <= 1)
        return false;
    
    for (int i = 2; i * i <= num; i++)
    {
        if (num % i == 0)
            return false;
    }
    return true;
}
```
<br>

6. Write a function to print all Prime numbers between two given numbers. (TSRN)
```
#include <stdio.h>
#include <stdbool.h>

void print_prime_between_a_and_b(int a, int b);
bool is_prime(int);

int main()
{
    int a, b;
    printf("Program to print prime numbers between given two numbers\n");
    printf("Enter numbers (separated by space): \n");
    scanf("%d %d", &a, &b);

    print_prime_between_a_and_b(a, b);

    return 0;
}

void print_prime_between_a_and_b(int a, int b)
{
    if (a >= b)
        printf("%d >= %d\n", a, b);
    else
    {
        printf("Prime numbers between %d and %d are: \n", a, b);
        for (int i = a; i <= b; i++)
        {
            if (is_prime(i))
                printf("%d\t", i);
        }
    }
    
}

bool is_prime(int num)
{
    if (num <= 1)
        return false;
    
    for (int i = 2; i * i <= num; i++)
    {
        if (num % i == 0)
            return false;
    }
    return true;
}
```
<br>

7. Write a function to print first N terms of Fibonacci series (TSRN)
```
#include <stdio.h>

void print_fibonacci(int);

int main()
{
    int N;

    printf("Program to generate first N terms of fibonacci series\n");
    printf("Enter N\n");
    scanf("%d", &N);

    print_fibonacci(N);

    return 0;
}

void print_fibonacci(int n)
{
    int count = 0, a = 0, b = 1;
    if (n == 1)
        printf("%d\n", a);
    else if (n == 2)
        printf("%d\t%d\n", a, b);
    else if (n > 2)
    {
        printf("%d\t%d", a, b);
        for(int i = 2; i < n; i++)
        {
            printf("\t%d", a + b);
            if (i%2 == 0)
                a = a + b;
            else
                b = a + b;
        }
        printf("\n");
    }
    else  
        printf("%d is not a valid N\n", n);
}
```
<br>

9. Write a program in C to find the square of any number using the function.
```
#include <stdio.h>

int square(int);

int main()
{
    int num, num_squared;
    printf("Program to calculate square of a number\n");
    printf("Enter number: \n");
    scanf("%d", &num);

    num_squared = square(num);
    printf("%d^2 = %d\n", num, num_squared);

    return 0;
}

int square(int a)
{
    return a * a;
}
```
<br>

10. Write a program in C to find the sum of the series 1! /1+2!/2+3!/3+4!/4+5!/5 using the function.
```
#include <stdio.h>

int sum_of_series(int);
int factorial(int);

int main()
{
    int n, sum;
    printf("Program to print the sum of series 1!/1 + 2!/2 + 3!/3 + 4!/4 + 5!/5 +......+ n!/n\n");
    printf("Enter n: \n");
    scanf("%d", &n);
    sum = sum_of_series(n);

    for (int i = 1; i <= n; i++)
    {
        if (i < n)
            printf("%d!/%d + ", i, i);
        else
            printf("%d!/%d = %d\n", i, i, sum);
    }
}

int sum_of_series(int n)
{
    int sum = 0;
    for (int i = 1; i <= n; i++)
    {
        sum += (factorial(i) / i);
    }
    return sum;
}

int factorial(int n)
{
    int fact = 1;
    
    if (n < 0)
        return 0;
    else if (n <= 1)
        return 1;
    else
    {
        for (int i = 1; i <= n; i++)
        {
            fact *= i;
        }
        return fact;
    }
}
```
