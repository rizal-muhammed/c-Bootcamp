1. Write a program to print Hello Students on the screen.
```
#include <stdio.h>


int main()
{
   printf("Hello Students\n");
   return 0;
}

```

2. Write a program to print Hello in the first line and Students in the second line.
```
#include <stdio.h>


int main()
{
   printf("Hello\nStudents\n");
   return 0;
}

```

3. Write a program to print “MySirG” on the screen. (Remember to print in double quotes)
```
#include <stdio.h>


int main()
{
   printf("\"MySirG\"\n");
   return 0;
}
```

4. WAP to find the area of the circle. Take radius of circle from user as input and print the
result in below given format.
Expected output format – “Area of circle is A having the radius R”. Replace A with area
& R with radius.
```
#include <stdio.h>
#include <math.h>


int main()
{
   float radius, area;
   printf("Enter Radious\n");
   scanf("%f", &radius);
   area = M_PI * pow(radius, 2);
   printf("Area of Circle is %f, having radius %f\n", area, radius);
   return 0;
}
```

5. WAP to calculate the length of String using printf function.
```
#include <stdio.h>
#include <string.h>


int main()
{
   char my_str[] = "Hello World!";
   printf("The length of \'%s\' is %lu\n", my_str, strlen(my_str));
   return 0;
}

```

6. WAP to print the name of the user in double quotes.
Expected output format – “Hello , Amit Kumar”
```
#include <stdio.h>
#define MAX_LENGTH 50


int main()
{
   char name[MAX_LENGTH];
   printf("Please enter your name : \n");
   scanf("%[^\n]", name);
   printf("\"Hello, %s\"\n", name);
   return 0;
}

```

7. WAP to print “%d” on the screen.
```
#include <stdio.h>


int main()
{
   printf("\"%%d\"\n");
   return 0;
}

```

8. WAP to print “\n” on the screen.
```
#include <stdio.h>


int main()
{
   printf("\"\\n\"\n");
   return 0;
}

```

9. WAP to print “\\” on the screen.
```
#include <stdio.h>


int main()
{
   printf("\"\\\\\"\n");
   return 0;
}

```

10. WAP to take date as an input in below given format and convert the date format and
display the result as given below.
User Input date format – “DD/MM/YYYY” (27/11/2022)
Output format –
“Day – DD , Month – MM , Year – YYYY” (Day – 27 ,Month – 07 , Year – 2022)
```
#include <stdio.h>
#include <string.h>
#define MAX_INPUT_LENGTH 50
#define MAX_LENGTH 5

int main ()
{
  char date_str[MAX_INPUT_LENGTH];
  char * pch;
  char day[MAX_LENGTH], month[MAX_LENGTH], year[MAX_LENGTH];
  int count = 0;

  printf("Enter your date in \'DD/MM/YYYY\' format : \n");
  scanf("%s", date_str);

  pch = strtok (date_str,"/");
  while (pch != NULL && count < 3)
  {
    if (count == 0)
        strcpy(day, pch);
    else if (count == 1)
        strcpy(month, pch);
    else if (count == 2)
        strcpy(year, pch);

    pch = strtok (NULL, "/");
    count++;
  }

  printf("Day-%s, Month-%s, Year-%s\n", day, month, year);
  return 0;
}
```

11. WAP to take time as an input in below given format and convert the time format and
display the result as given below.
User Input date format – “HH:MM”
Output format – “HH hour and MM Minute”
Example –
“11:25” converted to “11 Hour and 25 Minute”
```
#include <stdio.h>
#include <string.h>
#define MAX_INPUT_LENGTH 50
#define MAX_LENGTH 3

int main ()
{
  char time_str[MAX_INPUT_LENGTH];
  char * pch;
  char hour[MAX_LENGTH], minute[MAX_LENGTH];
  int count = 0;

  printf("Enter your time in \'HH:MM\' format : \n");
  scanf("%s", time_str);

  pch = strtok (time_str,":");
  while (pch != NULL && count < 2)
  {
    if (count == 0)
        strcpy(hour, pch);
    else if (count == 1)
        strcpy(minute, pch);

    pch = strtok (NULL, ":");
    count++;
  }

  printf("%s Hour and %s Minute.\n", hour, minute);
  return 0;
}

```

12. Find output of below code:
```
int main()
{
int x = printf(“ineuron”);
printf(“%d”,x);
return 0;
}
```

Sol) The output is 
```
ineuron7
```
`printf(“ineuron”)` at line 3 will print the string 'ineuron'. As per the documentation of `printf` function, the return type of `printf` is,
```
Return Value
On success, the total number of characters written is returned.
```
So printf returns the length of the string 'ineuron' , which is getting assigned to int variable x. And at line 4, we're printing this value. So the entire output will be `ineuron7`.

reference for `printf` function in C : https://cplusplus.com/reference/cstdio/printf/
