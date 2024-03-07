1. Write a program to check whether a given number is positive or non-positive.
```
#include <stdio.h>

int main()
{
    int num;
    printf("Enter your number: \n");
    scanf("%d", &num);

    if (num > 0)
        printf("The number %d is positive.\n", num);
    else    
        printf("The number %d is non positive.\n", num);
    
    return 0;
}
```

2. Write a program to check whether a given number is divisible by 5 or not
```
#include <stdio.h>

int main()
{
    int num;
    printf("Enter your number: \n");
    scanf("%d", &num);

    if (num%5 == 0)
        printf("%d is divisible by 5.\n", num);
    else
        printf("%d is not divisible by 5.\n", num);
    return 0;
}
```

3. Write a program to check whether a given number is an even number or an odd
number.
```
#include <stdio.h>

int main()
{
    int num;
    printf("Enter your number: \n");
    scanf("%d", &num);

    if (num == 0)
        printf("You've entered Zero.\n");
    else if (num%2 == 0)
        printf("%d is even.\n", num);
    else
        printf("%d is odd.\n", num);
    
    return 0;
}
```

4. Write a program to check whether a given number is an even number or an odd
number without using % operator.
```
#include <stdio.h>

int main()
{
    int num;
    printf("Enter your number: \n");
    scanf("%d", &num);

    /* If a number is odd, its binary representation ends with 1.
    Therefore we can perform num & 1, and check whether the result == 1,
    If yes, the number is odd.*/

    if (num == 0)
        printf("You've enetered Zero.\n");
    else if ((num&1) == 1)
        printf("%d is odd.\n", num);
    else 
        printf("%d is even.\n", num);
    
    return 0;
}
```

5. Write a program to check whether a given number is a three-digit number or not.
```
#include <stdio.h>

int main()
{
    int num;
    
    printf("Enter your number. \n");
    scanf("%d", &num);

    if (num>99 && num<1000)
        printf("%d is three digit.\n", num);
    else    
        printf("%d is not three digit.\n", num);

    return 0;
}
```

6. Write a program to print greater between two numbers. Print one number of both are
the same.
```
#include <stdio.h>
#include <string.h>

int main()
{
    int a, b;
    
    printf("Enter two numbers separated by space. \n");
    scanf("%d %d", &a, &b);

    if (a == b)
        printf("%d\n", a);
    else if (a > b)
        printf("%d\n", a);
    else
        printf("%d\n", b);

    return 0;
}
```

7. Write a program to check whether roots of a given quadratic equation are real &
distinct, real & equal or imaginary roots
```
#include <stdio.h>
#include <string.h>

int main()
{
    float a, b, c, delta;
    
    printf("Enter coefficients of a quadratic equation separated by space. \n");
    scanf("%f %f %f", &a, &b, &c);

    delta = b*b - 4*a*c;
    if (delta == 0)
        printf("Roots are real and equal.\n");
    else if (delta > 0)
        printf("Roots are real and distinct.\n");
    else
        printf("Roots are imaginary.\n");

    return 0;
}
```

8. Write a program to check whether a given year is a leap year or not.
```
#include <stdio.h>
#include <string.h>

int main()
{
    int year;
    printf("Enter your year: \n");
    scanf("%d", &year);

    if ((year%4 == 0 && year%100 != 0) || (year%400 == 0))
        printf("%d is leap year.\n", year);
    else
        printf("%d is not a leap year.\n", year);

    return 0;
}
```
9. Write a program to find the greatest among three given numbers. Print number once
if the greatest number appears two or three times.
```
#include <stdio.h>

int main()
{
    int a, b, c, greatest=-9999;
    printf("Enter three numbers (followed by space) : \n");
    scanf("%d %d %d", &a, &b, &c);

    if (a >= b)
    {
        if (a >= c)
        {
            if (a == b || a == c)
            {
                greatest = a;
                printf("%d\n", a);
            }
            else
                greatest = c;
        }
    }
    else if (b >= c)
    {
        if (b == c)
            printf("%d\n", b);
        else
            greatest = c;
    }

return 0;
}
```
10. Write a program which takes the cost price and selling price of a product from the
user. Now calculate and print profit or loss percentage.
```
#include <stdio.h>

int main()
{
    float cost_price, selling_price, p_or_l, p_or_l_perc;
    printf("Enter Cost Price : \n");
    scanf("%f", &cost_price);

    printf("Enter Selling Price: \n");
    scanf("%f", &selling_price);

    p_or_l = selling_price - cost_price;
    p_or_l_perc = (p_or_l / cost_price) * 100 ; 

    printf("Profit / Loss Percentage = %.2f %%\n", p_or_l_perc);

    return 0;
}
```
11. Write a program to take marks of 5 subjects from the user. Assume marks are given
out of 100 and passing marks is 33. Now display whether the candidate passed the
examination or failed.
```
#include <stdio.h>

int main()
{
    float a, b, c, d, e;
    int passing_marks = 33;
    int pass = 1;

    for (int i=1; i<=5; i++)
    {
        printf("Enter marks for subject %d\n", i);

        switch (i)
        {
        case 1:
            scanf("%f", &a);
            if (a < passing_marks)
                pass = 0;
            break;
        case 2:
            scanf("%f", &b);
            if (b < passing_marks)
                pass = 0;
            break;
        case 3:
            scanf("%f", &c);
            if (c < passing_marks)
                pass = 0;
            break;
        case 4:
            scanf("%f", &d);
            if (d < passing_marks)
                pass = 0;
            break;
        case 5:
            scanf("%f", &e);
            if (e < passing_marks)
                pass = 0;
            break;
        
        default:
            break;
        }
    }

    if(pass)
        printf("Student passed the examination\n");
    else
        printf("Student failed the examination\n");

    return 0;
}
```
12. Write a program to check whether a given alphabet is in uppercase or lowercase.
```
#include <stdio.h>

int main()
{
    int16_t a_char;
    printf("Enter a character: \n");
    a_char = getchar();

    if (a_char >= 'A' && a_char <= 'Z')
        printf("%c is an Upper Case Character.\n", a_char);
    else if (a_char >= 'a' && a_char <= 'z')
        printf("%c is a Lower Case Character.\n", a_char);
    else
        printf("Neither Upper Case Nor Lower Case Character.\n");
    return 0;
}
```
13. Write a program to check whether a given number is divisible by 3 and divisible by 2.
```
#include <stdio.h>

int main()
{
    int num;
    printf("Enter a number: \n");
    scanf("%d", &num);

    if (num%3 == 0 && num%2 == 0)
        printf("%d is divisible by 2 and 3\n", num);
    else
        printf("%d is not divisible by 2 and 3\n", num);

    return 0;
}
```

14. Write a program to check whether a given number is divisible by 7 or divisible by 3.
```
#include <stdio.h>

int main()
{
    int num;
    printf("Enter a number: \n");
    scanf("%d", &num);

    if (num%3 == 0 || num%7 == 0)
        printf("%d is divisible by 3 or 7\n", num);
    else
        printf("%d is not divisible by 3 or 7\n", num);

    return 0;
}
```

15. Write a program to check whether a given number is positive, negative or zero.
```
#include <stdio.h>

int main()
{
    int num;
    printf("Enter your number: \n");
    scanf("%d", &num);

    if (num == 0)
        printf("The number is Zero.\n");
    else if (num > 0)
        printf("%d is Positive.\n", num);
    else 
        printf("%d is Negative\n", num);

    return 0;
}
```

16. Write a program to check whether a given character is an alphabet (uppercase), an
alphabet (lower case), a digit or a special character.
```
#include <stdio.h>

int main() 
{
    char c;
    printf("Enter an alphabet, digit or special character: \n");
    scanf(" %c", &c);

    if (c >= '0' && c <= '9')
        printf("%c is a digit.\n", c);
    else if (c >= 'A' && c <= 'Z')
        printf("%c is an uppercase alphabet.\n", c);
    else if (c >= 'a' && c <= 'z')
        printf("%c is a lower case alphabet.\n", c);
    else if (c >= '!' && c <= '/')
        printf("%c is a special character.\n", c);
    else 
        printf("Not a valid digit, uppercase or lowercase alphabet, and special character.\n");

    return 0;
}
```

17. Write a program which takes the length of the sides of a triangle as an input. Display
whether the triangle is valid or not.
```
#include <stdio.h>

int main()
{
    float side1, side2, side3;

    printf("Enter length of side 1: \n");
    scanf("%f", &side1);

    printf("Enter length of side 2: \n");
    scanf("%f", &side2);

    printf("Enter length of side 3: \n");
    scanf("%f", &side3);

    if ((side1 + side2 > side3) && 
        (side1 + side3 > side2) && 
        (side2 + side3 > side1))
        printf("%.1f, %.1f  and %.1f are sides of a valid triangle.\n", side1, side2, side3);
    else 
        printf("%.1f, %.1f  and %.1f are not sides of a valid triangle.\n", side1, side2, side3);

    return 0;
}
```

18. Write a program which takes the month number as an input and display number of
days in that month
```
#include <stdio.h>

int main()
{
    int month_num;

    printf("Enter month number: \n");
    scanf("%d", &month_num);

    switch (month_num)
    {
    case 1:
        printf("Jan contains 31 days\n");
        break;
    
    case 2:
        printf("Feb contains 28 or 29 days depending year.\n");
        break;

    case 3:
        printf("Mar contains 31 days\n");
        break;

    case 4:
        printf("Apr contains 30 days\n");
        break;

    case 5:
        printf("May contains 31 days\n");
        break;

    case 6:
        printf("Jun contains 30 days\n");
        break;

    case 7:
        printf("Jul contains 31 days\n");
        break;
    
    case 8:
        printf("Aug contains 31 days\n");
        break;
    
    case 9:
        printf("Sep contains 30 days\n");
        break;

    case 10:
        printf("Oct contains 31 days\n");
        break;

    case 11:
        printf("Nov contains 30 days\n");
        break;

    case 12:
        printf("Dec contains 31 days\n");
        break;
    
    default:
        printf("Not a valid month number.\n");
        break;
    }

    return 0;
}
```
