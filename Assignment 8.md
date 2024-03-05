## Pattern Problems
<br>


![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/56a1cf1a-d401-4485-9527-bd202a7f65d8)
```
#include <stdio.h>

int main()
{
    int num;

    printf("Program to print * pattern\n");
    printf("Enter number of rows\n");
    scanf("%d", &num);

    for (int i = 0; i < num; i++)
    {
        for (int j = 0; j <= i; j++)
        {
            printf("*");
        }
        printf("\n");
    }

    return 0;
}
```
