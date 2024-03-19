# The S.O.L.I.D principles

## 

The S.O.L.I.D is an acronym for:

1. Single-responsibility principle
2. Open-close principle
3. Liskov substitution principle
4. Interface segregation principle
5. Dependency inversion principle

These principles are part of a larger set of principles first 
introduced by Robert C. Martin, a software engineer and 
instructor in his paper _Design Principles and Design 
Patterns_ in the year 2000 discussing software rot.
---
## The Single Responsibility Principle (SRP)

There should never be more than one reason for a class/code 
unit to change. Every class should have only one responsibility.

In essence, the SRP promotes the idea that a class should be
focused on doing one thing well rather than trying to handle
multiple responsibilities. The principle helps to **improve 
code maintainability, readability, and flexibility by keeping 
classes focused and cohesive**.

For example, let's consider a class responsible for managing user
accounts in a system.

According to the SRP, the class should focus solely on 
- managing user accounts, 
  - such as creating, 
  - updating and 
  - deleting accounts.

It should NOT be responsible for 
- handling email notifications,
- generating reports, or 
- performing other unrelated tasks.

However, it's essential to note that applying the SRP doesn't
mean creating numerous tiny classes/methods for every minor 
responsibility. Instead, it is about finding the right balance
and ensuring that each class has a **clear and cohesive** purpose
within the overall design of the system.

---
## The Open/Closed Principle

The Open/Closed Principle (OCP) is a fundamental concept
in the SOLID principles of object-oriented design. It emphasizes
that software entities (classes, modules, functions, etc.) should
be open for extension but closed for modification.

In simpler terms, the principle suggests that you should be able
to extend the behavior of a software component without modifying
its source code. Instead of directly changing existing code,
you should be able to add new functionality by extending or
subclassing existing components.

The idea behind the OCP is to **promote software designs that are
flexible and easily adaptable to change**. By adhering to this 
principle, you can add new features or modify existing behaviour
without risking unintended side effects or breaking existing code.

One common way to achieve the OCP is through the use of 
abstraction and inheritance. By defining abstract classes or
interfaces that specify the behavior of a component, you can
create concrete implementations that adhere to these contracts.
When you need to extend the functionality of a component, you 
can create new subclasses that provide additional or modified
behavior without altering the existing codebase.

For example, consider a system that calculates the area of 
various shapes. Instead of having a single class with different
methods for calculating the area of each shape (e.g. 
`calculateCircleArea`, `calculateRectangleArea`, etc.), 
you could define an abstract `Shape` class or interface with
method like `calculateArea`. Then, you can create concrete
subclasses for each shape (e.g. `Circle`, `Rectangle`, etc.)
that implement the `calculateArea` method according to the 
specific formula for that shape.

OCP encourages modular, reusable and maintainable code by 
promoting a design that can easily accommodate changes and 
extensions without requiring modifications to existing code.
By designing software components to be open for extension and 
closed for modification, you can build system that are more 
resilient to change and easier to maintain over time.

---
The Liskov Substitution Principle (LSP)

Liskov's Substitution Principle (LSP) is named after Barbara
Liskov. The principle states that objects of a superclass
should be replaceable with objects of its subclasses without
affecting the correctness of the program.

In simpler terms, if S is a subset of T, then object of type T
may be replaced with objects of type S without altering any 
of the desirable properties of the program.

This principle is crucial for ensuring the consistency and 
reliability of object-oriented systems. It helps to maintain
the behaviour and expectations of client code when working
with objects of different types with a hierarchy.

To adhere to the Liskov Substitution Principle, subclass
must fulfill the contract established by their superclass.
This means that subclasses should extend the functionality
of the superclass, not override or change it in a way
that violates the expected behavior of the superclass.

Violating the LSP can lead to unexpected behavior and errors
in a system. For example, if a subclass overrides a method in
a way that contradicts the behavior defined in the superclass,
it can lead to inconsistencies and bugs when objects of the 
subclass are used interchangeably with objects of the superclass.

In practical terms, when 