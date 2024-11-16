# Datatypes Selection Guide

#### **When to Use Which Data Type?**

| **Category**                   | **Data Type**        | **When to Use**                                                              | **Key Parameters**                              | **Example Usage**                                               |
| ------------------------------ | -------------------- | ---------------------------------------------------------------------------- | ----------------------------------------------- | --------------------------------------------------------------- |
| **Primitive Types**            | `int`                | Use for general integer storage (whole numbers).                             | Size: 4 bytes, Signed, Range: depends on system | `int age = 25;`                                                 |
|                                | `short`              | Use for smaller integer values (when memory is limited).                     | Size: 2 bytes, Signed, Range: -32,768 to 32,767 | `short height = 150;`                                           |
|                                | `long`               | Use for larger integers.                                                     | Size: 4 or 8 bytes, Signed                      | `long population = 700000;`                                     |
|                                | `long long`          | Use for very large integers (requires large memory).                         | Size: 8 bytes, Signed                           | `long long bigNumber = 999999999999;`                           |
|                                | `unsigned int`       | Use for non-negative integer values.                                         | Size: 4 bytes, Unsigned, Range: 0 to max value  | `unsigned int count = 0;`                                       |
|                                | `float`              | Use for single-precision floating-point values.                              | Size: 4 bytes, Precision: 7 decimal digits      | `float price = 19.99f;`                                         |
|                                | `double`             | Use for double-precision floating-point values (default for floating-point). | Size: 8 bytes, Precision: 15 decimal digits     | `double temp = 23.456789;`                                      |
|                                | `long double`        | Use for extended precision floating-point numbers.                           | Size: 8-16 bytes, Higher precision than double  | `long double pi = 3.14159265358979L;`                           |
|                                | `char`               | Use for single character (ASCII).                                            | Size: 1 byte, Character (ASCII)                 | `char grade = 'A';`                                             |
|                                | `wchar_t`            | Use for wide characters (Unicode).                                           | Size: 2 or 4 bytes                              | `wchar_t symbol = L'Ω';`                                        |
|                                | `bool`               | Use for storing Boolean values (true or false).                              | Size: 1 byte, Values: true/false                | `bool isValid = true;`                                          |
|                                | `void`               | Use for functions that don’t return a value.                                 | No value type                                   | `void printMessage() {}`                                        |
|                                | `nullptr`            | Use for null pointer initialization.                                         | Null pointer constant                           | `int* ptr = nullptr;`                                           |
| **Derived Types**              | **Array**            | Use for storing multiple elements of the same type.                          | Size: Fixed number of elements, Indexed         | `int arr[5] = {1, 2, 3, 4, 5};`                                 |
|                                | **Pointer**          | Use for dynamic memory management or accessing memory locations.             | Stores memory addresses, Can be null            | `int* ptr = &x;`                                                |
|                                | **Reference**        | Use for passing variables by reference to avoid copies.                      | Refer to existing variable                      | `int& ref = x;`                                                 |
|                                | **Function Pointer** | Use for pointing to functions, useful for callback mechanisms.               | Points to functions with specific signature     | `void (*funcPtr)() = &functionName;`                            |
| **User-Defined Types**         | **Struct**           | Use for grouping related data of different types (complex data structures).  | Custom data types, Can contain multiple types   | `struct Car { string model; int year; };`                       |
|                                | **Union**            | Use when you need to store multiple data types in the same memory space.     | All members share same memory                   | `union Data { int i; float f; };`                               |
|                                | **Enum**             | Use for defining a set of named constants, making code more readable.        | Creates named constants                         | `enum Color { RED, GREEN, BLUE };`                              |
|                                | **Enum Class**       | Use for scoped and type-safe enumerations (C++11 and beyond).                | Scoped, Type-safe, More control                 | `enum class Direction { NORTH, SOUTH, EAST, WEST };`            |
|                                | **Typedef/using**    | Use to create type aliases, making complex type declarations simpler.        | Simplifies type names                           | `typedef unsigned long ulong;` or `using String = std::string;` |
| **Abstract Data Types (ADTs)** | **Stack**            | Use for LIFO (Last In, First Out) data storage.                              | Supports push/pop operations                    | `stack<int> s; s.push(10);`                                     |
|                                | **Queue**            | Use for FIFO (First In, First Out) data storage.                             | Supports enqueue/dequeue operations             | `queue<int> q; q.push(10);`                                     |
|                                | **List**             | Use when you need dynamic data storage that supports insertion/deletion.     | Supports fast insertion/deletion at both ends   | `list<int> lst; lst.push_back(10);`                             |
|                                | **Tree**             | Use for hierarchical data (parent-child relationships).                      | Efficient searching and sorting                 | `binary_tree<int> tree;`                                        |
|                                | **Graph**            | Use for complex networks of relationships.                                   | Suitable for networks, paths, and connectivity  | `graph<int> g; g.addEdge(1, 2);`                                |
|                                | **Hash Table**       | Use for fast lookup and retrieval of key-value pairs.                        | Constant time complexity for search/insert      | `unordered_map<int, string> map; map[1] = "apple";`             |

***

#### **When to Use Each Data Type:**

* **Primitive Data Types**: Used when you need simple, predefined types (integers, floating-point numbers, characters, etc.) for basic data manipulation.
* **Derived Data Types**: Used when you need to combine basic types to manage complex data structures like arrays, pointers, and references.
* **User-Defined Data Types**: Used when you need to design custom structures or types to model complex systems (using `struct`, `union`, `enum`, and `typedef`).
* **Abstract Data Types (ADTs)**: Used when you need to define specific data structures (like stacks, queues, trees, etc.) to efficiently organize and manipulate data.
