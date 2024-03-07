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

```
<br>

3. Write a program which takes the day number of a week and displays a unique greeting message for the day.
```

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

```
<br>

6. Program to check whether a year is a leap year or not. Using switch
statement
```
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
```
<br>

9. Program to Convert even number into its upper nearest odd number
Switch Statement.
```
```
<br>

10. C program to find all roots of a quadratic equation using switch case
```
```
<br>















