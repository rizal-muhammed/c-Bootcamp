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
<br>

2. Write a program to count the occurrence of a given character in a given string.
```
#include <stdio.h>

# define MAX_LENGH 100

int count(char string[], char a_char);

int count(char string[], char a_char)
{
    int count = 0;

    for (int i = 0; string[i]; i++)
    {
        if (string[i] == a_char)
            count++;
    }
    return count;
    
}

int main()
{
    char string [MAX_LENGH], a_char;
    int rc, char_count;
    printf("Program to count the occurence of a given character in a given string\n");

    printf ("Input your string: ");
    fgets(string, MAX_LENGH, stdin);
    rc = fputs(string, stdout);
    if (rc == EOF)
        perror("fputs()");
    printf("\n");

    fflush(stdin);
    printf ("Enter your character: ");
    a_char = getchar();
    getchar(); // for new line

    char_count = count(string, a_char);
    printf("The character '%c' occurs %d times in the above string\n", a_char, char_count);

    return 0;
}
```
<br>

