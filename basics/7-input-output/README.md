# 7 - Input - Output

## **Introduction to C++ Streams**

### **What are Streams in C++?**

* **Streams** are abstractions for handling input and output (I/O) operations in C++. Streams are essential for reading from and writing to different sources like the console, files, and other devices.
* **Why Streams are Important?**\
  They provide an efficient way to perform I/O operations, support multiple data types, and facilitate formatted and unformatted data handling.

### **Types of Streams in C++**

1. **Input Streams**: Used for receiving data, e.g., from the keyboard or files.
   * Example: `std::cin` is an input stream used for console input.
2. **Output Streams**: Used for sending data, e.g., to the console or files.
   * Example: `std::cout` is an output stream used for printing data to the console.
3. **Bidirectional Streams**: Support both input and output operations.
   * Example: `std::fstream` allows reading and writing to files.

### **C++ Stream Classes Overview**

1. **`std::istream`**: Base class for input streams.
   * Used for reading data from input sources.
2. **`std::ostream`**: Base class for output streams.
   * Used for writing data to output destinations.
3. **`std::iostream`**: A combination of both input and output stream classes.
   * Supports both reading and writing.

### **Stream Buffering and Synchronization**

* Stream buffering helps in improving performance by temporarily storing data before it’s processed (e.g., `std::cout` buffers output).
* **Synchronization** ensures that multiple streams (e.g., `std::cin`, `std::cout`) work properly together. By default, `std::cin` and `std::cout` are synchronized with C's standard streams, but this synchronization can be disabled for performance optimization.

***

## **Basic Console Input/Output**

### **Console Output Using `std::cout`**

* `std::cout` is used to display information on the console.

**Syntax and Usage:**

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    int a = 5;
    cout << "The value of a is: " << a << endl;
    return 0;
}
```

* **Explanation**:
  * `<<` is the **stream insertion operator**, used to send data to `std::cout`.
  * `std::endl` is used to print a new line and flush the output buffer. You can also use  to print a new line.

### **Console Input Using `std::cin`**

* `std::cin` is used to read input from the console.

**Syntax and Usage:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int age;
    cout << "Enter your age: ";
    cin >> age;  // Reading user input and storing it in the variable 'age'
    cout << "You entered: " << age << endl;
    return 0;
}
```

* **Explanation**:
  * `>>` is the **stream extraction operator**, used to read data from `std::cin`.
  * The user input is stored in the variable `age`.

**You can combine input and output in a single statement or process.**

**Example:**

```cpp
#include <iostream>
using namespace std;

int main() {
    string name;
    int age;
    
    cout << "Enter your name: ";
    cin >> name;
    
    cout << "Enter your age: ";
    cin >> age;
    
    cout << "Name: " << name << ", Age: " << age << endl;
    return 0;
}
```

* **Explanation**:
  * First, the program prompts for the user's name and age using `std::cin`.
  * Then it displays the entered information using `std::cout`.
