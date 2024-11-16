# Formatting Output & Manipulators

## **Formatting Output**

**Why and When to Format Output**

* **Purpose**: Formatting output is necessary for making the output more readable, ensuring proper alignment, and controlling the presentation of data.
* **When to Format**: Format output when displaying reports, tables, scientific results, or anytime the output needs to follow specific formatting rules (e.g., financial data, percentages, etc.).

### **Basic Formatting Techniques**

1. **Manipulating Output with `std::setw`**
   * **Description**: Used to set the field width for the next output.
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           int num = 42;
           cout << setw(5) << num << endl;  // Sets width to 5 characters
           return 0;
       }
       ```
2. **Adjusting Precision with `std::setprecision`**
   * **Description**: Controls the number of digits displayed after the decimal point.
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           double pi = 3.14159265359;
           cout << setprecision(4) << pi << endl;  // Displays 3.142
           return 0;
       }
       ```
3. **Controlling Width with `std::left`, `std::right`, `std::internal`**
   * **Description**: Aligns output in a field:
     * `std::left`: Aligns left.
     * `std::right`: Aligns right.
     * `std::internal`: Places the sign in the middle of the field.
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           int num = 42;
           cout << left << setw(10) << num << endl;
           cout << right << setw(10) << num << endl;
           cout << internal << setw(10) << num << endl;
           return 0;
       }
       ```
4. **Aligning Numbers with `std::setw` and `std::setfill`**
   * **Description**: Align numbers and fill empty spaces with a specific character.
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           cout << setw(10) << setfill('*') << 42 << endl;  // Output: "*******42"
           return 0;
       }
       ```
5. **Filling Empty Spaces with `std::setfill`**
   * **Description**: Sets the character used for filling empty spaces when using `std::setw`.
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           cout << setw(10) << setfill('-') << 123 << endl;  // Output: "-------123"
           return 0;
       }
       ```

***

### **Floating-Point Number Formatting**

1. **`std::fixed` and `std::scientific` Format Flags**
   * **Description**:
     * `std::fixed`: Outputs numbers in fixed-point notation.
     * `std::scientific`: Outputs numbers in scientific notation.
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           double num = 12345.6789;
           cout << fixed << setprecision(2) << num << endl;  // Output: 12345.68
           cout << scientific << setprecision(2) << num << endl;  // Output: 1.23e+04
           return 0;
       }
       ```
2. **Controlling Decimal Places**
   * **Description**: Set the number of decimal places using `std::setprecision`.
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           double pi = 3.14159265359;
           cout << fixed << setprecision(3) << pi << endl;  // Output: 3.142
           return 0;
       }
       ```
3. **Example: Formatting Floating-Point Numbers for Precision**
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           double pi = 3.14159265359;
           cout << "Fixed: " << fixed << setprecision(4) << pi << endl;  // Output: 3.1416
           cout << "Scientific: " << scientific << setprecision(4) << pi << endl;  // Output: 3.1416e+00
           return 0;
       }
       ```

***

### **Using Format Flags for Output Customization**

1. **`std::showpoint` and `std::noshowpoint`**
   * **Description**: Controls whether to display the decimal point for floating-point numbers.
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           double num = 123;
           cout << showpoint << num << endl;  // Output: 123.000000
           cout << noshowpoint << num << endl;  // Output: 123
           return 0;
       }
       ```
2. **`std::showbase` and `std::nobase`**
   * **Description**: Displays or hides the base of numbers (e.g., `0x` for hex).
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           int num = 255;
           cout << showbase << hex << num << endl;  // Output: 0xff
           cout << nobase << hex << num << endl;  // Output: ff
           return 0;
       }
       ```
3. **`std::uppercase` and `std::nouppercase`**
   * **Description**: Controls the case of hexadecimal output.
   *   **Example**:

       ```cpp
       #include <iostream>
       #include <iomanip>
       using namespace std;

       int main() {
           int num = 255;
           cout << uppercase << hex << num << endl;  // Output: FF
           cout << nouppercase << hex << num << endl;  // Output: ff
           return 0;
       }
       ```

***

### **Writing Output to a File with Formatted Data**

*   **Example**:

    ```cpp
    #include <iostream>
    #include <fstream>
    #include <iomanip>
    using namespace std;

    int main() {
        ofstream outFile("output.txt");
        outFile << setw(10) << setfill('*') << 123 << endl;  // Write to file with formatting
        outFile.close();
        return 0;
    }
    ```

    * **Explanation**: Data is written to a file `output.txt` with formatting applied.

***

## **Manipulators**

Here are code examples for each manipulator in C++, with a single-line definition beneath each topic. The code uses `namespace std::` as requested.

***

### **`endl`**

_Definition_: Flushing the output buffer and adding a newline.

```cpp
#include <iostream>
#include <iomanip>
namespace std {

int main() {
    cout << "Hello" << endl;  // Flushes the buffer and adds a newline
    cout << "World" << endl;  // Flushes the buffer and adds a newline
    return 0;
}
}
```

**Output**:

```
Hello
World
```

***

### **`setw`**

_Definition_: Sets the width of the next output field.

```cpp
#include <iostream>
#include <iomanip>
namespace std {

int main() {
    cout << setw(10) << 42 << endl;  // Sets field width to 10
    cout << setw(5) << 42 << endl;   // Sets field width to 5
    return 0;
}
}
```

**Output**:

```
        42
   42
```

***

### **`setprecision`**

_Definition_: Controls the number of digits displayed after the decimal point for floating-point numbers.

```cpp
#include <iostream>
#include <iomanip>
namespace std {

int main() {
    double pi = 3.14159265359;
    cout << setprecision(3) << pi << endl;  // Displays 3 significant digits
    cout << setprecision(5) << pi << endl;  // Displays 5 significant digits
    return 0;
}
}
```

**Output**:

```
3.14
3.1416
```

***

### **`fixed` / `scientific`**

_Definition_: Controls the format of floating-point numbers: `std::fixed` for fixed-point notation, and `std::scientific` for scientific notation.

```cpp
#include <iostream>
#include <iomanip>
namespace std {

int main() {
    double pi = 3.14159265359;
    cout << fixed << setprecision(3) << pi << endl;   // Fixed-point notation
    cout << scientific << setprecision(3) << pi << endl; // Scientific notation
    return 0;
}
}
```

**Output**:

```
3.142
3.142e+00
```

***

### **`left`, `right`, `internal`**

_Definition_: Controls the alignment of the output in a field: `std::left` for left-alignment, `std::right` for right-alignment, and `std::internal` for internal alignment (e.g., for signs).

```cpp
#include <iostream>
#include <iomanip>
namespace std {

int main() {
    cout << left << setw(10) << 42 << endl;   // Left-aligns the number
    cout << right << setw(10) << 42 << endl;  // Right-aligns the number
    cout << internal << setw(10) << -42 << endl; // Internal alignment
    return 0;
}
}
```

**Output**:

```
42        
        42
   -42
```

***

### **`setfill`**

_Definition_: Sets the character used to fill empty space in a field when the width is greater than the data size.

```cpp
#include <iostream>
#include <iomanip>
namespace std {

int main() {
    cout << setw(10) << setfill('*') << 42 << endl;  // Fills the remaining space with '*'
    cout << setw(5) << setfill('-') << 42 << endl;   // Fills the remaining space with '-'
    return 0;
}
}
```

**Output**:

```
*******42
---42
```

***

### **`showbase` / `nobase`**

_Definition_: Displays or hides the base (e.g., `0x` for hexadecimal numbers).

```cpp
#include <iostream>
#include <iomanip>
namespace std {

int main() {
    int num = 255;
    cout << showbase << hex << num << endl;   // Displays base for hexadecimal (0x)
    cout << nobase << hex << num << endl;     // Hides base for hexadecimal
    return 0;
}
}
```

**Output**:

```
0xff
ff
```

***

### **`showpoint` / `noshowpoint`**

_Definition_: Displays or hides the decimal point for floating-point numbers.

```cpp
#include <iostream>
#include <iomanip>
namespace std {

int main() {
    double num = 123;
    cout << showpoint << num << endl;  // Displays decimal point (123.0000...)
    cout << noshowpoint << num << endl; // Hides decimal point (123)
    return 0;
}
}
```

**Output**:

```
123.000
123
```
