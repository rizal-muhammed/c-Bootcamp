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
            if (j < i)
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

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/ca250ac0-3471-4ffa-b697-3899f6f1908e)
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
        for (int j = 0; j < 2 * rows - 1; j++)
        {
            if (j < rows-1 - i || j > rows-1 + i)
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

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/6e0cb3d0-1e66-4bd3-a3c1-812f287ee3c6)
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
        for (int j = 0; j < 2 * rows - i; j++)
        {
            if (j < i || j > rows - i + 3)
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

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/2e3a6cd2-1a4c-4491-8214-2f7e7cd47104)

```
#include <stdio.h>

int main()
{
    int rows;
    char k;

    printf("Program to print pattern with alphabets\n");

    printf("Enter number of rows: \n");
    scanf("%d", &rows);

    for (int i = 0; i < rows; i++)
    {
        k = 'A';
        for (int j = 0; j < 2 * rows - 1; j++)
        {
            if (j > (rows - 1) - i && j < (rows - 1) + i)
                printf(" ");
            else
                printf("*");
        }
        printf("\n");
    }

    return 0;
}
}
```
<br>

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/a2a6df58-6135-4191-91a2-eaa46469f309)
```
#include <stdio.h>

int main()
{
    int rows;
    int k;
    printf("Program to print number pattern\n");
    printf("Enter number of rows\n");
    scanf("%d", &rows);

    for (int i = 0; i < rows; i++)
    {
        k = 1;
        for (int j = 0; j < 2 * rows - 1; j++)
        {
            if (j < rows-1 - i || j > rows-1 + i)
                printf(" ");
            else if (j < rows - 1)
                printf("%d", k++);
            else if (j == rows - 1)
                printf("%d", k);
            else
                printf("%d", --k);
        }
        printf("\n");
    }
    
    return 0;
}
```
<br>

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/3c481782-9434-46f2-b156-673d65ab9bd0)
```
#include <stdio.h>

int main()
{
    int rows, k;

    printf("Program to print number pattern\n");
    printf("Enter number of rows\n");
    scanf("%d", &rows);

    for (int i = 0; i < rows; i++)
    {
        k = 1;
        for (int j = 0; j < 2 * rows - i - 1; j++)
        {
            if (j < i || j > rows - i + 3)
                printf(" ");
            else if (j < rows - 1)
                printf("%d", k++);
            else if (j == rows - 1)
                printf("%d", k);
            else
                printf("%d", --k);
        }
        printf("\n");
    }

    return 0;
}
```
<br>

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/94e6d34e-d740-4655-862a-b3691700eab8)

```
#include <stdio.h>

int main()
{
    int rows, k;

    printf("Program to print number pattern\n");
    printf("Enter number of rows\n");
    scanf("%d", &rows);

    for (int i = 0; i < rows; i++)
    {
        k = 1;
        for (int j = 0; j < 2 * rows - 1; j++)
        {
            if (j < rows - i || j > rows - 2 + i)
                {
                    if (j < rows - 1)
                        printf("%d", k++);
                    else if (j == rows - 1)
                        printf("%d", k);
                    else
                        printf("%d", --k);
                }
            else
                printf(" ");
        }
        printf("\n");
    }

    return 0;
}
```
<br>

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/3b86feba-9310-42d8-a083-63a3145511d4)
```
#include <stdio.h>

int main()
{
    int rows = 5;
    char k;

    printf("Program to print pattern with alphabets\n");

    printf("Enter number of rows: \n");
    scanf("%d", &rows);

    for (int i = 0; i < rows; i++)
    {
        k = 'A';

        for (int j = 0; j < 2 * rows - 1; j++)
        {
            if (j < rows-1 - i || j > rows-1 + i)
                printf(" ");
            else if (j < rows - 1)
                printf("%c", k++);
            else if (j == rows - 1)
                printf("%c", k);
            else
                printf("%c", --k);
        }
        printf("\n");
    }

    return 0;
}
```
<br>

Pattern 12 <br>
![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/26ca8247-00b0-46a4-a98e-270d4d293025)
```
#include <stdio.h>

int main()
{
    int rows;
    char k;

    printf("Program to print patterns with alphabets\n");
    
    printf("Enter number of rows: \n");
    scanf("%d", &rows);
    
    for (int i = 0; i < rows; i++)
    {
        k = 'A';
        for (int j = 0; j < 2 * rows - 1; j++)
        {
            if (j < i || j > 2 * rows - 2 - i)
                printf(" ");
            else if (j >= i && j < rows - 1)
                printf("%c", k++);
            else if (j == rows - 1)
                printf("%c", k);
            else if (j > rows - 1)
                printf("%c", --k);
        }
        printf("\n");
    }

    return 0;
}
```
<br>

![image](https://github.com/rizal-muhammed/c-Bootcamp/assets/37320039/ca97b7be-77e6-4ae0-a2a9-bbd589506ccc)
```

```


