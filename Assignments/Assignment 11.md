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

