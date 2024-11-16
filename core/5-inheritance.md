# 5 - Inheritance

#### **Comprehensive Guide to Inheritance in C++**

Inheritance is one of the four key pillars of Object-Oriented Programming (OOP), along with encapsulation, abstraction, and polymorphism. Inheritance allows one class to acquire the properties (methods and fields) of another class, promoting code reusability, maintainability, and a hierarchical class structure.

***

#### **Concept Outline**

```
Inheritance in C++
│
├── What is Inheritance?
│   ├── Definition of Inheritance
│   │   ├── Mechanism in OOP that Allows One Class (Child/Derived Class) to Inherit Attributes and Methods from Another Class (Parent/Base Class)
│   │   ├── Enables Code Reusability and Method Overriding
│   │   └── Facilitates Creating Hierarchical Relationships Between Classes
│   ├── Benefits of Inheritance
│   │   ├── Promotes Code Reusability and Extensibility
│   │   ├── Allows for Better Organization of Code in Hierarchical Structures
│   │   └── Enables Polymorphism, Method Overriding, and Dynamic Dispatch
│   ├── Inheritance in Object-Oriented Programming (OOP)
│   │   ├── Provides a Clear Parent-Child Relationship Between Classes
│   │   └── The Child Class Inherits Data Members and Functions of the Parent Class
│
├── Types of Inheritance in C++
│   ├── Single Inheritance
│   │   ├── A Derived Class Inherits from Only One Base Class
│   │   ├── Simple Parent-Child Relationship
│   │   └── Example: `Car` inherits from `Vehicle` class
│   ├── Multiple Inheritance
│   │   ├── A Derived Class Inherits from More Than One Base Class
│   │   ├── C++ Allows Multiple Inheritance, Unlike Some Other Languages
│   │   └── Example: `FlyingCar` inherits from both `Car` and `Aircraft` classes
│   ├── Multilevel Inheritance
│   │   ├── A Class is Derived from Another Derived Class, Forming a Chain of Inheritance
│   │   ├── Example: `Car` inherits from `Vehicle`, `ElectricCar` inherits from `Car`
│   │   └── The Child Class Inherits Properties and Methods of Its Parent and Grandparent Classes
│   ├── Hierarchical Inheritance
│   │   ├── Multiple Derived Classes Inherit from a Single Base Class
│   │   ├── Each Derived Class Inherits the Same Attributes and Methods from the Base Class
│   │   └── Example: `Car`, `Truck`, and `Bus` inherit from `Vehicle` class
│   ├── Hybrid Inheritance
│   │   ├── A Combination of More Than One Type of Inheritance
│   │   ├── Can Involve Multiple, Multilevel, or Hierarchical Inheritance
│   │   └── Example: A Class `FlyingTruck` Inherits from Both `Truck` (Hierarchical) and `Aircraft` (Multiple)
│
├── Access Specifiers and Inheritance
│   ├── Overview of Access Specifiers
│   │   ├── `public`: Members Are Accessible from Anywhere
│   │   ├── `protected`: Members Are Accessible Within the Class and Derived Classes
│   │   └── `private`: Members Are Only Accessible Within the Class Itself
│   ├── Access Specifiers in Derived Classes
│   │   ├── How Different Access Specifiers Affect Inheritance
│   │   ├── `public` Inheritance: Public Members of the Base Class Stay Public in the Derived Class
│   │   ├── `protected` Inheritance: Public Members of the Base Class Become Protected in the Derived Class
│   │   └── `private` Inheritance: Public Members of the Base Class Become Private in the Derived Class
│   └── Example: Effects of Access Specifiers in Inherited Classes
│       ├── Example of Public Inheritance and Member Visibility
│       └── Example of Private Inheritance Making Base Class Members Inaccessible
│
├── Constructor and Destructor Behavior in Inheritance
│   ├── Constructor Behavior
│   │   ├── Base Class Constructor Is Called First, Then Derived Class Constructor
│   │   ├── Can Be Explicitly Called Using Constructor Initialization List
│   │   └── Example: Calling the Base Class Constructor from Derived Class Constructor
│   ├── Destructor Behavior
│   │   ├── Derived Class Destructor Is Called First, Then Base Class Destructor
│   │   ├── Ensures Proper Cleanup of Resources in Both Base and Derived Classes
│   │   └── Virtual Destructors in Base Class to Avoid Undefined Behavior on Deletion of Derived Class Objects
│   └── Example: Constructor and Destructor Call Order in Inheritance
│       ├── Example of Constructor Initialization List for Base Class
│       └── Example of Virtual Destructor in Base Class
│
├── Virtual Base Classes
│   ├── What is a Virtual Base Class?
│   │   ├── A Mechanism to Avoid the Diamond Problem in Multiple Inheritance
│   │   ├── Ensures That a Base Class is Only Inherited Once, Even if It Appears Multiple Times in the Inheritance Chain
│   │   └── Introduced Using the `virtual` Keyword in the Base Class of a Multiple Inheritance Hierarchy
│   ├── The Diamond Problem
│   │   ├── Occurs When Two Classes Inherit From the Same Base Class and a Further Class Inherits from Both of Them
│   │   └── Results in Multiple Instances of the Same Base Class
│   └── Example: Use of Virtual Base Class to Resolve Diamond Problem
│       ├── Example of Virtual Base Class with Multiple Inheritance
│       └── Ensuring Only One Instance of Base Class Members
│
├── Example: Implementing Inheritance in C++
│   ├── Simple Example of Inheritance: Vehicle and Car
│   │   ├── `Vehicle` Class as the Base Class
│   │   └── `Car` Class as the Derived Class, Overriding a Function (e.g., `drive()`)
│   ├── Complex Example of Multiple Inheritance: FlyingCar
│   │   ├── `Car` Class and `Aircraft` Class as Base Classes
│   │   └── `FlyingCar` Class Inherits from Both, Demonstrating Multiple Inheritance
│   └── Polymorphism in Inheritance
│       ├── Example: Using Base Class Pointers to Call Derived Class Methods
│       └── Demonstrating Dynamic Binding in Inheritance
│
├── Inheritance vs Composition
│   ├── What is Composition?
│   │   ├── Creating Complex Objects by Combining Simpler Objects
│   │   ├── A "Has-A" Relationship Between Classes
│   │   └── Example: `Car` Has-A `Engine` (Composition) vs `Car` Is-A `Vehicle` (Inheritance)
│   ├── Inheritance
│   │   ├── Establishes "Is-A" Relationship
│   │   └── Derived Class Inherits Behavior and Attributes from the Base Class
│   ├── Composition
│   │   ├── Establishes "Has-A" Relationship
│   │   └── Combines Objects to Form More Complex Structures
│   ├── When to Use Inheritance vs Composition
│   │   ├── Use Inheritance When There Is a Clear Hierarchical Relationship
│   │   └── Use Composition When You Need to Combine Components and Avoid Inheritance Overhead
│   └── Example: Comparing Inheritance and Composition
│       ├── Example of Inheritance: `Bird` Is-A `Animal`
│       └── Example of Composition: `Car` Has-A `Engine`
```

***

#### **1. What is Inheritance?**

**Inheritance** is a feature of OOP where one class (called the **derived class** or **child class**) inherits properties and behaviors (fields and methods) from another class (called the **base class** or **parent class**). Inheritance allows us to define new classes based on existing ones, making it easy to create more specific versions of generic objects.

***

#### **2. Types of Inheritance in C++**

C++ supports different types of inheritance, each useful in different scenarios.

**Single Inheritance**

This is the simplest form of inheritance where a single derived class inherits from a single base class.

```cpp
class Base {
public:
    void show() {
        cout << "Base class method" << endl;
    }
};

class Derived : public Base {
};
```

**Multiple Inheritance**

In multiple inheritance, a derived class inherits from more than one base class.

```cpp
class Base1 {
public:
    void show() {
        cout << "Base1 class method" << endl;
    }
};

class Base2 {
public:
    void display() {
        cout << "Base2 class method" << endl;
    }
};

class Derived : public Base1, public Base2 {
};
```

**Multilevel Inheritance**

In multilevel inheritance, a class derives from another derived class, creating a chain of inheritance.

```cpp
class Base {
public:
    void show() {
        cout << "Base class method" << endl;
    }
};

class Intermediate : public Base {
};

class Derived : public Intermediate {
};
```

**Hierarchical Inheritance**

This occurs when more than one class is derived from a single base class.

```cpp
class Base {
public:
    void show() {
        cout << "Base class method" << endl;
    }
};

class Derived1 : public Base {
};

class Derived2 : public Base {
};
```

**Hybrid Inheritance**

Hybrid inheritance is a combination of two or more types of inheritance. It can often lead to the **diamond problem** in C++, which is resolved using **virtual base classes**.

***

#### **3. Access Specifiers and Inheritance**

When inheritance occurs, the access specifier (`public`, `protected`, `private`) plays a crucial role in determining what members of the base class are accessible in the derived class. There are three ways a derived class can inherit members of the base class:

1. **Public Inheritance**: The public and protected members of the base class remain public and protected in the derived class.
2. **Protected Inheritance**: Public and protected members of the base class become protected members in the derived class.
3. **Private Inheritance**: Public and protected members of the base class become private members in the derived class.

```cpp
class Base {
protected:
    int protected_var;
public:
    int public_var;
};

class Derived : public Base {
public:
    void access() {
        public_var = 10;    // Allowed
        protected_var = 20; // Allowed (protected members are accessible in derived class)
    }
};
```

***

#### **4. Constructor and Destructor Behavior in Inheritance**

In C++, constructors of base classes are called **before** the constructor of the derived class, while destructors are called in the **reverse order** (derived class destructor first, then base class destructor).

```cpp
class Base {
public:
    Base() {
        cout << "Base class constructor" << endl;
    }
    ~Base() {
        cout << "Base class destructor" << endl;
    }
};

class Derived : public Base {
public:
    Derived() {
        cout << "Derived class constructor" << endl;
    }
    ~Derived() {
        cout << "Derived class destructor" << endl;
    }
};
```

**Output**:

```
Base class constructor
Derived class constructor
Derived class destructor
Base class destructor
```

***

#### **5. Virtual Base Classes**

When using **multiple inheritance** and a class inherits from the same base class through multiple paths (diamond problem), C++ allows us to use a **virtual base class** to ensure that only one instance of the base class is created.

```cpp
class Base {
public:
    int var;
};

class Derived1 : virtual public Base {
};

class Derived2 : virtual public Base {
};

class Derived3 : public Derived1, public Derived2 {
};
```

Without virtual inheritance, `Derived3` would have two separate instances of `Base`, but with `virtual`, only one instance of `Base` exists.

***

#### **6. Example: Implementing Inheritance in C++**

Let’s consider an example where we implement inheritance using a base class `Animal` and derived classes `Dog` and `Cat`.

```cpp
#include <iostream>
using namespace std;

// Base class
class Animal {
public:
    void speak() {
        cout << "This is an animal" << endl;
    }
};

// Derived class for Dog
class Dog : public Animal {
public:
    void speak() {
        cout << "Dog says: Woof Woof" << endl;
    }
};

// Derived class for Cat
class Cat : public Animal {
public:
    void speak() {
        cout << "Cat says: Meow Meow" << endl;
    }
};

int main() {
    Dog dog;
    Cat cat;

    dog.speak(); // Output: Dog says: Woof Woof
    cat.speak(); // Output: Cat says: Meow Meow

    return 0;
}
```

In this example:

* `Dog` and `Cat` inherit from the base class `Animal`.
* Each derived class provides its own implementation of the `speak` method.

***

#### **7. Inheritance vs Composition**

Although inheritance is a powerful feature, it’s not always the best solution. In some cases, **composition** might be a better choice. Inheritance creates a _"is-a"_ relationship (e.g., a Dog is an Animal), while composition represents a _"has-a"_ relationship (e.g., a Car has an Engine).

**When to use inheritance?**

* When you need to model a _"is-a"_ relationship.
* When the derived class is a specialized version of the base class.

**When to use composition?**

* When you need to model a _"has-a"_ relationship.
* When you want to avoid tightly coupling classes together.

***

#### **8. Real-World Analogy of Inheritance**

Imagine a large company where there are several types of employees: managers, engineers, interns, etc. Despite their differences, they share common characteristics, such as having an employee ID, name, and department. Inheritance allows you to create a base class `Employee` with shared attributes, and then have specific classes like `Manager`, `Engineer`, and `Intern` that inherit from `Employee` while adding their own specialized methods and attributes.

***

#### **9. Best Practices for Using Inheritance**

1. **Use Inheritance for Logical Hierarchies**: Ensure that the relationship between classes is logical and follows the "is-a" rule.
2. **Avoid Overusing Inheritance**: Don’t use inheritance for code reuse only; consider composition if that fits better.
3. **Use Virtual Destructors**: If you have polymorphic behavior, always use virtual destructors in base classes to ensure proper cleanup.
4. **Be Aware of the Diamond Problem**: Use virtual base classes when needed to prevent duplicate base class instances.
5. **Favor Composition Over Inheritance**: If the relationship is more about functionality than hierarchy, use composition.

***

#### **10. Thought-Provoking Questions**

1. **Why is multiple inheritance less common than single inheritance in real-world systems?**
   * **Hint**: Consider the complexities and potential issues, like the diamond problem, associated with multiple inheritance.
2. **How does virtual inheritance solve the diamond problem?**
   * **Hint**: Reflect on how virtual inheritance ensures that only one instance of the base class exists.
3. **What would be the impact of omitting a virtual destructor in an inherited class?**
   * **Hint**: Think about how destructors are called and how that affects derived class objects when handled through a base class pointer.
4. **When would you prefer composition over inheritance in system design?**
   * **Hint**: Focus on the benefits of flexibility, decoupling, and a _"has-a"_ relationship.

***

#### **Conclusion**

Inheritance in C++ is a powerful mechanism that allows you to create hierarchical relationships between classes. It promotes code reusability, simplifies design, and provides a natural way to represent relationships between objects. However, it should be used judiciously and in conjunction with composition when appropriate to design systems that are flexible and maintainable. Understanding how to effectively leverage inheritance will help you write cleaner, more modular C++ code.
