### OUTLINE

---
In C++, **variables** are used to store data that can be used and modified throughout the program. They act as containers for holding values of various types. Let’s go through each concept systematically.

---
### 1. **Declaration and Initialization**
   - **Declaration** means telling the compiler what type of data the variable will hold. 
   - **Initialization** is the process of assigning an initial value to the variable.

#### Syntax:
```cpp
int age;       // Declaration
age = 25;      // Initialization

int year = 2023;  // Declaration and Initialization
```

In this example:
- `int age;` declares a variable `age` of type `int`.
- `age = 25;` initializes `age` with a value.
- `int year = 2023;` does both declaration and initialization in one step.

---
### 2. **Variable Types**
Variables can be categorized based on their **scope** and **lifetime**.

#### 2.1 **Local Variables**:
   - Declared **inside** a function/block and can only be accessed within that function/block.
   - They are destroyed once the function/block ends.
   
   ```cpp
   void myFunction() {
       int localVar = 10;  // Local to myFunction
       std::cout << localVar;
   }
   ```

#### 2.2 **Global Variables**:
   - Declared **outside** all functions, typically at the top of the program.
   - Can be accessed by any function within the program.
   - They exist throughout the program’s execution.

   ```cpp
   int globalVar = 20;  // Global Variable

   void display() {
       std::cout << globalVar;  // Accessing global variable
   }
   ```

#### 2.3 **Static Variables**:
   - Retain their value between function calls.
   - Even though they are declared inside a function, they are not destroyed when the function ends.

   ```cpp
   void countCalls() {
       static int counter = 0;  // Static variable
       counter++;
       std::cout << "Called " << counter << " times\n";
   }
   ```

   Each time `countCalls()` is invoked, `counter` will retain its last value.

#### 2.4 **Register Variables**:
   - Stored in the CPU registers instead of RAM (memory) to access them faster.
   - Usually used for small, frequently accessed variables like loop counters.

   ```cpp
   void fastFunction() {
       register int i;  // Register variable
       for (i = 0; i < 100; i++) {
           std::cout << i << " ";
       }
   }
   ```

---

### 3. **Constant Variables**
In certain situations, you may not want a variable’s value to be modified once it's initialized. This is where constant variables come into play.

#### 3.1 **`const` Variables**:
   - Variables declared with `const` cannot be modified after they are initialized.

   ```cpp
   const int maxScore = 100;  // Constant variable
   // maxScore = 110;  // This will result in a compilation error
   ```

#### 3.2 **`constexpr` Variables**:
   - Similar to `const`, but the value of a `constexpr` variable must be determined at compile time, not runtime.
   - Typically used for constants whose values will never change, like mathematical constants.

   ```cpp
   constexpr double pi = 3.14159;
   constexpr int maxPlayers = 4;
   ```

   If you use a constant that needs to be evaluated at runtime, use `const`. For compile-time constants, use `constexpr`.

---

### 4. **Type Inference**
Sometimes, you may not want to explicitly mention the type of a variable. Instead, you can let the compiler deduce it for you.

#### 4.1 **`auto`**:
   - The `auto` keyword tells the compiler to automatically deduce the type based on the variable’s initial value.

   ```cpp
   auto num = 10;  // Compiler infers 'num' is of type 'int'
   auto piValue = 3.14;  // Compiler infers 'piValue' is of type 'double'
   ```

   - **Best Practice**: Use `auto` when the type is obvious or very long to write (like when dealing with iterators or complex types).

#### 4.2 **`decltype`**:
   - Used to **query the type** of an existing variable or expression, which can then be used to declare other variables.

   ```cpp
   int a = 5;
   decltype(a) b = 10;  // 'b' is of the same type as 'a' (int)
   ```

   - This is useful when you want to ensure two variables have the same type, or when you need to refer to the type of a more complex expression.

---

### 5. **Practical Real-Life Example**
Let’s look at a real-world example: tracking the number of passengers on a bus. We can declare variables to store the current number of passengers, the bus capacity, and a constant for the fare.

```cpp
#include <iostream>

const int fare = 15;  // Constant fare per passenger

void updatePassengers() {
    static int passengers = 0;  // Static variable retains value between function calls
    int newPassengers;

    std::cout << "Enter number of new passengers: ";
    std::cin >> newPassengers;

    passengers += newPassengers;
    std::cout << "Total passengers: " << passengers << "\n";
}

int main() {
    updatePassengers();
    updatePassengers();
    return 0;
}
```

In this program:
- We use a `const` variable for the fare since it never changes.
- The `static` variable `passengers` retains its value between calls to `updatePassengers()`.
- `newPassengers` is a local variable that gets reset each time the function is called.

---