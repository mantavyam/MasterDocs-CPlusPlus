# Looping Constructs

## **Overview of Looping Constructs**

1. **Purpose of Loops in Repeating Code Blocks**:
   * Loops are used to execute a block of code multiple times, depending on a condition. They help reduce redundancy in code, making it more efficient and maintainable.
   * They are essential for tasks like iterating over arrays, processing data, and automating repetitive tasks.
2. **Types of Loops in C++**:
   * **`for` Loop**: Used when the number of iterations is known in advance.
   * **`while` Loop**: Used when the number of iterations is not known, but the condition must be checked before the loop body is executed.
   * **`do-while` Loop**: Similar to the `while` loop but guarantees at least one execution of the loop body.

***

### **1. `for` Loop**

1.  **Syntax of `for` Loop**:

    ```cpp
    for (initialization; condition; increment/decrement) {
        // Code to execute repeatedly
    }
    ```

    * **Initialization**: Defines the starting point of the loop (e.g., setting a counter).
    * **Condition**: A boolean expression evaluated before each iteration. If true, the loop executes; if false, it terminates.
    * **Increment/Decrement**: Modifies the loop variable after each iteration (e.g., `i++` or `i--`).
2.  **Example: Using `for` for Counting or Iterating Over Arrays**:

    ```cpp
    for (int i = 0; i < 5; i++) {
        cout << "Iteration: " << i << endl;
    }
    ```

    * This prints the numbers from 0 to 4.
3.  **Nested `for` Loops**:

    * A `for` loop can be nested inside another `for` loop to handle multi-dimensional data or complex iteration patterns.

    ```cpp
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cout << "i: " << i << ", j: " << j << endl;
        }
    }
    ```

    * This will print all combinations of `i` and `j` from 0 to 2.
4.  **Using `break` and `continue` Inside a `for` Loop**:

    * **`break`**: Exits the loop entirely.
    * **`continue`**: Skips the current iteration and moves to the next one.

    ```cpp
    for (int i = 0; i < 5; i++) {
        if (i == 3) {
            break;  // Exit loop when i is 3
        }
        cout << i << " ";
    }
    // Output: 0 1 2
    ```
5.  **Use of `for` Loop for Range-based Iteration in C++11 and Later**:

    * Introduced in C++11, range-based `for` loops allow easy iteration over containers like arrays or vectors.

    ```cpp
    int arr[] = {1, 2, 3, 4};
    for (int num : arr) {
        cout << num << " ";  // Output: 1 2 3 4
    }
    ```

***

### **2. `while` Loop**

1.  **Syntax of `while` Loop**:

    ```cpp
    while (condition) {
        // Code to execute repeatedly as long as the condition is true
    }
    ```

    * The loop continues as long as the condition is true. The condition is checked before each iteration, meaning if the condition is false initially, the loop might not execute at all.
2.  **Example: Using `while` for Repeating Code While a Condition is True**:

    ```cpp
    int count = 0;
    while (count < 5) {
        cout << "Count: " << count << endl;
        count++;
    }
    ```

    * This loop will print "Count: 0" through "Count: 4".
3.  **Potential Risks: Infinite Loops in `while` Loop**:

    * **Infinite Loops**: If the loop condition is always true, the loop will run indefinitely, which is a common mistake.

    ```cpp
    int count = 0;
    while (count >= 0) {  // This will create an infinite loop
        cout << count << endl;
        count++;  // If this line is omitted, the condition will always be true
    }
    ```

***

### **3. `do-while` Loop**

1.  **Syntax of `do-while` Loop**:

    ```cpp
    do {
        // Code to execute at least once
    }
    while (condition);
    ```

    * The key difference between `do-while` and `while` is that the condition is checked **after** the loop body is executed, guaranteeing that the loop will execute at least once, regardless of the condition.
2.  **Example: Using `do-while` for Loops that Must Execute at Least Once**:

    ```cpp
    int count = 0;
    do {
        cout << "Count: " << count << endl;
        count++;
    }
    while (count < 5);
    ```

    * This will print "Count: 0" through "Count: 4".
3. **Differences Between `while` and `do-while`**:
   * **`while` Loop**: The condition is evaluated before the loop body executes. If the condition is false initially, the loop might not run at all.
   * **`do-while` Loop**: The loop body always executes at least once, even if the condition is false.
4. **Potential Use Cases for `do-while` Loops**:
   * **Menu systems**: When you want to display a menu and ask for user input at least once.
   * **Retrying an operation**: When you want to give the user a chance to retry an operation if the first attempt fails.

***

## **Summary**

* **`for` Loop**: Ideal when the number of iterations is known in advance. Can be used with simple increments/decrements or more complex logic (e.g., nested loops, range-based iteration).
* **`while` Loop**: Ideal when you don’t know how many times the loop should run, but it should run as long as the condition is true. Be cautious of infinite loops.
* **`do-while` Loop**: Ensures the loop runs at least once, making it useful for situations where the loop must execute an action before checking a condition (e.g., user input validation).
