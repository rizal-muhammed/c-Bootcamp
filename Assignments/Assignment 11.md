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



