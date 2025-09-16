# Polymorphism in C++ – Overloading Concepts

## Aim

To study **Polymorphism in C++** with focus on **Overloading concepts**:

* Constructor Overloading
* Function Overloading
* Operator Overloading

---

## Introduction to Overloading in C++

In C++, **overloading** allows us to define multiple functions, constructors, or operators with the same name but different parameter lists or behaviors.

**Why use Overloading?**

* Improves code readability
* Enhances flexibility
* Promotes reusability

When an overloaded function or constructor is called, the **compiler decides which version to execute** based on the number or type of arguments passed.

---

## Theory

### Polymorphism

Polymorphism in C++ means *"one name, many forms"*.

* **Compile-time Polymorphism** → Achieved using *overloading* (functions, constructors, operators).
* Behavior differs depending on input.

---

## Constructor Overloading

### Definition

A class can have more than one constructor, each with a different parameter list.

### Purpose

Enables object creation in multiple ways depending on arguments.

### Key Points

* Constructors share the same name as the class.
* Differentiated by parameter list (number/type).
* Improves flexibility and readability.

### Example

```cpp
#include <iostream>
using namespace std;

class Student {
    string name;
    int age;

public:
    Student() { name="Unknown"; age=0; }
    Student(string n) { name=n; age=0; }
    Student(string n, int a) { name=n; age=a; }

    void display() { cout << "Name: " << name << ", Age: " << age << endl; }
};

int main() {
    Student s1;
    Student s2("Rahul");
    Student s3("Ananya",21);

    s1.display();
    s2.display();
    s3.display();
}
```

---

## Function Overloading

### Definition

Defining multiple functions with the same name but different parameter lists.

### Purpose

Allows functions to perform similar tasks with different inputs.

### Key Points

* Return type alone **cannot** differentiate overloaded functions.
* Parameter list must differ.
* Compiler decides at **compile-time**.

### Example

```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    int add(int a, int b) { return a + b; }
    int add(int a, int b, int c) { return a + b + c; }
};

int main() {
    Calculator calc;
    cout << "Sum1: " << calc.add(10,20) << endl;
    cout << "Sum2: " << calc.add(10,20,30) << endl;
}
```

---

## Operator Overloading

### Definition

Allows redefining the meaning of C++ operators (`+`, `-`, `*`, `==`, etc.) for **user-defined types**.

### Purpose

Enables intuitive manipulation of objects using operators.

### Key Points

* Defined using `operator` keyword.
* Makes custom types behave like built-in types.
* Cannot create new operators.
* Some operators (`::`, `sizeof`, `?:`, `.`) **cannot** be overloaded.

### Syntax

```cpp
class ClassName {
public:
    returnType operator op (argument) {
        // operator definition
    }
};
```

---

## Difference Between Overloading Types

| Feature              | Constructor Overloading                     | Function Overloading                                | Operator Overloading                        |
| -------------------- | ------------------------------------------- | --------------------------------------------------- | ------------------------------------------- |
| **Definition**       | Multiple constructors with different params | Multiple functions with same name, different params | Redefining operators for user-defined types |
| **Purpose**          | Create objects in different ways            | Perform similar operations with different inputs    | Use operators naturally with objects        |
| **Where Used**       | Inside a class (constructors only)          | Inside/outside classes                              | User-defined types (classes/structs)        |
| **Compile-time?**    | Yes                                         | Yes                                                 | Yes                                         |
| **Return Type**      | Not applicable                              | Cannot overload by return type alone                | Can differ, but params matter               |
| **Example Use Case** | Initialize objects differently              | Add numbers of different types                      | Add two complex numbers with `+`            |

---

## Codes and Algorithms

### 1. Constructor Overloading (Addition Example)

**Algorithm**

1. Define class `Add`.
2. Overload constructors with different parameter lists.
3. Perform addition inside constructors.
4. In `main()`, create objects with different arguments.

---

### 2. Constructor Overloading with Characters and Strings

**Algorithm**

1. Define class `Name`.
2. Constructor 1: Accepts characters → prints them.
3. Constructor 2: Accepts strings → concatenates and prints.
4. In `main()`, create objects with both chars and strings.

---

### 3. Function Overloading (Calculator Example)

**Algorithm**

1. Define two `calc()` functions with different parameter lists.
2. First → performs addition.
3. Second → performs subtraction.
4. In `main()`, call both versions.

---

### 4. Operator Overloading (Complex Number Addition – Manual)

**Algorithm**

1. Define class `ComplexAddition`.
2. Constructor initializes real & imaginary parts.
3. Define `add()` to add two complex numbers manually.
4. Display result in `main()`.

---

### 5. Operator Overloading (String Concatenation with `+`)

**Algorithm**

1. Define class `Name` with string members.
2. Overload `+` operator to concatenate names.
3. In `main()`, create objects and use `+`.

---

## Conclusion

Overloading in C++ is a powerful form of **compile-time polymorphism**.

* **Function Overloading** → Same function, multiple behaviors.
* **Constructor Overloading** → Multiple ways to initialize objects.
* **Operator Overloading** → Makes objects behave like built-in types.

### Benefits

* Cleaner and more intuitive code
* Reduced redundancy
* Increased flexibility and scalability

Overloading forms the backbone of professional and maintainable **Object-Oriented Programming in C++**.

