# Jump Statements

## **Overview of Jump Statements**

1. **Purpose of Jump Statements in Controlling Flow of Execution**:
   * Jump statements provide a way to alter the flow of execution of a program. They are used to transfer control to different parts of the program, making it possible to exit loops, skip iterations, or jump to specific parts of the code based on conditions.
2. **Types of Jump Statements in C++**:
   * **`break`**: Exits from a loop or `switch` statement prematurely.
   * **`continue`**: Skips the current iteration of a loop and moves to the next iteration.
   * **`goto`**: Transfers control to a labeled statement in the program (considered bad practice in modern C++).

***

### **1. `break` Statement**

1. **Definition and Purpose of `break`**:
   * The `break` statement is used to exit a loop (such as `for`, `while`, or `do-while`) or a `switch` statement before the loop or switch completes all its iterations.
2. **Using `break` to Exit Loops or `switch` Statements Early**:
   * The `break` statement stops further execution in the loop or `switch`, and control is passed to the next statement after the loop or `switch`.
3.  **Example: Breaking Out of a `for` or `while` Loop**:

    ```cpp
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            break;  // Exit the loop when i is 5
        }
        cout << "i = " << i << endl;
    }
    // Output: i = 0, i = 1, i = 2, i = 3, i = 4
    ```
4.  **Use of `break` for Control Flow in Nested Loops and `switch`**:

    * `break` can also be used in nested loops to exit the innermost loop.
    * In `switch` statements, `break` is used to exit the `switch` block after a case is executed.

    ```cpp
    switch (option) {
        case 1:
            cout << "Option 1" << endl;
            break;  // Exits switch
        case 2:
            cout << "Option 2" << endl;
            break;  // Exits switch
    }
    ```

***

### **2. `continue` Statement**

1. **Definition and Purpose of `continue`**:
   * The `continue` statement is used inside loops to skip the remaining part of the current iteration and jump to the next iteration of the loop.
2. **Using `continue` to Skip an Iteration in a Loop**:
   * When the `continue` statement is encountered, the rest of the code in the current loop iteration is skipped, and the loop proceeds to the next iteration.
3.  **Example: Skipping Even Numbers in a Loop**:

    ```cpp
    for (int i = 0; i < 10; i++) {
        if (i % 2 == 0) {
            continue;  // Skip even numbers
        }
        cout << "Odd number: " << i << endl;
    }
    // Output: Odd number: 1, Odd number: 3, Odd number: 5, Odd number: 7, Odd number: 9
    ```
4.  **How `continue` Affects Loops and Nested Loops**:

    * `continue` only affects the loop in which it is called. In nested loops, it will skip the current iteration of the innermost loop.

    ```cpp
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (j == 1) {
                continue;  // Skips the second column
            }
            cout << "i = " << i << ", j = " << j << endl;
        }
    }
    // Output: i = 0, j = 0
    //         i = 0, j = 2
    //         i = 1, j = 0
    //         i = 1, j = 2
    //         i = 2, j = 0
    //         i = 2, j = 2
    ```

***

### **3. `goto` Statement**

1. **Definition and Purpose of `goto`**:
   * The `goto` statement transfers control unconditionally to a labeled statement elsewhere in the program. It allows for jumping to any part of the code, making it possible to skip over code or return to a specific location.
2.  **Syntax of `goto` Statement**:

    ```cpp
    goto label;
    // code
    label:
    // code to jump to
    ```
3. **Use Cases of `goto` for Unconditional Jump**:
   * Although rarely used in modern programming, `goto` can be useful for exiting deeply nested loops or skipping sections of code based on certain conditions, especially when other alternatives (like `break`, `continue`, or `return`) are not suitable.
4. **Drawbacks of `goto` (Messy Code and Hard-to-Follow Control Flow)**:
   * **Messy Code**: `goto` makes code harder to read and maintain because it disrupts the logical flow, creating "spaghetti code."
   * **Hard-to-Follow Control Flow**: It can create complex and unpredictable control flows, especially in large programs, making debugging and maintenance difficult.
5.  **Example: Using `goto` for Jumping to Different Parts of Code**:

    ```cpp
    int i = 0;
    if (i == 0) {
        goto label;  // Jump to the label if condition is true
    }

    cout << "This won't be printed." << endl;

    label:
    cout << "Jumped to the label!" << endl;
    // Output: Jumped to the label!
    ```

***

## **Summary of Jump Statements**

* **`break`**: Exits loops or `switch` statements prematurely, providing a way to stop execution when a specific condition is met.
* **`continue`**: Skips the current iteration of a loop, allowing the program to continue with the next iteration without executing the remaining code in the loop body.
* **`goto`**: Transfers control to a labeled statement in the program, but it is generally discouraged due to its potential for creating hard-to-maintain and error-prone code.

In modern C++ programming, the use of `goto` is strongly discouraged. Instead, other control flow mechanisms like `break`, `continue`, and proper function structures should be used to maintain readability and code clarity.
