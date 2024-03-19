# Handling multiple Strings in C Language

1. Write a program to find the number of vowels in each of the 5 strings stored in two
dimensional arrays, taken from the user.
```
#include <stdio.h>
#include <string.h>

#define ROWS 5
#define MAX_LEN 1000

void input(char str[ROWS][MAX_LEN]);
void count_vowels(char str[ROWS][MAX_LEN], int freq[ROWS]);
void print_vowels(char str[ROWS][MAX_LEN], int freq[ROWS]);

void print_vowels(char str[ROWS][MAX_LEN], int freq[ROWS])
{
    for (int i = 0; i < ROWS; i++)
    {
        printf("String %d has %d vowels\n", i + 1, freq[i]);
    }
    
}

void count_vowels(char str[ROWS][MAX_LEN], int freq[ROWS])
{
    for (int i = 0; i < ROWS; i++)
    {
        for (int j = 0; str[i][j]; j++)
        {
            if (str[i][j] == 'a' || str[i][j] == 'A' ||
                str[i][j] == 'e' || str[i][j] == 'E' ||
                str[i][j] == 'i' ||str[i][j] == 'I' ||
                str[i][j] == 'o' || str[i][j] == 'O' ||
                str[i][j] == 'u' || str[i][j] == 'U')
                freq[i]++;
        }
        
    }
    print_vowels(str, freq);
    
}

void input(char str[ROWS][MAX_LEN])
{
    for (int i = 0; i < ROWS; i++)
    {
        printf("Enter string %d: ", i + 1);
        if (fgets(str[i], MAX_LEN, stdin) != NULL)
        {
            if (str[i][strlen(str[i]) - 1] == '\n')
                str[i][strlen(str[i]) - 1] = '\0';
        }
    }
    
}

int main()
{
    char string[ROWS][MAX_LEN];
    int frequency[ROWS] = {0};

    printf("Program to find the frequency of vowels in each of the 5 user input strings\n");

    printf("Let's input the strings\n");
    input(string);

    count_vowels(string, frequency);

    return 0;
}
```
<br>

2. Write a program to sort 10 city names stored in two dimensional arrays, taken from the user.
```
#include <stdio.h>
#include <string.h>

#define ROWS 10
#define MAX_LEN 100

void input(char str[][MAX_LEN]);
void sort(char str[][MAX_LEN]);

void sort(char str[][MAX_LEN])
{
    char temp[MAX_LEN];

    for (int i = 0; i < (ROWS - 1); i++)
    {
        for (int j = 0, k = 1; k < (ROWS - i); j++, k++)
        {
            if (strcmp(str[j], str[k]) > 0)
            {
                strcpy(temp, str[j]);
                strcpy(str[j], str[k]);
                strcpy(str[k], temp);
            }
        }
    }
}

void input(char str[][MAX_LEN])
{
    for (int i = 0; i < ROWS; i++)
    {
        printf("Enter city %d: ", i + 1);
        if (fgets(str[i], MAX_LEN, stdin) != NULL)
        {
            if (str[i][strlen(str[i]) - 1] == '\n')
                str[i][strlen(str[i]) - 1] = '\0';
        }
    }
    
}

int main()
{
    char strings[ROWS][MAX_LEN];

    printf("Program to sort %d city names in alphabetical order\n", ROWS);
    printf("Enter %d city names: \n", ROWS);
    printf("No of rows  = %lu\n", sizeof(strings) / sizeof(strings[0]));
    input(strings);
    sort(strings);
    
    printf("\nStrings in sorted order\n");
    for (int i = 0; i < sizeof(strings) / sizeof(strings[0]); i++)
    {
        printf("%s\n", strings[i]);
    }

    return 0;
}
```
<br>

3. Write a program to read and display a 2D array of strings in C language.
```
#include <stdio.h>
#include <string.h>

#define ROWS 5
#define MAX_LEN 1000

void input(char str[ROWS][MAX_LEN]);

void input(char str[ROWS][MAX_LEN])
{
    for (int i = 0; i < ROWS; i++)
    {
        printf("Enter string %d: ", i + 1);
        if (fgets(str[i], MAX_LEN, stdin) != NULL)
        {
            if (str[i][strlen(str[i]) - 1] == '\n')
                str[i][strlen(str[i]) - 1] = '\0';
        }
    }
    
}

int main()
{
    char string[ROWS][MAX_LEN];
    int frequency[ROWS] = {0};

    printf("Program to find the frequency of vowels in each of the 5 user input strings\n");

    printf("Let's input the strings\n");
    input(string);

    printf("\nThe strings are \n");
    printf("---------------\n");
    for (int i = 0; i < ROWS; i++)
    {
        printf("%s\n", string[i]);
    }
    

    return 0;
}
```
<br>

4. Write a program to search a string in the list of strings.
```
#include <stdio.h>
#include <strings.h>

#define ROWS 3
#define MAX_LEN 100

void input(char str[ROWS][MAX_LEN]);
void input_search_string(char search_string[MAX_LEN]);
int search(char str[][MAX_LEN], char search_str[]);
int string_compare(char str1[MAX_LEN], char str2[MAX_LEN]);
int string_len(char str[MAX_LEN]);

int string_len(char str[MAX_LEN])
{
    int len;
    for (len = 0; str[len]; len++);
    return len;
}

int string_compare(char str1[MAX_LEN], char str2[MAX_LEN])
{
    /* returns 1 if both strings are equal */
    int str1_len = string_len(str1);
    int str2_len = string_len(str2);

    for (int i = 0, j = 0; str1_len > str2_len ? str1[i]: str2[j]; i++, j++)
    {
        if (str1[i] != str2[j])
            return 0;
    }
    return 1;

}


int search(char str[][MAX_LEN], char search_str[])
{
    /* returns 1 if the search string is present in strings array */
    for (int i = 0; i < ROWS; i++)
    {
        if (string_compare(str[i], search_str) == 0)
            return 1;
    }
    return 0;
    
}

void input_search_string(char search_string[MAX_LEN])
{
    printf("Enter search string: ");
    if (fgets(search_string, MAX_LEN, stdin) != NULL)
    {
        if (search_string[strlen(search_string) - 1] == '\n')
            search_string[strlen(search_string) - 1] = '\0';
    }
}

void input(char str[ROWS][MAX_LEN])
{
    for (int i = 0; i < ROWS; i++)
    {
        printf("Enter string %d: ", i + 1);
        if (fgets(str[i], MAX_LEN, stdin) != NULL)
        {
            if (str[i][strlen(str[i]) - 1] == '\n')
                str[i][strlen(str[i]) - 1] = '\0';
        }
    }
    
}

int main()
{
    char strings[ROWS][MAX_LEN];
    char search_string[MAX_LEN];

    printf("program to search a string in the list of strings\n");
    input(strings);
    input_search_string(search_string);
    if (search(strings, search_string))
        printf("Search string is found\n");
    else
        printf("Search string doesn't found\n");
    
    return 0;
}
```
<br>

6. Write a program to print the strings which are palindrome in the list of strings.
```
#include <stdio.h>
#include <string.h>

#define ROWS 5
#define MAX_LEN 100

void input(char str[ROWS][MAX_LEN]);
void print_palindromes(char str[ROWS][MAX_LEN]);

void print_palindromes(char str[ROWS][MAX_LEN])
{
    int is_palindrome[ROWS];
    for (int i = 0; i < sizeof(is_palindrome) / sizeof(is_palindrome[0]); i++)
        is_palindrome[i] = 1;

    for (int i = 0; i < ROWS; i++)
    {
        for (int j = 0, k = strlen(str[i]) - 1; j <= k; j++, k--)
        {
            if (str[i][j] != str[i][k])
            {
                is_palindrome[i] = 0;
                break;
            }
        }
    }

    for (int i = 0; i < ROWS; i++)
    {
        if (is_palindrome[i]== 1)
            printf("%s\n", str[i]);
    }
    
    
}

void input(char str[ROWS][MAX_LEN])
{
    for (int i = 0; i < ROWS; i++)
    {
        printf("Enter string %d: ", i + 1);
        if (fgets(str[i], MAX_LEN, stdin) != NULL)
        {
            if (str[i][strlen(str[i]) - 1] == '\n')
                str[i][strlen(str[i]) - 1] = '\0';
        }
    }
    
}

int main()
{
    char string[ROWS][MAX_LEN] = {"sachin", "malayalam", "hi", "hello", "aba"};
    printf("Program to print palindrome strings\n");

    printf("Let's input the strings\n");
    input(string);

    printf("\nPalindromes are\n");
    printf("---------------\n");
    print_palindromes(string);
    return 0;
}
```
<br>

