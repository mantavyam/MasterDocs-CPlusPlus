# Literals

## **What are Literals?**

* **Definition**: A literal is a constant value that is directly written into the code. It is a fixed value used to represent data of a specific type, such as a number, character, or string.
* **Purpose**: Literals help represent data in its simplest, most direct form in your C++ program, and they are used in assignments, comparisons, and operations.

In C++, a **datatype** specifies the type of data a variable can hold, while a **literal** is the actual value assigned to that variable, matching the datatype.

#### Let's Understand the relation between Datatypes & Literals in a single line of code:

```cpp
int x = 42;  // 'int' is the datatype, '42' is the literal
```

Here, `int` is the datatype that defines the kind of value `x` can hold (an integer), and `42` is the literal assigned to `x`.

***

## **Types of Literals**

**1. Integer Literals**

Integer literals are used to represent whole numbers.

*   **Decimal (Base 10)**: The default base for integer literals.

    ```cpp
    int a = 42;  // Decimal literal
    ```
*   **Octal (Base 8)**: Prefix with `0` to indicate an octal value (C++98 onwards).

    ```cpp
    int b = 042;  // Octal literal (42 in decimal)
    ```
*   **Hexadecimal (Base 16)**: Prefix with `0x` or `0X` to indicate hexadecimal values.

    ```cpp
    int c = 0x2A;  // Hexadecimal literal (42 in decimal)
    ```
*   **Binary (Base 2)**: Introduced in C++14, prefix with `0b` or `0B`.

    ```cpp
    int d = 0b101010;  // Binary literal (42 in decimal)
    ```
*   **Long, Long Long Modifiers**: Append `L` for long and `LL` for long long integers.

    ```cpp
    long e = 42L;    // Long literal
    long long f = 42LL;  // Long long literal
    ```

**2. Floating-Point Literals**

Floating-point literals represent decimal numbers, allowing fractional parts.

*   **`float`**: Appended with `f` or `F` to denote a `float` type.

    ```cpp
    float g = 3.14f;  // Float literal
    ```
*   **`double`**: The default for floating-point literals.

    ```cpp
    double h = 3.14159;  // Double literal
    ```
*   **`long double`**: Appended with `l` or `L` for greater precision.

    ```cpp
    long double i = 3.1415926535L;  // Long double literal
    ```

**3. Character Literals**

Character literals represent individual characters or symbols.

*   **Single Character (`char`)**: Enclosed in single quotes (`'`).

    ```cpp
    char j = 'A';  // Character literal
    ```
*   **Wide Character (`wchar_t`)**: Enclosed in wide single quotes (`L'`).

    ```cpp
    wchar_t k = L'Ω';  // Wide character literal
    ```
*   **Universal Character Names (U and u)**: Used to represent Unicode characters.

    ```cpp
    char l = u'\u03A9';  // Unicode character literal (Omega)
    ```

**4. String Literals**

String literals represent sequences of characters.

*   **Normal Strings**: Enclosed in double quotes (`""`).

    ```cpp
    const char* str1 = "Hello, World!";  // String literal
    ```
*   **Wide String Literals (`L""`)**: Represented by prefixing with `L` for wide-character strings.

    ```cpp
    const wchar_t* str2 = L"Hello, World!";  // Wide string literal
    ```
*   **UTF-8 String Literals (`u8""`)**: Represented by the `u8` prefix for UTF-8 encoded strings.

    ```cpp
    const char* str3 = u8"Hello, World!";  // UTF-8 string literal
    ```
*   **Raw String Literals (`R"()"`)**: Allow you to include special characters (like newlines, backslashes) without escaping them.

    ```cpp
    const char* str4 = R"(This is a raw string literal\n)";
    ```

**5. Boolean Literals**

Boolean literals represent the logical values of `true` or `false`.

```cpp
bool m = true;    // Boolean literal
bool n = false;   // Boolean literal
```

**6. Pointer Literals**

Pointer literals are used for null pointers.

*   **`nullptr`**: Used to represent a null pointer.

    ```cpp
    int* ptr = nullptr;  // Null pointer literal
    ```

**7. User-Defined Literals**

User-defined literals allow you to create your own literals with specific suffixes, enhancing the expressiveness of your code.

*   **Literals with Suffixes**: You can define custom literals by appending suffixes to the literal values.

    ```cpp
    constexpr long double operator"" _kg(long double x) { return x * 1000.0; }
    long double weight = 5.0_kg;  // User-defined literal (converts 5 kg to grams)
    ```

***

## **Literal Suffixes**

**1. Integer Suffixes**

Suffixes to specify the type of an integer literal.

*   **`u` / `U`**: Unsigned integer type.

    ```cpp
    unsigned int x = 42U;
    ```
*   **`l` / `L`**: Long integer type.

    ```cpp
    long y = 42L;
    ```
*   **`ll` / `LL`**: Long long integer type.

    ```cpp
    long long z = 42LL;
    ```
*   **`f` / `F`**: Float type (for floating-point literals).

    ```cpp
    float fval = 3.14f;
    ```

**2. Floating-Point Suffixes**

Suffixes to specify the type of a floating-point literal.

*   **`f` / `F`**: `float` type.

    ```cpp
    float pi = 3.14f;
    ```
*   **`l` / `L`**: `long double` type.

    ```cpp
    long double pi_ld = 3.141592653589793238L;
    ```

**3. Character Suffixes**

*   **`u`, `U`**: Used for Unicode character literals (`char16_t`, `char32_t`).

    ```cpp
    char16_t ch = u'A';  // UTF-16 character literal
    ```
*   **`L`**: Used for wide characters (`wchar_t`).

    ```cpp
    wchar_t wideCh = L'Ω';  // Wide character literal
    ```
*   **`w`**: Used for wide character literals.

    ```cpp
    wchar_t wCh = w'A';  // Wide character literal
    ```
