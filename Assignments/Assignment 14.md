# Array in C Language

1. Write a program to calculate the sum of numbers stored in an array of size 10. Take array values from the user.
```
#include <stdio.h>

int main()
{
    int nums[10], sum = 0;
    int i;

    printf("Program to calculate the sum of 10 numbers\n");
    
    printf("Enter 10 numbers\n");
    for (i = 0; i < 10; i++)
        scanf("%d", &nums[i]);
    
    for (i = 0; i < 10; i++)
        sum += nums[i];
    
    printf("The sum = %d\n", sum);

    return 0;
}
```
<br>

