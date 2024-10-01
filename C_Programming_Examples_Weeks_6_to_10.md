
# C Programming Examples (Weeks 6-10)

## Week 6: Midterm Review (Combining Previous Topics)
No new examples; review and combine Week 1 to Week 5 examples.

## Week 7: Pointers

### Easy: Pointer to an Integer
```c
#include <stdio.h>

int main() {
    int a = 10;
    int *p = &a;
    printf("Value of a: %d\n", *p);
    return 0;
}
```

### Medium: Pointer Arithmetic
```c
#include <stdio.h>

int main() {
    int arr[5] = {1, 2, 3, 4, 5};
    int *ptr = arr;

    for (int i = 0; i < 5; i++) {
        printf("Value at arr[%d]: %d\n", i, *(ptr + i));
    }

    return 0;
}
```

### Hard: Swap Two Numbers Using Pointers
```c
#include <stdio.h>

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 5, y = 10;
    printf("Before swap: x = %d, y = %d\n", x, y);

    swap(&x, &y);

    printf("After swap: x = %d, y = %d\n", x, y);
    return 0;
}
```

## Week 8: Structs

### Easy: Simple Struct Example
```c
#include <stdio.h>

struct Student {
    char name[50];
    int age;
};

int main() {
    struct Student s1 = {"John Doe", 20};
    printf("Name: %s, Age: %d\n", s1.name, s1.age);
    return 0;
}
```

### Medium: Array of Structs
```c
#include <stdio.h>

struct Student {
    char name[50];
    int age;
};

int main() {
    struct Student students[2] = {{"John Doe", 20}, {"Jane Doe", 22}};

    for (int i = 0; i < 2; i++) {
        printf("Student %d: Name: %s, Age: %d\n", i+1, students[i].name, students[i].age);
    }

    return 0;
}
```

### Hard: Nested Structs
```c
#include <stdio.h>

struct Address {
    char city[50];
    int zip;
};

struct Student {
    char name[50];
    int age;
    struct Address addr;
};

int main() {
    struct Student s1 = {"John Doe", 20, {"New York", 10001}};

    printf("Name: %s, Age: %d, City: %s, Zip: %d\n", s1.name, s1.age, s1.addr.city, s1.addr.zip);
    return 0;
}
```

## Week 9: Midterm Exam
No new examples for the midterm exam.

## Week 10: Dynamic Memory Allocation

### Easy: Allocate Memory for an Array
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr;
    int n = 5;

    arr = (int*) malloc(n * sizeof(int));

    for (int i = 0; i < n; i++) {
        arr[i] = i + 1;
        printf("%d ", arr[i]);
    }

    free(arr);
    return 0;
}
```

### Medium: Resize an Array Using realloc
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr;
    int n = 5;

    arr = (int*) malloc(n * sizeof(int));

    for (int i = 0; i < n; i++) {
        arr[i] = i + 1;
    }

    arr = (int*) realloc(arr, 10 * sizeof(int));

    for (int i = 5; i < 10; i++) {
        arr[i] = i + 1;
    }

    for (int i = 0; i < 10; i++) {
        printf("%d ", arr[i]);
    }

    free(arr);
    return 0;
}
```

### Hard: Matrix Multiplication Using Dynamic Memory Allocation
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int r1, c1, r2, c2, i, j, k;
    printf("Enter rows and columns for the first matrix: ");
    scanf("%d %d", &r1, &c1);
    printf("Enter rows and columns for the second matrix: ");
    scanf("%d %d", &r2, &c2);

    if (c1 != r2) {
        printf("Error! Column of the first matrix must equal row of the second matrix.\n");
        return 1;
    }

    int **mat1 = (int **)malloc(r1 * sizeof(int *));
    for (i = 0; i < r1; i++) {
        mat1[i] = (int *)malloc(c1 * sizeof(int));
    }

    int **mat2 = (int **)malloc(r2 * sizeof(int *));
    for (i = 0; i < r2; i++) {
        mat2[i] = (int *)malloc(c2 * sizeof(int));
    }

    int **result = (int **)malloc(r1 * sizeof(int *));
    for (i = 0; i < r1; i++) {
        result[i] = (int *)malloc(c2 * sizeof(int));
    }

    printf("Enter elements of the first matrix:\n");
    for (i = 0; i < r1; i++) {
        for (j = 0; j < c1; j++) {
            scanf("%d", &mat1[i][j]);
        }
    }

    printf("Enter elements of the second matrix:\n");
    for (i = 0; i < r2; i++) {
        for (j = 0; j < c2; j++) {
            scanf("%d", &mat2[i][j]);
        }
    }

    for (i = 0; i < r1; i++) {
        for (j = 0; j < c2; j++) {
            result[i][j] = 0;
            for (k = 0; k < c1; k++) {
                result[i][j] += mat1[i][k] * mat2[k][j];
            }
        }
    }

    printf("Resultant matrix:\n");
    for (i = 0; i < r1; i++) {
        for (j = 0; j < c2; j++) {
            printf("%d ", result[i][j]);
        }
        printf("\n");
    }

    for (i = 0; i < r1; i++) {
        free(mat1[i]);
        free(result[i]);
    }
    for (i = 0; i < r2; i++) {
        free(mat2[i]);
    }
    free(mat1);
    free(mat2);
    free(result);

    return 0;
}
```

