# String Streams

## What is a **String Stream?**

* A **string stream** is an object of the class `std::stringstream`, part of the `<sstream>` header.
* It is used for performing input and output operations on strings, similar to how `std::cin` and `std::cout` work for console input and output.
* String streams allow you to treat a string like a file or console for both reading and writing operations.

**Purpose and Use Cases of `std::stringstream`**

* **Converting Data Between Strings and Other Data Types**:
  * `std::stringstream` can be used to easily convert other data types (like `int`, `float`, `double`) to strings and vice versa. It provides a flexible way to format and parse strings.
* **Temporary In-Memory String Buffers for I/O Operations**:
  * String streams provide an in-memory buffer for performing input and output operations without interacting with actual files. It can be used as a temporary buffer during computations or data manipulations.

## **Declaration and Initialization**

1. **Declaring and Initializing`string`**:
   *   A `string` can be declared like any other variable:

       ```cpp
       string myString;
       ```
2. **Example: Declaring and Initializing`string` with a Literal**:
   *   You can initialize a string with a literal (constant text):

       ```cpp
       string greeting = "Hello, World!";
       ```
   *   Alternatively, you can initialize it using the constructor:

       ```cpp
       string greeting("Hello, World!");
       ```
3. **Initializing`string` with User Input or Other Strings**:
   *   Using user input to initialize a string:

       ```cpp
       string userInput;
       getline(cin, userInput);
       ```
   *   Copying another string:

       ```cpp
       string copyOfString = greeting;
       ```

## **Common Operations on `String`**

1. **Finding the Length of a String (`length()` or `size()`)**:
   *   You can use `length()` or `size()` to get the number of characters in the string:

       ```cpp
       string str = "Hello";
       cout << str.length();  // Outputs: 5
       ```
2. **Accessing Characters (`operator[]` and `at()`)**:
   *   You can access individual characters in a string using:

       ```cpp
       char c = str[0];  // Access first character 'H'
       char d = str.at(1);  // Access second character 'e'
       ```
3. **Appending Strings (`append()` and `+=`)**:
   *   To append to a string, you can use `append()` or the `+=` operator:

       ```cpp
       str.append(" World");
       str += "!";
       ```
4. **Substring Extraction (`substr()`)**:
   *   Extract a portion of a string:

       ```cpp
       string substr = str.substr(0, 5);  // Extracts "Hello"
       ```
5. **Comparing Strings (`compare()`)**:
   *   Compare two strings lexicographically:

       ```cpp
       if (str.compare("Hello") == 0) {
           cout << "Strings are equal." << endl;
       }
       ```
6. **Searching for Characters or Substrings (`find()`)**:
   *   Search for a character or substring within a string:

       ```cpp
       size_t position = str.find("World");  // Returns position if found, std::string::npos if not found
       ```
7. **Removing Whitespace or Characters (`erase()`, `replace()`, `clear()`)**:
   *   Removing characters:

       ```cpp
       str.erase(0, 5);  // Removes the first 5 characters of str
       ```
   *   Replacing characters or substrings:

       ```cpp
       str.replace(0, 5, "Hi");
       ```
   *   Clearing the entire string:

       ```cpp
       str.clear();  // Empties the string
       ```

## **String Concatenation and Comparison**

1. **Concatenating Strings with `+` and `+=`**:
   *   You can concatenate strings using the `+` operator or the `+=` operator:

       ```cpp
       string str1 = "Hello";
       string str2 = "World";
       string combined = str1 + " " + str2;  // "Hello World"
       str1 += " World";  // Appends " World" to str1
       ```
2. **Comparing Strings Lexicographically**:
   *   Lexicographical comparison is done using the `compare()` method or the `<`, `>`, `==` operators:

       ```cpp
       if (str1 == str2) {
           cout << "Strings are equal." << endl;
       }
       ```
3. **Case-insensitive Comparison**:
   * For case-insensitive comparison, you can either convert both strings to lowercase/uppercase using `std::transform()` or use libraries that offer case-insensitive comparison directly.
4.  **Example: Using String Comparison and Concatenation in Real Programs**:

    <pre class="language-cpp"><code class="lang-cpp">string userFirstName, userLastName;
    cout &#x3C;&#x3C; "Enter your first name: ";
    getline(cin, userFirstName);

    <strong>cout &#x3C;&#x3C; "Enter your last name: ";
    </strong>getline(cin, userLastName);

    string fullName = userFirstName + " " + userLastName;
    cout &#x3C;&#x3C; "Full Name: " &#x3C;&#x3C; fullName &#x3C;&#x3C; endl;
    </code></pre>

## **String Input and Output**

1. **Inputting Strings Using `std::cin`**:
   *   You can use `std::cin` to read individual words or data:

       <pre class="language-cpp"><code class="lang-cpp">string name;
       <strong>cin >> name;  // Reads a single word (stops at space)
       </strong></code></pre>
2. **Reading Full Lines (including spaces) with `std::getline()`**:
   *   To read an entire line, including spaces, use `std::getline()`:

       ```cpp
       string sentence;
       getline(cin, sentence);  // Reads a full line including spaces
       ```
3. **Outputting Strings with `std::cout`**:
   *   To output a string, simply use `std::cout`:

       ```cpp
       string message = "Hello, World!";
       cout << message << endl;  // Outputs: Hello, World!
       ```

**Using `std::stringstream` for String Input and Output**

* String streams can be used for both extracting and inserting data. You can read from a string or write data to a string using `std::stringstream`.
*   **Example**:

    ```cpp
    #include <iostream>
    #include <sstream>  // For stringstream
    using namespace std;

    int main() {
        // Writing to a stringstream
        stringstream ss;
        ss << "Hello, " << "World! " << 2024;
        
        // Reading from a stringstream
        string result;
        ss >> result;  // Reads the first word ("Hello,")
        cout << "Extracted: " << result << endl;

        ss >> result;  // Reads the next word ("World!")
        cout << "Extracted: " << result << endl;

        return 0;
    }
    ```

## **Reading from String with `std::stringstream`**

* You can use `std::stringstream` to read data from a string the same way you use `std::cin` to read from the console.
*   **Example**:

    ```cpp
    #include <iostream>
    #include <sstream>
    using namespace std;

    int main() {
        string input = "123 456 789";
        stringstream ss(input);
        
        int num;
        while (ss >> num) {
            cout << "Read number: " << num << endl;
        }
        
        return 0;
    }
    ```

    **Output**:

    ```
    Read number: 123
    Read number: 456
    Read number: 789
    ```

## **Writing to String with `std::stringstream`**

* `std::stringstream` can be used to write formatted data into a string. This can be useful for constructing strings or formatting data.
*   **Example**:

    ```cpp
    #include <iostream>
    #include <sstream>
    using namespace std;

    int main() {
        stringstream ss;
        int a = 10, b = 20;
        
        // Writing to the stringstream
        ss << "Sum of " << a << " and " << b << " is: " << (a + b);
        
        // Converting the stringstream content to a string
        string result = ss.str();
        
        cout << "Result: " << result << endl;
        return 0;
    }
    ```

    **Output**:

    ```
    Result: Sum of 10 and 20 is: 30
    ```

