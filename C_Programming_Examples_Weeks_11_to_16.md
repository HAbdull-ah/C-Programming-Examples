
# C Programming Examples (Weeks 11-16)

## Week 11: File I/O

### Easy: Write to a File
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

### Medium: Read from a File
```c
#include <stdio.h>

int main() {
    char buffer[100];
    FILE *fptr;

    fptr = fopen("output.txt", "r");
    if (fptr == NULL) {
        printf("Error opening file!\n");
        return 1;
    }

    while (fgets(buffer, 100, fptr) != NULL) {
        printf("%s", buffer);
    }

    fclose(fptr);
    return 0;
}
```

### Hard: Copy Contents from One File to Another
```c
#include <stdio.h>

int main() {
    char ch;
    FILE *source, *destination;

    source = fopen("source.txt", "r");
    if (source == NULL) {
        printf("Error opening source file!\n");
        return 1;
    }

    destination = fopen("destination.txt", "w");
    if (destination == NULL) {
        printf("Error opening destination file!\n");
        fclose(source);
        return 1;
    }

    while ((ch = fgetc(source)) != EOF) {
        fputc(ch, destination);
    }

    fclose(source);
    fclose(destination);
    printf("File copied successfully.\n");
    return 0;
}
```

## Week 12: Advanced Topics (2D Arrays, Nested Loops)

### Easy: Sum of Two Matrices
```c
#include <stdio.h>

int main() {
    int mat1[2][2] = {{1, 2}, {3, 4}};
    int mat2[2][2] = {{5, 6}, {7, 8}};
    int sum[2][2];

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            sum[i][j] = mat1[i][j] + mat2[i][j];
        }
    }

    printf("Sum of matrices:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            printf("%d ", sum[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

### Medium: Transpose of a Matrix
```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    int transpose[3][3];

    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            transpose[i][j] = matrix[j][i];
        }
    }

    printf("Transpose of the matrix:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", transpose[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

### Hard: Multiply Two Matrices
```c
#include <stdio.h>

int main() {
    int mat1[2][2] = {{1, 2}, {3, 4}};
    int mat2[2][2] = {{5, 6}, {7, 8}};
    int result[2][2];

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            result[i][j] = 0;
            for (int k = 0; k < 2; k++) {
                result[i][j] += mat1[i][k] * mat2[k][j];
            }
        }
    }

    printf("Result of matrix multiplication:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            printf("%d ", result[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

## Week 13: Preprocessor and Macros

### Easy: Define a Constant Using a Macro
```c
#include <stdio.h>
#define PI 3.14159

int main() {
    printf("Value of PI: %f\n", PI);
    return 0;
}
```

### Medium: Macro with Arguments (Square of a Number)
```c
#include <stdio.h>
#define SQUARE(x) ((x) * (x))

int main() {
    int num = 5;
    printf("Square of %d is %d\n", num, SQUARE(num));
    return 0;
}
```

### Hard: Conditional Compilation Using Preprocessor Directives
```c
#include <stdio.h>
#define DEBUG 1

int main() {
    #ifdef DEBUG
        printf("Debugging is enabled.\n");
    #else
        printf("Debugging is disabled.\n");
    #endif

    return 0;
}
```

## Week 14: Final Project Work Session
No new examples.

## Week 15: Final Review
No new examples.

## Week 16: Final Exam
No new examples.
