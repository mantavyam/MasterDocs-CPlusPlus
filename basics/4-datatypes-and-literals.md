# 4 - Datatypes & Literals

#### OUTLINE

Understanding **datatypes** and **literals** is essential in mastering C++ programming. Datatypes tell the compiler what type of data a variable can hold, and literals are the actual values assigned to variables. This guide will walk you through these fundamental concepts with practical examples, real-life analogies, and some higher-order thinking questions to solidify your understanding.

#### **Table of Contents**

1. What are Datatypes?
2. Primitive Data Types in C++
   * Integer Types (`int`, `short`, `long`)
   * Floating-Point Types (`float`, `double`)
   * Character Type (`char`)
   * Boolean Type (`bool`)
   * Wide Character Type (`wchar_t`)
   * Void Type (`void`)
3. User-Defined Data Types
   * `struct`, `enum`, `union`
4. What are Literals?
5. Types of Literals
   * Integer Literals
   * Floating-Point Literals
   * Character Literals
   * String Literals
   * Boolean Literals
6. Real-Life Analogy
7. Thinkable Questions and Higher-Order Thinking

***

#### **1. What are Datatypes?**

A **datatype** defines the type of data that a variable can store. For example, if you declare a variable to hold a number, you specify an integer datatype like `int`. If the variable needs to store text, you’d use `char` or `string`. Understanding the types and sizes of data helps in efficient memory management and error-free coding.

***

#### **2. Primitive Data Types in C++**

C++ provides several basic (or primitive) datatypes. These include numbers, characters, and boolean values.

**Integer Types**

Integers are whole numbers without a decimal point. C++ offers different sizes of integers to handle various ranges of values.

* **`int`**: The most commonly used integer type.
* **`short`**: A smaller integer type.
* **`long`**: A larger integer type, which can hold bigger numbers.
* **`long long`**: For even larger integers (C++11 and above).

Example:

```cpp
int age = 21;
short int year = 1995;
long int population = 75000000;
long long int stars = 12345678901234;
```

**Experience Insight:**

While working on a financial project, I needed to store very large numbers for transactions. Originally, I used `int` but soon ran into overflow issues. Switching to `long long` allowed me to work with bigger numbers without errors. Always anticipate the potential size of data when choosing a datatype.

***

**Floating-Point Types**

Floating-point types store numbers with decimal points. These are used for precision when dealing with fractions, scientific computations, or any scenario requiring a non-whole number.

* **`float`**: Single-precision floating-point.
* **`double`**: Double-precision floating-point.

Example:

```cpp
float price = 9.99;
double distance = 12345.6789;
```

**Note**: Use `float` when memory is constrained, but prefer `double` for greater precision.

***

**Character Type**

Characters are used to store single characters such as letters, digits, or symbols. The `char` type is used for this, and it can hold a single ASCII character.

Example:

```cpp
char grade = 'A';
```

***

**Boolean Type**

A **boolean** represents true or false values. In C++, we use the `bool` datatype, which can take the values `true` or `false`.

Example:

```cpp
bool isPassed = true;
```

***

**Wide Character Type**

The `wchar_t` type is used for wide characters, allowing you to store characters from extended character sets like Unicode.

Example:

```cpp
wchar_t letter = L'Ω';  // Stores a Greek letter
```

***

**Void Type**

`void` is used when a function does not return any value. It’s not used for variables but is commonly used in function definitions.

Example:

```cpp
void printMessage() {
    std::cout << "Hello, World!" << std::endl;
}
```

***

#### **3. User-Defined Data Types**

C++ also allows the creation of custom data types to handle more complex structures of data. These are invaluable when building large applications.

**`struct` (Structures):**

Structures group variables of different datatypes under a single name. Useful when you want to create a record-like entity.

Example:

```cpp
struct Student {
    std::string name;
    int age;
    char grade;
};

Student s1 = {"John", 21, 'A'};
```

**`enum` (Enumerations):**

`enum` creates a set of named integer constants, improving code readability and reducing magic numbers.

Example:

```cpp
enum Day {Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday};
Day today = Monday;
```

**`union`:**

Unions allow different data types to share the same memory location. This can be useful for memory-efficient storage but must be used cautiously.

Example:

```cpp
union Data {
    int intValue;
    float floatValue;
};

Data d;
d.intValue = 10;
```

***

#### **4. What are Literals?**

**Literals** are constant values directly embedded in your code. They represent fixed values that do not change during the execution of the program. C++ has several types of literals, including integers, floating-point numbers, characters, strings, and booleans.

***

#### **5. Types of Literals**

**Integer Literals:**

Integer literals represent whole numbers. You can specify them in different formats:

* **Decimal**: Base 10 (e.g., `10`, `200`).
* **Octal**: Base 8 (e.g., `012`, `075`).
* **Hexadecimal**: Base 16 (e.g., `0xA`, `0x1F`).

Example:

```cpp
int num1 = 100;    // Decimal
int num2 = 012;    // Octal (8 in decimal)
int num3 = 0x1F;   // Hexadecimal (31 in decimal)
```

**Floating-Point Literals:**

Floating-point literals represent numbers with fractional parts.

Example:

```cpp
float pi = 3.14f;
double gravity = 9.8;
```

Note: The `f` at the end of `3.14` specifies that it is a `float`. Without the suffix, it defaults to `double`.

**Character Literals:**

Character literals represent a single character enclosed in single quotes.

Example:

```cpp
char letter = 'A';
```

You can also use escape sequences like  (newline) and  (tab).

**String Literals:**

String literals represent sequences of characters enclosed in double quotes.

Example:

```cpp
std::string name = "John Doe";
```

**Boolean Literals:**

Boolean literals represent the values `true` and `false`.

Example:

```cpp
bool isFinished = true;
```

***

#### **6. Real-Life Analogy**

Think of **datatypes** as the different kinds of containers you use in a kitchen:

* **Integers (`int`)**: A jar for holding whole beans.
* **Floats (`float`)**: A measuring cup for holding flour, which isn’t a whole number.
* **Characters (`char`)**: A spice bottle for a single spice (like salt or pepper).
* **Booleans (`bool`)**: A simple on/off switch for your stove.

By picking the right container (datatype), you can efficiently manage your ingredients (data) in the kitchen (program).

***

#### **7. Thinkable Questions and High-Order Thinking**

1. **Why do we have so many different integer types (`short`, `int`, `long`)?**
   * What would happen if C++ only had one integer type? How would it impact memory usage and performance?
   * How do you decide when to use `int`, `long`, or `short` in a real project?
2. **When should you prefer `double` over `float`?**
   * Does using `float` always make your program faster? What are the trade-offs between precision and performance?
3. **Can you think of scenarios where using a `union` would be beneficial?**
   * Why does C++ offer a feature that allows different types to share the same memory? In what situations would this be a risky choice?
4. **Do you always need to use a datatype like `int` or `float` when defining variables?**
   * Consider how `auto` and `decltype` can simplify your code by inferring types, especially when dealing with complex data types.

***

#### **Conclusion**

Datatypes and literals in C++ are foundational, and understanding them is crucial for writing efficient, bug-free programs. By knowing when to use different datatypes, you'll avoid pitfalls like overflow, imprecision, or unnecessary memory usage. Whether you're storing numbers, text, or complex structures, the right choice of datatype will make your programs both efficient and maintainable.

**Challenge for Thought**:\
Imagine you're writing a program that calculates the balance in a bank account. What datatypes would you choose for:

* The customer’s account number?
* The current balance?
* A flag indicating if the account is active?

This guide should give you both the basics and a deeper understanding of how to use and choose datatypes and literals effectively.
