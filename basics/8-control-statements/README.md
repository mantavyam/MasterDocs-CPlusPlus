# 8 - Control Statements

## **Introduction to Control Statements**

1. **Definition and Importance of Control Statements in C++**:
   * Control statements are used to alter the flow of execution in a program based on certain conditions or requirements.
   * They are crucial for making decisions (conditional statements), repeating actions (looping constructs), or transferring control to other parts of the program (jump statements).
2. **Role in Decision-Making and Repetition of Code**:
   * **Decision-Making**: Control statements allow the program to make decisions. For example, using `if` statements to check conditions and execute different blocks of code based on those conditions.
   * **Repetition of Code**: Looping constructs enable repeated execution of a block of code for a specific number of times or until a condition is met.
   * **Jump Statements**: These can change the control flow abruptly, such as using `break` to exit a loop or `continue` to skip the current iteration.
3. **Types of Control Statements**:
   * **Conditional Statements**: Used to perform actions based on certain conditions. Examples include `if`, `else`, `else if`, `switch`.
   * **Looping Constructs**: These repeat a block of code as long as a condition is true. Examples are `for`, `while`, and `do-while`.
   * **Jump Statements**: Used to jump to different parts of the program. Examples include `break`, `continue`, `return`, and `goto`.
4. **Syntax Structure of Control Statements in C++**:
   * **General Syntax**:
     * Conditional statements typically use comparison operators like `==`, `!=`, `<`, `>`, `<=`, `>=`, and logical operators like `&&` (AND), `||` (OR), and `!` (NOT).
     * Looping statements are based on a condition, and they may include initialization, condition checking, and update statements.
     * Jump statements modify the flow of control directly.

***

## **Example Code Snippets for Each Control Statement**:

**1. Conditional Statements**

*   **`if` Statement**:

    ```cpp
    if (age >= 18) {
        cout << "You are an adult." << endl;
    }
    ```
*   **`if-else` Statement**:

    ```cpp
    if (age >= 18) {
        cout << "You are an adult." << endl;
    }
    else {
        cout << "You are a minor." << endl;
    }
    ```
*   **`else if` Statement**:

    ```cpp
    if (age >= 18) {
        cout << "You are an adult." << endl;
    }
    else if (age >= 13) {
        cout << "You are a teenager." << endl;
    }
    else {
        cout << "You are a child." << endl;
    }
    ```
*   **`switch` Statement**:

    ```cpp
    switch (day) {
        case 1: cout << "Monday"; break;
        case 2: cout << "Tuesday"; break;
        case 3: cout << "Wednesday"; break;
        default: cout << "Invalid day"; break;
    }
    ```

**2. Looping Constructs**

*   **`for` Loop**:

    ```cpp
    for (int i = 0; i < 5; i++) {
        cout << "i is " << i << endl;
    }
    ```
*   **`while` Loop**:

    ```cpp
    int i = 0;
    while (i < 5) {
        cout << "i is " << i << endl;
        i++;
    }
    ```
*   **`do-while` Loop**:

    ```cpp
    int i = 0;
    do {
        cout << "i is " << i << endl;
        i++;
    }
    while (i < 5);
    ```

**3. Jump Statements**

*   **`break` Statement**:

    ```cpp
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            break;  // Exits the loop when i is 5
        }
        cout << i << endl;
    }
    ```
*   **`continue` Statement**:

    ```cpp
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            continue;  // Skips the current iteration when i is 5
        }
        cout << i << endl;
    }
    ```
*   **`return` Statement**:

    ```cpp
    int sum(int a, int b) {
        if (a < 0 || b < 0) return -1;  // Return early if a or b is negative
        return a + b;
    }
    ```
*   **`goto` Statement** (Not commonly used due to readability concerns):

    ```cpp
    int i = 0;
    start:
        cout << "i is " << i << endl;
        i++;
        if (i < 5) goto start;  // Jumps to the start label
    ```
