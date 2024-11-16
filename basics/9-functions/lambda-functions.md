# Lambda Functions

Lambda functions (or expressions) are a feature introduced in C++11 that allow for the creation of anonymous functions—functions without a name—directly within the code. They provide a powerful tool for short, concise, and inline function definitions, making the code cleaner and often more readable.

***

## **What are Lambda Functions?**

* A **Lambda Function** in C++ is an anonymous function that can be defined in-line within your code.
* It is often used as an argument to functions or algorithms that require a callback, such as sorting functions.
* A Lambda Function is a convenient way to define small functions that are used only once or a few times.

**Key Features**:

* Can be defined at the point of use.
* Useful for **callbacks** or operations that are small in scope.
* Can **capture variables** from the surrounding context.

***

## **Syntax of Lambda Expressions**

The basic syntax for a lambda expression is:

```cpp
[capture](parameters) -> return_type {
    // Function body
};
```

**Explanation**:

* `[capture]`: Specifies which variables are captured from the surrounding scope and how they are captured.
* `(parameters)`: Defines the parameters for the lambda, similar to a regular function.
* `-> return_type`: (Optional) Specifies the return type of the lambda.
* `{ body }`: Contains the code to be executed by the lambda.

**Example**:

```cpp
auto add = [](int a, int b) -> int {
    return a + b;
};
cout << add(5, 3);  // Output: 8
```

In this example:

* `[]` indicates that no external variables are captured.
* `(int a, int b)` specifies that the lambda takes two integer parameters.
* `-> int` specifies that the return type is `int`.
* The body simply returns the sum of `a` and `b`.

## **Capturing Variables in Lambda Functions**

Lambda expressions can access and use variables from the surrounding scope using a mechanism called **capturing**. There are two primary ways to capture variables:

### **Capture by Value**

* When capturing by value, a copy of the variable is made, and the lambda uses the copied value.
* Any changes made to the captured variable inside the lambda will not affect the original variable.

**Syntax**: `[x]` (capture `x` by value)

**Example**:

```cpp
int value = 10;
auto printValue = [value]() {
    cout << "Captured value: " << value << endl;
};
value = 20; // Changing the original variable
printValue(); // Output: Captured value: 10
```

In this case, `value` inside the lambda remains `10`, even though the original variable was changed to `20`.

### **Capture by Reference**

* When capturing by reference, the lambda has access to the original variable, and any changes made inside the lambda will reflect on the original variable.

**Syntax**: `[&x]` (capture `x` by reference)

**Example**:

```cpp
int value = 10;
auto modifyValue = [&value]() {
    value += 5;
};
modifyValue();
cout << "Modified value: " << value << endl; // Output: Modified value: 15
```

Here, `value` inside and outside the lambda refers to the same variable, so changes in the lambda are reflected globally.

## **Using Lambda Functions for Shorter Code**

Lambda functions are particularly handy when you want to write quick, in-line functions without defining a separate named function. They are often used with STL algorithms for shorter and more concise code.

**Example**:

```cpp
vector<int> numbers = {1, 3, 2, 5, 4};

// Using a lambda function to sort in descending order
sort(numbers.begin(), numbers.end(), [](int a, int b) {
    return a > b;
});

for (int num : numbers) {
    cout << num << " ";  // Output: 5 4 3 2 1
}
```

In this example, the lambda function is directly passed to `std::sort` to compare two integers, sorting them in descending order.

## **Using Lambda Functions with Algorithms**

Lambda functions are frequently used with algorithms from the C++ Standard Template Library (STL), like `std::sort`, `std::find_if`, and `std::for_each`.

**Example**:

```cpp
vector<int> data = {1, 2, 3, 4, 5, 6};

// Using `std::find_if` with a lambda function to find the first even number
auto isEven = [](int x) { return x % 2 == 0; };
auto result = find_if(data.begin(), data.end(), isEven);

if (result != data.end()) {
    cout << "First even number is: " << *result << endl; // Output: 2
}
```

Here, the lambda `isEven` is used to determine if a number is even, and it's directly passed to the `std::find_if` algorithm.

## **Advantages of Lambda Functions**

**Inline, Anonymous Functions**

* Lambda functions allow you to define small, one-off functions directly in the place where they're used, without cluttering the global scope with named functions.

**Localized Function Definitions for Convenience**

* Makes code easier to read and maintain, as the logic is encapsulated exactly where it is needed.
* Reduces the amount of boilerplate code, especially in simple scenarios where creating a named function would be overkill.

## **Limitations of Lambda Functions**

* **Complexity for Larger Functions**: While lambdas are great for small operations, larger functions can become unreadable if expressed as a lambda.
* **Type Inference Limitations**: In some cases, type inference in lambdas can be ambiguous, making the code harder to debug.
* **Performance Considerations**: Although lambdas are efficient, capturing variables (especially by value) can sometimes lead to unexpected performance hits if not managed carefully.
