# Switch Case Problems
<br>

1. Write a program which takes the month number as an input and display number of days in that month.
```
#include <stdio.h>

int main()
{
    int month; 
    printf("Program to print number of days in a month\n");
    printf("Enter month number: \n");
    scanf("%d", &month);

    switch (month)
    {
    case 1:
        printf("Jan has 31 days\n");
        break;
    case 2:
        printf("Feb has 28 or 29 days\n");
        break;
    case 3:
        printf("Mar has 31 days\n");
        break;
    case 4:
        printf("Apr has 30 days\n");
        break;
    case 5:
        printf("May has 31 days\n");
        break;
    case 6:
        printf("Jun has 30 days\n");
        break;
    case 7:
        printf("Jul has 31 days\n");
        break;
    case 8:
        printf("Aug has 31 days\n");
        break;
    case 9:
        printf("Sep has 30 days\n");
        break;
    case 10:
        printf("Oct has 31 days\n");
        break;
    case 11:
        break;
        printf("Nov has 30 days\n");
    case 12:
        printf("Dec has 31 days\n");
        break;
    
    default:
        printf("%d is not a valid month number\n", month);
        break;
    }

    return 0;
}
```
<br>

2. Write a menu driven program with the following options: <br>
    a. Addition <br>
    b. Subtraction <br>
    c. Multiplication <br>
    d. Division <br>
    e. Exit <br>
```
#include <stdio.h>

int main()
{
    int choice;
    float a, b, result;
    printf("Calculator\n");
    printf("----------");

    do
    {
        printf("1. Addition\n2. Subtraction\n3. Multiplication\n4. Division\n5. Exit\n");
        printf("\nEnter your choice\n\n");
        scanf("%d", &choice);
        
        switch (choice)
        {
        case 1:
            printf("Addition\n");
            printf("--------\n");
            printf("Enter two numbers to add(separated by space): \n");
            scanf("%f %f", &a, &b);
            result = a + b;
            printf("\nThe sum of %.2f and %.2f = %.2f\n", a, b, result);
            break;
        case 2:
            printf("Subtraction\n");
            printf("-----------\n");
            printf("Enter two numbers (separated by space): \n");
            scanf("%f %f", &a, &b);
            result = a - b;
            printf("\n%.2f - %.2f = %.2f\n", a, b, result);
            break;
        case 3:
            printf("Multiplication\n");
            printf("--------------\n");
            printf("Enter two numbers (separated by space): \n");
            scanf("%f %f", &a, &b);
            result = a * b;
            printf("\n%.2f * %.2f = %.2f\n", a, b, result);
            break;
        case 4:
            printf("Division\n");
            printf("--------\n");
            printf("Enter two numbers (separated by space): \n");
            scanf("%f %f", &a, &b);

            if (b != 0)
            {
                result = a / b;
                printf("\n%.2f / %.2f = %.2f\n", a, b, result);
            }
            else
                printf("Zero division error\n");
            break;
        case 5:
            break;
        
        default:
            printf("%d is not a valid choice\n", choice);
            break;
        }
    } while (choice != 5);
    
    return 0;
}
```
<br>

3. Write a program which takes the day number of a week and displays a unique greeting message for the day.
```
#include <stdio.h>

int main()
{
    int day;
    printf("Program to print unique greeting message for a day\n");
    
    printf("1. Mon\n2. Tue\n3. Wed\n4. Thu\n5. Fri\n6. Sat\n7. Sun\n\n");
    printf("Enter day number: \n");
    scanf("%d", &day);

    switch (day)
    {
    case 1:
        printf("I know it's hard because it's Monday, but keep smiling, nevertheless\n");
        break;
    case 2:
        printf("Got the momentum back, right? Keep pushing, because it's only Tuesday\n");
        break;
    case 3:
        printf("Oh! it's already Wednesday. Good Job\n");
        break;
    case 4:
        printf("Happy Thursday. It's almost weekend\n");
        break;
    case 5:
        printf("Yay! it's Friday, Are you ready for the party at night!!!\n");
        break;
    case 6:
        printf("Oh, it's Saturday. Zip a coffee for the hangover.");
        break;
    case 7:
        printf("Sunday Funday. Enjoy\n");
        break;
    
    default:
        printf("%d is not a valid choice\n", day);
        break;
    }

    return 0;
}

```
<br>

4. Write a menu driven program with the following options: <br>
    a. Check whether a given set of three numbers are lengths of an
    isosceles triangle or not <br>
    b. Check whether a given set of three numbers are lengths of sides of
    a right angled triangle or not <br>
    c. Check whether a given set of three numbers are equilateral triangle
    or not <br>
    d. Exit <br>
```
#include <stdio.h>
#include <math.h>

int main()
{
    float a, b, c;
    int choice;
    printf("Enter three numbers(separated by space)\n");
    scanf("%f %f %f", &a, &b, &c);

    printf("\n1. Check Isosceles triangle\n2. Right angled triangle\n"
           "3. Equilateral triagle\n4. Exit\n\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);

    switch (choice)
    {
    case 1:
        /* Isoceles triangle (two sides of equal length) */
        if ((a == b && a != c) || 
            (b == c && b != a) ||
            (a == c && a != b))
            printf("%0.1f, %0.1f, %0.1f are sides of an Isoceles triangle\n", a, b, c);
        else 
            printf("%0.1f, %0.1f, %0.1f do not form an Isoceles triangle\n", a, b, c);
        break;
    case 2:
        /* Right angled (Sum of squares of two shorter sides = Sqaure of hypotenuse) */
        if ((powf(a, 2) + powf(b, 2) == powf(c, 2)) ||
            (powf(b, 2) + powf(c, 2) == powf(a, 2)) ||
            (powf(a, 2) + powf(c, 2) == powf(b, 2)) )
            printf("%0.1f, %0.1f, %0.1f are sides of Right angled triangle\n", a, b, c);
        else 
            printf("%0.1f, %0.1f, %0.1f do not form a Right angled triangle\n", a, b, c);
        break;
    case 3:
        /* Equilateral triangle. Three sides are equal */
        if ((a == b) && (a == c))
            printf("Three sides are equal. Threfore sides of an Equilateral triangle\n");
        else
            printf("%0.1f, %0.1f, %0.1f do not form an Equilateral triangle\n", a, b, c);
        break;
    case 4:
        /* Exit */
        printf("Exiting the program\n");
        break;
    
    default:
        printf("%d is not a valid choice\n", choice);
        break;
    }

    return 0;
}
```
<br>

5. Convert the following if-else-if construct into switch case: <br>
```
  if(var == 1) 
    System.out.println("good"); 
  else if(var == 2) 
    System.out.println("better"); 
  else if(var == 3) 
    System.out.println("best"); 
  else 
    System.out.println("invalid"); 
```
```
#include <stdio.h>

int main()
{
    int num;
    printf("Program to print some messages based on your input\n");
    printf("Enter a number: \n");
    scanf("%d", &num);

    switch (num)
    {
    case 1:
        printf("good\n");
        break;
    case 2:
        printf("better\n");
        break;
    case 3:
        printf("best\n");
        break;
    
    default:
        printf("Invalid\n");
        break;
    }
    return 0;
}
```
<br>

6. Program to check whether a year is a leap year or not. Using switch
statement
```
#include <stdio.h>

int main()
{
    int year;
    printf("Program to check if a given is leap year or not\n");
    printf("Enter year: \n");
    scanf("%d", &year);

    switch ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0))
    {
    case 0:
        printf("%d is not a leap year\n", year);
        break;
    case 1:
        printf("%d is a leap year\n", year);
        break;
    
    default:
        printf("%d is not a valid year\n", year);
        break;
    }


    return 0;
}
```
<br>

7. Program to take the value from the user as input electricity unit charges
and calculate total electricity bill according to the given condition . Using
the switch statement. <br>
 <br>
    For the first 50 units Rs. 0.50/unit <br>
    For the next 100 units Rs. 0.75/unit <br>
    For the next 100 units Rs. 1.20/unit <br>
    For units above 250 Rs. 1.50/unit <br>
    An additional surcharge of 20% is added to the bill.
   
```
```
<br>

8. Program to convert a positive number into a negative number and negative
number into a positive number using a switch statement.
```
#include <stdio.h>

int main()
{
    int num;
    printf("Program to convert a positive number into negative number and vice versa\n");
    printf("Enter number: \n");
    scanf("%d", &num);

    switch (num >= 0)
    {
    case 0:
        /* negative number */
        printf("%d is a negative number.\nThe corresponding positive num is %d\n", num, -1 * num);
        break;
    case 1:
        /* Zero or Positive number */
        if (num == 0)
            printf("You've enetered Zero\n");
        else 
            printf("%d is a Positive number.\nThe corresponding negative num is %d\n", num, -1 * num);
        break;
    
    default:
        break;
    }
    return 0;
}
```
<br>

9. Program to Convert even number into its upper nearest odd number
Switch Statement.
```
#include <stdio.h>
#include <ctype.h>

int main()
{
    int num;
    printf("Program to print the upper nearest odd number of an even number\n");
    printf("Enter a number: ");
    scanf("%d", &num);

    switch (num % 2 == 0)
    {
    case 0:
        /* odd number */
        printf("The upper nearest even number of %d is %d\n", num, num + 1);
        break;
    case 1:
        /* even number */
        printf("The %d is an even number\n", num);
        break;
    
    default:
        printf("%d is not a valid choice\n", num);
        break;
    }
    return 0;
}
```
<br>

10. C program to find all roots of a quadratic equation using switch case
```
```
<br>















