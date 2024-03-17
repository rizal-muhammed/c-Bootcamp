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

3. Write a program to count vowels in a given string
```
#include <stdio.h>

# define MAX_LENGH 100

int vowels_count(char string[]);

int vowels_count(char string[])
{
    int count = 0;

    for (int i = 0; string[i]; i++)
    {
        if (string[i] == 'A' || 
            string[i] == 'E' || 
            string[i] == 'I' || 
            string[i] == 'O' || 
            string[i] == 'U' || 
            string[i] == 'a' ||
            string[i] == 'e' || 
            string[i] == 'i' || 
            string[i] == 'o' || 
            string[i] == 'u' )
            count++;
    }
    return count;
    
}

int main()
{
    char string [MAX_LENGH];
    int rc, count;
    printf("Program to count vowels in a given string\n");

    printf ("Input your string: ");
    fgets(string, MAX_LENGH, stdin);
    rc = fputs(string, stdout);
    if (rc == EOF)
        perror("fputs()");
    printf("\n");

    count = vowels_count(string);
    printf("There are %d vowels in above string\n", count);

    return 0;
}
```
<br>

4. Write a program to convert a given string into uppercase
```
#include <stdio.h>
#include <stdlib.h> 

# define MAX_LENGH 100

void upper(char string[]);

void upper(char string[])
{
    int len_alphabets = 26;

    char lower[26] = {'a'};

    for (int i = 1; i < len_alphabets; i++)
        lower[i] = lower[i - 1] + 1;
    
    for (int i = 0; string[i]; i++)
    {
        for (int j = 0; lower[j]; j++)
        {
            if (string[i] == lower[j])
                string[i] -= abs('a' - 'A');
        }
        
    }
    
}

int main()
{
    char string [MAX_LENGH];
    int rc, count;
    printf("Program to convert a given string into uppercase\n");

    printf ("Input your string: ");
    fgets(string, MAX_LENGH, stdin);
    printf("You've entered: \n");
    rc = fputs(string, stdout);
    if (rc == EOF)
        perror("fputs()");

    upper(string);
    printf("%s\n", string);

    return 0;
}
```
<br>

5. Write a program to convert a given string into lowercase
```
#include <stdio.h>
#include <stdlib.h> 

# define MAX_LENGH 100

void lower(char string[]);

void lower(char string[])
{
    int len_alphabets = 26;

    char lower[26] = {'A'};

    for (int i = 1; i < len_alphabets; i++)
        lower[i] = lower[i - 1] + 1;
    
    for (int i = 0; string[i]; i++)
    {
        for (int j = 0; lower[j]; j++)
        {
            if (string[i] == lower[j])
                string[i] += abs('a' - 'A');
        }
        
    }
    
}

int main()
{
    char string [MAX_LENGH];
    int rc, count;
    printf("Program to convert a given string into lowercase\n");

    printf ("Input your string: ");
    fgets(string, MAX_LENGH, stdin);
    printf("You've entered: \n");
    rc = fputs(string, stdout);
    if (rc == EOF)
        perror("fputs()");

    lower(string);
    printf("%s\n", string);

    return 0;
}
```
<br>

6. Write a program to reverse a string.
```
#include <stdio.h>
#include <string.h>

# define MAX_LENGH 100

void reverse(char string[]);

void reverse(char string[])
{

    for (int i = 0, j = strlen(string) - 1; i <= j; i++, j--)
    {
        char temp = string[i];
        string[i] = string[j];
        string[j] = temp;
    }
    
    
}

int main()
{
    char string [MAX_LENGH];
    int rc, count;
    printf("Program to reverse a given string\n");

    printf ("Input your string: ");
    if (fgets(string, MAX_LENGH, stdin) != NULL)
    {
        int len = strlen(string);
        if (len > 0 && string[len - 1] == '\n')
            string[len - 1] = '\0';
    }
    rc = fputs(string, stdout);
    if (rc == EOF)
        perror("fputs()");
    printf("\n");

    reverse(string);
    printf("\n%s\n", string);

    return 0;
}
```
<br>

7. Write a program in C to count the total number of alphabets, digits and special characters in a string.
```
#include <stdio.h>
#include <string.h>

#define MAX_LENGTH 100

int main()
{
    char string[MAX_LENGTH];
    int num_alphabets = 0, num_digits = 0, num_sp_characters = 0;
    printf("Program to count the total number of alphabets, "
    "digits and special characters in a string\n");

    printf("Enter string: \n");
    if (fgets(string, MAX_LENGTH, stdin) != NULL)
    {
        if (string[strlen(string) - 1] == '\n')
            string[strlen(string) - 1] = '\0';
    }

    for (int i = 0; string[i]; i++)
    {
        if ((string[i] >= 'A' && string[i] <= 'Z') ||
            (string[i] >= 'a' && string[i] <= 'z'))
            num_alphabets++;
        else if(string[i] >= '0' && string[i] <= '9')
            num_digits++;
        else if ((string[i] >= '!' && string[i] <= '/') ||
                 (string[i] >= ':' && string[i] <= '@') ||
                 (string[i] >= '[' && string[i] <= '`') ||
                 (string[i] >= '{' && string[i] <= '~'))
            num_sp_characters++;
    }

    printf("\nThe above string contains\n%d Alphabet(s)\n%d Digit(s)\n%d "
    "Special charater(s)\n", num_alphabets, num_digits, num_sp_characters);
    
}
```
<br>

8. Write a program in C to copy one string to another string.
```
#include <stdio.h>
#include <string.h>

#define MAX_LENGTH 100

int main()
{
    char string[MAX_LENGTH];
    int i;
    printf("Program to copy one string to another string\n");
    printf("Enter string: ");
    if (fgets(string, MAX_LENGTH, stdin) != NULL)
    {
        if (string[strlen(string) - 1] == '\n')
            string[strlen(string)] = '\0';
    }

    printf("You've entered: %s\n", string);
    char copied_string[strlen(string)];
    for (i = 0; i < strlen(string); i++)
    {
        copied_string[i] = string[i];
    }
    copied_string[i] = '\0';

    printf("Copied string: \n");
    printf("%s", copied_string);
    
    return 0;
}
```
<br>


