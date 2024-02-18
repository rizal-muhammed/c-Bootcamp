# Operators in C Language

1. Write a program to print unit digit of a given number
```
#include <stdio.h>

int main()
{
    int num;
    printf("Enter your number : \n");
    scanf("%d", &num);

    int unit_digit = num % 10;

    printf("Unit digit of %d is %d\n", num, unit_digit);
    return 0;
}
```

2. Write a program to print a given number without its last digit.
```
#include <stdio.h>

int main()
{
    int num, result;
    printf("Enter your number : \n");
    scanf("%d", &num);

    result = num;
    result -= (num % 10); // subtracting unit digit.
    result /= 10; // integer division by 10.
    printf("The number %d without last digit is %d.\n", num, result);
    return 0;
}
```

3. Write a program to swap values of two int variables
```
#include <stdio.h>

int main()
{
    int a, b, temp;
    printf("Enter two integers followed by space : \n");
    scanf("%d %d", &a, &b);
    printf("Before swapping : %d, %d\n", a, b);

    // swapping
    temp = a;
    a = b;
    b = temp;
    
    printf("After swapping: %d, %d\n", a, b);

    return 0;
}
```

4. Write a program to swap values of two int variables without using a third variable.
```
#include <stdio.h>

int main()
{
    int a, b;
    printf("Enter two numbers separated by space : \n");
    scanf("%d %d", &a, &b);

    a = (a ^ b); // bitwise XOR
    b = (a ^ b); // bitwise XOR
    a = (a ^ b); // bitwise XOR

    printf("%d, %d\n", a, b);
    return 0;
}
```

5. Write a program to input a three-digit number and display the sum of the digits.
```
#include <stdio.h>

int main()
{
    int num, a, b, temp;
    printf("Enter your three digit number : \n");
    scanf("%d", &num);
    temp = num;

    a = num % 10; // Extracting unit digit
    num /= 10; // Dropping unit digit
    b = num % 10; // Extracting 10th place digit
    num /= 10; // Dropping 10th place digit
    // Now the num variable will contain 100th place digit

    printf("The sum of %d is %d.\n", temp, a + b + num);

    return 0;
}

```

6. Write a program which takes a character as an input and displays its ASCII code.
```
#include <stdio.h>

int main()
{
    char ch;
    int ascii_val;
    printf("Enter your character : \n");
    scanf("%1c", &ch);

    ascii_val = (int)ch; // converting to int to get the ascii value
    printf("The ASCII value of %1c is %d.\n", ch, ascii_val);

    return 0;
}
```

8. Write a program to check whether the given number is even or odd using a bitwise
operator.
```
#include <stdio.h>


int main()
{
    int num;
    printf("Enter your number to check whether odd or even : \n");
    scanf("%d", &num);
    
    /*If the number is odd, then the correponding binary representation
    will end with 1.
    To check whether a number's binary end with 1, we can perform bitwise AND operation
    and check whether it is equal to 1.*/
    if (num == 0) // Excluding 0, since 0 is neither odd nor even.
        printf("%d is Zero, neither odd nor even.\n", num);
    else if ((num & 1) == 1) // perform bitwise AND check whether equal to 1
        printf("%d is Odd.\n", num);
    else
        printf("%d is Even.\n", num);
}
```


10. Write a program to print size of an int, a float, a char and a double type variable
```
#include <stdio.h>

int main()
{
    int a;
    float b;
    char c;
    double d;
    printf("The size of int variable is %lu bytes.\n", sizeof(a));
    printf("The size of float variable is %lu bytes.\n", sizeof(b));
    printf("The size of char variable is %lu bytes.\n", sizeof(c));
    printf("The size of double variable is %lu bytes.\n", sizeof(d));

    return 0;
}

```

10. Write a program to make the last digit of a number stored in a variable as zero.
(Example - if x=2345 then make it x=2340)
```
#include <stdio.h>

int main()
{
    int num, result;
    printf("Enter your number : \n");
    scanf("%d", &num);

    result = num;
    result -= (num % 10); // subtracting unit digit.
    printf("The number %d is transformed into %d.\n", num, result);
    return 0;
}

```

11. Write a program to input a number from the user and also input a digit. Append a
digit in the number and print the resulting number. (Example - number=234 and
digit=9 then the resulting number is 2349)
```
#include <stdio.h>

int main()
{
    int num, digit, result;
    printf("Enter your number : \n");
    scanf("%d", &num);

    printf("Enter your digit to append : \n");
    scanf("%1d", &digit);

    printf("---------------------\n");
    printf("The number is %d.\n", num);
    printf("The digit is %d.\n", digit);

    printf("Appending digit %d to number %d...\n", digit, num);
    result = (num * 10) + digit; // multiplying by 10 and adding digit.

    printf("The resultant of appending digit %d to number %d is %d.\n", digit, num, result);
    return 0;
}
```

12. Assume price of 1 USD is INR 76.23. Write a program to take the amount in INR and
convert it into USD.
```
#include <stdio.h>
#define FACTOR 76.23

int main()
{
    float inr, usd;
    printf("Enter your money in INR : \n");
    scanf("%f", &inr);

    printf("------------------\n");
    usd = inr / FACTOR;
    printf("%.2f INR is equivalent to %.2f USD.\n", inr, usd);
    return 0;
}
```
