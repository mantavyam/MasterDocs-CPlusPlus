# Default Arguments

In C++, **default arguments** allow you to specify a value for a function's parameters when the user does not provide them. This can simplify code, reduce redundancy, and provide flexibility by setting default behavior for functions.

***

## **Definition**

* **Default Arguments** are values that are assigned to parameters in a function declaration.
* If no value is provided when the function is called, the default value is used.
* This helps to create functions that can be called with varying numbers of arguments, increasing their usability.

**Example**:

```cpp
#include <iostream>
using namespace std;

// Function declaration with default argument
void greet(string name = "Guest") {
    cout << "Hello, " << name << "!" << endl;
}

int main() {
    greet();            // Uses default value "Guest"
    greet("Alice");     // Uses the provided value "Alice"
    return 0;
}
```

**Output**:

```
Hello, Guest!
Hello, Alice!
```

## **Syntax**

* Default arguments are specified in the **function declaration**, not in the function definition.
* They are provided by assigning a value to a parameter in the function's prototype or the function's definition if there's no separate prototype.

**Syntax Example**:

```cpp
void functionName(int param1 = 5, float param2 = 10.5);
```

**Explanation**:

* Here, `param1` has a default value of `5` and `param2` has a default value of `10.5`.
* If `functionName()` is called without arguments, it will use the default values.
* You can also partially omit arguments, and C++ will use defaults for the omitted ones.

## **How Default Arguments Work**

* **Default arguments** work by automatically substituting values when arguments are missing in the function call.
* During a function call, if a user does not provide values for parameters with default values, the compiler substitutes the default arguments.
* This allows you to call the same function with different numbers of parameters.

**Example**:

```cpp
#include <iostream>
using namespace std;

// Function declaration with multiple default arguments
void displayInfo(string name = "Unknown", int age = 18, string country = "Unknown") {
    cout << "Name: " << name << ", Age: " << age << ", Country: " << country << endl;
}

int main() {
    displayInfo();                         // All defaults: "Unknown", 18, "Unknown"
    displayInfo("John");                   // Defaults: age = 18, country = "Unknown"
    displayInfo("Emma", 25);               // Default: country = "Unknown"
    displayInfo("Liam", 30, "Canada");     // No defaults used
    return 0;
}
```

**Output**:

```
Name: Unknown, Age: 18, Country: Unknown
Name: John, Age: 18, Country: Unknown
Name: Emma, Age: 25, Country: Unknown
Name: Liam, Age: 30, Country: Canada
```

## **Order of Default Arguments**

* Default arguments must be **trailing parameters** in the parameter list.
* Once you provide a default value for a parameter, **all subsequent parameters must also have default values**.

**Correct Example**:

```cpp
void calculate(int a, int b = 10, int c = 20);  // Valid
```

**Incorrect Example**:

```cpp
void calculate(int a = 10, int b);  // Invalid: 'a' has a default but 'b' does not
```

**Explanation**:

* In the correct example, parameters `b` and `c` have default values.
* In the incorrect example, the compiler would not know what to do if only one argument is provided.

## **Example: Function with Default Arguments**

Here’s a practical example to illustrate how default arguments can be useful:

```cpp
#include <iostream>
using namespace std;

// Function to calculate the final price after applying a discount
// Default discount percentage is 5%
double calculateFinalPrice(double price, double discount = 5.0) {
    double discountAmount = (price * discount) / 100;
    return price - discountAmount;
}

int main() {
    double price1 = 100.0;
    double price2 = 200.0;

    // Using default discount of 5%
    cout << "Final price with default discount: " << calculateFinalPrice(price1) << endl;

    // Providing a custom discount of 10%
    cout << "Final price with 10% discount: " << calculateFinalPrice(price2, 10.0) << endl;

    return 0;
}
```

**Output**:

```
Final price with default discount: 95
Final price with 10% discount: 180
```
