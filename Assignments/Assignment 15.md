# Array and Functions in C Language

1. Write a function to find the greatest number from the given array of any size. (TSRS)
```
#include <stdio.h>

int max(int arr[], int size) 
{
    int max = arr[0];
    for (int i = 1; i < size; i++) 
    {
        if (arr[i] > max)
            max = arr[i];
    }
    return max;
}

int main() 
{
    int max_ele;
    int a[] = {34, 3, 34, 45, 300, 59};
    int size = sizeof(a) / sizeof(a[0]);
    
    max_ele = max(a, size);
    printf("Greatest Number = %d\n", max_ele);

    return 0;
}

```
<br>

2. Write a function to find the smallest number from the given array of any size. (TSRS)
```
#include <stdio.h>

int min(int arr[], int size)
{
    int min_num = arr[0];
    for (int i = 1; i < size; i++)
    {
        if (arr[i] < min_num)
            min_num = arr[i];
    }
    return min_num;
}

int main()
{
    int min_ele;
    int a[] = {3, 2, 3, 5, 4, 10};
    int size = sizeof(a) / sizeof(a[0]);
    min_ele = min(a, size);
    printf("Smallest element = %d\n", min_ele);
    return 0;
}
```
<br>

3. Write a function to sort an array of any size. (TSRS)
```
#include <stdio.h>

#define COUNT 5

void sort(int arr[], int size)
{
    int temp;

    for (int j = 0; j < COUNT - 1; j++)
    {
        for (int i = 0; i < COUNT - 1 - j; i++)
        {
            if (arr[i] > arr[i + 1])
            {
                temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1] = temp;
            }
        }
    }
}

int main()
{
    int i, nums[COUNT];
    int size = sizeof(nums) / sizeof(nums[0]);

    printf("Program to sort elements of an array\n");
    
    printf("Enter %d numbers: \n", COUNT);
    for (i = 0; i < COUNT; i++)
        scanf("%d", &nums[i]);
    
    sort(nums, size);

    printf("Sorted array\n");
    printf("------------\n");
    for (i = 0; i < COUNT; i++)
        printf("%d\t", nums[i]);
    
    
    return 0;
}

```
<br>

5. Write a function to find the first occurrence of adjacent duplicate values in the array. Function has to return the value of the element.
```
#include <stdio.h>
#include <stdbool.h>

int adj_duplicates(int arr[], int size)
{
    /* Returns index of duplicate adjacent element if exists, else return -1 */
    for (int i = 0; i < size - 1; i++)
    {
        if (arr[i] == arr[i + 1])
        {
            return i;
        }
    }
    return -1;
    
}

int main()
{
    int n , idx;
    printf("Program to print element of first occurrence of adjacent duplicates in n elements array\n");
    printf("Enter n: \n");
    scanf("%d", &n);
    int nums[6] = {0, 0, 3, 4, 4, 5};

    printf("Enter %d numbers: \n", n);
    for (int i = 0; i < n; i++)
        scanf("%d", &nums[i]);
    
    idx = adj_duplicates(nums, n);

    if (idx != -1)
        printf("First occured adjascent duplicate element = %d\n", nums[idx]);
    else 
        printf("No adjacent duplicates\n");
    
    return 0;
}

```
<br>

6. Write a function in C to read n number of values in an array and display it in reverse order.
```
#include <stdio.h>

void print_reverse(int arr[], int n)
{
    printf("Elements in reverse order\n");
    for (int i = n - 1; i >= 0; i--)
    {
        printf("%d\t", arr[i]);
    }
}

int main()
{
    int n;
    printf("program to read n number of values and display it in reverse order\n");
    printf("Enter n: ");
    scanf("%d", &n);
    int nums[n];
    printf("Enter %d numbers: \n", n);
    for (int i = 0; i < n; i++)
        scanf("%d", &nums[i]);

    print_reverse(nums, n);

    return 0;
}
```
<br>
