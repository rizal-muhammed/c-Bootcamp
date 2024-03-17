# String and Functions in C Language


1. Write a function to calculate length of the string
```
#include <stdio.h>

#define MAX_LENGTH 100

void input(char string[MAX_LENGTH]);
int string_len(char string[MAX_LENGTH]);

int string_len(char string[MAX_LENGTH])
{
    int len;
    for (len = 0; string[len]; len++);
    return len;
}

void input(char string[MAX_LENGTH])
{
    printf("Enter string: ");
    if (fgets(string, MAX_LENGTH, stdin) != NULL)
    {
        if (string[string_len(string) - 1] == '\n')
            string[string_len(string) - 1] = '\0';
    }
}

int main()
{
    char string[MAX_LENGTH], len;
    printf("Program to calculate length of given string\n");
    input(string);
    len = string_len(string);
    printf("String has %d characters\n", len);
    return 0;

}
```
<br>

