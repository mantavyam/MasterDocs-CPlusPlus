# 4 - Datatypes

## **What are Data Types?**

**Definition of Data Types**

Data types in C++ define the type of data that a variable can hold. They specify the size and type of information that can be stored in a variable, such as integers, floating-point numbers, characters, and more. In essence, they inform the compiler how to interpret the value stored in a variable.

**Importance of Data Types in C++**

* **Memory Management**: Data types determine how much memory should be allocated for a variable.
* **Type Safety**: Ensures that the operations performed are appropriate for the data type.
* **Code Clarity**: Helps in understanding what kind of data a variable will hold, leading to more readable code.
* **Performance**: Optimizes operations since knowing the type of data allows the compiler to generate efficient machine code.

## **Categories of Data Types**

Data types in C++ are broadly categorized into:

1. **Primitive Data Types** (built-in types like `int`, `float`).
2. **Derived Data Types** (arrays, pointers, references, functions).
3. **User-Defined Data Types** (structs, unions, enums, classes).

{% hint style="info" %}
Refer to the page linked below to understand when to use which datatype. The page lists down scenarios for the use case of different datatypes.
{% endhint %}

{% content-ref url="datatypes-selection-guide.md" %}
[datatypes-selection-guide.md](datatypes-selection-guide.md)
{% endcontent-ref %}

**Memory Allocation for Data Types**

Each data type in C++ occupies a specific amount of memory:

* **int**: Typically 4 bytes.
* **double**: Usually 8 bytes.
* **char**: 1 byte.
* These sizes may vary depending on the system architecture and compiler.

### **Primitive Data Types in C++**

Primitive data types are the building blocks of data manipulation in C++. They are the most basic data types supported by the language.

**Integer Types**

Used to represent whole numbers, both positive and negative.

1. **`int`**:
   * Commonly used for general integer storage.
   * **Memory**: Typically 4 bytes.
   * **Range**: Depends on the compiler but usually `-2,147,483,648` to `2,147,483,647`.
   *   **Example**:

       ```cpp
       int age = 25;
       ```
2. **`short`**:
   * A smaller version of `int`, often 2 bytes.
   * **Range**: Typically `-32,768` to `32,767`.
   *   **Example**:

       ```cpp
       short height = 170;
       ```
3. **`long`**:
   * A larger integer type, at least 4 bytes, sometimes 8 bytes.
   *   **Example**:

       ```cpp
       long distance = 1234567890;
       ```
4. **`long long`**:
   * The largest integer type, often 8 bytes.
   *   **Example**:

       ```cpp
       long long bigNumber = 9223372036854775807;
       ```
5. **Unsigned Variants**:
   * These variants only store non-negative values, doubling the positive range.
   *   **Example**:

       ```cpp
       unsigned int score = 100;
       unsigned long long population = 8000000000;
       ```

**Floating-Point Types**

Used for numbers with decimal points (fractions).

1. **`float`**:
   * A single-precision floating-point.
   * **Memory**: Typically 4 bytes.
   *   **Example**:

       ```cpp
       float pi = 3.14f;
       ```
2. **`double`**:
   * A double-precision floating-point.
   * **Memory**: Typically 8 bytes.
   *   **Example**:

       ```cpp
       double largeValue = 2.718281828459045;
       ```
3. **`long double`**:
   * Extended precision floating-point, at least as precise as `double`.
   *   **Example**:

       ```cpp
       long double preciseValue = 3.1415926535897932384626L;
       ```

**Character Types**

Used to store individual characters.

1. **`char`**:
   * Stores a single character.
   * **Memory**: 1 byte.
   *   **Example**:

       ```cpp
       char initial = 'A';
       ```
2. **`wchar_t`**:
   * Used for wider characters, often for Unicode.
   * **Memory**: Typically 2 or 4 bytes.
   *   **Example**:

       ```cpp
       wchar_t wideChar = L'Ω';
       ```

**Boolean Type**

1. **`bool`**:
   * Represents true or false.
   * **Memory**: 1 byte.
   *   **Example**:

       ```cpp
       bool isActive = true;
       ```

**Void Type**

1. **`void`**:
   * Represents no type or absence of a value.
   * Commonly used for functions that do not return a value.
   *   **Example**:

       ```cpp
       void printMessage() {
           cout << "Hello, World!" << endl;
       }
       ```

***

### **Derived Data Types**

Derived data types are created using primitive data types. They provide ways to group or manipulate multiple values.

**Arrays**

A collection of elements of the same type stored in contiguous memory locations.

*   **Single-Dimensional Arrays**:

    ```cpp
    int numbers[5] = {1, 2, 3, 4, 5}; // Array of 5 integers
    ```
*   **Multi-Dimensional Arrays**:

    ```cpp
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    ```
*   **Array of Structures**:

    ```cpp
    struct Person {
        string name;
        int age;
    };

    Person group[3] = { {"Alice", 30}, {"Bob", 25}, {"Charlie", 35} };
    ```

**Pointers**

Variables that store the address of another variable.

*   **Pointer to Variable**:

    ```cpp
    int value = 42;
    int* ptr = &value; // Pointer to 'value'
    ```
*   **Pointer to Array**:

    ```cpp
    int numbers[3] = {10, 20, 30};
    int* arrPtr = numbers; // Points to the first element of the array
    ```
*   **Pointer to Function**:

    ```cpp
    void greet() {
        cout << "Hello, Function Pointer!" << endl;
    }
    void (*funcPtr)() = greet; // Pointer to a function
    funcPtr(); // Calls the function via the pointer
    ```

**References**

An alias for another variable.

*   **Reference to Variable**:

    ```cpp
    int x = 10;
    int& ref = x; // 'ref' is a reference to 'x'
    ref = 20;     // Now 'x' is also 20
    ```
*   **References vs Pointers**:

    | **Aspect**       | **Reference**                                  | **Pointer**                      |
    | ---------------- | ---------------------------------------------- | -------------------------------- |
    | **Nullability**  | Cannot be null                                 | Can be null (`nullptr`)          |
    | **Reassignment** | Cannot be changed to refer to another variable | Can point to a different address |
    | **Syntax**       | Cleaner syntax (`x`)                           | Requires dereferencing (`*x`)    |

***

### **User-Defined Data Types**

User-defined data types are created to better represent and organize data in complex systems.

**Structures (`struct`)**

A way to group related variables of different types under a single name.

*   **Example**:

    ```cpp
    struct Car {
        string brand;
        int year;
        double price;
    };

    Car myCar = {"Toyota", 2022, 30000.0};
    ```

**Unions**

Similar to structures, but all members share the same memory location.

*   **Example**:

    ```cpp
    union Data {
        int i;
        float f;
        char c;
    };

    Data d;
    d.i = 10;
    ```

**Enumerations (`enum`)**

A way to define a set of named integral constants.

*   **Example**:

    ```cpp
    enum Color { RED, GREEN, BLUE };
    Color favoriteColor = GREEN;
    ```
*   **Enum Classes**:

    ```cpp
    enum class Direction { NORTH, SOUTH, EAST, WEST };
    Direction myDirection = Direction::NORTH;
    ```

Certainly! Here’s a concise expansion on **typedef** and **Abstract Data Types (ADTs)** in C++, staying focused and to the point:

#### **Typedefs**

**Typedef** is a keyword used to create an alias (alternative name) for an existing data type, simplifying code readability and usage.

**Key Points:**

* **Alias for Types**: Creates a shorthand for complex type declarations.
* **Improves Readability**: Makes code more intuitive, especially with lengthy types.
* **Compatibility**: `typedef` has largely been replaced by the `using` keyword in modern C++ for type aliases.

**Examples:**

1.  **Basic Typedef**:

    ```cpp
    typedef unsigned long ulong;
    ulong fileSize = 1048576; // Easier to read than 'unsigned long'
    ```
2.  **Typedef for Function Pointer**:

    ```cpp
    typedef void (*FunctionPtr)(); // Alias for a pointer to a function returning void
    ```

#### **Abstract Data Types (ADTs)**

An **Abstract Data Type (ADT)** is a model or concept for data structures that defines the data type logically, without specifying its implementation. ADTs encapsulate data and the operations that can be performed on that data.

**Key Points:**

* **Encapsulation**: Encapsulates data and functions together.
* **Data Hiding**: Internal representation of data is hidden from the user.
* **Implementation Independent**: The focus is on what operations are available, not how they're implemented.
* **Examples of ADTs**: Stack, Queue, List, Tree, Graph.

**Example:**

```cpp
class Stack {  // Example of an ADT: Stack
private:
    int data[100];
    int top;
    
public:
    Stack() : top(-1) {} // Constructor initializing an empty stack

    void push(int value) { data[++top] = value; } // Push operation
    int pop() { return data[top--]; }             // Pop operation
    bool isEmpty() const { return top == -1; }    // Check if the stack is empty
};
```
