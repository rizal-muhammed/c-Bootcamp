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
