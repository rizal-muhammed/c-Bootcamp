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
