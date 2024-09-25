# BASICS
1. [[1 - Comments]]
   - Single-line comments (`//`)
   - Multi-line comments (`/* */`)
   - Best practices for code commenting

2. [[2 - Tokens]]
   - Keywords
   - Identifiers
   - Constants
   - String literals
   - Operators
   - Punctuation marks (delimiters)

3. [[3 - Variables]]
   - Declaration and initialization
   - Variable types (local, global, static, register)
   - Constant variables (`const`, `constexpr`)
   - Type inference (`auto`, `decltype`)

4. [[4 - Datatypes & Literals]]
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

5. [[5 - Namespace]]
    - Using and defining namespaces
    - Anonymous namespaces
    - `std` namespace and `using` keyword

6. [[6 - Preprocessor Directives]]
    - `include`, `define`, `undef`, `ifdef`, `ifndef`, `pragma`
    - Macro functions and usage

7. [[7 - Input - Output]]
   - Standard input/output (`cin`, `cout`)
   - Formatted I/O (`setw`, `setprecision`, `endl`)
   - File handling (`ifstream`, `ofstream`, `fstream`)
     - File modes and file streams
     - Reading from and writing to files

8. [[8 - Control Statements]]
   - Conditional Statements:
     - `if`, `else`, `switch`
   - Loops:
     - `for`, `while`, `do-while`
     - Nested loops
   - Jump Statements:
     - `break`, `continue`, `goto`
     - `return`

9. [[9 - Functions]]
   - Declaration and definition
   - Function arguments (by value, by reference)
   - Return types and return values
   - Default arguments
   - Function overloading
   - Recursion
   - Inline functions
   - Function pointers

10. [[10 - Pointers & References]]
   - Pointer basics, dereferencing, null pointers
   - Pointer arithmetic
   - Void pointers, function pointers
   - Reference basics
   - Lvalue and Rvalue references (`&&`)

11. [[11 - Arrays]]
   - Single-dimensional, multi-dimensional arrays
   - Passing arrays to functions
   - Array of pointers
   - Pointer arithmetic with arrays

12. [[12 - Strings]]
    - C-style strings (`char[]`, `char*`)
    - `std::string` class
    - String manipulation (concatenation, comparison)
    - Conversion between C-style strings and `std::string`

13. [[13 - Structure & Union]]
    - Structure declaration and usage
    - Nested structures
    - `typedef` with structures
    - Unions, memory sharing in unions
    - Differences between structures and unions

14. [[14 - Dynamic Memory Management]]
    - `new`, `delete`
    - `new[]`, `delete[]`
    - Memory leaks, dangling pointers
    - Smart pointers (`std::unique_ptr`, `std::shared_ptr`, `std::weak_ptr`)