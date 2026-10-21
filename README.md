#include <stdio.h>

void find(int a[], int n, int i, int max1, int max2) {
    if (i == n) {
        printf("2 max: %d\n", max2);
        return;
    }
    if (a[i] > max1) {
        max2 = max1;
        max1 = a[i];
    } else if (a[i] > max2) {
        max2 = a[i];
    }
    find(a, n, i + 1, max1, max2);
}

int main() {
    int a[10], i;
    printf("vvedite 10 chisel:\n");
    for (i = 0; i  < 10; i++) {
        scanf("%d", &a[i]);
    }
    find(a, 10, 1, a[0], a[0]);

    return 0;
}
