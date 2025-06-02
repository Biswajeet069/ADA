#include <stdio.h>
#include<time.h>
void heapify(int arr[], int n, int i) {
    int largest = i;
    int left = 2 * i + 1;
    int right = 2 * i + 2;
    if (left < n && arr[left] > arr[largest])
        largest = left;
    if (right < n && arr[right] > arr[largest])
        largest = right;
    if (largest != i) {
        int temp = arr[i];
        arr[i] = arr[largest];
        arr[largest] = temp;
        heapify(arr, n, largest);
    }
}

void heapSort(int arr[], int n) {
    for (int i = n / 2 - 1; i >= 0; i--)
        heapify(arr, n, i);
    for (int i = n - 1; i > 0; i--) {
        int temp = arr[0];
        arr[0] = arr[i];
        arr[i] = temp;
        heapify(arr, i, 0);
    }
}

int main() {
    clock_t start,end;
    double timeused;
    int n, arr[100];
    printf("Enter the number of array elements:");
    scanf("%d", &n);
    printf("Enter array elements:");
    for (int i = 0; i < n; i++)
        scanf("%d", &arr[i]);
    
    start = clock();
    heapSort(arr, n);
    end = clock();
    timeused= ((double)(end-start))/CLOCKS_PER_SEC;

    printf("Array elements(sorted):");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);
    
    printf("\nTime taken : %f seconds",timeused);
    return 0;
}



O/P:
Enter the number of array elements:7
Enter array elements:3 5 4 7 9 2 12
Array elements(sorted):2 3 4 5 7 9 12 
Time taken : 0.000000 seconds
