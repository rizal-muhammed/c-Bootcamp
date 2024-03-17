# String Basics in C Language

1. Write a program to calculate the length of the string. (without using built-in method)
```
#include <stdio.h>

# define MAX_LENGH 100

int main()
{
    char string [MAX_LENGH];
    int len;
    printf("Program to calculate the length of string\n");

    printf ("Input your string: ");
    fgets(string, MAX_LENGH, stdin);
    printf ("You've entered: %s\n",string);

    for (len = 0; string[len]; len++);
    printf("The length of the string = %d\n", len);

    return 0;
}
```
