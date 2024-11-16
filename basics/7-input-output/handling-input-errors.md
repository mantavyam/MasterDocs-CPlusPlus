# Handling Input Errors

## **Types of Input Errors**

1. **Invalid Input (e.g., type mismatches)**: This occurs when the user enters a value that doesn't match the expected type, such as entering text when a number is expected.
2. **End-of-File (EOF) Conditions**: This happens when the input stream reaches the end of the file (or standard input stream) and no further input can be read.
3. **Stream Failures**: These happen when the input stream encounters an error, like if the input is corrupted or unavailable.

***

## **Detecting and Handling Input Failures**

1.  **Using `std::cin.fail()` for Checking Input Errors**\
    This function checks if the input stream has failed due to incorrect input. It returns `true` if the last input operation failed.

    ```cpp
    if (std::cin.fail()) {
        std::cout << "Input error occurred!" << std::endl;
    }
    ```
2.  **Clearing Error Flags with `std::cin.clear()`**\
    When an error occurs (e.g., invalid input), the input stream is set into a fail state. You can clear the error flags to resume normal input.

    ```cpp
    std::cin.clear();  // Clears error flags
    ```
3.  **Ignoring Incorrect Input with `std::cin.ignore()`**\
    If an invalid input is entered (such as a non-integer when expecting an integer), `std::cin.ignore()` can be used to ignore the invalid input and clear the buffer.

    ```cpp
    std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
    ```
4.  **Flushing the Input Stream using `std::cin.ignore()` and `std::cin.get()`**\
    Sometimes, it’s necessary to clear all remaining characters from the input buffer. `std::cin.ignore()` skips unwanted characters, and `std::cin.get()` reads the next character.

    ```cpp
    std::cin.ignore();  // Ignore the first character
    std::cin.get();     // Read and discard the next character
    ```
5.  **Example: Handling Invalid Integer Input** Here’s a simple example that asks the user to enter a number and checks for invalid input:

    ```cpp
    int number;
    std::cout << "Enter an integer: ";
    while (!(std::cin >> number)) {  // Checks for invalid input
        std::cin.clear();             // Clears error flag
        std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n'); // Clears buffer
        std::cout << "Invalid input. Please enter a valid integer: ";
    }
    std::cout << "You entered: " << number << std::endl;
    ```

***

## **Correcting Input Mistakes**

1.  **Asking for Input Again**\
    When invalid input is detected, you can prompt the user to re-enter the input until it’s valid.

    ```cpp
    std::cout << "Invalid input, please try again: ";
    ```
2. **Cleaning up Input Buffers**\
   After handling input errors, it’s often necessary to clean up the input buffer to prevent leftover characters from affecting subsequent inputs. This can be done using `std::cin.ignore()` or `std::cin.get()` as discussed earlier.

***

## **Dealing with EOF (End of File)**

*   **EOF Detection**: You can detect when the end of the input stream has been reached by checking the EOF flag.

    ```cpp
    if (std::cin.eof()) {
        std::cout << "End of file reached." << std::endl;
    }
    ```
*   **Handling EOF in Input Loops**: You can use `std::cin` to read inputs until the end of the file is encountered. For example, reading a file or input stream until EOF is reached:

    ```cpp
    std::string line;
    while (std::getline(std::cin, line)) {  // Reads until EOF or error
        std::cout << "You entered: " << line << std::endl;
    }
    ```
