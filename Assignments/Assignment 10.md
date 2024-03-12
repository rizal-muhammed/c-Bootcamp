1. Write a function to calculate the area of a circle. (TSRS)
```
#include <stdio.h>
#include <math.h>

#define PI 3.14159

float area_of_circle(float);

/* Write a function to calculate the area of a circle. (TSRS) */

int main()
{
    float radious, area;
    printf("Program to calculate area of a circle\n");
    printf("Enter radious: \n");
    scanf("%f", &radious);
    area = area_of_circle(radious);
    printf("Area of circle with radious %.1f = %.2f\n", radious, area);
    return 0;
}

float area_of_circle(float r)
{
    float area;
    area = PI * powf(r, 2);
    return area;
}
```
<br>

2. Write a function to calculate simple interest. (TSRS)
```
#include <stdio.h>

float simple_interest(float, float, float);

int main()
{
    float p, r, y, si;

    printf("Program to calculate simple interest\n");
    printf("Enter Principal: \n");
    scanf("%f", &p);
    printf("Enter rate or interest in percentage: \n");
    scanf("%f", &r);
    printf("Enter time(years): \n");
    scanf("%f", &y);

    si = simple_interest(p, r, y);
    printf("Simple ineterst = %0.2f\n", si);

    return 0;
}

float simple_interest(float p, float r, float y)
{
    float si;
    si = (p * r * y) / 100;
    return si;
}
```
<br>

3. Write a function to check whether a given number is even or odd. Return 1 if the number is even, otherwise return 0. (TSRS)
```
#include <stdio.h>

int is_even(int);

int main()
{
    int num;
    printf("Program to check if a given number is even or odd\n");
    printf("Enter a number\n");
    scanf("%d", &num);
    if (is_even(num))
        printf("%d is even\n", num);
    else 
        printf("%d is odd\n", num);
    return 0;
}

int is_even(int n)
{
    if (n % 2 == 0)
        return 1;
    else 
        return 0;
}
```
<br>

4. Write a function to print first N natural numbers (TSRN)
```
#include <stdio.h>

void first_N_natural_numbers(int);

void first_N_natural_numbers(int N)
{
    int i;
    printf("First %d natural numbers are\n", N);
    printf("----------------------------\n");
    for (i = 1; i <= N; i++)
        printf("%d\t", i);
}

int main()
{
    int N;
    printf("Program to print first N natural numbers\n");
    printf("Enter N: \n");
    scanf("%d", &N);
    first_N_natural_numbers(N);
    return 0;
}

```
<br>

5. Write a function to print first N odd natural numbers. (TSRN)
```
#include <stdio.h>

void first_n_odd_natural_nums(int);

void first_n_odd_natural_nums(int n)
{
    for (int i = 1; i <= n; i += 2)
        printf("%d\t", i);
}

int main()
{
    int N;
    printf("Program to print first N odd natural numbers\n");
    printf("Enter N: \n");
    scanf("%d", &N);
    first_n_odd_natural_nums(N);
    return 0;
}
```
<br>

6. Write a function to calculate the factorial of a number. (TSRS)
```
#include <stdio.h>

float factorial(int N);

float factorial(int n)
{
    float fact = 1;
    
    if (n == 0 || n == 1)
        return 1;
    for (int i = 1; i <= n; i++)
        fact *= i;
    
    return fact;
}

int main()
{
    int N, fact;
    printf("Program to calculate factorial of a number\n");
    printf("Enter N: \n");
    scanf("%d", &N);
    fact = factorial(N);
    printf("%d! = %d\n", N, fact);
    return 0;
}
```
<br>

7. Write a function to calculate the number of combinations one can make from n items and r selected at a time. (TSRS)
```
#include <stdio.h>
#include <math.h>

int combinations(int, int);

int main()
{
    int n, r, c;
    printf("Program to calculate combinations\n");
    printf("Enter n: \n");
    scanf("%d", &n);
    printf("Enter r: \n");
    scanf("%d", &r);

    c = combinations(n, r);
    printf("C(%d, %d) = %d\n", n, r, c);

    return 0;
}

int combinations(int n, int r)
{
    /* C(n,r)=n!/r!(n-r)! */ 

    /*
    float       tgamma ( float num );

    If num is a natural number, std::tgamma(num) is the factorial of num - 1. 
    Many implementations calculate the exact integer-domain factorial if the argument 
    is a sufficiently small integer. 

    https://en.cppreference.com/w/cpp/numeric/math/tgamma
    */
    int n_fact, r_fact, n_minus_r_fact, comb;

    n_fact = (int)(tgamma((float)n) * n);
    r_fact = (int)(tgamma((float)r) * r);
    n_minus_r_fact = (int)(tgamma((float)(n - r)) * (n - r));

    comb = n_fact / (r_fact * n_minus_r_fact);
    return comb;
}
```
<br>

8. Write a function to calculate the number of arrangements one can make from n items and r selected at a time. (TSRS)
```
#include <stdio.h>
#include <math.h>

int permutations(int, int);

int main()
{
    int n, r, p;
    printf("Program to calculate permutations P(n, r)\n");
    printf("Enter n: \n");
    scanf("%d", &n);
    printf("Enter r: \n");
    scanf("%d", &r);

    p = permutations(n, r);
    printf("P(%d, %d) = %d\n", n, r, p);

    return 0;
}

int permutations(int n, int r)
{
    /* P(n, r) = n! / (n - r)! */

    /*
    float       tgamma ( float num );

    If num is a natural number, std::tgamma(num) is the factorial of num - 1. 
    Many implementations calculate the exact integer-domain factorial if the argument 
    is a sufficiently small integer. 

    https://en.cppreference.com/w/cpp/numeric/math/tgamma
    */

    int n_fact, n_minus_r_fact, perms;

    n_fact = (int)(tgamma((float)n) * n);
    n_minus_r_fact = (int)(tgamma((float)(n - r)) * (n - r));

    perms = n_fact / n_minus_r_fact;

    return perms;

}
```
<br>

9. Write a function to check whether a given number contains a given digit or not. (TSRS)
```
#include <stdio.h>
#include <stdbool.h>

bool contains(int, int);

int main()
{
    int n, d;
    printf("Program to check whether a number contains a digit\n");
    printf("Enter number: \n");
    scanf("%d", &n);
    printf("Enter digit\n");
    scanf("%d", &d);
    if (contains(n, d))
        printf("%d contains digit %d\n", n, d);
    else
        printf("%d doesn't contain digit %d\n", n, d);
    return 0;
}

bool contains(int num, int digit)
{
    bool result = false;

    do
    {
        result = ((num % 10) == digit);
        if (result)
            return result;
        num = num / 10;
    } while (num);

    return result;
}
```
<br>

10. Write a function to print all prime factors of a given number. For example, if the number is 36 then your result should be 2, 2, 3, 3. (TSRN)
```

```
