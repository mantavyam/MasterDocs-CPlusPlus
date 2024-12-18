# 14 - Dynamic Memory Management

#### **Guide to Dynamic Memory Management in C++**

In C++, **dynamic memory management** is a powerful feature that allows developers to allocate and deallocate memory during runtime, giving programs the ability to use memory efficiently and handle larger data sets when needed. This guide will take you through the fundamentals of dynamic memory, how to use it in C++, and best practices for writing efficient code.

***

#### **Concept Outline**

```
Dynamic Memory Management in C++
│
├── What is Dynamic Memory Management?
│   ├── Definition of Dynamic Memory Management
│   ├── Importance of Dynamic Memory in C++
│   │   ├── Efficient Memory Usage
│   │   ├── Memory Allocation at Runtime
│   │   └── Flexibility in Allocating Memory for Variable-Sized Data
│   ├── When to Use Dynamic Memory Management
│   │   ├── Scenarios Requiring Variable-Sized Data Structures
│   │   ├── Memory Allocation During Runtime
│   │   └── Avoiding Fixed Memory Allocation Limits
│   └── Types of Memory in C++
│       ├── Static Memory
│       ├── Stack Memory
│       └── Heap Memory (Dynamic Memory)
│
├── Static vs. Dynamic Memory
│   ├── Static Memory
│   │   ├── Memory Allocation at Compile-Time
│   │   ├── Fixed Size, Fixed Lifetime
│   │   ├── Example: Local Variables
│   │   └── Benefits and Limitations of Static Memory
│   ├── Dynamic Memory
│   │   ├── Memory Allocation at Runtime
│   │   ├── Flexible Size and Lifetime
│   │   ├── Example: Memory for Data Structures (e.g., dynamic arrays, linked lists)
│   │   └── Benefits and Limitations of Dynamic Memory
│   └── Key Differences
│       ├── Memory Allocation Timing
│       ├── Lifetime of Memory
│       └── Flexibility in Allocation Size
│
├── Dynamic Memory Allocation in C++
│   ├── What is Dynamic Memory Allocation?
│   │   ├── Allocating Memory During Program Execution
│   │   ├── Memory Managed by the Heap
│   │   ├── Flexibility to Allocate Memory for Large or Variable Data
│   │   └── Importance of Proper Memory Management
│   ├── `new` Operator
│   │   ├── Syntax for Allocating Memory with `new`
│   │   ├── Example: Allocating a Single Object
│   │   ├── Example: Allocating an Array of Objects
│   │   └── Allocating Memory for Pointers
│   ├── `delete` Operator
│   │   ├── Syntax for Releasing Memory with `delete`
│   │   ├── Example: Deleting a Single Object
│   │   ├── Example: Deleting an Array of Objects with `delete[]`
│   │   └── Importance of Deleting Dynamically Allocated Memory
│   ├── Memory Alignment and Padding
│   │   ├── How Memory is Allocated and Organized
│   │   ├── Alignment Restrictions
│   │   └── Example: Viewing the Size and Alignment of Objects with `sizeof()`
│
├── Dynamic Arrays
│   ├── What Are Dynamic Arrays?
│   │   ├── Arrays with Size Determined at Runtime
│   │   ├── Allocating Arrays with `new` Operator
│   │   └── Flexibility to Change the Array Size Dynamically
│   ├── Example: Allocating a Dynamic Array of Integers
│   ├── Resizing Dynamic Arrays
│   │   ├── Manually Resizing Arrays by Allocating New Memory
│   │   ├── Using `std::vector` for Resizable Arrays
│   │   └── Example: Handling Resizing and Reallocation of Arrays
│   ├── Deallocating Dynamic Arrays
│   │   ├── Releasing Memory for Dynamic Arrays Using `delete[]`
│   │   └── Importance of Properly Deallocating Memory to Prevent Memory Leaks
│
├── Memory Leaks and How to Avoid Them
│   ├── What are Memory Leaks?
│   │   ├── Definition of Memory Leaks
│   │   ├── Occurs When Dynamically Allocated Memory is Not Freed
│   │   ├── Impact on Performance and System Resources
│   │   └── Example: Memory Leak Scenario
│   ├── Causes of Memory Leaks
│   │   ├── Not Calling `delete` After `new`
│   │   ├── Lost Pointers (Dereferencing after Deletion)
│   │   └── Forgetting to Release Memory in Loops or Functions
│   ├── How to Avoid Memory Leaks
│   │   ├── Always Pair `new` with `delete`
│   │   ├── Use Smart Pointers for Automatic Memory Management
│   │   └── Tools for Detecting Memory Leaks (e.g., Valgrind, AddressSanitizer)
│
├── Smart Pointers: Modern C++ Memory Management
│   ├── What are Smart Pointers?
│   │   ├── Definition of Smart Pointers in C++
│   │   ├── Automatic Memory Management with Smart Pointers
│   │   ├── Types of Smart Pointers: `std::unique_ptr`, `std::shared_ptr`, `std::weak_ptr`
│   │   └── Benefits Over Raw Pointers
│   ├── `std::unique_ptr`
│   │   ├── Exclusive Ownership of Dynamically Allocated Memory
│   │   ├── Syntax for Declaring and Using `unique_ptr`
│   │   ├── Automatic Deallocation When the Pointer Goes Out of Scope
│   │   └── Example: Using `std::unique_ptr` for Dynamic Memory Management
│   ├── `std::shared_ptr`
│   │   ├── Shared Ownership of Dynamically Allocated Memory
│   │   ├── Reference Counting Mechanism
│   │   ├── Syntax for Declaring and Using `shared_ptr`
│   │   └── Example: Using `std::shared_ptr` for Shared Ownership of Resources
│   ├── `std::weak_ptr`
│   │   ├── Non-owning Weak Reference to Memory Managed by `shared_ptr`
│   │   ├── Breaking Circular References Between `shared_ptr` Instances
│   │   └── Example: Using `std::weak_ptr` to Avoid Cyclic Dependencies
│   ├── When to Use Smart Pointers
│   │   ├── Replacing Raw Pointers with Smart Pointers for Automatic Cleanup
│   │   └── Ensuring Proper Memory Management with Multiple Ownership Scenarios
│   └── Best Practices for Smart Pointers
│       ├── Use `std::unique_ptr` for Single Ownership
│       ├── Use `std::shared_ptr` for Shared Ownership
│       └── Avoid Raw Pointers When Possible
│
└── Advanced Topics in Dynamic Memory Management
    ├── Memory Pools
    │   ├── What are Memory Pools?
    │   ├── Allocating Memory in Blocks for Efficiency
    │   └── Use Case: Custom Allocators for Performance in High-demand Systems
    ├── RAII (Resource Acquisition Is Initialization)
    │   ├── Ensuring Automatic Resource Cleanup with Object Destruction
    │   ├── Using RAII in Memory Management
    │   └── Example: Implementing RAII for File and Memory Resources
    ├── Custom Memory Allocators
    │   ├── Implementing Custom Memory Management for Performance
    │   └── Example: Creating a Simple Custom Allocator for Small Objects
    └── Garbage Collection (GC) in C++
        ├── What is Garbage Collection?
        ├── Why C++ Doesn't Have Built-in GC (Manual Memory Management)
        ├── Third-Party Libraries for Garbage Collection
        └── Example: Integrating Garbage Collection in C++ Projects

```



***

#### **1. What is Dynamic Memory Management?**

**Dynamic memory management** refers to the process of allocating and freeing memory at runtime, instead of at compile-time. This allows programs to handle variable amounts of data that can grow or shrink during execution, which is essential for applications like:

* **Data structures** that change size (e.g., linked lists, trees, graphs)
* **Handling large data sets** where the size isn't known beforehand
* **Managing resources like files and network connections**

***

#### **2. Static vs. Dynamic Memory**

**Static Memory**

* **Allocated at compile-time**: The memory size for variables, arrays, etc., is fixed before the program runs.
* **Lifetime**: Exists for the entire duration of the program.
* **Scope**: Local or global, depending on where it's declared.

**Example**:

```cpp
int arr[100];  // Static array, size is fixed at compile-time
```

**Dynamic Memory**

* **Allocated at runtime**: Memory is allocated only when needed, and the size can vary based on user input or runtime conditions.
* **Lifetime**: Can be managed by the developer; exists until explicitly deallocated.

**Example**:

```cpp
int* arr = new int[100];  // Dynamic array, size can be determined at runtime
```

***

#### **3. Dynamic Memory Allocation in C++**

In C++, dynamic memory is managed using the `new` and `delete` operators.

**`new` Operator**

The `new` operator dynamically allocates memory and returns a pointer to the allocated memory block. This memory must be deallocated manually using the `delete` operator to avoid memory leaks.

**Syntax**:

```cpp
datatype* pointer = new datatype;
```

**Example**:

```cpp
int* p = new int;  // Allocates memory for an integer
*p = 10;
std::cout << *p;   // Output: 10
```

For allocating arrays dynamically:

```cpp
int* arr = new int[5];  // Allocates memory for an array of 5 integers
arr[0] = 1;
std::cout << arr[0];  // Output: 1
```

**`delete` Operator**

The `delete` operator is used to free the memory allocated by `new`. It is crucial to call `delete` after memory is no longer needed to avoid memory leaks.

**Syntax**:

```cpp
delete pointer;  // For single variables
delete[] pointer;  // For arrays
```

**Example**:

```cpp
int* p = new int;
delete p;  // Deallocates memory for the integer
```

For arrays:

```cpp
int* arr = new int[5];
delete[] arr;  // Deallocates memory for the array
```

**Key Point**: Always use `delete[]` for arrays to ensure the entire block of memory is freed.

***

#### **4. Dynamic Arrays**

Dynamic arrays allow you to allocate memory for arrays during runtime, which is useful when the size of the array isn't known in advance.

**Example**:

```cpp
int size;
std::cin >> size;  // Get size from user
int* arr = new int[size];  // Dynamically allocate array
for (int i = 0; i < size; ++i) {
    std::cin >> arr[i];  // Populate array
}
delete[] arr;  // Free the memory when done
```

This flexibility is crucial in situations where user input or other runtime data dictates how much memory is needed.

***

#### **5. Memory Leaks and How to Avoid Them**

A **memory leak** occurs when memory that is dynamically allocated is not properly deallocated, leading to wasted memory that the program can no longer use. Over time, this can exhaust system memory and cause the program to crash.

**Common Causes**:

* Forgetting to call `delete` after `new`.
* Overwriting a pointer before deallocating the memory it points to.

**Example**:

```cpp
int* ptr = new int(10);
ptr = new int(20);  // Memory for the first allocation is leaked
```

To avoid memory leaks:

* Always call `delete` after `new`.
* Use **smart pointers** (discussed below).

***

#### **6. Smart Pointers: Modern C++ Memory Management**

C++11 introduced **smart pointers**, which automatically manage memory for you. Smart pointers automatically deallocate memory when they go out of scope, which helps prevent memory leaks.

Types of smart pointers:

*   **`std::unique_ptr`**: Manages exclusive ownership of memory. Memory is freed when the pointer is destroyed.

    **Example**:

    ```cpp
    std::unique_ptr<int> p = std::make_unique<int>(10);  // No need to call delete
    ```
*   **`std::shared_ptr`**: Manages shared ownership of memory. Multiple shared pointers can point to the same memory, and it's freed only when the last shared pointer is destroyed.

    **Example**:

    ```cpp
    std::shared_ptr<int> p1 = std::make_shared<int>(10);
    std::shared_ptr<int> p2 = p1;  // Shared ownership
    ```
* **`std::weak_ptr`**: Works with `std::shared_ptr` to break circular references.

Smart pointers should be your go-to choice in modern C++ programs, as they significantly reduce the risk of memory leaks and dangling pointers.

***

#### **7. Best Practices for Using Dynamic Memory**

1. **Prefer Smart Pointers**: In most cases, use smart pointers (`std::unique_ptr`, `std::shared_ptr`) to manage dynamic memory. They provide automatic memory management and prevent leaks.
2. **Avoid Raw Pointers When Possible**: Raw pointers (`new`, `delete`) require manual memory management, which can be error-prone. Use them only if necessary, and always ensure you `delete` them.
3. **Use `new` and `delete` in Pairs**: Always match each `new` with a corresponding `delete` to avoid memory leaks.
4.  **Check for `nullptr`**: When allocating memory, check if the pointer is `nullptr` to avoid dereferencing invalid pointers.

    **Example**:

    ```cpp
    int* ptr = new(std::nothrow) int;  // Prevents throwing exception if allocation fails
    if (!ptr) {
        std::cout << "Memory allocation failed.";
    }
    ```
5. **Don’t Forget to Use `delete[]` for Arrays**: Remember to use `delete[]` when deallocating memory for arrays to avoid partial deallocation.

***

#### **8. Thought-Provoking Questions**

1. **When should you use dynamic memory instead of static memory in a program?**
   * **Hint**: Think about use cases where the amount of memory isn’t known at compile-time.
2. **How do smart pointers prevent memory leaks, and what are the trade-offs of using them?**
   * **Hint**: Consider how smart pointers handle ownership and deallocation, but also think about potential overhead or complexity.
3. **What are the potential risks of using raw pointers and manual memory management, and how can you mitigate them in real-world projects?**
   * **Hint**: Think about dangling pointers, memory leaks, and how modern C++ features can solve these issues.
4. **How can dynamic memory allocation improve the performance of certain algorithms or data structures?**
   * **Hint**: Consider the flexibility dynamic memory offers, especially for data structures like linked lists and trees.

***

#### **Conclusion**

Dynamic memory management in C++ gives you the flexibility to allocate and free memory at runtime, which is crucial for writing efficient and scalable programs. While managing memory manually with `new` and `delete` is powerful, it can also be risky if not handled properly, leading to memory leaks or crashes.

Modern C++ offers a safer alternative with **smart pointers**, which automate memory management and greatly reduce the risk of memory-related bugs. Mastering dynamic memory management will allow you to build more complex and efficient programs, giving you greater control over how your applications use resources.

By understanding and practicing dynamic memory management techniques, you will gain the ability to write efficient, high-performance code that scales well for real-world applications.
