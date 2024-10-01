
# C Programming Examples (Weeks 1-5)

## Week 1: Basic Syntax & Output

### Easy: "Hello, World!"
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

### Medium: Display Personal Information
```c
#include <stdio.h>

int main() {
    printf("Name: John Doe\n");
    printf("Age: 25\n");
    return 0;
}
```

### Hard: Ask the User for Input and Display
```c
#include <stdio.h>

int main() {
    char name[50];
    int age;

    printf("Enter your name: ");
    scanf("%s", name);
    printf("Enter your age: ");
    scanf("%d", &age);

    printf("Name: %s, Age: %d\n", name, age);
    return 0;
}
```

## Week 2: Variables and Data Types

### Easy: Basic Arithmetic Operations
```c
#include <stdio.h>

int main() {
    int a = 10, b = 20;
    int sum = a + b;
    printf("Sum: %d\n", sum);
    return 0;
}
```

### Medium: Temperature Conversion (Celsius to Fahrenheit)
```c
#include <stdio.h>

int main() {
    float celsius, fahrenheit;
    printf("Enter temperature in Celsius: ");
    scanf("%f", &celsius);

    fahrenheit = (celsius * 9 / 5) + 32;
    printf("Temperature in Fahrenheit: %.2f\n", fahrenheit);
    return 0;
}
```

### Hard: Swap Two Numbers Without a Temporary Variable
```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    // Swapping logic
    a = a + b;
    b = a - b;
    a = a - b;

    printf("After swapping: a = %d, b = %d\n", a, b);
    return 0;
}
```

## Week 3: Conditional Statements

### Easy: Even or Odd Check
```c
#include <stdio.h>

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);

    if (num % 2 == 0) {
        printf("%d is even\n", num);
    } else {
        printf("%d is odd\n", num);
    }
    return 0;
}
```

### Medium: Find the Largest of Three Numbers
```c
#include <stdio.h>

int main() {
    int a, b, c;
    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if (a >= b && a >= c) {
        printf("Largest: %d\n", a);
    } else if (b >= a && b >= c) {
        printf("Largest: %d\n", b);
    } else {
        printf("Largest: %d\n", c);
    }
    return 0;
}
```

### Hard: Simple Calculator (Addition, Subtraction, Multiplication, Division)
```c
#include <stdio.h>

int main() {
    char operator;
    float num1, num2, result;

    printf("Enter operator (+, -, *, /): ");
    scanf(" %c", &operator);

    printf("Enter two numbers: ");
    scanf("%f %f", &num1, &num2);

    switch (operator) {
        case '+':
            result = num1 + num2;
            break;
        case '-':
            result = num1 - num2;
            break;
        case '*':
            result = num1 * num2;
            break;
        case '/':
            if (num2 != 0)
                result = num1 / num2;
            else {
                printf("Error! Division by zero.\n");
                return 1;
            }
            break;
        default:
            printf("Invalid operator.\n");
            return 1;
    }

    printf("Result: %.2f\n", result);
    return 0;
}
```

## Week 4: Functions

### Easy: Simple Function to Add Two Numbers
```c
#include <stdio.h>

int add(int a, int b) {
    return a + b;
}

int main() {
    int num1 = 5, num2 = 10;
    printf("Sum: %d\n", add(num1, num2));
    return 0;
}
```

### Medium: Function to Find the Factorial of a Number
```c
#include <stdio.h>

int factorial(int n) {
    if (n == 0)
        return 1;
    return n * factorial(n - 1);
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    printf("Factorial of %d is %d\n", num, factorial(num));
    return 0;
}
```

### Hard: Function to Check Prime Number
```c
#include <stdio.h>

int isPrime(int n) {
    if (n <= 1)
        return 0;
    for (int i = 2; i <= n / 2; i++) {
        if (n % i == 0)
            return 0;
    }
    return 1;
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);

    if (isPrime(num))
        printf("%d is a prime number\n", num);
    else
        printf("%d is not a prime number\n", num);

    return 0;
}
```

## Week 5: Arrays

### Easy: Sum of Array Elements
```c
#include <stdio.h>

int main() {
    int arr[5] = {1, 2, 3, 4, 5};
    int sum = 0;

    for (int i = 0; i < 5; i++) {
        sum += arr[i];
    }

    printf("Sum of array elements: %d\n", sum);
    return 0;
}
```

### Medium: Find the Largest Element in an Array
```c
#include <stdio.h>

int main() {
    int arr[5] = {2, 8, 4, 1, 7};
    int max = arr[0];

    for (int i = 1; i < 5; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }

    printf("Largest element: %d\n", max);
    return 0;
}
```

### Hard: Sort an Array Using Bubble Sort
```c
#include <stdio.h>

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
}

int main() {
    int arr[5] = {5, 2, 9, 1, 6};
    int n = 5;

    bubbleSort(arr, n);

    printf("Sorted array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```

