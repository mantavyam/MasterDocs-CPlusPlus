# 6 - Polymorphism

#### **Comprehensive Guide to Polymorphism in C++**

**Polymorphism** is one of the four fundamental principles of Object-Oriented Programming (OOP), alongside encapsulation, abstraction, and inheritance. It allows objects of different classes to be treated as objects of a common superclass. In C++, polymorphism enables you to write flexible and reusable code that can work with objects of different types in a uniform way.

***

#### **Concept Outline**

```
Polymorphism in C++
│
├── What is Polymorphism?
│   ├── Definition of Polymorphism in C++
│   │   ├── "Poly" (many) + "Morph" (forms) = Multiple Forms of Behavior
│   │   ├── Allows Objects of Different Classes to Be Treated as Objects of a Common Base Class
│   │   └── Enhances Flexibility and Reusability in Code
│   ├── Importance of Polymorphism
│   │   ├── Enables Method Overriding and Dynamic Dispatch
│   │   ├── Promotes Code Reusability and Extensibility
│   │   └── Supports Decoupling Between Components of the Program
│
├── Types of Polymorphism in C++
│   ├── Compile-Time Polymorphism
│   │   ├── Resolved at Compile Time
│   │   ├── Involves Function Overloading, Operator Overloading, and Template Functions
│   │   └── Benefits: Faster Execution, Early Error Detection
│   ├── Run-Time Polymorphism
│   │   ├── Resolved at Run Time Using Dynamic Dispatch
│   │   ├── Achieved Through Virtual Functions and Inheritance
│   │   └── Benefits: Allows More Flexible and Dynamic Behavior at Runtime
│
├── Compile-Time Polymorphism
│   ├── Function Overloading
│   │   ├── Definition: Defining Multiple Functions with the Same Name but Different Parameters
│   │   ├── Resolves at Compile Time Based on Function Signature (Number, Type, or Order of Parameters)
│   │   └── Example: Overloaded `add()` Function with Different Parameter Types (int, float)
│   ├── Operator Overloading
│   │   ├── Definition: Giving Special Meaning to Existing Operators for User-Defined Data Types
│   │   ├── Enables Custom Operations on Objects, Using Operators Like `+`, `-`, `[]`, etc.
│   │   └── Example: Overloading `+` for a `ComplexNumber` class
│   ├── Template Functions
│   │   ├── Definition: A Single Function Template That Works with Any Data Type
│   │   ├── Allows Function to Be Written Once and Used for Different Data Types
│   │   └── Example: A Template `max()` Function for Any Type `T`
│
├── Run-Time Polymorphism
│   ├── Virtual Functions
│   │   ├── Definition: Functions Defined in the Base Class and Overridden in Derived Classes
│   │   ├── Uses Dynamic Dispatch to Determine Which Function to Call at Run Time
│   │   ├── Ensures the Correct Function is Called Based on Object Type (Not Pointer Type)
│   │   └── Example: Virtual `draw()` Method in a Shape Class Hierarchy (Base: `Shape`, Derived: `Circle`, `Square`)
│   ├── Pure Virtual Functions and Abstract Classes
│   │   ├── Definition of Pure Virtual Function: A Function That Has No Implementation in the Base Class
│   │   ├── Abstract Class: A Class Containing At Least One Pure Virtual Function
│   │   ├── Abstract Classes Cannot Be Instantiated; They Are Intended to Be Used as Base Classes
│   │   └── Example: `Shape` Class with Pure Virtual `draw()` Function
│   ├── Virtual Functions and V-Table Mechanism
│   │   ├── V-Table (Virtual Table) Explained: A Lookup Table for Function Pointers Used in Dynamic Dispatch
│   │   ├── Each Object of a Class with Virtual Functions Has a Pointer to the V-Table
│   │   ├── When a Virtual Function Is Called, the V-Table Determines the Correct Function to Invoke
│   │   └── Example: Visualizing the V-Table with Inheritance and Overridden Functions
│   ├── Polymorphism with Pointers and References
│   │   ├── Using Base Class Pointers/References to Call Overridden Functions in Derived Classes
│   │   ├── Ensures that the Correct Function Is Called Based on the Actual Object Type
│   │   ├── Demonstrates the Power of Dynamic Binding in Polymorphism
│   │   └── Example: Base Class Pointer to Derived Class Object Calling the Overridden Function
│
├── Example: Implementing Polymorphism in C++
│   ├── Simple Example: Function Overloading with Different Parameter Types
│   │   ├── Overloaded `add()` Function for Integers and Floats
│   │   └── Output: Demonstrating Compile-Time Polymorphism
│   ├── Inheritance-Based Example: Virtual Function Overriding
│   │   ├── Base Class `Shape` with Virtual Function `draw()`
│   │   ├── Derived Classes `Circle` and `Square` Override `draw()`
│   │   └── Demonstrating Run-Time Polymorphism Using Base Class Pointers
│   ├── Advanced Example: Using Abstract Class and Virtual Functions
│   │   ├── Abstract `Shape` Class with Pure Virtual Function `draw()`
│   │   ├── Derived Classes Implement `draw()`
│   │   └── Example of Incomplete Polymorphism Using Abstract Class Instances
│
├── Polymorphism vs Overloading
│   ├── Difference Between Polymorphism and Overloading
│   │   ├── Overloading (Function/Operator): Resolved at Compile-Time, Multiple Functions/Operators with Same Name
│   │   └── Polymorphism: Resolved at Run-Time, Allows Dynamic Dispatch of Overridden Methods in Derived Classes
│   ├── Overloading vs Overriding
│   │   ├── Overloading: Multiple Functions with Same Name but Different Signatures
│   │   └── Overriding: Derived Class Replaces Base Class Method with New Implementation
│   ├── Use Cases for Polymorphism
│   │   ├── Polymorphism Is Used for Dynamic Behavior Based on Object Type (e.g., GUI Frameworks, Game Engines)
│   │   └── Overloading Is Useful for Simplifying Multiple Methods That Perform Similar Tasks with Different Data Types
│   └── Example of Polymorphism vs Overloading
│       ├── Example of Overloading for Multiple `add()` Implementations
│       └── Example of Polymorphism Using Virtual Functions for Dynamic Dispatch

```



***

#### **1. What is Polymorphism?**

The term **polymorphism** comes from Greek, meaning "many forms." In programming, it refers to the ability of a function or an object to behave differently in different contexts. In C++, polymorphism allows you to call the same function on different objects, and each object responds in its own way.

Polymorphism enhances the flexibility and maintainability of code by allowing objects to be treated as instances of their parent class rather than their actual derived class.

***

#### **2. Types of Polymorphism in C++**

Polymorphism in C++ can be broadly categorized into two types:

* **Compile-Time Polymorphism** (Static Polymorphism)
* **Run-Time Polymorphism** (Dynamic Polymorphism)

**Compile-Time Polymorphism**

Compile-time polymorphism is achieved through:

* **Function Overloading**
* **Operator Overloading**
* **Template Functions**

**Function Overloading**

Function overloading allows you to have multiple functions with the same name but different parameter lists.

**Example:**

```cpp
void display(int num) {
    std::cout << "Displaying integer: " << num << std::endl;
}

void display(double num) {
    std::cout << "Displaying double: " << num << std::endl;
}

void display(std::string str) {
    std::cout << "Displaying string: " << str << std::endl;
}
```

**Operator Overloading**

Operator overloading allows you to redefine the way operators work with user-defined types.

**Example:**

```cpp
class Complex {
public:
    double real, imag;

    Complex(double r = 0, double i =0) : real(r), imag(i) {}

    // Overload + operator
    Complex operator + (const Complex& obj) {
        return Complex(real + obj.real, imag + obj.imag);
    }
};
```

{% content-ref url="7-overloading.md" %}
[7-overloading.md](7-overloading.md)
{% endcontent-ref %}

**Template Functions**

Templates allow you to write generic functions that work with any data type.

**Example:**

```cpp
template <typename T>
T add(T a, T b) {
    return a + b;
}
```

**Run-Time Polymorphism**

Run-time polymorphism is achieved through:

* **Virtual Functions**
* **Pure Virtual Functions and Abstract Classes**

**Virtual Functions**

A **virtual function** is a member function in a base class that can be overridden in derived classes. It ensures that the correct function is called for an object, regardless of the reference type used to call the function.

**Syntax:**

```cpp
class Base {
public:
    virtual void display() {
        std::cout << "Display Base" << std::endl;
    }
};
```

**Pure Virtual Functions and Abstract Classes**

A **pure virtual function** is a function declared in a base class that has no definition relative to the base class.

**Syntax:**

```cpp
class Base {
public:
    virtual void display() = 0; // Pure virtual function
};
```

A class containing at least one pure virtual function is considered an **abstract class** and cannot be instantiated.

***

#### **3. Virtual Functions and V-Table Mechanism**

When a class has virtual functions, the compiler creates a **Virtual Table (V-Table)** for the class. The V-Table stores addresses of the virtual functions. Each object of the class contains a **Virtual Table Pointer (V-Ptr)** that points to the class's V-Table.

At runtime, when a virtual function is called using a base class pointer or reference, the V-Ptr is used to look up the correct function in the V-Table, ensuring that the appropriate derived class function is executed.

***

#### **4. Polymorphism with Pointers and References**

Polymorphism works when you use pointers or references to base classes to refer to objects of derived classes.

**Example:**

```cpp
class Base {
public:
    virtual void display() {
        std::cout << "Display Base" << std::endl;
    }
};

class Derived : public Base {
public:
    void display() override {
        std::cout << "Display Derived" << std::endl;
    }
};

int main() {
    Base* ptr;
    Derived obj;
    ptr = &obj;
    ptr->display(); // Output: Display Derived
    return 0;
}
```

In this example, even though `ptr` is of type `Base*`, it points to an object of `Derived`, and the `Derived` version of `display()` is called.

***

#### **5. Example: Implementing Polymorphism in C++**

Let's create a practical example using a base class `Shape` and derived classes `Circle` and `Rectangle`.

```cpp
#include <iostream>
#include <cmath>

class Shape {
public:
    virtual void draw() = 0;        // Pure virtual function
    virtual double area() = 0;      // Pure virtual function
    virtual ~Shape() {}             // Virtual destructor
};

class Circle : public Shape {
private:
    double radius;
public:
    Circle(double r) : radius(r) {}
    void draw() override {
        std::cout << "Drawing Circle" << std::endl;
    }
    double area() override {
        return M_PI * radius * radius;
    }
};

class Rectangle : public Shape {
private:
    double length, width;
public:
    Rectangle(double l, double w) : length(l), width(w) {}
    void draw() override {
        std::cout << "Drawing Rectangle" << std::endl;
    }
    double area() override {
        return length * width;
    }
};

int main() {
    Shape* shapes[2];

    shapes[0] = new Circle(5.0);
    shapes[1] = new Rectangle(4.0, 6.0);

    for (int i = 0; i < 2; ++i) {
        shapes[i]->draw();
        std::cout << "Area: " << shapes[i]->area() << std::endl;
    }

    // Clean up
    for (int i = 0; i < 2; ++i)
        delete shapes[i];

    return 0;
}
```

**Output:**

```
Drawing Circle
Area: 78.5398
Drawing Rectangle
Area: 24
```

In this example:

* `Shape` is an abstract class with pure virtual functions.
* `Circle` and `Rectangle` implement the `draw()` and `area()` functions.
* An array of `Shape*` is used to store different shapes.
* The correct `draw()` and `area()` functions are called at runtime.

***

#### **6. Polymorphism vs Overloading**

While both polymorphism and overloading involve functions with the same name, they are different concepts.

* **Polymorphism** allows the same function to behave differently based on the object that invokes it. It relies on inheritance and virtual functions and is resolved at runtime.
* **Overloading** is when multiple functions have the same name but different parameter lists. It is a compile-time mechanism.

***

#### **7. Best Practices for Using Polymorphism**

1.  **Use Virtual Destructors:**

    Always declare destructors as `virtual` in base classes when dealing with polymorphism to ensure derived class destructors are called properly.

    ```cpp
    class Base {
    public:
        virtual ~Base() {}
    };
    ```
2.  **Prefer References and Pointers:**

    Polymorphism works through base class pointers or references. Use them to store and manipulate derived class objects.
3.  **Avoid Slicing:**

    Object slicing occurs when a derived class object is assigned to a base class object, losing the derived part. To prevent this, use pointers or references.

    ```cpp
    Base b = Derived(); // Slicing occurs
    ```
4.  **Be Mindful of Performance:**

    Virtual function calls have a slight overhead due to the V-Table lookup. While usually negligible, be aware in performance-critical code.
5.  **Leverage Polymorphism for Extensibility:**

    Design your classes to be open for extension but closed for modification, following the Open/Closed Principle.

***

#### **8. Real-World Analogy of Polymorphism**

Consider a universal remote control (the base class) that can operate various devices like a TV, DVD player, or sound system (the derived classes). The remote sends the same "play" command, but each device responds differently:

* The **TV** might start playing a channel.
* The **DVD player** starts playing a disc.
* The **Sound system** might start playing music from a connected device.

This demonstrates polymorphism—the same action results in different behaviors depending on the object.

***

#### **9. Thought-Provoking Questions**

1.  **How does polymorphism contribute to the flexibility and maintainability of a software system?**

    _Hint:_ Think about how new classes can be added without modifying existing code.
2.  **What are some potential downsides of using polymorphism, and how can they be mitigated?**

    _Hint:_ Consider performance overhead and complexity.
3.  **How does polymorphism relate to the SOLID principles in software engineering?**

    _Hint:_ Reflect on the Open/Closed Principle and Liskov Substitution Principle.
4.  **Can polymorphism be achieved without inheritance? If so, how?**

    _Hint:_ Explore concepts like duck typing in other programming languages and templates in C++.

***

#### **Conclusion**

Polymorphism is a powerful feature of C++ that allows for flexible and reusable code. By understanding and effectively applying both compile-time and run-time polymorphism, you can design systems that are extensible and maintainable. Polymorphism enables you to program to an interface rather than an implementation, which is a key principle in software engineering.

Remember to use virtual functions wisely, always provide virtual destructors in base classes, and leverage polymorphism to write clean and efficient code. With practice and thoughtful design, polymorphism can greatly enhance the quality of your C++ applications.

