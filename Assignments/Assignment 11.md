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


