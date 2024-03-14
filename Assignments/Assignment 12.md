1. Write a recursive function to print first N natural numbers
```
#include <stdio.h>

void printN(int);

int main()
{
    int N;
    printf("Program to print first N natural numbers\n");
    printf("Enter N: ");
    scanf("%d", &N);
    printN(N);
    return 0;
}

void printN(int n)
{
    if (n > 0)
    {
        printN(n - 1);
        printf("%d\t", n);
    }
}
```
<br>

2. Write a recursive function to print first N natural numbers in reverse order
```
#include <stdio.h>

void printN_reverse(int);

int main()
{
    int N;
    printf("Program to print first N natural numbers in reverse order\n");
    printf("Enter N: ");
    scanf("%d", &N);
    printN_reverse(N);
    return 0;
}

void printN_reverse(int n)
{
    if (n > 0)
    {
        printf("%d\t", n);
        printN_reverse(n-1);
    }
}
```
<br>

3. Write a recursive function to print first N odd natural numbers
```
#include <stdio.h>

void print_odd_N(int, int);

int main()
{
    int N ;
    printf("Program to print first N odd natural numbers\n");
    printf("Enter N: ");
    scanf("%d", &N);
    print_odd_N(N, 1);
    return 0;
}

void print_odd_N(int n, int c)
{
    if (n > 0)
    {
        printf("%d\t", c);
        print_odd_N(n - 1, c + 2);
    }
}
```
<br>

4. Write a recursive function to print first N odd natural numbers in reverse order
```
#include <stdio.h>

void print_odd_N(int, int);

int main()
{
    int N ;
    printf("Program to print first N odd natural numbers in reverse order\n");
    printf("Enter N: ");
    scanf("%d", &N);
    print_odd_N(N, 1);
    return 0;
}

void print_odd_N(int n, int c)
{
    if (n > 0)
    {
        print_odd_N(n - 1, c + 2);
        printf("%d\t", c);
    }
}
```
<br>

5. Write a recursive function to print first N even natural numbers
```
#include <stdio.h>

void print_odd_N(int, int);

int main()
{
    int N ;
    printf("Program to print first N even natural numbers\n");
    printf("Enter N: ");
    scanf("%d", &N);
    print_odd_N(N, 2);
    return 0;
}

void print_odd_N(int n, int c)
{
    if (n > 0)
    {
        printf("%d\t", c);
        print_odd_N(n - 1, c + 2);
    }
}
```
<br>

6. Write a recursive function to print first N even natural numbers in reverse order
```
#include <stdio.h>

void print_odd_N(int, int);

int main()
{
    int N ;
    printf("Program to print first N even natural numbers in reverse order\n");
    printf("Enter N: ");
    scanf("%d", &N);
    print_odd_N(N, 2);
    return 0;
}

void print_odd_N(int n, int c)
{
    if (n > 0)
    {
        print_odd_N(n - 1, c + 2);
        printf("%d\t", c);
    }
}
```
<br>

7. Write a recursive function to print squares of first N natural numbers
```
#include <stdio.h>

void squaresN(int);

int main()
{
    int N;

    printf("Program to print squares of first N natural numbers\n");
    printf("Enter N: ");
    scanf("%d", &N);
    squaresN(N);

    return 0;
}

void squaresN(int n)
{
    if (n > 0)
    {
        squaresN(n - 1);
        printf("%d\t", n * n);
    }
}

```
<br>

8. Write a recursive function to print binary of a given decimal number
```
#include <stdio.h>

void print_binary(int);

int main()
{
    int n;

    printf("Program to print binary of a given decimal number\n");
    printf("Enter decimal number: ");
    scanf("%d", &n);

    print_binary(n);
    return 0;
}

void print_binary(int n)
{
    int bd;

    if (n > 0)
    {
        bd = n % 2;
        print_binary(n / 2);
        printf("%d", bd);
    }
}
```
<br>

10. Write a recursive function to print reverse of a given number
```
#include <stdio.h>
#include <math.h>

int reverse(int);
int len(int);

int main()
{
    int n, n_reverse;

    printf("Program to print reverse of a given number\n");
    printf("Enter number: ");
    scanf("%d", &n);

    n_reverse = reverse(n);
    printf("The reverse of %d is %d\n", n, n_reverse);

    return 0;
}

int reverse(int n)
{
    int ld, n_len;
    n_len = len(n);

    if (n_len > 1)
    {
        ld = n % 10;
        n /= 10;
        return ld * (powf(10, n_len - 1)) + reverse(n);
    }
    else if (len(n) == 1)
        return n;
    return 0;
}

int len(int n)
{
    int l = 0;

    do
    {
        l++;
        n /= 10;
    } while (n);
    

    return l;
}
```
<br>

