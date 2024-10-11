Sure! Here’s a comprehensive guide to sorting algorithms in C++, covering their concepts, implementations, and complexity analysis.

---

# **Sorting Algorithms in C++**

Sorting algorithms are essential for organizing data in a specific order (ascending or descending). This guide covers the most commonly used sorting algorithms in C++, their implementations, and their time and space complexities.

## **1. Introduction to Sorting Algorithms**
Sorting algorithms can be categorized into two main types:
- **Comparison-Based Sorting**: Sorts elements by comparing them.
- **Non-Comparison-Based Sorting**: Sorts elements without comparisons, such as counting sort.

---

## **2. Common Sorting Algorithms**

### **2.1. Bubble Sort**
- **Concept**: Repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order.
- **Time Complexity**: 
  - Worst Case: O(n²)
  - Average Case: O(n²)
  - Best Case: O(n) (when the array is already sorted)
- **Space Complexity**: O(1) (in-place)

#### **Implementation**
```cpp
#include <iostream>
using namespace std;

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
            }
        }
    }
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(arr)/sizeof(arr[0]);
    bubbleSort(arr, n);
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

---

### **2.2. Selection Sort**
- **Concept**: Divides the array into a sorted and an unsorted region. It repeatedly selects the smallest (or largest) element from the unsorted region and moves it to the sorted region.
- **Time Complexity**: 
  - Worst Case: O(n²)
  - Average Case: O(n²)
  - Best Case: O(n²)
- **Space Complexity**: O(1) (in-place)

#### **Implementation**
```cpp
#include <iostream>
using namespace std;

void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        swap(arr[i], arr[minIndex]);
    }
}

int main() {
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr) / sizeof(arr[0]);
    selectionSort(arr, n);
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

---

### **2.3. Insertion Sort**
- **Concept**: Builds the sorted array one item at a time by comparing the current element to its predecessors and inserting it into the correct position.
- **Time Complexity**: 
  - Worst Case: O(n²)
  - Average Case: O(n²)
  - Best Case: O(n) (when the array is already sorted)
- **Space Complexity**: O(1) (in-place)

#### **Implementation**
```cpp
#include <iostream>
using namespace std;

void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

int main() {
    int arr[] = {12, 11, 13, 5, 6};
    int n = sizeof(arr) / sizeof(arr[0]);
    insertionSort(arr, n);
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

---

### **2.4. Merge Sort**
- **Concept**: A divide-and-conquer algorithm that divides the array into halves, sorts them, and then merges the sorted halves.
- **Time Complexity**: O(n log n) for all cases.
- **Space Complexity**: O(n) (not in-place)

#### **Implementation**
```cpp
#include <iostream>
using namespace std;

void merge(int arr[], int left, int mid, int right) {
    int n1 = mid - left + 1;
    int n2 = right - mid;
    int* L = new int[n1];
    int* R = new int[n2];

    for (int i = 0; i < n1; i++)
        L[i] = arr[left + i];
    for (int j = 0; j < n2; j++)
        R[j] = arr[mid + 1 + j];

    int i = 0, j = 0, k = left;
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            arr[k++] = L[i++];
        } else {
            arr[k++] = R[j++];
        }
    }

    while (i < n1) {
        arr[k++] = L[i++];
    }
    while (j < n2) {
        arr[k++] = R[j++];
    }

    delete[] L;
    delete[] R;
}

void mergeSort(int arr[], int left, int right) {
    if (left < right) {
        int mid = left + (right - left) / 2;
        mergeSort(arr, left, mid);
        mergeSort(arr, mid + 1, right);
        merge(arr, left, mid, right);
    }
}

int main() {
    int arr[] = {38, 27, 43, 3, 9, 82, 10};
    int n = sizeof(arr) / sizeof(arr[0]);
    mergeSort(arr, 0, n - 1);
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

---

### **2.5. Quick Sort**
- **Concept**: Another divide-and-conquer algorithm that selects a 'pivot' element and partitions the array into two sub-arrays according to whether the elements are less than or greater than the pivot.
- **Time Complexity**: 
  - Worst Case: O(n²)
  - Average Case: O(n log n)
  - Best Case: O(n log n)
- **Space Complexity**: O(log n) (in-place)

#### **Implementation**
```cpp
#include <iostream>
using namespace std;

int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = (low - 1);
    for (int j = low; j <= high - 1; j++) {
        if (arr[j] < pivot) {
            i++;
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i + 1], arr[high]);
    return (i + 1);
}

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    int arr[] = {10, 7, 8, 9, 1, 5};
    int n = sizeof(arr) / sizeof(arr[0]);
    quickSort(arr, 0, n - 1);
    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

---

### **3. Comparison of Sorting Algorithms**

| Sorting Algorithm | Time Complexity (Worst) | Time Complexity (Average) | Time Complexity (Best) | Space Complexity | Stable |
|-------------------|-------------------------|---------------------------|-------------------------|------------------|--------|
| Bubble Sort       | O(n²)                   | O(n²)                     | O(n)                    | O(1)             | Yes    |
| Selection Sort    | O(n²)                   | O(n²)                     | O(n²)                   | O(1)             | No     |
| Insertion Sort    | O(n²)                   | O(n²)                     | O(n)                    | O(1)             | Yes    |
| Merge Sort        | O(n log n)              | O(n log n)                | O(n log n)              | O(n)             | Yes    |
| Quick Sort        | O(n²)                   | O(n log n)                | O(n log n)              | O(log n)         | No     |

---

### **4. Conclusion**
Sorting algorithms are fundamental for data manipulation and organization.