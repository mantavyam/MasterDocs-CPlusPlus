# Conditional Statements

## **Overview of Conditional Statements**

1. **Purpose of Conditional Statements for Decision-Making**:
   * Conditional statements are used to make decisions based on certain conditions or logical expressions. They determine which part of the code will be executed depending on whether a condition evaluates to true or false.
   * These statements allow programs to behave differently under various circumstances, making them more flexible and dynamic.
2. **How They Work: Evaluating Conditions to Choose Code Paths**:
   * Conditional statements evaluate expressions that result in boolean values (true or false).
   * If the condition is true, a specific block of code is executed; if it’s false, the program may take an alternative action (e.g., skip a block of code, execute another block, or do nothing at all).

***

### **1. `if` Statement**

1.  **Basic Syntax and Structure of `if`**:

    ```cpp
    if (condition) {
        // Code to execute if the condition is true
    }
    ```
2.  **Example: Using `if` for Simple Condition Checks**:

    ```cpp
    int age = 20;
    if (age >= 18) {
        cout << "You are an adult." << endl;
    }
    ```
3.  **Nested `if` Statements**:

    * An `if` statement can be nested inside another `if` statement to evaluate multiple conditions.

    ```cpp
    int age = 20;
    if (age >= 18) {
        if (age >= 21) {
            cout << "You are eligible to drive." << endl;
        }
        else {
            cout << "You are an adult but not eligible to drive." << endl;
        }
    }
    ```

***

### **2. `else` and `else if`**

1. **Purpose of `else` for Default Execution**:
   * The `else` statement provides a default action if the condition in the `if` statement is false.
   * It is used to define what should happen when none of the conditions are true.
2.  **Syntax and Structure of `else`**:

    ```cpp
    if (condition) {
        // Code if condition is true
    }
    else {
        // Code if condition is false
    }
    ```
3.  **Using `else if` for Multiple Conditions**:

    * The `else if` allows checking multiple conditions in a sequence.

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
4.  **Example: Combining `if`, `else if`, and `else` for Complex Conditions**:

    ```cpp
    int age = 20;
    if (age >= 65) {
        cout << "You are a senior." << endl;
    }
    else if (age >= 18) {
        cout << "You are an adult." << endl;
    }
    else if (age >= 13) {
        cout << "You are a teenager." << endl;
    }
    else {
        cout << "You are a child." << endl;
    }
    ```

***

### **3. Ternary Operator (?:)**

1.  **Definition and Syntax of the Ternary Operator**:

    * The ternary operator is a shorthand way of expressing `if-else` logic in a single line.

    ```cpp
    condition ? expression_if_true : expression_if_false;
    ```
2.  **How the Ternary Operator Works (Shortened `if-else` Logic)**:

    * The ternary operator checks a condition. If the condition is true, it executes the expression before the colon (`:`); otherwise, it executes the expression after the colon.

    ```cpp
    int age = 18;
    string result = (age >= 18) ? "Adult" : "Minor";
    cout << result << endl;  // Outputs: Adult
    ```
3.  **Example: Using the Ternary Operator for Condition-Based Assignment**:

    ```cpp
    int age = 20;
    string eligibility = (age >= 18) ? "Eligible" : "Not Eligible";
    cout << "You are " << eligibility << " to vote." << endl;  // Outputs: You are Eligible to vote.
    ```
4. **Advantages and Limitations of the Ternary Operator**:
   * **Advantages**: Compact syntax, faster for simple conditional expressions.
   * **Limitations**: Can reduce readability for complex conditions, and it is harder to debug compared to traditional `if-else` statements.

***

### **4. `switch` Statement**

1. **Definition and Purpose of the `switch` Statement**:
   * The `switch` statement is used to select one of many code blocks to execute based on the value of a variable or expression.
   * It is often more efficient than using multiple `if-else` conditions when comparing a variable to a series of possible values.
2.  **Basic Syntax and Structure of `switch`**:

    ```cpp
    switch (expression) {
        case value1:
            // Code to execute if expression == value1
            break;
        case value2:
            // Code to execute if expression == value2
            break;
        default:
            // Code to execute if expression doesn't match any case
            break;
    }
    ```
3. **Case Labels and Default Case**:
   * The `case` labels define the possible values of the expression.
   * The `default` case is optional and executes when none of the case labels match.
4.  **Example: Using `switch` for Multi-Option Decisions**:

    ```cpp
    int day = 3;
    switch (day) {
        case 1:
            cout << "Monday" << endl;
            break;
        case 2:
            cout << "Tuesday" << endl;
            break;
        case 3:
            cout << "Wednesday" << endl;
            break;
        default:
            cout << "Invalid day" << endl;
    }
    ```
5. **`break` and `continue` in `switch`**:
   * **`break`**: Exits the `switch` statement once a matching case is executed.
   * **`continue`**: Skips the remaining `switch` cases and continues with the rest of the program (not often used within `switch` but applicable in loops).
6.  **Nested `switch` Statements**:

    * `switch` statements can be nested within each other, allowing more complex decision-making logic.

    ```cpp
    int number = 2;
    switch (number) {
        case 1:
            cout << "Option 1" << endl;
            break;
        case 2:
            switch (number) {
                case 2:
                    cout << "Sub-option 2" << endl;
                    break;
            }
            break;
        default:
            cout << "Invalid option" << endl;
    }
    ```

***

## **Summary**

* **`if` Statements**: Used for basic condition checks. They can be nested for more complex logic.
* **`else` and `else if`**: Used to provide default actions or check multiple conditions.
* **Ternary Operator**: A shorthand for `if-else` logic, ideal for simple conditions.
* **`switch` Statement**: Efficient for multiple choices based on a single variable, with `case` labels and optional `default` handling.
