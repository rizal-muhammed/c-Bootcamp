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

    if (a_char >= 65 && a_char <= 90)
        printf("%c is an Upper Case Character.\n", a_char);
    else if (a_char >= 97 && a_char <= 122)
        printf("%c is a Lower Case Character.\n", a_char);
    else
        printf("Neither Upper Case Nor Lower Case Character.\n");
    return 0;
}
```
