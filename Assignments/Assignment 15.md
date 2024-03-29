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

4. Write a function to rotate an array by n position in d direction. The d is an indicative value for left or right. (For example, if array of size 5 is [32, 29, 40, 12, 70]; n is 2 and d is left, then the resulting array after left rotation 2 times is [40, 12, 70, 32, 29] )
```
#include <stdio.h>
#include <stdbool.h>
#include <string.h>

void rotate_array(int a[], int, int, int);
void rotate_left(int a[], int);
void rotate_right(int a[], int);

void rotate_array(int a[], int n, int d, int size)
{
    if (d == -1)
    {
        for (int i = 0; i < n; i++)
        {
            rotate_left(a, size); 
        }
    }
    else if (d == 1)
    {
        for (int i = 0; i < n; i++)
        {
            rotate_right(a, size); 
        }
    }
}

void rotate_left(int a[], int size)
{
    int j = 0;
    int temp = a[j];
    for (int i = 1; i < size; i++, j++)
    {
        a[j] = a[i];
    }
    a[j] = temp;
}

void rotate_right(int a[], int size)
{
    int i = size, j = size - 1;
    int temp = a[j];
    for (; i > 0; i--, j--)
    {
        a[i] = a[j];
    }
    a[i] = temp;
}

int main()
{
    printf("Program to rotate an array by n positions in d direction\n");
    int arr[] = {32, 29, 40, 12, 70, 34, 22, 10};
    int n, d = 0; 
    char direction[6];
    int size = sizeof(arr) / sizeof(arr[0]);

    printf("Enter n: ");
    if (scanf("%d", &n) != 1)
    {
        printf("Invalid input\n");
        return 1;
    }
    while (getchar() != '\n');

    printf("Enter direction: 'left' or 'right' :  ");
    fflush (stdout);
    fgets(direction, sizeof(direction), stdin);
    direction[strcspn(direction, "\n")] = '\0'; 
    puts(direction);
    if (strcmp(direction, "left") == 0)
        d = -1;
    else if (strcmp(direction, "right") == 0)
        d = 1;
    else
    {
        printf("Invalid input\n");
        return 1;
    }
    
    rotate_array(arr, n, d, size);

    for (int i = 0; i < size; i++)
    {
        printf("%d\t", arr[i]);
    }
    
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

7. Write a function in C to count a total number of duplicate elements in an array.
```
#include <stdio.h>
#include <stdbool.h>

void print_frequency(int a[], int);

void print_frequency(int a[], int size)
{
    int new_max;
    /* Finding max */
    int max = a[0];

    for (int i = 1; i < size; i++)
    {
        if (a[i] > max)
            max = a[i];
    }

    /* Finding min */
    int min = a[0];

    for (int i = 0; i < size; i++)
    {
        if (a[i] < min)
            min = a[i];
    }

    if (min < 0)
        new_max = (max + 1) + (-1 * min);
    else
        new_max = max;

    int frequency[new_max];
    /* Initializing frequency array with 0 */
    for (int i = 0; i < new_max; i++)
        frequency[i] = 0;
    
    for (int i = 0; i < size; i++)
    {
        if (a[i] < 0)
            frequency[max + (-1 * a[i])]++;
        else
            frequency[a[i]]++;
    }
    
    /* Printing frequency if not 0 */
    printf("Element\t| Frequency\n");
    printf("-------\t  ----------\n");
    for (int i = 0; i < new_max; i++)
    {
        if (frequency[i] == 2)
            if (i > max)
                printf("%d\t|\t%d\n", -1 * (i - max), frequency[i]);
            else
                printf("%d\t|\t%d\n", i, frequency[i]);
    }    
    printf("\n");
}

int main()
{
    int arr[] = {3, 4, 3, 4, 5, 34, 23, 4, 100, 101, -10, -10, -5, -5, -5, -3, 0};
    printf("Program to count total number of duplcate elements in an array(meaning frequency = 2)\n");
    int size = sizeof(arr) / sizeof(arr[0]);

    printf("The elements of array are: \n");
    for (int i = 0; i < size; i++)
        printf("%d\t", arr[i]);
    printf("\n\n");
    
    print_frequency(arr, size);
    
    return 0;
}
```
<br>

8. Write a function in C to print all unique elements in an array.
```
#include <stdio.h>
#include <stdbool.h>

void print_unique(int a[], int);

void print_unique(int arr[], int size)
{
    for (int i = 0; i < size; i++)
    {
        bool unique = true;
        for (int j = 0; j < size; j++)
        {
            if (i != j && arr[i] == arr[j])
            {
                unique = false;
                break;
            }
        }
        if (unique)
        {
            printf("%d\t", arr[i]);
        }
    }
    
}

int main()
{
    int arr[] = {1, 2, 23, 2, 1, 3, 4, 5, 6, 6};
    int size = sizeof(arr) / sizeof(arr[0]);
    
    printf("\nProgram to print unique elements in an array\n\n");

    printf("The array is : \n");
    for (int i = 0; i < size; i++)
        printf("%d\t", arr[i]);
    
    printf("\n\n");
    printf("The unique elements are : \n");
    print_unique(arr, size);
    printf("\n");

    return 0;
}

```
<br>

```
#include <stdio.h>
#include <stdbool.h>

void print_frequency(int a[], int);

void print_frequency(int a[], int size)
{
    int new_max;
    /* Finding max */
    int max = a[0];

    for (int i = 1; i < size; i++)
    {
        if (a[i] > max)
            max = a[i];
    }

    /* Finding min */
    int min = a[0];

    for (int i = 0; i < size; i++)
    {
        if (a[i] < min)
            min = a[i];
    }

    if (min < 0)
        new_max = (max + 1) + (-1 * min);
    else
        new_max = max;

    int frequency[new_max];
    /* Initializing frequency array with 0 */
    for (int i = 0; i < new_max; i++)
        frequency[i] = 0;
    
    for (int i = 0; i < size; i++)
    {
        if (a[i] < 0)
            frequency[max + (-1 * a[i])]++;
        else
            frequency[a[i]]++;
    }
    
    /* Printing frequency if not 0 */
    printf("Unique elements\n");
    printf("---------------\n");
    for (int i = 0; i < new_max; i++)
    {
        if (frequency[i] == 1)
            if (i > max)
                printf("%d\t", -1 * (i - max));
            else
                printf("%d\t", i);
    }    
    printf("\n");
}

int main()
{
    int arr[] = {3, 4, 3, 4, 5, 34, 23, 4, 100, 101, -10, -10, -5, -5, -5, -3, 0};
    printf("Program to count the frequency of each element of an array\n");
    int size = sizeof(arr) / sizeof(arr[0]);

    printf("The elements of array are: \n");
    for (int i = 0; i < size; i++)
        printf("%d\t", arr[i]);
    printf("\n\n");
    
    print_frequency(arr, size);
    
    return 0;
}
```

9. Write a function in C to merge two arrays of the same size sorted in descending order.
```
#include <stdio.h>

void merge(int a[], int b[], int c[], int, int, int);

void merge(int a[], int b[], int c[], int size1, int size2, int size3)
{
    int i, j = 0;
    for (int k = 0; k < size3; k++)
    {
        if (a[i] < b[j])
        {
            c[k] = b[j];
            j++;
        }
        else
        {
            c[k] = a[i];
            i++;
        }
    }
    
}

int main()
{
    printf("Program to merge two arrays of same size sorted in descending order\n");

    int arr1[] = {10, 3, 1, 1, 1};
    int arr2[] = {5, 4, 3, 2, 2};
    int size1 = sizeof(arr1) / sizeof(arr1[0]), size2 = sizeof(arr2) / sizeof(arr2[0]);
    int size3 = size1 + size2;
    int arr3[size3];

    merge(arr1, arr2, arr3, size1, size2, size3);

    printf("Elements of array 1 are : \n");
    for (int i = 0; i < size1; i++)
        printf("%d\t", arr1[i]);
    printf("\n");

    printf("Elements of array 2 are : \n");
    for (int i = 0; i < size2; i++)
        printf("%d\t", arr2[i]);
    printf("\n");
    
    printf("Elements of merged array are: \n");
    for (int i = 0; i < size3; i++)
        printf("%d\t", arr3[i]);
    printf("\n");
    
    return 0;
}
```
<br>

10. Write a function in C to count the frequency of each element of an array.
```
#include <stdio.h>
#include <stdbool.h>

void print_frequency(int a[], int);

void print_frequency(int a[], int size)
{
    int new_max;
    /* Finding max */
    int max = a[0];

    for (int i = 1; i < size; i++)
    {
        if (a[i] > max)
            max = a[i];
    }

    /* Finding min */
    int min = a[0];

    for (int i = 0; i < size; i++)
    {
        if (a[i] < min)
            min = a[i];
    }

    if (min < 0)
        new_max = (max + 1) + (-1 * min);
    else
        new_max = max;

    int frequency[new_max];
    /* Initializing frequency array with 0 */
    for (int i = 0; i < new_max; i++)
        frequency[i] = 0;
    
    for (int i = 0; i < size; i++)
    {
        if (a[i] < 0)
            frequency[max + (-1 * a[i])]++;
        else
            frequency[a[i]]++;
    }
    
    /* Printing frequency if not 0 */
    printf("Element\t| Frequency\n");
    printf("-------\t  ----------\n");
    for (int i = 0; i < new_max; i++)
    {
        if (frequency[i] != 0)
            if (i > max)
                printf("%d\t|\t%d\n", -1 * (i - max), frequency[i]);
            else
                printf("%d\t|\t%d\n", i, frequency[i]);
    }    
    printf("\n");
}

int main()
{
    int arr[] = {3, 4, 3, 4, 5, 34, 23, 4, 100, 101, -10, -10, -5, -5, -5, -3, 0};
    printf("Program to count the frequency of each element of an array\n");
    int size = sizeof(arr) / sizeof(arr[0]);

    printf("The elements of array are: \n");
    for (int i = 0; i < size; i++)
        printf("%d\t", arr[i]);
    printf("\n\n");
    
    print_frequency(arr, size);
    
    return 0;
}
```
