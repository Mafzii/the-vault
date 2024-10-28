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


