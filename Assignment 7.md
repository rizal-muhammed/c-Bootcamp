1. Write a program to find the Nth term of the Fibonnaci series.
```
#include <stdio.h>

int main()
{
    int N, a = 0, b = 1, Nth_term;

    printf("Program to find the Nth term of the fibonacci series\n");
    printf("Enter N\n");
    scanf("%d", &N);

    if (N == 1) // First term of fibonacci sequence is 0
        printf("%d\n", a);
    else if (N == 2) // second term of fibonacci sequence is 1
        printf("%d\n", b);
    else if (N > 2)
    {
        for(int i = 2; i < N; i++)
        {
            if (i%2 == 0)
            {
                a = a + b;
                Nth_term = a;
            }
            else
            {
                b = a + b;
                Nth_term = b;
            }
        }

        printf("%dth term of the fibonacci series is %d\n", N, Nth_term);
    }
    else
        printf("%d is not valid N\n", N);

    return 0;
}
```
<br>

2. Write a program to print first N terms of Fibonacci series
```
#include <stdio.h>

int main()
{
    int N, count = 0, a = 0, b = 1;

    printf("Program to generate first N terms of fibonacci series\n");
    printf("Enter N\n");
    scanf("%d", &N);

    if (N == 1)
        printf("%d\n", a);
    else if (N == 2)
        printf("%d\t%d\n", a, b);
    else if (N > 2)
    {
        printf("%d\t%d", a, b);
        for(int i = 2; i < N; i++)
        {
            printf("\t%d", a + b);
            if (i%2 == 0)
                a = a + b;
            else
                b = a + b;
        }
        printf("\n");
    }
    else  
        printf("%d is not a valid N\n", N);

    return 0;
}
```
<br>

3. Write a program to check whether a given number is there in the Fibonacci series or not.
```
#include <stdio.h>

int main()
{
    int num, is_fib = 0, a = 0, b = 1, Nth_term = 2; 

    printf("Program to check whether a given is in fibonacci sequence\n");
    printf("Enter your number: \n");
    scanf("%d", &num);

    if (num ==0 || num == 1)
        is_fib = 1;
    else if (num >= 2)
    {
        int i = 2;
        while (num >= Nth_term)
        {
            if (i%2 == 0)
            {
                a = a + b;
                Nth_term = a;
                if (Nth_term == num)
                {
                    is_fib = 1;
                    break;
                }
            }
            else
            {
                b = a + b;
                Nth_term = b;
                if (Nth_term == num)
                {
                    is_fib = 1;
                    break;
                }
            }
            i++;
        }
        
    }

    if (is_fib)
        printf("%d is in fibonacci sequence\n", num);
    else 
        printf("%d is not in fibonacci sequence\n", num);

    return 0;
}
```
<br>

4. Write a program to calculate HCF of two numbers
```

```
