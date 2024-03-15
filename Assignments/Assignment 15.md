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

