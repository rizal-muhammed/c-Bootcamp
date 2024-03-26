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

5. Suppose we have a list of email addresses, check whether all email addresses have ‘@’ in it. Print the odd email out.
```
#include <stdio.h>
#include <string.h>

#define ROWS 5
#define MAX_LEN 100
#define SPECIAL_CHAR '@'

void input(char str[][MAX_LEN]);
void print_odd_emails_out(char strings[][MAX_LEN]);
int contains_sp_char(char string[MAX_LEN], char sp_char);

int contains_sp_char(char string[MAX_LEN], char sp_char)
{
    for (int i = 0; string[i]; i++)
    {
        if (string[i] == sp_char)
            return 1;
    }
    return 0;
    
}

void print_odd_emails_out(char strings[][MAX_LEN])
{
    for (int i = 0; i < ROWS; i++)
    {
        if (!contains_sp_char(strings[i], SPECIAL_CHAR))
            printf("%s\n", strings[i]);
    }
    
}

void input(char str[][MAX_LEN])
{
    for (int i = 0; i < ROWS; i++)
    {
        printf("Enter email %d: ", i + 1);
        if (fgets(str[i], MAX_LEN, stdin) != NULL)
        {
            if (str[i][strlen(str[i]) - 1] == '\n')
                str[i][strlen(str[i]) - 1] = '\0';
        }
    }
    
}

int main()
{
    char emails[ROWS][MAX_LEN];

    printf("Program to print odd emails out\n");
    input(emails);

    printf("\nOdd emails out: \n");
    print_odd_emails_out(emails);

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

7. From the list of IP addresses, check whether all ip addresses are valid.
```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

#define MAX_LENGTH 20

int main()
{
    char ip[] = {"127.0.0.1"};
    char temp[MAX_LENGTH];
    strcpy(temp, ip);
    char * pch;
    int int_pch, flag = 1, i = 0;
    pch = strtok(temp, ".");
    while (pch != NULL)
    {
        i++;
        int_pch = atoi(pch);
        if (!(int_pch >= 0 && int_pch <= 255))
        {
            flag = 0;
            break;
        }
        pch = strtok(NULL, ".");
    }
    if ((flag == 1) && (i == 4))
        printf("IP address %s is valid\n", ip);
    else
        printf("IP addresss %s is not valid\n", ip);
    
    return 0;
}
```
<br>

8. Given a list of words followed by two words, the task is to find the minimum distance
between the given two words in the list of words.
(Example : s = {“the”,”quick”,”brown”,”fox”,”quick”}
word1 = “the”, word2 = “fox”, OUTPUT : 1 )
```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

#define MAX_LENGTH 100

int minimum_distance(char words[][MAX_LENGTH], size_t n, char word1[], char word2[]);
void input(char word1[], char word2[]);

void input(char word1[], char word2[])
{
    printf("Enter word 1: ");
    if (fgets(word1, MAX_LENGTH, stdin) != NULL)
    {
        if (word1[strlen(word1) - 1] == '\n')
            word1[strlen(word1) - 1] = '\0';
    }

    printf("Enter word 2: ");
    if (fgets(word2, MAX_LENGTH, stdin) != NULL)
    {
        if (word2[strlen(word2) - 1] == '\n')
            word2[strlen(word2) - 1] = '\0';
    }
}

int minimum_distance(char words[][MAX_LENGTH], size_t n, char word1[], char word2[])
{
    int w1_idx = -1, w2_idx = -1;
    int min_dist = 9999;

    for (int i = 0; i < n; i++)
    {
        if (strcmp(words[i], word1) == 0)
            w1_idx = i;
        if (strcmp(words[i], word2) == 0)
            w2_idx = i;
    }

    if (w1_idx != -1 && w2_idx != -1)
    {
        for (int i = 0; word1[i] != '\0'; i++)
        {
            for (int j = 0; word2[j] != '\0'; j++)
            {
                if (abs(word1[i] - word2[j]) < min_dist)
                    min_dist = abs(word1[i] - word2[j]);
            }
            
        }
        
        return min_dist;
    }
    
    return 0;
}

int main()
{
    char words[][MAX_LENGTH] = {"the", "quick", "brown", "fox"};
    char word1[MAX_LENGTH], word2[MAX_LENGTH];
    size_t n = sizeof(words) / sizeof(words[0]);
    int min_dist;

    printf("Program to find the minimum distance between two given words\n");
    input(word1, word2);
    min_dist = minimum_distance(words, n, word1, word2);
    if (min_dist)
        printf("The minimum distance between %s and %s is %d\n", word1, word2, min_dist);
    else
        printf("One or more words entered doesn't exists in the list\n");

    return 0;
}
```
<br>

9. Write a program that asks the user to enter a username. If the username entered is one of the names in the list then the user is allowed to calculate the factorial of a number. Otherwise, an error message is displayed
```
#include <stdio.h>
#include <string.h>

#define ROWS 5
#define MAX_LEN 100

int get_factorial(char strings[][MAX_LEN], char string[MAX_LEN]);
int factorial(int n);

int factorial(int n)
{

    if (n == 0 || n == 1)
        return 1;
    if (n > 1)
        return n * factorial(n - 1);
    return 0;
}

int get_factorial(char strings[][MAX_LEN], char string[MAX_LEN])
{
    int N, fact;

    for (int i = 0; i < ROWS; i++)
    {
        if (strcmp(strings[i], string) == 0)
        {
            printf("Authentication successful\n");
            printf("Enter N: ");
            scanf("%d", &N);
            fact = factorial(N);
            return fact;
        }
    }

    printf("User not found\n");
    return 0;
    
}

int main()
{
    char usernames[ROWS][MAX_LEN] = {"john_doe", "jane_smith", "chris_taylor", "amanda_green", "emily_jones"};
    char username[MAX_LEN];
    int fact;

    printf("Program to calculate factorial of a given number N\n");
    printf("Enter your username: \n");

    if (fgets(username, MAX_LEN, stdin) != NULL)
    {
        if (username[strlen(username) - 1] == '\n')
            username[strlen(username) - 1] = '\0';
    }

    fact = get_factorial(usernames, username);
    if (fact != 0)
        printf("%d\n", fact);

    return 0;
}
```
<br>

10. Create an authentication system. It should be menu driven.
```
#include <stdio.h>
#include <string.h>

#define MAX_USERS 5
#define MAX_LENGTH 100

char usernames[MAX_USERS][MAX_LENGTH] = {"AlexAdventures", 
                                        "JakeJourneyman", 
                                        "EthanExpedition",
                                        "LiamWanderer",
                                        "OliviaOdyssey"};
char passwords[MAX_USERS][MAX_LENGTH] = {"Password", 
                                        "12345678", 
                                        "welcome",
                                        "monkey",
                                        "football"};

void login();

void login()
{
    char user[MAX_LENGTH], password[MAX_LENGTH];
    int flag = 0;

    printf("Welcome\n");
    printf("Enter Username: ");
    if (fgets(user, MAX_LENGTH, stdin) != NULL)
    {
        if (user[strlen(user) - 1] == '\n')
            user[strlen(user) - 1] = '\0';
    }

    printf("Enter Password: ");
    if (fgets(password, MAX_LENGTH, stdin) != NULL)
    {
        if (password[strlen(password) - 1] == '\n')
            password[strlen(password) - 1] = '\0';
    }

    for (int i = 0; i < MAX_USERS; i++)
    {
        if (strcmp(usernames[i], user) == 0 && strcmp(passwords[i], password) == 0)
        {
            printf("Welcome, %s\n", user);
            return;
        }
    }

    printf("User not found\n");
    
}

int main()
{
    login();
    return 0;
}
```
<br>

