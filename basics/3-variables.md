# 3 - Variables

## **What Are Variables?**

Variables in C++ are named storage locations in memory that hold data values. Think of a variable as a container or a label that points to a specific memory location, allowing you to store, manipulate, and retrieve information during the execution of a program.

**Definition:**

A variable is an identifier associated with a memory location where a value can be stored, changed, or retrieved.

**Example:**

```cpp
int age = 25; // 'age' is a variable of type 'int' initialized with the value 25
```

## **Why Are Variables Required?**

Variables are essential because they allow us to:

1. **Store Data**: Variables let us hold information that a program can use.
2. **Manipulate Data**: Variables provide a way to modify and manipulate values during execution.
3. **Make Code Dynamic**: Using variables makes your code adaptable to changes without needing to hard-code values.
4. **Maintain State**: Variables allow a program to keep track of information over time, like counters, settings, or configuration states.

Without variables, our programs would be static and limited, unable to respond dynamically to inputs or changing conditions.

## **How to Declare and Initialize Variables**

**Declare:**

Declaring a variable means specifying its type and giving it a name.

**Syntax:**

```cpp
type variable_name;
```

**Example:**

```cpp
int score;   // Declares an integer variable named 'score'
double rate; // Declares a floating-point variable named 'rate'
```

**Initialize:**

Initializing a variable involves assigning an initial value to it at the time of declaration.

**Syntax:**

```cpp
type variable_name = value;
```

**Example:**

```cpp
int score = 100;       // Declares and initializes 'score' to 100
double rate = 0.75;    // Declares and initializes 'rate' to 0.75
```

> ⚠️ It’s always good practice to initialize variables to avoid unexpected behavior.

***

## **Types of Variables**

### **Based on Scope**

**1. Local Variables**

* **Definition**: A local variable is declared inside a function or a block (within `{}` braces) and can only be accessed within that function or block.
* **Scope**: Limited to the block where it's defined.
*   **Example**:

    ```cpp
    void myFunction() {
        int localVar = 10; // Local variable, only accessible within 'myFunction'
    }
    ```

**2. Global Variables**

* **Definition**: A global variable is declared outside all functions and is accessible from any function within the same file.
* **Scope**: Entire file or program.
*   **Example**:

    ```cpp
    int globalVar = 20; // Global variable

    void myFunction() {
        std::cout << globalVar; // Accessible here
    }
    ```

**Local vs. Global Variables - Comparison Table**

| Aspect             | Local Variables                       | Global Variables                    |
| ------------------ | ------------------------------------- | ----------------------------------- |
| **Scope**          | Limited to the function/block         | Entire program or file              |
| **Lifetime**       | Exists only during function execution | Exists throughout the program's run |
| **Accessibility**  | Accessible only within the function   | Accessible from any function        |
| **Memory Usage**   | Uses stack memory                     | Uses static or global memory        |
| **Initialization** | Must be initialized manually          | Defaults to 0 if not initialized    |

### **Based on Lifetime**

{% hint style="info" %}
Please Note that to Understand the Topics below you'll need more understanding of OOP, If you're just a beginner just skim by them and just understand their essence, It is not recommended to dive deep into these at this stage.
{% endhint %}

Of course! Let's break down the types of variables based on their **lifetime** in C++ with more beginner-friendly examples, aiming to make each concept crystal clear.

#### **1. Automatic Variables**

**Automatic variables** are the most common type of variables. They are created when the scope (such as a function) is entered and destroyed when the scope is exited. These variables are **local** to the block in which they are defined.

**Think of it Like:**

A cup you fill with water when you start drinking and empty when you’re done. You only have the cup while you’re in the kitchen.

**Example Explained:**

```cpp
void greet() {
    int counter = 0; // 'counter' is an automatic variable
    counter++;       // Increment the value of counter by 1
    std::cout << "Hello! Counter is: " << counter << std::endl;
} // 'counter' is destroyed here, and the memory is released
```

In the above example:

* Every time you call `greet()`, `counter` is **created**, set to `0`, incremented, and then **destroyed** when the function ends.
* If you call `greet()` multiple times, `counter` will always start at `0` because it's recreated each time.

#### **2. Static Variables**

**Static variables** retain their value between function calls. They are initialized only **once** and exist for the entire lifetime of the program, but their scope can still be limited to a function or a block.

**Think of it Like:**

A counter that stays on a desk even when you leave the room. It will remember the number even if you come back days later.

**Example Explained:**

```cpp
void staticCounter() {
    static int counter = 0; // 'counter' is a static variable, initialized once
    counter++;              // Increment the value of counter by 1
    std::cout << "Static Counter is: " << counter << std::endl;
}

int main() {
    staticCounter(); // Output: Static Counter is: 1
    staticCounter(); // Output: Static Counter is: 2
    staticCounter(); // Output: Static Counter is: 3
}
```

In the example:

* The variable `counter` is declared as `static`.
* It's only **initialized once**, the first time `staticCounter()` is called.
* The value of `counter` persists between calls to `staticCounter()`, so it keeps incrementing.

#### **3. Instance Variables (Member Variables)**

Instance variables belong to **objects** in Object-Oriented Programming. Each object has its own set of variables, and their lifetime is tied to the object's lifetime.

**Think of it Like:**

Personal notebooks that each student in a class carries. Each student (object) has their own notebook (instance variable), and the notebook exists as long as the student does.

**Example Explained:**

```cpp
class Person {
public:
    std::string name; // Instance variable

    Person(std::string personName) {
        name = personName; // Initialize the instance variable
    }

    void greet() {
        std::cout << "Hello, my name is " << name << std::endl;
    }
};

int main() {
    Person alice("Alice");
    Person bob("Bob");

    alice.greet(); // Output: Hello, my name is Alice
    bob.greet();   // Output: Hello, my name is Bob
}
```

In the example:

* Each `Person` object has its own `name`.
* When you create `alice` and `bob`, each object stores a separate value for `name`.
* The `name` variable only exists as long as the object exists.

#### **4. External Variables**

**External variables** (also known as **global variables**) are declared outside all functions and are accessible from any part of the program. They exist throughout the entire lifetime of the program.

**Think of it Like:**

A large public noticeboard in the hallway that everyone in the building can see and update.

**Example Explained:**

File 1 (`main.cpp`):

```cpp
#include <iostream>

// Declare the variable 'sharedData' defined in another file
extern int sharedData; 

void printData() {
    std::cout << "Shared Data: " << sharedData << std::endl;
}

int main() {
    printData(); // Will access 'sharedData' from another file
}
```

File 2 (`data.cpp`):

```cpp
// Define the global variable 'sharedData'
int sharedData = 42;
```

In the example:

* `sharedData` is defined in `data.cpp` and declared as `extern` in `main.cpp`.
* This means `sharedData` is **shared** between files, and any file that includes `extern int sharedData;` can use it.

#### **5. Register Variables**

**Register variables** are a special type where you request the compiler to store the variable in a CPU register instead of RAM for faster access. This is mostly a historical feature since modern compilers are very good at optimization.

**Think of it Like:**

A frequently accessed document you keep in your desk drawer instead of filing it in the cabinet for quicker access. Nowadays, you just trust the assistant (compiler) to decide.

**Example Explained:**

```cpp
void quickAccess() {
    register int fastVar = 10; // 'fastVar' is suggested to be kept in a CPU register
    for (int i = 0; i < fastVar; i++) {
        std::cout << "Count: " << i << std::endl;
    }
} // The request to store in register is optional, compiler decides.
```

In the example:

* `fastVar` is declared with `register`, suggesting faster access.
* The actual decision is left to the compiler, which may ignore the hint if it sees fit.

#### **6. Thread Local Variables**

**Thread-local variables** have a unique instance for each thread, meaning that each thread has its own copy of the variable.

**Think of it Like:**

Imagine a locker room where each thread has its own personal locker. Even if they have the same name, each locker belongs to a different person.

**Example Explained:**

```cpp
#include <iostream>
#include <thread>

// Thread-local variable
thread_local int threadVar = 0;

void increment() {
    threadVar++;
    std::cout << "Thread ID: " << std::this_thread::get_id() << " | threadVar: " << threadVar << std::endl;
}

int main() {
    std::thread t1(increment);
    std::thread t2(increment);
    std::thread t3(increment);

    t1.join();
    t2.join();
    t3.join();
}
```

In the example:

* `threadVar` is declared as `thread_local`, meaning each thread (`t1`, `t2`, `t3`) has its own independent copy.
* If you run the program, you’ll see that each thread has its own value of `threadVar`.

***

| **Variable Type** | **Example Situation**                                           | **Lifetime**             |
| ----------------- | --------------------------------------------------------------- | ------------------------ |
| **Automatic**     | A temporary variable inside a function, like `int temp`         | Function/Block execution |
| **Static**        | A counter that retains its value between function calls         | Entire program run       |
| **Instance**      | A name assigned to each created object of a class               | Duration of the object   |
| **External**      | A configuration variable defined globally and accessed anywhere | Entire program run       |
| **Register**      | A frequently accessed loop counter                              | Function/Block execution |
| **Thread Local**  | A variable that each thread has a separate copy of              | Duration of the thread   |

***

## **Type Inference in C++**

#### **1. `auto` Keyword**

* Allows the compiler to **automatically deduce** the type of the variable based on the assigned value.
* Simplifies code when the exact type is evident from context.
*   **Example**:

    ```cpp
    auto x = 10;        // 'x' is deduced to be of type 'int'
    auto y = 3.14;      // 'y' is deduced to be of type 'double'
    auto z = "Hello";   // 'z' is deduced to be of type 'const char*'
    ```

#### **2. `decltype` Keyword**

* Returns the type of an expression without evaluating it.
* Useful when you want a variable to have the same type as another.
*   **Example**:

    ```cpp
    int a = 42;
    decltype(a) b = 5; // 'b' is of the same type as 'a', which is 'int'
    ```

**When to Use which Type Inference: `auto` vs. `decltype` - Comparison Table**

| Use Case                   | `auto`                               | `decltype`                                          |
| -------------------------- | ------------------------------------ | --------------------------------------------------- |
| **Simple Initialization**  | Use `auto` to simplify code          | Rarely needed                                       |
| **Matching Type**          | Avoid if type is ambiguous           | Use when exact type of another variable is required |
| **Performance Impact**     | No overhead, avoids redundancy       | No overhead, evaluates type only                    |
| **Template Programming**   | Ideal for deducing return types      | Useful for complex type deduction                   |
| **Avoiding Typing Errors** | `auto` helps prevent type mismatches | `decltype` ensures exact match                      |
