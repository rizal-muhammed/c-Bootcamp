1. Write a program to find the Nth term of the Fibonnaci series.
```
#include <stdio.h>

int main()
{
    int N, a = 0, b = 1, Nth_term;

    printf("Program to find the Nth term of the fibonacci series\n");
    printf("Enter N\n");
    scanf("%d", &N);

    if (N == 1) // First term of fibonacci sequence is 0
        printf("%d\n", a);
    else if (N == 2) // second term of fibonacci sequence is 1
        printf("%d\n", b);
    else if (N > 2)
    {
        for(int i = 2; i < N; i++)
        {
            if (i%2 == 0)
            {
                a = a + b;
                Nth_term = a;
            }
            else
            {
                b = a + b;
                Nth_term = b;
            }
        }

        printf("%dth term of the fibonacci series is %d\n", N, Nth_term);
    }
    else
        printf("%d is not valid N\n", N);

    return 0;
}
```
<br>

2. Write a program to print first N terms of Fibonacci series
```
#include <stdio.h>

int main()
{
    int N, count = 0, a = 0, b = 1;

    printf("Program to generate first N terms of fibonacci series\n");
    printf("Enter N\n");
    scanf("%d", &N);

    if (N == 1)
        printf("%d\n", a);
    else if (N == 2)
        printf("%d\t%d\n", a, b);
    else if (N > 2)
    {
        printf("%d\t%d", a, b);
        for(int i = 2; i < N; i++)
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
        printf("%d is not a valid N\n", N);

    return 0;
}
```
<br>

3. Write a program to check whether a given number is there in the Fibonacci series or not.
```
#include <stdio.h>

int main()
{
    int num, is_fib = 0, a = 0, b = 1, Nth_term = 2; 

    printf("Program to check whether a given is in fibonacci sequence\n");
    printf("Enter your number: \n");
    scanf("%d", &num);

    if (num ==0 || num == 1)
        is_fib = 1;
    else if (num >= 2)
    {
        int i = 2;
        while (num >= Nth_term)
        {
            if (i%2 == 0)
            {
                a = a + b;
                Nth_term = a;
                if (Nth_term == num)
                {
                    is_fib = 1;
                    break;
                }
            }
            else
            {
                b = a + b;
                Nth_term = b;
                if (Nth_term == num)
                {
                    is_fib = 1;
                    break;
                }
            }
            i++;
        }
        
    }

    if (is_fib)
        printf("%d is in fibonacci sequence\n", num);
    else 
        printf("%d is not in fibonacci sequence\n", num);

    return 0;
}
```
<br>

4. Write a program to calculate HCF of two numbers
```
#include <stdio.h>

int main()
{
    int a, b, hcf = 1;
    int abs_a, abs_b, max;

    printf("Program to calculate the HCF(Highest Common Factor) of two numbers\n");
    printf("Enter two numbers(separated by space)\n");
    scanf("%d %d", &a, &b);

    abs_a = a < 0? -1 * a : a; // Absolute value of a
    abs_b = b < 0? -1 * b : b; // Absolute value of b
    max = abs_a > abs_b? abs_a : abs_b; // Maximum

    /* We use factor method to computed the highest common factor of two numbers */
    if (abs_a == abs_b)
        hcf = abs_a;
    else
    {
        for (int i = 2; i <= max/2 + 1; i++)
        {
            if (abs_a % i == 0 && abs_b % i == 0)
                hcf = i;
        }
    }

    if (hcf != 1)
        printf("HCF of %d and %d is %d\n", a, b, hcf);
    else 
        printf("There are no common factors between %d and %d\n", a, b);

    return 0;
}
```
<br>

5. Write a program to check whether two given numbers are co-prime numbers or not
```
#include <stdio.h>

int main()
{
    int a, b, cf = 1;
    int abs_a, abs_b, max;

    printf("Program to check if two numbers are co-primes\n");
    printf("Enter two numbers(separated by space)\n");
    scanf("%d %d", &a, &b);

    abs_a = a < 0? -1 * a : a; // Absolute value of a
    abs_b = b < 0? -1 * b : b; // Absolute value of b
    max = abs_a > abs_b? abs_a : abs_b; // Maximum

    /* We use factor method to computed the highest common factor of two numbers */
    /* If two numbers have only common factor as 1, then the two numbers are co-prime */
    if (abs_a == abs_b)
        cf = abs_a;
    else
    {
        for (int i = 2; i <= max/2 + 1; i++)
        {
            if (abs_a % i == 0 && abs_b % i == 0)
            {
                cf = abs_a;
                break;
            }
        }
    }

    if (cf != 1)
        printf("%d and %d are not co-primes\n", a, b);
    else 
        printf("%d and %d are co-primes\n", a, b);

    return 0;
}
```
<br>

6. Write a program to print all Prime numbers under 100
```
#include <stdio.h>
#include <stdbool.h>

bool is_prime(int);

int main()
{
    printf("Program to print all the prime numbers less than 100\n");
    printf("Prime numbers less than 100 are \n");

    for (int i = 1; i <= 100; i++)
    {
        if (is_prime(i))
            printf("%d\t", i);
    }
    printf("\n");

    return 0;
}

bool is_prime(int x)
{
    /* 

    Description
    -----------
    Function to check if x is prime or not 

    Input(s)
    --------
    x : int type
    The input number to check if prime or not

    Returns
    -------
    bool type
    returns true if x is prime, otherwise, false is returned

    */

    if (x <= 1)
        return false;
    
    for (int i = 2; i <= x/2 + 1; i++)
    {
        if (x != i && x%i == 0)
            return false;
    }

    return true;
}
```
<br>

7. Write a program to print all Prime numbers between two given numbers
```
#include <stdio.h>
#include <stdbool.h>

bool is_prime(int);

int main()
{
    int a, b;

    printf("Program to print all prime numbers between two given numbers a and b\n");
    printf("Enter a and b (separated by space)\n");
    scanf("%d %d", &a, &b);

    printf("Prime numbers between %d and %d are\n", a, b);
    printf("-----------------------------------\n");

    for (int i = a; i <= b; i++)
    {
        if (is_prime(i))
            printf("%d\t", i);
    }
    printf("\n");

    return 0;
}

bool is_prime(int x)
{
    /* 

    Description
    -----------
    Function to check if x is prime or not 

    Input(s)
    --------
    x : int type
    The input number to check if prime or not

    Returns
    -------
    bool type
    returns true if x is prime, otherwise, false is returned

    */

    if (x <= 1)
        return false;
    
    for (int i = 2; i <= x/2 + 1; i++)
    {
        if (x != i && x%i == 0)
            return false;
    }

    return true;
}
```
<br>

8. Write a program to find next Prime number of a given number
```
#include <stdio.h>
#include <limits.h>
#include <stdbool.h>

bool is_prime(int);

int main()
{
    int num, next_prime, temp;

    printf("Program to find the next prime number of a given number\n");
    printf("Enter your number\n");
    scanf("%d", &num);
    temp = num;

    while (num >= 0)
    {
        if (is_prime(num))
        {
            next_prime = num;
            break;
        }
        num++;
    }
    

    printf("\nNext prime number after %d is %d\n", temp, next_prime);
    return 0;
}

bool is_prime(int x)
{
    /* 

    Description
    -----------
    Function to check if x is prime or not 

    Input(s)
    --------
    x : int type
    The input number to check if prime or not

    Returns
    -------
    bool type
    returns true if x is prime, otherwise, false is returned

    */

    if (x <= 1)
        return false;
    
    for (int i = 2; i <= x/2 + 1; i++)
    {
        if (x != i && x%i == 0)
            return false;
    }

    return true;
}
```
<br>

9. Write a program to check whether a given number is an Armstrong number or not
```
#include <stdio.h>
#include <math.h>

/* 
An Armstrong number (also known as a narcissistic number) is a number 
that is equal to the sum of its own digits raised to the power of the 
number of digits in the number itself.

For example, let's take the number 153:

    The number of digits in 153 is 3.
    The sum of the cubes of its digits is 1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153
    So, 153 is an Armstrong number.

Examples for Armstrong number are
0 (Though it doesn't fit the usual definition, it's considered an Armstrong number in some conventions.)
1
153
370
371
407
1634
8208
9474
54748
92727
93084

*/

int main()
{
    int num, temp, sum = 0, num_digits = 0;

    printf("Program to check whether a given number is Armstrong number or not\n");
    printf("Enter your number\n");
    scanf("%d", &num);
    temp = num;

    /* Finding the number of digits in the input number */
    do
    {
        num_digits++;
        num /= 10;
    } while (num);

    /* Checking whether the input number is Armstrong number or not*/
    num = temp;
    do
    {
        sum += (int)powf(num % 10, num_digits);
        num /= 10;
    } while (num);

    if (temp == sum)
        printf("%d is an Armstrong number\n", temp);
    else
        printf("%d is not an Armstrong number\n", temp);

    return 0;
}
```
<br>

10. Write a program to print all Armstrong numbers under 1000
```

```
