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
