1. Write a program to print MySirG 5 times on the screen
```
#include <stdio.h>

int main()
{
    for (int i = 0; i < 5; i++)
        printf("MySirG\n");
    return 0;
}
```
2. Write a program to print the first 10 natural numbers.
```
#include <stdio.h>

int main()
{
    printf("First 10 natural numbers.\n");
    printf("-------------------------\n");

    for (int i = 1; i <= 10; i++)
        printf("%d\n", i);

    return 0;
}
```
3. Write a program to print the first 10 natural numbers in reverse order
```
#include <stdio.h>

int main()
{
    printf("First 10 natural numbers in reverse order.\n");
    printf("------------------------------------------\n");

    for (int i = 10; i >= 1; i--)
        printf("%d\n", i);

    return 0;
}
```
4. Write a program to print the first 10 odd natural numbers
```
#include <stdio.h>

int main()
{
    printf("First 10 odd natural numbers.\n");
    printf("-----------------------------\n");

    for (int i = 1; i <= 2*10; i = i+2)
        printf("%d\n", i);

    return 0;
}
```
or
```
#include <stdio.h>

int main()
{
    printf("First 10 odd natural numbers.\n");
    printf("-----------------------------\n");

    for (int i = 1; i <= 2*10; i++)
    {
        if (i%2 == 1)
            printf("%d\n", i);
    }

    return 0;
}
```
5. Write a program to print the first 10 odd natural numbers in reverse order.
```
#include <stdio.h>

int main()
{
    printf("First 10 odd natural numbers in reverse order.\n");
    printf("----------------------------------------------\n");

    for (int i = 2*10 - 1; i >= 1; i = i-2)
        printf("%d\n", i);

    return 0;
}
```
or 
```
#include <stdio.h>

int main()
{
    printf("First 10 odd natural numbers in reverse order.\n");
    printf("----------------------------------------------\n");

    for (int i = 2*10 - 1; i >= 1; i--)
    {
        if (i%2 == 1)
            printf("%d\n", i);
    }

    return 0;
}
```
6. Write a program to print the first 10 even natural numbers
```
#include <stdio.h>

int main()
{
    printf("First 10 even natural numbers.\n");
    printf("------------------------------\n");

    for (int i = 2; i <= 2*10; i = i+2)
        printf("%d\n", i);

    return 0;
}
```
or
```
#include <stdio.h>

int main()
{
    printf("First 10 even natural numbers.\n");
    printf("------------------------------\n");

    for (int i = 2; i <= 2*10; i++)
    {
        if (i%2 == 0)
            printf("%d\n", i);
    }

    return 0;
}
```
7. Write a program to print the first 10 even natural numbers in reverse order
```
#include <stdio.h>

int main()
{
    printf("First 10 even natural numbers in reverse order.\n");
    printf("-----------------------------------------------\n");

    for (int i = 2*10; i >= 2; i = i-2)
        printf("%d\n", i);
    return 0;
}
```
or 
```
#include <stdio.h>

int main()
{
    printf("First 10 even natural numbers in reverse order.\n");
    printf("-----------------------------------------------\n");

    for (int i = 2*10; i >= 2; i--)
    {
        if (i % 2 == 0)
            printf("%d\n", i);
    }
    return 0;
}
```
8. Write a program to print squares of the first 10 natural numbers
```
#include <stdio.h>
#include <math.h>

int main()
{
    printf("Squares of first 10 natural numbers.\n");
    printf("------------------------------------\n");

    for (int i = 1; i <= 10; i++)
        printf("%d\n", (int)(powf(i, 2)));
    return 0;
}
```
9. Write a program to print cubes of the first 10 natural numbers
```
#include <stdio.h>
#include <math.h>

int main()
{
    printf("Cubes of first 10 natural numbers.\n");
    printf("------------------------------------\n");

    for (int i = 1; i <= 10; i++)
        printf("%d\n", (int)(powf(i, 3)));
    return 0;
}
```
10. Write a program to print a table of 5.
```
#include <stdio.h>

int main()
{
    printf("Table of 5\n");
    printf("----------\n");

    for (int i = 1; i <= 10; i++)
        printf("%d x %d = %d\n", i, 5, i * 5);
    return 0;
}

```
