Master Documentation Outline for C++

# [[0 - BASICS]]
1. Comments
   - Single-line comments (`//`)
   - Multi-line comments (`/* */`)
   - Best practices for code commenting

2. Tokens
   - Keywords
   - Identifiers
   - Constants
   - String literals
   - Operators
   - Punctuation marks (delimiters)

3. Variables
   - Declaration and initialization
   - Variable types (local, global, static, register)
   - Constant variables (`const`, `constexpr`)
   - Type inference (`auto`, `decltype`)

4. Datatypes and Literals
   - Primitive Data Types:
     - Integer types (`int`, `short`, `long`, `long long`)
     - Floating-point types (`float`, `double`, `long double`)
     - Character type (`char`)
     - Boolean type (`bool`)
   - Derived Data Types:
     - Arrays
     - Pointers
     - References
   - User-defined Data Types:
     - Enumerations (`enum`)
     - Structures
     - Unions
   - Literals:
     - Integer, floating-point, character, string, boolean literals
     - Escape sequences and special characters

5. Namespaces
    - Using and defining namespaces
    - Anonymous namespaces
    - `std` namespace and `using` keyword

6. Preprocessor Directives
    - `include`, `define`, `undef`, `ifdef`, `ifndef`, `pragma`
    - Macro functions and usage

7. Input/Output
   - Standard input/output (`cin`, `cout`)
   - Formatted I/O (`setw`, `setprecision`, `endl`)
   - File handling (`ifstream`, `ofstream`, `fstream`)
     - File modes and file streams
     - Reading from and writing to files

8. Control Statements
   - Conditional Statements:
     - `if`, `else`, `switch`
   - Loops:
     - `for`, `while`, `do-while`
     - Nested loops
   - Jump Statements:
     - `break`, `continue`, `goto`
     - `return`

9. Functions
   - Declaration and definition
   - Function arguments (by value, by reference)
   - Return types and return values
   - Default arguments
   - Function overloading
   - Recursion
   - Inline functions
   - Function pointers

10. Pointers & References
   - Pointer basics, dereferencing, null pointers
   - Pointer arithmetic
   - Void pointers, function pointers
   - Reference basics
   - Lvalue and Rvalue references (`&&`)

11. Arrays
   - Single-dimensional, multi-dimensional arrays
   - Passing arrays to functions
   - Array of pointers
   - Pointer arithmetic with arrays

12. Strings
    - C-style strings (`char[]`, `char*`)
    - `std::string` class
    - String manipulation (concatenation, comparison)
    - Conversion between C-style strings and `std::string`

13. Structures & Unions
    - Structure declaration and usage
    - Nested structures
    - `typedef` with structures
    - Unions, memory sharing in unions
    - Differences between structures and unions

14. Dynamic Memory Management
    - `new`, `delete`
    - `new[]`, `delete[]`
    - Memory leaks, dangling pointers
    - Smart pointers (`std::unique_ptr`, `std::shared_ptr`, `std::weak_ptr`)

# [[0 - CORE]]
1. Object-Oriented Programming (OOP)
   - Principles of OOP (Encapsulation, Abstraction, Inheritance, Polymorphism)
   - Benefits of OOP

2. Classes & Objects
   - Defining classes and creating objects
   - Access specifiers (`public`, `private`, `protected`)
   - Constructors and destructors
     - Default, parameterized, copy constructors
     - Destructor
   - Member functions (inline, constant, static)
   - `this` pointer
   - Friend functions and friend classes

3. Encapsulation
   - Data hiding with access specifiers
   - Importance of encapsulation in OOP

4. Abstraction
   - Abstract classes and pure virtual functions
   - Interfaces and real-world examples

5. Inheritance
   - Types of inheritance (single, multiple, multilevel, hierarchical, hybrid)
   - Constructor/destructor behavior in inheritance
   - Function overriding
   - Access control in inheritance (`public`, `protected`, `private`)
   - Virtual inheritance

6. Polymorphism
   - Compile-time Polymorphism:
     - Function overloading
     - Operator overloading
   - Run-time Polymorphism:
     - Virtual functions, overriding
     - Virtual destructors
     - Function pointers vs virtual functions
     - Pure virtual functions

7. Overloading
   - Function Overloading:
     - Rules and ambiguities in function overloading
   - Operator Overloading:
     - Overloading unary and binary operators
     - Overloading comparison, stream operators

8. Template Programming
   - Function templates and class templates
   - Template specialization (full and partial)
   - Variadic templates (C++11 onward)

9. Exception Handling
   - Basics of exception handling:
     - `try`, `catch`, `throw`
     - Custom exceptions
   - Standard exception classes:
     - `std::exception`, `std::runtime_error`, `std::logic_error`
   - Stack unwinding and rethrowing exceptions
   - `noexcept` specifier
# DSA
## [[0 - DATA STRUCTURES]]
   - Stack:
     - Concept, applications, and implementations (array, linked list)
     - STL stack (`std::stack`)
   - Queue:
     - Concept, applications, and implementations
     - Circular queue, double-ended queue (Deque)
     - STL queue (`std::queue`, `std::deque`)
   - Linked Lists:
     - Singly linked list, doubly linked list, circular linked list
     - Operations: insertion, deletion, traversal
   - Trees:
     - Binary trees, binary search trees (BST)
     - AVL trees, Red-Black trees
     - Tree traversal (in-order, pre-order, post-order)
     - Heaps (min-heap, max-heap)
     - Tries
   - Graphs:
     - Graph representation (adjacency matrix, adjacency list)
     - Graph traversal (BFS, DFS)
     - Weighted graphs, shortest path algorithms (Dijkstra, Bellman-Ford)
   - Hashing:
     - Hash tables, hash functions
     - Collision resolution (chaining, open addressing)
   - Sets and Maps:
     - `std::set`, `std::map`, `unordered_set`, `unordered_map`
     - Applications and operations
## [[0 - ALGORITHMS]]
   - Sorting Algorithms:
     - Bubble sort, selection sort, insertion sort
     - Quick sort, merge sort, heap sort
   - Searching Algorithms:
     - Linear search, binary search, hash-based search
   - Greedy Algorithms:
     - Coin change, fractional knapsack problem
   - Dynamic Programming:
     - Memoization vs tabulation
     - 0/1 knapsack, Fibonacci series
   - Backtracking:
     - N-Queens problem, Sudoku solver
   - Divide and Conquer:
     - Merge sort, quick sort, binary search
   - Graph Algorithms:
     - Minimum spanning tree (Kruskal, Prim)
     - Shortest path (Dijkstra, Bellman-Ford)
     - Topological sort

# Advanced C++
1. Memory Management
   - Memory layout (stack, heap, text, data segments)
   - Placement `new`
   - Custom memory allocators, pool allocation
   - Garbage collection techniques (manual, smart pointers)

2. Move Semantics and Rvalue References
   - Move constructor, move assignment operator
   - Move Semantics in Depth:
     - Copy vs Move semantics
     - When and why to use move semantics
   - Rvalue References:
     - Rvalue and Lvalue distinction
     - Rvalue reference applications in resource management
   - Perfect Forwarding:
     - Using `std::forward` and `std::move` to preserve value categories

3. Concurrency and Multithreading
   - Threads:
     - Creating and managing threads (`std::thread`)
     - Thread joining and detaching
   - Synchronization:
     - Mutex (`std::mutex`), `lock_guard`, `unique_lock`
     - Condition variables (`std::condition_variable`)
     - Deadlock and race conditions
   - Atomics:
     - Atomic variables (`std::atomic`)
   - Async and Future:
     - `std::async`, `std::promise`, `std::future`
     - Packaged task (`std::packaged_task`)

4. Lambda Expressions
   - Syntax and usage
   - Capturing variables (by value, by reference)
   - Generic lambdas (C++14 onward)

5. Type Traits and Metaprogramming  
   - Type Introspection:
     - `std::is_same`, `std::is_base_of`, `std::is_integral`, `std::is_pointer`, etc.
   - Type Manipulation:
     - `std::remove_reference`, `std::remove_pointer`, `std::add_const`, `std::decay`
   - Compile-time Programming with `constexpr`:
     - `constexpr` functions and variables
     - Differences between `const` and `constexpr`
   - Static Assertions (`static_assert`):
     - Compile-time validation and checks
     - Usage in templates and meta-programming
   - SFINAE (Substitution Failure Is Not An Error):
     - Concept and practical applications
     - Enabling/disabling functions via `std::enable_if`
   - Variadic Templates:
     - Concept and syntax
     - Recursive template expansion
     - Applications in generic programming

6. STL (Standard Template Library)
   - Overview of STL:
     - Benefits and advantages of STL in C++
     - Components of STL (Containers, Iterators, Algorithms, Function Objects)
   - Containers:
     - Sequence Containers:
       - `std::vector`, `std::deque`, `std::list`
       - Operations (insertion, deletion, traversal)
     - Associative Containers:
       - `std::set`, `std::map`, `std::multiset`, `std::multimap`
       - Ordered data storage, unique vs duplicate keys
     - Unordered Associative Containers:
       - `std::unordered_set`, `std::unordered_map`
       - Hashing and performance considerations
     - Container Adapters:
       - `std::stack`, `std::queue`, `std::priority_queue`
       - Usage and applications
   - Iterators:
     - Iterator types (input, output, forward, bidirectional, random access)
     - Iterator operations (`begin()`, `end()`, `advance()`, `distance()`, etc.)
   - STL Algorithms:
     - Sorting (`std::sort`, `std::stable_sort`)
     - Searching (`std::find`, `std::binary_search`)
     - Modifying sequences (`std::copy`, `std::fill`, `std::replace`)
     - Non-modifying sequence algorithms (`std::count`, `std::accumulate`)
     - Numeric algorithms (`std::inner_product`, `std::partial_sum`)
     - Lambda functions in STL algorithms
   - Function Objects (Functors):
     - Creating custom function objects
     - Using built-in function objects (`std::plus`, `std::minus`, `std::greater`)
     - Functors in algorithms

7. Smart Pointers (Advanced)
   - Types of Smart Pointers:
     - `std::unique_ptr`, `std::shared_ptr`, `std::weak_ptr`
   - Usage Scenarios:
     - Ownership models in C++
     - Avoiding memory leaks with smart pointers
   - Reference Counting and Weak References:
     - Circular references and solving them with `std::weak_ptr`

8. Design Patterns in C++ (Optional)
   - Creational Patterns:
     - Singleton Pattern:
       - Lazy vs eager initialization
       - Thread-safe Singleton
     - Factory Pattern:
       - Factory method, abstract factory
     - Builder Pattern:
       - Step-by-step construction of objects
   - Structural Patterns:
     - Adapter Pattern:
       - Interface conversion for compatibility
     - Decorator Pattern:
       - Adding functionality dynamically
     - Proxy Pattern:
       - Controlled access to objects
   - Behavioral Patterns:
     - Observer Pattern:
       - Implementing publisher-subscriber systems
     - Strategy Pattern:
       - Defining a family of algorithms
     - Command Pattern:
       - Encapsulating requests as objects

# Supplementary Topics
1. Inline Namespaces
   - Using inline namespaces for versioning
   - Compatibility management using namespaces

2. Typecasting in C++
   - C-style Casting vs C++ Typecasting:
     - `static_cast`, `dynamic_cast`, `const_cast`, `reinterpret_cast`
   - Safe Typecasting with `dynamic_cast`:
     - Type safety in polymorphic class hierarchies

3. Memory Models and Layout
   - Memory Segments:
     - Text, data, stack, heap segments
   - Manual Memory Management:
     - Allocating and freeing memory manually (`malloc`, `free`, `new`, `delete`)
   - Memory Leaks and Debugging:
     - Tools and techniques to detect memory leaks (Valgrind, etc.)

4. Debugging Techniques and Tools
   - Basic Debugging Concepts:
     - Breakpoints, step-through debugging
     - Watch variables and call stacks
   - Tools for Debugging:
     - GDB, Valgrind, AddressSanitizer
   - Logging Best Practices:
     - Using logging libraries (`spdlog`, `log4cxx`, etc.)
     - Log levels and performance considerations


C++ Revolutions: Playlist 🔗
mantavyam@outlook.com