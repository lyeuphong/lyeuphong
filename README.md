#include <stdio.h>

int main() {
    FILE *fp;
    int  arr[50];
    int  n, x, temp;
    printf("Nhap n = "); scanf("%d", &n);
    printf("Nhap x = "); scanf("%d", &x);
    for(int i = 0; i <= n - 1; i++){
        printf("Nhap arr[%d] = ", i);
        scanf("%d", &arr[i]);
    }
    for(int i = 0; i <= n - 1; i++){
        if(arr[i] == x){
            printf("%d ", i + 1);
        }
    }
    for(int i = 0; i < n - 1; i++){
        for(int j = i + 1; j < n; j++){
            if(arr[i] > arr[j]){
                temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }
    fp = fopen("sapxep.txt", "w+");
    for(int i = 0; i < n; i++){
        printf("%5d", arr[i]);
        if(arr[i] % 2 == 0){
            fprintf(fp, "%d ", arr[i]);
        }
    }
    fclose(fp);
    return 0;
}
