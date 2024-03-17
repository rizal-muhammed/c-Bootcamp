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

2. Write a function to reverse a string.
```
#include <stdio.h>

#define MAX_LENGTH 100

void input(char string[MAX_LENGTH]);
int string_len(char string[MAX_LENGTH]);
void reverse_string(char string[MAX_LENGTH]);

void reverse_string(char string[MAX_LENGTH])
{
    int i, j;
    char temp;
    for (i = 0, j = string_len(string) - 1; i <= j; i++, j--)
    {
        temp = string[i];
        string[i] = string[j];
        string[j] = temp;
    }
    
}

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
    char string[MAX_LENGTH];
    printf("Program to reverse a string\n");
    input(string);
    reverse_string(string);
    printf("Reversed string\n");
    printf("---------------\n");
    printf("%s\n", string);
    return 0;
}
```
<br>

3. Write a function to compare two strings.
```
#include <stdio.h>

#define MAX_LENGTH 100

void input(char string[MAX_LENGTH]);
int string_len(char string[MAX_LENGTH]);
int compare(char str1[MAX_LENGTH], char str2[MAX_LENGTH]);
char lower(char a_char);

char lower(char a_char)
{
    if (a_char >= 'A' && a_char <= 'Z')
        return a_char + 'a' - 'A';
    return a_char;
}

int compare(char str1[MAX_LENGTH], char str2[MAX_LENGTH])
{
    int i, j;
    for (i = 0, j = 0; str1[i] || str2[j]; i++, j++)
    {
        if (lower(str1[i]) > lower(str2[j]))
            return lower(str1[i]) - lower(str2[j]);
        else
            break;
    }
    return 0;
}

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
    char str1[MAX_LENGTH], str2[MAX_LENGTH];
    printf("Program to compare two strings\n");
    printf("Enter two strings\n");
    printf("Enter string 1: ");
    input(str1);
    printf("Enter string 2: ");
    input(str2);
    printf("Strings in alphabetical order\n");
    printf("-----------------------------\n");
    if (compare(str1, str2))
    {
        printf("%s\n", str2);
        printf("%s\n", str1);
    }
    else
    {
        printf("%s\n", str1);
        printf("%s\n", str2);
    }
    return 0;

}
```
<br>


