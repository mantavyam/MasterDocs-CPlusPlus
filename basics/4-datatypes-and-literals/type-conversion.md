# Type Conversion

## What is **Type Conversion in C++**

**Type conversion** refers to the process of converting a variable from one datatype to another. This is necessary when we perform operations involving variables of different types, or when we want to fit a value into a particular data type.

### **1. Implicit Type Conversion (Automatic Conversion)**

* **Definition**: Implicit type conversion occurs automatically by the compiler when you assign a value of one type to a variable of another type. This happens when the source type can be safely converted to the target type without loss of information.
* **Example**: Assigning a smaller integer to a larger one (like `int` to `float`) happens automatically.

```cpp
int x = 10;      // int type
float y = x;     // implicit conversion from int to float
```

In this case, the value `10` of type `int` is implicitly converted to `float` when assigned to `y`.

### **2. Explicit Type Conversion (Casting)**

Explicit type conversion, also known as **casting**, is performed manually by the programmer. This is used when a value is being assigned to a variable of a different type, and the conversion isn’t safe or automatic.

**a. `static_cast`**

* Used for conversions between related types (e.g., `int` to `float` or pointers to derived classes).
* This is the most commonly used casting mechanism in C++.

```cpp
int a = 10;
float b = static_cast<float>(a);  // int to float conversion
```

**b. `dynamic_cast`**

* Primarily used for safely casting pointers or references to a base or derived class in a class hierarchy.
* It checks at runtime whether the cast is valid, especially when working with polymorphic types.

```cpp
class Base { virtual void foo() {} };
class Derived : public Base {};

Base* basePtr = new Derived();
Derived* derivedPtr = dynamic_cast<Derived*>(basePtr);  // Safe casting
```

**c. `const_cast`**

* Used to add or remove `const` qualifier from a variable.
* Only used for casting away `const` or `volatile` qualifiers.

```cpp
const int x = 10;
int* p = const_cast<int*>(&x);  // Cast away const qualifier
```

**d. `reinterpret_cast`**

* Used for low-level reinterpretation of data types, such as casting between unrelated pointer types.
* This should be used cautiously, as it can lead to undefined behavior if not used correctly.

```cpp
int x = 10;
char* p = reinterpret_cast<char*>(&x);  // Reinterpret address as char pointer
```

### **3. Type Promotion**

**Type promotion** occurs when an expression involves operands of different types. The compiler automatically promotes the smaller type to a larger type (if applicable), so that the operation can proceed without loss of information.

* **Example**: In arithmetic operations, `char` or `short` are promoted to `int` before the operation.

```cpp
char c = 10;
int i = 20;
float result = c + i;  // char 'c' is promoted to int before addition
```

Here, `char c` is promoted to `int` because of the operation with `int`, and the result is stored in a `float`.

***

## **Size & Limits of Data Types**

**1. `sizeof` Operator**

* The `sizeof` operator is used to determine the size, in bytes, of a data type or a variable.
* It helps understand the memory consumption of different types and objects.

```cpp
int a = 10;
cout << "Size of int: " << sizeof(a) << " bytes" << endl;
```

This will print the size of the `int` type.

**2. Limits for Integral Types**

C++ provides predefined constants to determine the limits for various integral types such as `int`, `short`, `long`, etc.

* **Header**: `<climits>` defines the limits for integral types.

```cpp
#include <climits>
cout << "Max value of int: " << INT_MAX << endl;
cout << "Min value of int: " << INT_MIN << endl;
```

Here are some commonly used limits:

* `CHAR_BIT` – Number of bits in a `char`.
* `INT_MAX` – Maximum value of an `int`.
* `INT_MIN` – Minimum value of an `int`.
* `LONG_MAX` – Maximum value of a `long`.

```cpp
cout << "Size of char: " << sizeof(char) << " bytes" << endl;
cout << "CHAR_MAX: " << CHAR_MAX << endl;
```

**3. Limits for Floating-Point Types**

C++ also defines limits for floating-point types such as `float`, `double`, and `long double`.

* **Header**: `<cfloat>` provides these constants.

```cpp
#include <cfloat>
cout << "Max value of float: " << FLT_MAX << endl;
cout << "Min value of float: " << FLT_MIN << endl;
```

Here are some floating-point specific constants:

* `FLT_MAX` – Maximum finite value for `float`.
* `FLT_MIN` – Minimum positive normalized value for `float`.
* `DBL_MAX` – Maximum finite value for `double`.
* `DBL_MIN` – Minimum positive normalized value for `double`.
