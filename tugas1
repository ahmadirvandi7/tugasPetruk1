#include <iostream>
#include <chrono>
#include <algorithm>

// Bubble Sort
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                std::swap(arr[j], arr[j+1]);
            }
        }
    }
}

// Insertion Sort
void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}

// Selection Sort
void selectionSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        int min_idx = i;
        for (int j = i+1; j < n; j++) {
            if (arr[j] < arr[min_idx]) {
                min_idx = j;
            }
        }
        std::swap(arr[min_idx], arr[i]);
    }
}

// Merge Sort helper function to merge two subarrays
void merge(int arr[], int l, int m, int r) {
    int n1 = m - l + 1;
    int n2 = r - m;
    int L[n1], R[n2];
    for (int i = 0; i < n1; i++) {
        L[i] = arr[l + i];
    }
    for (int i = 0; i < n2; i++) {
        R[i] = arr[m + 1 + i];
    }
    int i = 0, j = 0, k = l;
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            arr[k] = L[i];
            i++;
        } else {
            arr[k] = R[j];
            j++;
        }
        k++;
    }
    while (i < n1) {
        arr[k] = L[i];
        i++;
        k++;
    }
    while (j < n2) {
        arr[k] = R[j];
        j++;
        k++;
    }
}

// Merge Sort
void mergeSort(int arr[], int l, int r) {
    if (l < r) {
        int m = l + (r - l) / 2;
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
        merge(arr, l, m, r);
    }
}

// Quick Sort helper function to partition the array
int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = (low - 1);
    for (int j = low; j <= high - 1; j++) {
        if (arr[j] < pivot) {
            i++;
            std::swap(arr[i], arr[j]);
        }
    }
    std::swap(arr[i + 1], arr[high]);
    return (i + 1);
}

// Quick Sort
void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    const int n = 10;
    int arr[n] = {64, 34, 25, 12, 22, 11, 90, 24, 45, 67};
    
    // Bubble Sort
    int bubbleArr[n];
    std::copy(arr, arr + n, bubbleArr);
    auto start = std::chrono::high_resolution_clock::now();
    bubbleSort(bubbleArr, n);
    auto end = std::chrono::high_resolution_clock::now();
    std::chrono::duration<double, std::micro> bubbleDuration = end - start;
    std::cout << "Bubble Sort Duration: " << bubbleDuration.count() << " microseconds\n";

    // Insertion Sort
    int insertionArr[n];
    std::copy(arr, arr + n, insertionArr);
    start = std::chrono::high_resolution_clock::now();
    insertionSort(insertionArr, n);
    end = std::chrono::high_resolution_clock::now();
    std::chrono::duration<double, std::micro> insertionDuration = end - start;
    std::cout << "Insertion Sort Duration: " << insertionDuration.count() << " microseconds\n";

    // Selection Sort
    int selectionArr[n];
    std::copy(arr, arr + n, selectionArr);
    start = std::chrono::high_resolution_clock::now();
    selectionSort(selectionArr, n);
    end = std::chrono::high_resolution_clock::now();
    std::chrono::duration<double, std::micro> selectionDuration = end - start;
    std::cout << "Selection Sort Duration: " << selectionDuration.count() << " microseconds\n";

    // Merge Sort
    int mergeArr[n];
    std::copy(arr, arr + n, mergeArr);
    start = std::chrono::high_resolution_clock::now();
    mergeSort(mergeArr, 0, n-1);
    end = std::chrono::high_resolution_clock::now();
    std::chrono::duration<double, std::micro> mergeDuration = end - start;
    std::cout << "Merge Sort Duration: " << mergeDuration.count() << " microseconds\n";

    // Quick Sort
    int quickArr[n];
    std::copy(arr, arr + n, quickArr);
    start = std::chrono::high_resolution_clock::now();
    quickSort(quickArr, 0, n-1);
    end = std::chrono::high_resolution_clock::now();
    std::chrono::duration<double, std::micro> quickDuration = end - start;
    std::cout << "Quick Sort Duration: " << quickDuration.count() << " microseconds\n";

    return 0;
}
