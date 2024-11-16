# 7 - Standard Template Library

#### **Comprehensive Guide to the Standard Template Library (STL) in C++**

The **Standard Template Library (STL)** is a powerful feature of C++ that provides a collection of ready-to-use templates for data structures, algorithms, and iterators. STL allows developers to use well-defined and efficient data handling tools without reinventing the wheel.

***

#### **Concept Outline**

```
STL (Standard Template Library) in C++
│
├── What is STL?
│   ├── Definition of STL in C++
│   ├── A Collection of Template Classes and Functions
│   ├── Provides Common Data Structures and Algorithms
│   ├── Promotes Code Reusability and Efficiency
│   └── Key Advantage: Generic Programming Using Templates
│
├── Key Components of STL
│   ├── Containers
│   │   ├── Store and Manage Data
│   │   ├── Various Types for Different Data Storage Needs
│   │   └── Examples: `vector`, `list`, `map`
│   ├── Iterators
│   │   ├── Provides Access to Elements of Containers
│   │   ├── Allows Sequential Traversal of Containers
│   │   └── Examples: `begin()`, `end()`, `next()`
│   ├── Algorithms
│   │   ├── Predefined Algorithms for Operations on Containers
│   │   ├── Examples: Sorting, Searching, Modifying Sequences
│   │   └── Designed to Work with Iterators
│   └── Functors
│       ├── Objects that Can Be Called Like Functions
│       └── Used to Customize Algorithms
│
├── STL Containers
│   ├── Sequence Containers
│   │   ├── Containers that Store Elements in a Linear Sequence
│   │   ├── Elements can Be Accessed in Sequence
│   │   ├── Examples: `vector`, `deque`, `list`
│   │   ├── `vector`
│   │   │   ├── Dynamic Array
│   │   │   ├── Fast Access by Index
│   │   │   ├── Supports Efficient Insertion and Deletion at End
│   │   │   └── Example Use Case: Storing a List of Numbers
│   │   ├── `deque`
│   │   │   ├── Double-Ended Queue
│   │   │   ├── Allows Fast Insertions/Deletions at Both Ends
│   │   │   └── Example Use Case: Queue with Push/Pop from Both Ends
│   │   ├── `list`
│   │   │   ├── Doubly Linked List
│   │   │   ├── Efficient Insertions/Deletions Anywhere
│   │   │   └── Example Use Case: List of Dynamic Elements with Frequent Insertions
│   ├── Associative Containers
│   │   ├── Containers that Store Data in Sorted Order (Based on Keys)
│   │   ├── Examples: `set`, `map`, `multiset`, `multimap`
│   │   ├── `set`
│   │   │   ├── Stores Unique Elements in Sorted Order
│   │   │   └── Example Use Case: Unique Sorted Data
│   │   ├── `map`
│   │   │   ├── Stores Key-Value Pairs in Sorted Order by Key
│   │   │   └── Example Use Case: Dictionary or Key-Value Pair Data
│   │   ├── `multiset`
│   │   │   ├── Stores Duplicate Elements in Sorted Order
│   │   │   └── Example Use Case: Count Occurrences of Elements
│   │   ├── `multimap`
│   │   │   ├── Stores Key-Value Pairs with Duplicate Keys
│   │   │   └── Example Use Case: Multi-Key Dictionary Data
│   ├── Unordered Containers
│   │   ├── Containers that Store Data in Unordered Fashion Using Hashing
│   │   ├── Faster Average Search/Insert Time Compared to Sorted Containers
│   │   ├── Examples: `unordered_set`, `unordered_map`
│   │   ├── `unordered_set`
│   │   │   ├── Stores Unique Elements in No Specific Order
│   │   │   └── Example Use Case: Fast Membership Testing (contains)
│   │   ├── `unordered_map`
│   │   │   ├── Stores Key-Value Pairs in No Specific Order (Using Hashing)
│   │   │   └── Example Use Case: Fast Lookup of Key-Value Pairs
│   ├── Container Adaptors
│   │   ├── Containers That Adapt the Interface of Other Containers
│   │   ├── Provide Specialized Behaviors (Stack, Queue)
│   │   ├── Examples: `stack`, `queue`, `priority_queue`
│   │   ├── `stack`
│   │   │   ├── LIFO (Last In, First Out) Data Structure
│   │   │   └── Example Use Case: Expression Evaluation
│   │   ├── `queue`
│   │   │   ├── FIFO (First In, First Out) Data Structure
│   │   │   └── Example Use Case: Task Scheduling
│   │   ├── `priority_queue`
│   │   │   ├── Stores Elements in a Sorted Order with Fast Access to Highest Priority Element
│   │   │   └── Example Use Case: Task Scheduling with Priorities
│
├── STL Iterators
│   ├── Definition and Purpose
│   │   ├── Abstract Object Used to Access and Traverse the Elements of a Container
│   │   └── Supports Standardized Iteration Syntax
│   ├── Input and Output Iterators
│   │   ├── Input Iterator: Reads Data from a Container
│   │   ├── Output Iterator: Writes Data to a Container
│   │   └── Example Use Case: Iterating through an Array with Input and Output Iterators
│   ├── Forward, Bidirectional, and Random Access Iterators
│   │   ├── Forward Iterator: Can Move in One Direction (e.g., `list`, `forward_list`)
│   │   ├── Bidirectional Iterator: Can Move in Both Directions (e.g., `set`, `map`)
│   │   ├── Random Access Iterator: Can Move Arbitrarily Across Containers (e.g., `vector`, `deque`)
│   │   └── Example Use Case: Iterating through a `vector` with Random Access Iterators
│
├── STL Algorithms
│   ├── Definition and Importance
│   │   ├── Predefined Operations That Can Be Performed on Containers
│   │   ├── Designed to Be Used with Iterators
│   │   └── Enhances Code Reusability and Efficiency
│   ├── Sorting and Searching
│   │   ├── `sort()`: Sorts Elements in a Container
│   │   ├── `binary_search()`: Searches for an Element in a Sorted Container
│   │   └── Example Use Case: Sorting a `vector` of Numbers Using `sort()`
│   ├── Modifying Sequence Algorithms
│   │   ├── `fill()`: Fills a Range of Elements with a Value
│   │   ├── `reverse()`: Reverses the Order of Elements
│   │   ├── `replace()`: Replaces Elements with a Specific Value
│   │   └── Example Use Case: Modifying a `vector` Using `fill()` and `reverse()`
│   ├── Non-Modifying Sequence Algorithms
│   │   ├── `find()`: Finds an Element in a Container
│   │   ├── `count()`: Counts Occurrences of a Value in a Container
│   │   ├── `equal()`: Compares Two Sequences for Equality
│   │   └── Example Use Case: Finding an Element in a `list` Using `find()`
│   ├── Utility Algorithms
│   │   ├── `swap()`: Swaps Values of Two Variables
│   │   ├── `min()` and `max()`: Finds the Minimum and Maximum of Two Values
│   │   └── Example Use Case: Swapping Two Elements in a `vector` Using `swap()`
│
└── Example: Implementing STL Containers and Algorithms
    ├── Example 1: Using `vector` to Store and Sort Integers
    ├── Example 2: Using `map` to Count Word Frequency in a Text
    └── Example 3: Using `priority_queue` for Task Scheduling with Priorities

```



***

#### **1. What is STL?**

The **Standard Template Library (STL)** is a library of template classes and functions, providing general-purpose, reusable algorithms and data structures. It supports common data handling tasks like sorting, searching, and manipulating sequences of data. STL is crucial for C++ development as it promotes code reuse, consistency, and efficiency.

***

#### **2. Key Components of STL**

The STL is composed of three core components:

1. **Containers**: Store data (e.g., arrays, lists, queues).
2. **Iterators**: Act as pointers to elements in the containers.
3. **Algorithms**: Perform operations on the data (e.g., sorting, searching).

These components together provide a foundation for handling data in a flexible and efficient way.

***

#### **3. STL Containers**

**Containers** are the objects that store data. STL provides several container types, each with different properties to suit various use cases.

**3.1 Sequence Containers**

**Sequence containers** store elements in a linear sequence.

1.  **`vector`**:

    * A dynamic array that can resize itself automatically when elements are added or removed.
    * Fast random access and amortized constant time insertion at the end.

    ```cpp
    #include <iostream>
    #include <vector>

    int main() {
        std::vector<int> vec = {1, 2, 3, 4};
        vec.push_back(5);
        
        for (int val : vec) {
            std::cout << val << " ";
        }
        return 0;
    }
    ```
2.  **`deque`**:

    * A double-ended queue that allows insertion and deletion at both ends.

    ```cpp
    #include <iostream>
    #include <deque>

    int main() {
        std::deque<int> dq = {1, 2, 3};
        dq.push_front(0);  // Insert at the beginning
        dq.push_back(4);   // Insert at the end

        for (int val : dq) {
            std::cout << val << " ";
        }
        return 0;
    }
    ```
3.  **`list`**:

    * A doubly linked list, where each element points to the next and the previous element.
    * Provides fast insertions/deletions at both ends or in the middle.

    ```cpp
    #include <iostream>
    #include <list>

    int main() {
        std::list<int> lst = {1, 2, 3};
        lst.push_back(4);  // Insert at the end
        lst.push_front(0); // Insert at the beginning

        for (int val : lst) {
            std::cout << val << " ";
        }
        return 0;
    }
    ```

***

**3.2 Associative Containers**

Associative containers store key-value pairs and automatically sort them based on the key.

1.  **`set`**:

    * A container that stores unique elements in sorted order.

    ```cpp
    #include <iostream>
    #include <set>

    int main() {
        std::set<int> s = {1, 2, 3, 4};
        s.insert(5);  // Insert an element

        for (int val : s) {
            std::cout << val << " ";
        }
        return 0;
    }
    ```
2.  **`map`**:

    * Stores key-value pairs in sorted order by key.

    ```cpp
    #include <iostream>
    #include <map>

    int main() {
        std::map<int, std::string> m;
        m[1] = "One";
        m[2] = "Two";

        for (const auto& pair : m) {
            std::cout << pair.first << ": " << pair.second << std::endl;
        }
        return 0;
    }
    ```
3. **`multiset` and `multimap`**:
   * Similar to `set` and `map`, but allow multiple elements with the same key.

***

**3.3 Unordered Containers**

Unordered containers store elements in no particular order, but they offer fast lookup using **hashing**.

1.  **`unordered_set`**:

    * A hash-based implementation of `set`.

    ```cpp
    #include <iostream>
    #include <unordered_set>

    int main() {
        std::unordered_set<int> uset = {1, 2, 3};
        uset.insert(4);

        for (int val : uset) {
            std::cout << val << " ";
        }
        return 0;
    }
    ```
2. **`unordered_map`**:
   * A hash-based implementation of `map`.

***

**3.4 Container Adaptors**

Adaptors provide restricted interfaces for underlying containers.

1.  **`stack`**:

    * A LIFO (Last-In-First-Out) data structure.

    ```cpp
    #include <iostream>
    #include <stack>

    int main() {
        std::stack<int> stk;
        stk.push(10);
        stk.push(20);

        std::cout << "Top element: " << stk.top() << std::endl;
        return 0;
    }
    ```
2. **`queue`**:
   * A FIFO (First-In-First-Out) data structure.
3. **`priority_queue`**:
   * A heap-based priority queue.

***

#### **4. STL Iterators**

**Iterators** are used to point to elements of a container. They provide a way to traverse the elements of a container, similar to pointers.

* **Input Iterators**: Read values from a container.
* **Output Iterators**: Write values to a container.
* **Forward Iterators**: Traverse forward through a container.
* **Bidirectional Iterators**: Traverse both forward and backward.
* **Random Access Iterators**: Access any element directly.

Example with `vector` iterator:

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> vec = {1, 2, 3, 4};
    std::vector<int>::iterator it;

    for (it = vec.begin(); it != vec.end(); ++it) {
        std::cout << *it << " ";
    }
    return 0;
}
```

***

#### **5. STL Algorithms**

STL provides a variety of algorithms that can be used with containers. These algorithms operate via iterators.

1.  **Sorting**:

    ```cpp
    #include <algorithm>
    std::sort(vec.begin(), vec.end());
    ```
2.  **Searching**:

    ```cpp
    if (std::binary_search(vec.begin(), vec.end(), 3)) {
        std::cout << "Found 3!";
    }
    ```
3. **Modifying Algorithms**: `transform`, `replace`, `fill`, etc.
4. **Non-Modifying Algorithms**: `find`, `count`, `accumulate`, etc.

***

#### **6. Practical Examples and Use Cases**

* Using STL to manage complex data structures like graph representations (via `map` and `set`).
* Sorting large datasets with the highly optimized `sort` algorithm.
* Efficient lookup of values in a collection using `unordered_map`.

***

#### **7. Advantages of Using STL**

* **Efficiency**: STL algorithms and data structures are highly optimized.
* **Reusability**: Generic templates provide reusable code for different types.
* **Consistency**: Uniform interface across all containers and algorithms.
* **Simplicity**: STL abstracts the complexity of writing custom data structures and algorithms.

***

#### **8. Common Pitfalls and Best Practices**

* **Iterator Invalidations**: Be cautious when modifying containers as it might invalidate iterators.
* **Choosing the Right Container**: Always choose the container that best suits your needs (e.g., prefer `vector` over `list` when random access is important).
* **Understand Complexity**: Know the time complexity of operations for the container you are using.
