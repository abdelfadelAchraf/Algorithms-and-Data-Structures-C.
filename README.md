# **Algorithms and Data Structures in C**

Welcome to the **Algorithms and Data Structures Repository**! 🎉 This repository contains implementations of various algorithms and data structures written in the C programming language, designed to help you learn, practice, and improve your programming skills.

---

## **📚 Table of Contents**
- [Introduction](#introduction)
- [Folder Structure](#folder-structure)
- [Implemented Data Structures](#implemented-data-structures)
- [Implemented Algorithms](#implemented-algorithms)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [License](#license)

---

## **📖 Introduction**
This repository is a comprehensive collection of:
- **Common data structures** like arrays, linked lists, trees, graphs, etc.
- **Fundamental algorithms** such as sorting, searching, and traversal techniques.

Each implementation includes:
- A detailed explanation.
- Code with comments for better understanding.
- Examples and test cases.

---

## **📁 Folder Structure**
The repository is organized as follows:

```plaintext
📦 Algorithms-and-Data-Structures-C
 ├── README.md
 ├── arrays/
 │   ├── array_operations.c
 │   └── array_operations.h
 ├── linked_lists/
 │   ├── singly_linked_list.c
 │   └── doubly_linked_list.c
 ├── sorting/
 │   ├── bubble_sort.c
 │   ├── merge_sort.c
 │   └── quick_sort.c
 ├── searching/
 │   ├── linear_search.c
 │   └── binary_search.c
 ├── trees/
 │   ├── binary_tree.c
 │   └── binary_search_tree.c
 └── graphs/
     ├── adjacency_matrix.c
     └── adjacency_list.c

```
# Arrays in C

Arrays are one of the simplest and most widely used data structures in programming. They store a fixed-size sequential collection of elements of the same type.

## **Features of Arrays**
- Elements are stored in contiguous memory locations.
- They allow random access using an index.
- Useful for scenarios where the size of the data is known in advance.

---

## **Basic Operations**
1. **Traversal**: Access each element sequentially.
2. **Insertion**: Add an element at a specific position.
3. **Deletion**: Remove an element at a specific position.
4. **Search**: Find the index of an element.
5. **Update**: Modify the value of an element.

---

## **Implementation in C**
### **array_operations.c**
```c
#include <stdio.h>

// Function to traverse and print an array
void traverse(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}

// Function to insert an element into the array
int insert(int arr[], int size, int capacity, int element, int position) {
    if (size >= capacity) {
        printf("Insertion failed. Array is full.\n");
        return size;
    }
    for (int i = size; i > position; i--) {
        arr[i] = arr[i - 1];
    }
    arr[position] = element;
    return size + 1;
}

// Function to delete an element from the array
int delete (int arr[], int size, int position) {
    if (position >= size || position < 0) {
        printf("Invalid position.\n");
        return size;
    }
    for (int i = position; i < size - 1; i++) {
        arr[i] = arr[i + 1];
    }
    return size - 1;
}

int main() {
    int arr[10] = {1, 2, 3, 4, 5};
    int size = 5;
    int capacity = 10;

    printf("Original Array: ");
    traverse(arr, size);

    // Insert 99 at position 2
    size = insert(arr, size, capacity, 99, 2);
    printf("After Insertion: ");
    traverse(arr, size);

    // Delete element at position 3
    size = delete (arr, size, 3);
    printf("After Deletion: ");
    traverse(arr, size);

    return 0;
}

