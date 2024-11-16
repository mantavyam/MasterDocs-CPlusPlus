# File Input/Output

## **Introduction to File Streams**

* **Difference Between Console I/O and File I/O**\
  Console I/O uses standard input/output streams like `std::cin` and `std::cout`, which work with the console. File I/O, on the other hand, involves reading from and writing to files using specific file stream classes.
* **Opening and Closing Files**\
  To work with files, you need to open them using the appropriate file stream class (`std::ifstream`, `std::ofstream`, or `std::fstream`) and close them when done to free up resources.
* **Stream Classes for File I/O**\
  C++ provides three primary classes for file I/O operations:
  1. **`std::ifstream`**: For reading from files.
  2. **`std::ofstream`**: For writing to files.
  3. **`std::fstream`**: For both reading from and writing to files.

***

## **File Stream Classes**

* **`std::ifstream` (Input File Stream)**
  * Used to read from files.
  *   Syntax for reading from files:

      ```cpp
      std::ifstream inputFile("file.txt");
      if (inputFile.is_open()) {
          std::string line;
          while (getline(inputFile, line)) {
              std::cout << line << std::endl;
          }
          inputFile.close();
      } else {
          std::cout << "Unable to open file." << std::endl;
      }
      ```
* **`std::ofstream` (Output File Stream)**
  * Used to write to files.
  *   Syntax for writing to files:

      ```cpp
      std::ofstream outputFile("file.txt");
      if (outputFile.is_open()) {
          outputFile << "Hello, World!" << std::endl;
          outputFile.close();
      } else {
          std::cout << "Unable to open file." << std::endl;
      }
      ```
* **`std::fstream` (Bidirectional File Stream)**
  * Used for both reading from and writing to files.
  *   Syntax for both reading and writing:

      ```cpp
      std::fstream file("file.txt", std::ios::in | std::ios::out);
      if (file.is_open()) {
          file << "Writing to the file." << std::endl;
          file.seekg(0, std::ios::beg);  // Move to the beginning for reading
          std::string line;
          getline(file, line);
          std::cout << "Read from file: " << line << std::endl;
          file.close();
      } else {
          std::cout << "Unable to open file." << std::endl;
      }
      ```

***

## **File Handling Operations**

*   **Opening Files with `open()`**\
    Files can also be opened explicitly using the `open()` function:

    ```cpp
    std::ifstream inputFile;
    inputFile.open("file.txt");
    if (!inputFile) {
        std::cout << "Error opening file." << std::endl;
    }
    ```
*   **Checking File Open Status**\
    You can check if a file is open using `is_open()`:

    ```cpp
    if (file.is_open()) {
        std::cout << "File is open." << std::endl;
    } else {
        std::cout << "Failed to open the file." << std::endl;
    }
    ```
*   **Writing to Files with `<<`**\
    The `<<` operator is used for writing to files, just as it is for console output.

    ```cpp
    std::ofstream outputFile("file.txt");
    outputFile << "Writing to file" << std::endl;
    outputFile.close();
    ```
*   **Reading from Files with `>>`**\
    The `>>` operator can be used to extract data from files, similar to reading from the console:

    ```cpp
    int num;
    std::ifstream inputFile("file.txt");
    inputFile >> num;
    std::cout << "Read number: " << num << std::endl;
    inputFile.close();
    ```
*   **Closing Files**\
    After completing file operations, always close the file:

    ```cpp
    outputFile.close();
    ```
*   **File I/O Error Handling**\
    You can handle errors during file I/O operations by checking the state of the stream:

    ```cpp
    if (file.fail()) {
        std::cout << "File operation failed!" << std::endl;
    }
    ```

***

## **File Reading and Writing Examples**

1.  **Reading from a File**

    ```cpp
    std::ifstream inputFile("file.txt");
    std::string line;
    while (getline(inputFile, line)) {
        std::cout << line << std::endl;
    }
    inputFile.close();
    ```
2.  **Writing to a File**

    ```cpp
    std::ofstream outputFile("file.txt");
    outputFile << "Writing to a file" << std::endl;
    outputFile.close();
    ```
3.  **Bidirectional File Operations**

    ```cpp
    std::fstream file("file.txt", std::ios::in | std::ios::out);
    file << "Initial text." << std::endl;
    file.seekg(0, std::ios::beg);  // Reset to the beginning to read
    std::string text;
    getline(file, text);
    std::cout << "Read from file: " << text << std::endl;
    file.close();
    ```

***

### **Handling Text and Binary Files**

* **Text Files**\
  Text files store data as readable characters and are manipulated using `std::ifstream`, `std::ofstream`, and `std::fstream`.
*   **Binary Files**\
    Binary files store data in raw binary form (non-human readable). For binary files, use `std::ios::binary` flag when opening files:

    ```cpp
    std::ofstream binaryFile("file.bin", std::ios::binary);
    int num = 12345;
    binaryFile.write(reinterpret_cast<char*>(&num), sizeof(num));
    binaryFile.close();
    ```

    To read binary data:

    ```cpp
    std::ifstream binaryFile("file.bin", std::ios::binary);
    int num;
    binaryFile.read(reinterpret_cast<char*>(&num), sizeof(num));
    std::cout << "Read from binary file: " << num << std::endl;
    binaryFile.close();
    ```
