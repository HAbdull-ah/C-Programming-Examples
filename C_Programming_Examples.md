
# C Programming Examples

## Week 1: "Hello, World" Program
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

## Week 2: Basic Arithmetic Operations
```c
#include <stdio.h>

int main() {
    int a = 10, b = 20;
    int sum = a + b;
    printf("Sum: %d\n", sum);
    return 0;
}
```

## Week 3: If Statement Example
```c
#include <stdio.h>

int main() {
    int x = 5;
    if (x > 0) 
        printf("Positive\n");
    return 0;
}
```

## Week 4: Function Example
```c
#include <stdio.h>

int add(int a, int b) {
    return a + b;
}

int main() {
    int result = add(10, 20);
    printf("Result: %d\n", result);
    return 0;
}
```

## Week 5: Array Sorting Program
```c
#include <stdio.h>

void sort(int arr[], int n) {
    int i, j, temp;
    for (i = 0; i < n-1; i++) {
        for (j = i+1; j < n; j++) {
            if (arr[i] > arr[j]) {
                temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }
}

int main() {
    int arr[5] = {5, 3, 4, 1, 2};
    sort(arr, 5);
    for (int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
    return 0;
}
```

## Week 7: Pointers Example
```c
#include <stdio.h>

int main() {
    int a = 10;
    int *p = &a;
    printf("Value of a: %d\n", *p);
    return 0;
}
```

## Week 8: Struct Example
```c
#include <stdio.h>

struct Student {
    char name[50];
    int age;
};

int main() {
    struct Student s1 = {"John", 20};
    printf("Name: %s, Age: %d\n", s1.name, s1.age);
    return 0;
}
```

## Week 10: Dynamic Memory Allocation Example
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr = (int*) malloc(5 * sizeof(int));
    for (int i = 0; i < 5; i++) {
        arr[i] = i * 10;
        printf("%d ", arr[i]);
    }
    free(arr);
    printf("\n");
    return 0;
}
```

## Week 11: File I/O Example
```c
#include <stdio.h>

int main() {
    FILE *fptr;
    fptr = fopen("output.txt", "w");
    fprintf(fptr, "Writing to a file.\n");
    fclose(fptr);
    return 0;
}
```

## Week 12: 2D Array Example
```c
#include <stdio.h>

int main() {
    int a[2][2] = {{1, 2}, {3, 4}};
    int b[2][2] = {{5, 6}, {7, 8}};
    int c[2][2];
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            c[i][j] = a[i][j] + b[i][j];
            printf("%d ", c[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```

## Week 13: Macro Example
```c
#include <stdio.h>
#define PI 3.14159

int main() {
    printf("Value of PI: %f\n", PI);
    return 0;
}
```
