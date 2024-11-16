# Passing Data between Functions

When working with functions in C++, understanding how data is passed between functions is crucial. Two common methods are **Pass-by-Value** and **Pass-by-Reference**. Each has unique characteristics, pros, and cons, which are important to know for efficient programming.

***

## **Pass-by-Value**

**Definition and Characteristics of Pass-by-Value**

* **Pass-by-Value** is a method where a copy of the actual value is passed to the function.
* The original variable in the caller is not affected by operations within the function since the function only deals with a copy.
* **Changes made to the parameter inside the function do not reflect in the original variable**.

**How Function Arguments are Passed in Pass-by-Value**

* When using **Pass-by-Value**, the function receives a copy of the data.
* The values are stored in a temporary location in memory, so modifications within the function do not affect the original variables.
* This is the default behavior in C++ for most built-in data types like `int`, `float`, `double`, etc.

**Copy of Value is Passed to Function**

* A new memory location is allocated for the copied value.
* **Modifications** are local to the function and have no impact on the caller's variable.

**Example: Function with Pass-by-Value Parameter**

```cpp
#include <iostream>
using namespace std;

// Function that uses Pass-by-Value
void incrementByValue(int num) {
    num = num + 1;  // This modification is local to the function
    cout << "Inside function (Pass-by-Value), num = " << num << endl;
}

int main() {
    int number = 10;
    cout << "Before function call, number = " << number << endl;
    
    incrementByValue(number);  // Call function with Pass-by-Value
    
    cout << "After function call, number = " << number << endl;  // Original variable remains unchanged
    return 0;
}
```

**Output**:

```
Before function call, number = 10
Inside function (Pass-by-Value), num = 11
After function call, number = 10
```

* **Note**: The original variable `number` remains `10` even though `num` was modified in the function.

***

## **Pass-by-Reference**

**Definition and Characteristics of Pass-by-Reference**

* **Pass-by-Reference** allows a function to directly access and modify the original variable.
* Instead of passing a copy, the function gets the **memory address** of the variable.
* Changes made to the parameter within the function **affect the original variable** in the calling code.

**Passing the Memory Address of a Variable**

* The reference to the original variable is passed, which means no new memory allocation is required.
* **Syntax**: In C++, an `&` (ampersand) is used in the parameter list to indicate a reference.

**Modifying Original Variables in the Calling Function**

* Since the function operates on the same memory location, modifications inside the function will alter the original data.
* This can be more efficient for large data types (e.g., arrays, objects) since no copying is required.

#### **Using Reference Variables in Functions**

* Reference variables are declared using the `&` symbol in the function's parameter list. This tells the compiler that the variable should be passed by reference, not by value.
*   **Syntax Example**:

    ```cpp
    void modify(int &x);  // Function declaration with reference
    ```
*   This way, the function directly accesses the original variable:

    ```cpp
    void modify(int &x) {
        x = x * 2;  // Directly modifies the original variable
    }
    ```

**Example: Function with Pass-by-Reference Parameter**

```cpp
#include <iostream>
using namespace std;

// Function that uses Pass-by-Reference
void incrementByReference(int &num) {
    num = num + 1;  // This modification affects the original variable
    cout << "Inside function (Pass-by-Reference), num = " << num << endl;
}

int main() {
    int number = 10;
    cout << "Before function call, number = " << number << endl;
    
    incrementByReference(number);  // Call function with Pass-by-Reference
    
    cout << "After function call, number = " << number << endl;  // Original variable is changed
    return 0;
}
```

**Output**:

```
Before function call, number = 10
Inside function (Pass-by-Reference), num = 11
After function call, number = 11
```

* **Note**: The original variable `number` is updated to `11` after the function call.

***

## **Comparison: Pass-by-Value vs Pass-by-Reference**

| **Criteria**            | **Pass-by-Value**                            | **Pass-by-Reference**                                 |
| ----------------------- | -------------------------------------------- | ----------------------------------------------------- |
| **Definition**          | Copies the value to the function             | Passes the reference (memory address) to the function |
| **Memory Usage**        | More memory (new copy created)               | Less memory (no copy, direct reference)               |
| **Modification Effect** | Changes do not affect the original variable  | Changes affect the original variable                  |
| **Use Case**            | When changes to variables should be local    | When the original variable needs to be modified       |
| **Performance**         | Slower for large data types (due to copying) | Faster for large data types (no copying)              |
| **Default Behavior**    | For basic data types like `int`, `float`     | Not default, requires `&` in parameter declaration    |
| **Safety**              | Safe, no unintended side-effects             | Can lead to unintended modifications if not careful   |
| **Complexity**          | Simpler to use and understand                | Slightly complex due to pointer/reference handling    |

***

## **When to Use Each Approach**

**When to Use Pass-by-Value**

* **When data should remain unchanged** after the function call.
* **For small data types** (e.g., `int`, `char`, `bool`), where copying is inexpensive.
* In scenarios where **safety** is a concern, as changes inside the function won’t impact the original data.
* Examples: Simple calculations, reading data without modifying, small operations.

**When to Use Pass-by-Reference**

* When the function needs to **modify the original data**.
* **For large data structures** (like arrays, vectors, or custom objects) where copying can be slow and memory-consuming.
* When **performance matters**, and avoiding unnecessary copies is crucial.
* Examples: Swapping values, modifying large data sets, algorithms that update data directly.

***
