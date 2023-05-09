# Embedded-Software-Engineer-QuizEmbedded-Software-Engineer-Quiz-Q1
# Quiz 1
#include <stdio.h>

void print_squares(int n, int m) {
    int size, i, j;
    while (n > 0 && m > 0) {
        size = n > m ? m : n;  // choose the smaller dimension
        printf("%dx%d, ", size, size);
        for (i = 0; i < n / size; i++) {
            for (j = 0; j < m / size; j++) {
                printf("1x1, ");  // print the remaining 1x1 squares
            }
        }
        if (n % size == 0) {
            n = 0;
        } else {
            m %= size;
        }
        if (m % size == 0) {
            m = 0;
        } else {
            n %= size;
        }
    }
    printf("\n");
}

int main() {
    int n, m;
    printf("Enter the dimensions of the paper (N M): ");
    scanf("%d %d", &n, &m);
    printf("The series of squares that can be made are: ");
    print_squares(n, m);
    return 0;
}

