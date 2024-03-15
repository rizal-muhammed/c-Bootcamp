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

2. Write a program to calculate the average of numbers stored in an array of size 10. Take array values from the user.
```
#include <stdio.h>

int main()
{
    int nums[10], sum = 0;
    int i;
    float avg;

    printf("Program to calculate the average of 10 numbers\n");
    
    printf("Enter 10 numbers: \n");
    for (i = 0; i < 10; i++)
        scanf("%d", &nums[i]);
    
    for (i = 0; i < 10; i++)
        sum += nums[i];
    avg = sum / 10.0;
    
    printf("The average = %.2f\n", avg);

    return 0;
}
```
<br>

3. Write a program to calculate the sum of all even numbers and sum of all odd numbers, which are stored in an array of size 10. Take array values from the user.
```
#include <stdio.h>

int main()
{
    int odd_sum, even_sum = 0, nums[10];
    int i;

    printf("Program to calculate the sum of all even numbers and sum of all odd numbers of 10 given numbers\n");
    
    printf("Enter 10 numbers\n");
    for (i = 0; i < 10; i++)
        scanf("%d", &nums[i]);
    
    for (i = 0; i < 10; i++)
    {
        if (nums[i] % 2 == 0)
            even_sum += nums[i];
        else
            odd_sum += nums[i];
    }
    
    printf("Sum of even numbers = %d\n", even_sum);
    printf("Sum of odd numbers = %d\n", odd_sum);

    return 0;
}
```
<br>

4. Write a program to find the greatest number stored in an array of size 10. Take array values from the user.
```
#include <stdio.h>

int main()
{
    int nums[10], max;
    int i;

    printf("Program to calculate the greatest among 10 numbers\n");
    
    printf("Enter 10 numbers\n");
    for (i = 0; i < 10; i++)
        scanf("%d", &nums[i]);
    
    max = nums[0];
    for (i = 1; i < 10; i++)
    {
        if (nums[i] > max)
            max = nums[i];
    }
    
    printf("The gretest element is %d\n", max);

    return 0;
}
```
<br>

5. Write a program to find the smallest number stored in an array of size 10. Take array values from the user.
```
#include <stdio.h>

int main()
{
    int nums[10], min;
    int i;

    printf("Program to calculate the smallest among 10 numbers\n");
    
    printf("Enter 10 numbers\n");
    for (i = 0; i < 10; i++)
        scanf("%d", &nums[i]);
    
    min = nums[0];
    for (i = 1; i < 10; i++)
    {
        if (nums[i] < min)
            min = nums[i];
    }
    
    printf("The smallest element is %d\n", min);

    return 0;
}
```
<br>

6. Write a program to sort elements of an array of size 10. Take array values from the user.
```
#include <stdio.h>

#define COUNT 10

int main()
{
    int i, nums[COUNT], max, temp;

    printf("Program to sort elements of an array\n");
    
    printf("Enter 10 numbers: \n");
    for (i = 0; i < COUNT; i++)
        scanf("%d", &nums[i]);
    
    for (int j = 0; j < COUNT - 1; j++)
    {
        for (i = 0; i < COUNT - 1 - j; i++)
        {
            if (nums[i] > nums[i + 1])
            {
                temp = nums[i];
                nums[i] = nums[i + 1];
                nums[i + 1] = temp;
            }
        }
    }

    printf("Sorted array\n");
    printf("------------\n");
    for (i = 0; i < COUNT; i++)
        printf("%d\t", nums[i]);
    
    
    return 0;
}


```
<br>

10. Write a program in C to copy the elements of one array into another array.Take array values from the user.
```
#include <stdio.h>

int main()
{
    int nums[10], arr[10];
    int i;

    printf("Enter 10 numbers: \n");
    for (i = 0; i < 10; i++)
        scanf("%d", &nums[i]);
    
    for (i = 0; i < 10; i++)
        arr[i] = nums[i];

    for (i = 0; i < 10; i++)
        printf("%d\n", arr[i]);

    return 0;
}
```
<br>