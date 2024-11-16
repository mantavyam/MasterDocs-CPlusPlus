# 9 - Functions

## **Introduction to Functions**

1. **Definition and Purpose of Functions in C++**:
   * A **function** is a block of code that performs a specific task when it is called. It allows code to be reused and makes the program modular.
   * Functions help divide the program into smaller, manageable chunks, enabling easier maintenance and understanding.
2. **Benefits of Using Functions**:
   * **Code Reusability**: Functions allow you to write a block of code once and call it multiple times, reducing redundancy.
   * **Modularity**: Functions break down complex tasks into smaller, manageable modules.
   * **Code Organization and Clarity**: Functions organize code into logical units, making the code easier to understand and maintain.
   * **Simplifying Debugging and Maintenance**: With modular code, it's easier to identify and fix errors since each function handles a specific task.
3. **Types of Functions in C++**:
   * **Built-in Functions**: These are pre-defined functions provided by C++ libraries (e.g., `sqrt()`, `sin()`, etc.).
   * **User-defined Functions**: Functions that programmers define to meet specific needs in their programs.
4. **Function Syntax Overview**:
   * Functions in C++ consist of a function **declaration** (prototype), **definition**, and **call**.
   * The basic structure includes the return type, function name, parameters (if any), and the function body containing the logic.

***

## **Function Declaration and Definition**

### **Function Declaration (Prototype)**

1. **Definition and Purpose of Function Declaration**:
   * A **function declaration** (also called a function prototype) tells the compiler about the function's name, return type, and parameters (if any). It does not include the function's body. This allows functions to be called before their definitions in the code.
2. **Syntax of a Function Declaration**:
   *   The syntax for declaring a function is:

       ```cpp
       return_type function_name(parameter_list);
       ```
3.  **Example: Declaring a Function Before Main**:

    ```cpp
    #include <iostream>
    using namespace std;

    // Function Declaration
    int add(int, int);

    int main() {
        int result = add(3, 4);  // Function call
        cout << "The sum is: " << result << endl;
        return 0;
    }

    // Function Definition
    int add(int a, int b) {
        return a + b;
    }
    ```

### **Function Definition**

1. **Syntax of Function Definition**:
   * The **function definition** provides the actual implementation of the function.
   *   Syntax:

       ```cpp
       return_type function_name(parameter_list) {
           // Function body (logic goes here)
       }
       ```
2. **Matching Declaration and Definition**:
   * The function declaration and definition must match in terms of return type, function name, and parameter types.
3. **Providing Function Logic**:
   * The function logic is placed inside the function body, where you perform the task the function is meant to execute.
4.  **Example: Defining a Function to Perform Addition**:

    ```cpp
    #include <iostream>
    using namespace std;

    // Function Declaration
    int add(int, int);

    int main() {
        int result = add(5, 7);  // Function call
        cout << "The sum is: " << result << endl;
        return 0;
    }

    // Function Definition
    int add(int a, int b) {
        return a + b;  // Logic for adding two numbers
    }
    ```

**Function Declaration vs. Function Definition**

* **Function Declaration**: Specifies the function's return type, name, and parameters without defining the function's body. It's like a promise to the compiler that the function will be defined later.
* **Function Definition**: Provides the actual implementation of the function, including the logic that is executed when the function is called.

***

## **Function Parameters**

**What are Parameters?**

* **Parameters** are variables that are declared in a function definition or prototype. They allow data to be passed into functions so that the function can work with this data. In C++, parameters can be used to accept input values and provide output from the function.
* **Function Signature**: A function's signature includes the function name, the return type, and the parameters it takes. The parameters allow the function to perform its task using the values passed to it.

### **Types of Parameters**

**Formal Parameters:**

* **Formal parameters** are the variables declared in the function definition. They act as placeholders that store the values passed to the function when it is called.
* These parameters are used within the function body to perform operations or computations based on the values passed to the function.
*   **Example**:

    ```cpp
    // Function with formal parameters
    void displaySum(int a, int b) {
        cout << "Sum: " << a + b << endl;  // a and b are formal parameters
    }
    ```

**Actual Parameters:**

* **Actual parameters** (or **arguments**) are the real values or variables passed to a function when it is called.
* These values are assigned to the formal parameters in the function.
*   **Example**:

    ```cpp
    // Function call with actual parameters
    int x = 5, y = 10;
    displaySum(x, y);  // x and y are actual parameters
    ```

**Number of Parameters (Zero or More)**

* A function can have zero, one, or multiple parameters.
*   **Zero Parameters**: A function can be defined without any parameters, in which case it does not expect any values to be passed when it is called.

    **Example: Function with Zero Parameters**:

    ```cpp
    void greet() {
        cout << "Hello, World!" << endl;
    }
    ```
*   **One or More Parameters**: Functions can take multiple parameters, and each parameter can have a specific type.

    **Example: Function with Multiple Parameters**:

    ```cpp
    int multiply(int a, int b) {
        return a * b;  // The function returns the product of a and b
    }
    ```

***

## **Return Types**

**What is a Return Type?**

* **Return type** specifies the type of value that a function will return to the calling code after it completes its task.
* Every function must declare a return type, which can be any valid data type such as `int`, `float`, `double`, `char`, or `void`.
* If a function is intended to return a value, it must include a `return` statement that specifies what value will be returned to the caller.

### **Common Return Types:**

1.  **`int`**: Used when a function needs to return an integer value.

    ```cpp
    int add(int a, int b) {
        return a + b;  // Function returns an int value (sum of a and b)
    }
    ```
2.  **`float` or `double`**: Used when a function needs to return a floating-point number.

    ```cpp
    float divide(float a, float b) {
        return a / b;  // Function returns a float value (result of division)
    }
    ```
3.  **`void`**: A function that does not return any value. The `void` keyword indicates that no value will be returned from the function.

    ```cpp
    void printMessage() {
        cout << "This is a message." << endl;  // Function does not return anything
    }
    ```
4.  **`char`**: A function can return a single character.

    ```cpp
    char getGrade(int score) {
        if (score >= 90)
            return 'A';
        else if (score >= 80)
            return 'B';
        else
            return 'C';
    }
    ```

## **Returning Values from Functions**

* The return value of a function is specified using the `return` keyword. This ends the execution of the function and returns the value back to the calling code.
*   **Example**: Function that returns the sum of two integers.

    ```cpp
    int sum(int a, int b) {
        return a + b;  // Returning the sum of a and b
    }
    ```

**Example: Function Returning a Value (e.g., sum of two numbers):**

*   This function demonstrates how to use a return type (`int`) to return a value after performing an operation (addition).

    ```cpp
    #include <iostream>
    using namespace std;

    // Function Declaration
    int add(int a, int b);

    int main() {
        int result = add(3, 4);  // Function call
        cout << "The sum is: " << result << endl;  // Display the result
        return 0;
    }

    // Function Definition
    int add(int a, int b) {
        return a + b;  // Returning the sum of a and b
    }
    ```
