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
#include <string.h>

int main()
{
    int num, is_three_digit=0, count=0, temp;
    
    printf("Enter your number. \n");
    scanf("%d", &num);
    temp = num;

    do
    {
        temp = temp / 10;
        if (count == 1 && temp != 0)
            is_three_digit = 1;
        if (count > 1 && temp != 0)
            is_three_digit = 0;
        count++;
    } while (count < 3);
    
    if (is_three_digit)
        printf("%d is three digit.\n", num);
    else    
        printf("%d is not three digit.\n", num);

    return 0;
}
```

6. Write a program to print greater between two numbers. Print one number of both are
the same.
