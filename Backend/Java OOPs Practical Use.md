---
tags:
  - backend
---
### 1. Abstraction

Hiding the underlying complexity of code:

Can be done with the use of the `abstract` keyword. (partial abstraction)
- This is a parent class that cannot be instantiated
- Create a child class and extend the abstract class to use it
- Methods can be of 2 types:
	- `abstract` methods only declare the function signature
	- concrete methods have the function body too
	- The implementation of the abstract methods will be written in the child class
- Can have private, protected, public, static variables and methods

Can also be done with the use of *Interfaces*.

This is a fully abstract class
- Declare methods that are all public by default
- Use the class with the `implements` keyword
- Allows for multiple inheritance
- Only allows static, final and public access modifiers

### 2. Encapsulation
- Can be implemented by restricting access to fields of a class
- This is done through the use of private, public and protected access modifiers
- Using methods to access these fields rather than doing it directly
- Making fields inaccessible from outside the class is also known as data hiding

### 3. Inheritance
- DRY principle
- Uses the `extends` keyword or `implements` if its an interface
- Multilevel Inheritance
	- Child class extends parent which extends ancestor
- Multiple Inheritance
	- The diamond problem
	- Super class is an abstract class with a method called `run()` and 2 children: A and B. The child classes implement a method from the super class in a different way. Class C which inherits both A and B calls the `run()` method. This is going to cause issues as there are 2 versions of the run method and no way to resolve which one to use. This is called the **DIAMOND PROBLEM**.
	- Must use interfaces to do multiple inheritance

### 4. Polymorphism
- Overloading
	- Same function name but different number or types of parameters
- Overriding
	- Function exists in the parent class but the implementation can be redeclared in the child class using the `@Override` annotation


