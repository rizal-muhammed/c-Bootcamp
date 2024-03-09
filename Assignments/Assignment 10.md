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
