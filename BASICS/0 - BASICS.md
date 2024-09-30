# BASICS
1. [[1 - Comments]]
   - Why Comments are Useful ?
   - How Comments are Understood by the Compiler ?
   - Single-line comments (`//`)
   - Multi-line comments (`/* */`)
   [![Video Guide](https://img.youtube.com/vi/WM4tig_3QR4/maxresdefault.jpg)](https://youtu.be/WM4tig_3QR4?si=yuJYuLxKxZbkFKKZ)

2. [[2 - Tokens]]
   - Operator 
   - Constants 
   - String literals
   - Special Symbols
   - Keywords
   - Identifiers
   [![Video Guide](https://img.youtube.com/vi/ILZU6INJQhk/maxresdefault.jpg)](https://youtu.be/ILZU6INJQhk?si=VxXb21jk6dncLKkx)

3. [[3 - Variables]]
   - Declaration and initialization
   - Syntax
   - Variable types (local, global, static, register)
   - Constant variables (`const`, `constexpr`)
   - Type inference (`auto`, `decltype`)

4. [[4 - Datatypes & Literals]]
    What are Datatypes?
    Primitive Data Types in C++
    - Integer Types (`int`, `short`, `long`)
    - Floating-Point Types (`float`, `double`)
    - Character Type (`char`)
    - Boolean Type (`bool`)
    - Wide Character Type (`wchar_t`)
    - Void Type (`void`)
    User-Defined Data Types
    - `struct`, `enum`, `union`
    What are Literals?
    Types of Literals
    - Integer Literals
    - Floating-Point Literals
    - Character Literals
    - String Literals
    - Boolean Literals

2. [[5 - Namespace]]
    What is a Namespace?
    Why Use Namespaces?
    Declaring a Namespace
    Accessing Namespace Members
    - Using the `scope resolution (::)` operator
    - `using` directive
    - `using` declaration
    Nested Namespaces
    Anonymous (Unnamed) Namespaces
    Standard Namespace (`std`)

2. [[6 - Preprocessor Directives]]
    What is the Preprocessor?
    Common Preprocessor Directives
    - `#define`
    - `#include`
    - `#undef`
    - `#ifdef`, `#ifndef`, `#if`, `#else`, `#elif`, `#endif`
    - `#pragma`
    Conditional Compilation
    Macros vs. Inline Functions
    The Power of `#include` and Header Guards

2. [[7 - Input - Output]]
    Basic Console Input/Output
       - `std::cout` – Output
       - `std::cin` – Input
    Formatting Output
    - Manipulators (`std::endl`, `std::setw`, `std::fixed`)
    Handling Input Errors
    File Input/Output
    - File Streams (`std::ifstream`, `std::ofstream`, `std::fstream`)
    - String Streams (`std::stringstream`)

2. [[8 - Control Statements]]
    Conditional Statements
     - `if` Statement
     - `else` and `else if`
     - Ternary Operator (`?:`)
     - `switch` Statement
    Looping Constructs
    - `for` Loop
    - `while` Loop
    - `do-while` Loop
    Jump Statements
    - `break`
    - `continue`
    - `goto`

1. [[9 - Functions]]
    Function Declaration and Definition
    Function Parameters and Return Types
    Passing by Value vs Passing by Reference
    Default Arguments
    Inline Functions
    Function Overloading
    Recursion in Functions
    Lambda Functions (C++11 and Beyond)

2. [[10 - Pointers & References]]
    Pointers
    - Pointer Declaration
    - Dereferencing Pointers
    - Null Pointers
    - Pointer Arithmetic
    - Pointers and Arrays
    - Function Pointers
    - Dynamic Memory Management
    References
       - Reference Declaration
       - Differences Between Pointers and References
       - Reference as Function Parameters
       - Const References

2. [[11 - Arrays]]
    Array Declaration and Initialization
    Accessing Array Elements
    Multidimensional Arrays
    Arrays as Function Arguments
    Advantages and Limitations of Arrays
    Common Pitfalls with Arrays
    **Alternative Data Structures**: Vectors vs Arrays

2. [[12 - Strings]]
    C-style Strings (Character Arrays)
       - Declaration and Initialization
       - Common Operations on C-style Strings
       - Limitations of C-style Strings
    C++ Strings (`std::string`)
       - Declaration and Initialization
       - Common Operations on `std::string`
       - String Concatenation and Comparison
       - String Input and Output
    Converting Between C-style Strings and `std::string`

2. [[13 - Structure & Union]]
    Structures in C++
       - Declaration and Initialization
       - Accessing Structure Members
       - Structures with Functions
       - Structures and Memory Allocation
       - Nested Structures
    Unions in C++
       - Declaration and Initialization
       - Accessing Union Members
       - Union Memory Management
    Differences Between Structures and Unions

2. [[14 - Dynamic Memory Management]]
    What is Dynamic Memory Management?
    Static vs. Dynamic Memory
    Dynamic Memory Allocation in C++
    - `new` Operator
    - `delete` Operator
    Dynamic Arrays
    Memory Leaks and How to Avoid Them
    Smart Pointers: Modern C++ Memory Management
