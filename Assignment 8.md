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
<br>

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/cdcca976-6575-4adb-b8f2-206ff8310d9c)
```
#include <stdio.h>

int main()
{
    int rows;

    printf("Program to print * pattern\n");
    printf("Enter number of rows\n");
    scanf("%d", &rows);

    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < rows; j++)
        {
            if (j < rows - (i + 1))
                printf(" ");
            else 
                printf("*");
        }
        printf("\n");
    }

    return 0;
}

```
<br>

Pattern 3 <br>
![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/0349a2e9-85f1-499f-89f6-488ab70c91e3)
```
#include <stdio.h>

int main()
{
    int rows;

    printf("Program to print * pattern\n");
    printf("Enter number of rows\n");
    scanf("%d", &rows);

    for (int i = 0; i < rows; i++)
    {
        for (int j = 0; j < rows; j++)
        {
            if (j < (rows - i))
                printf("*");
            else 
                printf(" ");
        }
        printf("\n");
    }
    return 0;
}
```
<br>

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/bb1ecb44-7e61-4ca2-90c2-4196ee8dc216)
```

```

