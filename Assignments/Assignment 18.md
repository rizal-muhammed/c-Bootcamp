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

4. Write a function to transform string into uppercase
```
#include <stdio.h>

#define MAX_LENGTH 100

void input(char string[MAX_LENGTH]);
int string_len(char string[MAX_LENGTH]);
void upper(char string[MAX_LENGTH]);

void upper(char string[MAX_LENGTH])
{
    int i;
    for (i = 0; string[i]; i++)
    {
        if (string[i] >= 'a' && string[i] <= 'z')
            string[i] -= 'a' - 'A';
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

    printf("Program to transform given string into uppercase\n");
    input(string);
    upper(string);
    printf("Upper case string\n");
    printf("-----------------\n");
    printf("%s\n", string);
    return 0;
}
```
<br>

5. Write a function to transform a string into lowercase
```
#include <stdio.h>

#define MAX_LENGTH 100

void input(char string[MAX_LENGTH]);
int string_len(char string[MAX_LENGTH]);
void lower(char string[MAX_LENGTH]);

void lower(char string[MAX_LENGTH])
{
    int i;
    for (i = 0; string[i]; i++)
    {
        if (string[i] >= 'A' && string[i] <= 'Z')
            string[i] += 'a' - 'A';
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

    printf("Program to transform given string into uppercase\n");
    input(string);
    lower(string);
    printf("Lower case string\n");
    printf("-----------------\n");
    printf("%s\n", string);
    return 0;
}
```
<br>

6. Write a function to check whether a given string is an alphanumeric string or not. (Alphanumeric string must contain at least one alphabet and one digit)
```
#include <stdio.h>
#include <stdbool.h>

#define MAX_LENGTH 100

void input(char string[MAX_LENGTH]);
int string_len(char string[MAX_LENGTH]);
bool is_alphanumeric(char string[MAX_LENGTH]);

bool is_alphanumeric(char string[MAX_LENGTH])
{
    int i;
    bool alpha = false, numerical = false;

    for (i = 0; string[i]; i++)
    {
        if (string[i] >= '0' && string[i] <= '9')
            numerical = true;
        if ((string[i] >= 'A' && string[i] <= 'Z') ||
            (string[i] >= 'a' && string[i] <= 'z'))
            alpha = true;
    }
    return alpha & numerical;
    
}

int string_len(char string[MAX_LENGTH])
{
    int len;
    for(len = 0; string[len]; len++);
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
    printf("Program to check whether a given string is alphanumeric string or not\n");
    input(string);
    if (is_alphanumeric(string))
        printf("Given string is alphanumeric\n");
    else
        printf("Given string is not alphanumeric\n");
    return 0;
}
```
<br>

7. Write a function to check whether a given string is palindrome or not.
```
#include <stdio.h>
#include <stdbool.h>

#define MAX_LENGTH 100

void input(char string[MAX_LENGTH]);
int string_len(char string[MAX_LENGTH]);
bool is_palindrome(char string[MAX_LENGTH]);

bool is_palindrome(char string[MAX_LENGTH])
{
    bool palindrome = false;
    int i, j;
    for (i = 0, j = string_len(string) - 1; i <= j; i++, j--)
    {
        if (string[i] != string[j])
            return palindrome;
    }
    return palindrome = true;
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
    printf("Program to check whether a given string is palindrom or not\n");
    input(string);
    if(is_palindrome(string))
        printf("The given string is palindrome\n");
    else
        printf("The given string is not palindrome\n");
    return 0;
}
```
<br>

8. Write a function to count words in a given string
```
#include <stdio.h>
#include <stdbool.h>

#define MAX_LENGTH 100

void input(char string[MAX_LENGTH]);
int string_len(char string[MAX_LENGTH]);
int count_words(char string[MAX_LENGTH]);

int count_words(char string[MAX_LENGTH])
{
    int word_count = 0;
    bool in_word = false;

    for (int i = 0; string[i]; i++)
    {
        if (i == 0 && string[i] != ' ')
            word_count++;
        
       if (string[i] == ' ')
            word_count++;
    }
    return word_count;
    
}

int string_len(char string[MAX_LENGTH])
{
    int len;
    for (len = 0; string[len]; len++);
    return len;
}

void input(char string[MAX_LENGTH])
{
    printf("Enter sentence: ");
    if (fgets(string, MAX_LENGTH, stdin) != NULL)
    {
        if (string[string_len(string) - 1] == '\n')
            string[string_len(string) - 1] = '\0';
    }
}

int main()
{
    char string[MAX_LENGTH];
    int word_count;
    printf("Program to print count of words in a given string\n");
    input(string);
    word_count = count_words(string);
    printf("Word count = %d\n", word_count);

    return 0;
}
```
<br>

9. Write a function to reverse a string word wise. (For example if the given string is “Mysirg Education Services” then the resulting string should be “Services Education Mysirg” )
```
#include <stdio.h>
#include <string.h>

#define MAX_LENGTH 1000

void reverse(char string[MAX_LENGTH]);
void reverse_string(char string[MAX_LENGTH]);
void input(char string[MAX_LENGTH]);

void reverse_string(char string[MAX_LENGTH])
{
    int i, j;
    char temp;
    for (i = 0, j = strlen(string) - 1; i <= j; i++, j--)
    {
        temp = string[i];
        string[i] = string[j];
        string[j] = temp;
    }
    
}

void reverse(char string[MAX_LENGTH])
{
    int i, j = 0, k, l;
    char temp[MAX_LENGTH];
    temp[strlen(string)] = '\0';

    for (i = 0; string[i]; i++)
    {
        if (string[i - 1] == ' ')
            j = i;
        if (string[i + 1] == '\0' || string[i + 1] == ' ')
        {

            for (k = i, l = j; l <= k; k--, j++)
            {
                temp[j] = string[k];
            }
            if (string[i + 1] == ' ')
                temp[i+1] = ' ';
            
        }
    }
    strcpy(string, temp);
    reverse_string(string);
    printf("Reversed string\n");
    printf("---------------\n");
    printf("%s\n", string);
    
}

void input(char string[MAX_LENGTH])
{
    printf("Enter sentence: ");
    if (fgets(string, MAX_LENGTH, stdin) != NULL)
    {
        if (string[strlen(string) - 1] == '\n')
            string[strlen(string) - 1] = '\0';
    }
}


int main()
{
    char string[MAX_LENGTH] = {"My name is Sachin"};
    printf("Program to reverse given string in a specific way\n");
    input(string);
    reverse(string);

    return 0;
}
```
<br>

10. Write a function to find the repeated character in a given string.
```
#include <stdio.h>
#include <stdbool.h>

#define MAX_LENGTH 100

void input(char string[MAX_LENGTH]);
int string_len(char string[MAX_LENGTH]);
void print_repeated_characters(char string[MAX_LENGTH]);

void print_repeated_characters(char string[MAX_LENGTH])
{
    char frequency[256] = {0};
    for (int i = 0; string[i]; i++)
    {
        frequency[string[i]]++;
    }

    printf("Repeated characters: \n");
    for (int j = 0; j < sizeof(frequency) / sizeof(frequency[0]); j++)
    {
        if (frequency[j] > 1)
            printf("%c ", j);        
    }
    printf("\n");
    
    
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
    printf("Program to find the repeated characters in a given sentence\n");
    input(string);
    print_repeated_characters(string);
    return 0;
}
```
<br>

