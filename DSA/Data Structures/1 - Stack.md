Sure! Here's a comprehensive guide to understanding stacks in C++ as part of Data Structures and Algorithms (DSA). This guide will cover the definition, operations, implementations, applications, and examples.

---

# **Guide to Stack in C++ DSA**

## **1. Introduction to Stack**
A **stack** is a linear data structure that follows the **Last In First Out (LIFO)** principle, meaning the last element added to the stack is the first one to be removed. It can be visualized as a stack of plates where you can only add or remove the top plate.

### **Basic Properties**
- **Push:** Add an element to the top of the stack.
- **Pop:** Remove the top element from the stack.
- **Top/Peek:** Retrieve the top element without removing it.
- **isEmpty:** Check if the stack is empty.
- **Size:** Get the number of elements in the stack.

## **2. Stack Operations**
The primary operations for a stack include:

| Operation | Description                     |
|-----------|---------------------------------|
| **push(x)**   | Adds element `x` to the top of the stack. |
| **pop()**     | Removes the top element of the stack.     |
| **top()**     | Returns the top element without removing it. |
| **isEmpty()** | Returns true if the stack is empty, else false. |
| **size()**    | Returns the number of elements in the stack. |

## **3. Stack Implementation in C++**

### **Using an Array**
Here’s how you can implement a stack using a fixed-size array:

```cpp
#include <iostream>
using namespace std;

#define MAX 100

class Stack {
private:
    int arr[MAX];
    int top;

public:
    Stack() {
        top = -1; // Initialize the top to -1
    }

    // Push operation
    void push(int x) {
        if (top >= MAX - 1) {
            cout << "Stack Overflow!" << endl;
            return;
        }
        arr[++top] = x; // Increment top and insert the element
    }

    // Pop operation
    int pop() {
        if (top < 0) {
            cout << "Stack Underflow!" << endl;
            return -1; // Return an invalid value
        }
        return arr[top--]; // Return the top element and decrement top
    }

    // Peek operation
    int peek() {
        if (top < 0) {
            cout << "Stack is empty!" << endl;
            return -1; // Return an invalid value
        }
        return arr[top]; // Return the top element
    }

    // Check if stack is empty
    bool isEmpty() {
        return (top < 0);
    }

    // Get the size of the stack
    int size() {
        return top + 1;
    }
};

int main() {
    Stack s;

    s.push(10);
    s.push(20);
    s.push(30);

    cout << "Top element is: " << s.peek() << endl; // Output: 30
    cout << "Stack size is: " << s.size() << endl;  // Output: 3

    cout << "Popped element is: " << s.pop() << endl; // Output: 30
    cout << "New top element is: " << s.peek() << endl; // Output: 20

    return 0;
}
```

### **Using STL (Standard Template Library)**
C++ provides a built-in stack container in the STL, which can be used as follows:

```cpp
#include <iostream>
#include <stack> // Include the stack header
using namespace std;

int main() {
    stack<int> s;

    // Push elements
    s.push(10);
    s.push(20);
    s.push(30);

    cout << "Top element is: " << s.top() << endl; // Output: 30
    cout << "Stack size is: " << s.size() << endl; // Output: 3

    cout << "Popped element is: " << s.top() << endl; // Output: 30
    s.pop();

    cout << "New top element is: " << s.top() << endl; // Output: 20

    return 0;
}
```

## **4. Applications of Stack**
Stacks have numerous applications, including:

1. **Function Call Management:** Function calls are managed using a call stack, where local variables and return addresses are stored.
2. **Expression Evaluation:** Stacks can be used to evaluate postfix and infix expressions.
3. **Backtracking Algorithms:** Used in algorithms like maze solving, N-Queens, etc.
4. **Memory Management:** Used in managing memory, especially for local variables in recursive functions.
5. **Undo Mechanisms:** In text editors, stacks can be used to implement the undo feature.

## **5. Complexity Analysis**
The time complexity for the primary stack operations is as follows:
- **Push:** O(1)
- **Pop:** O(1)
- **Top/Peek:** O(1)
- **isEmpty:** O(1)
- **Size:** O(1)

## **6. Conclusion**
Understanding stacks is essential for mastering more complex data structures and algorithms. They are widely used in both theoretical and practical applications, making them a fundamental concept in computer science.

Feel free to ask if you need further clarification on specific operations, or examples, or if you have any other questions related to stacks in C++!