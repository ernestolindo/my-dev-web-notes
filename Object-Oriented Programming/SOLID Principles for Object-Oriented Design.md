# **SOLID Principles for Object-Oriented Design**

## **Single-Responsibility Principle**

> "A class should have only one reason to change."

By splitting responsibilities into separate, dedicated classes, you achieve **modularity** and **scalability** in your design.
### *Key Techniques to Apply the Principle*

1. **Define clear responsibilities**: Identify the primary purpose of a class.
2. **Split classes**: Extract responsibilities into new, dedicated classes.
3. **Use interfaces**:	Represent specific roles or behaviors to enforce SRP.
4. **Delegate responsibilities**: Assign tasks to helper or dependency classes via [[Composition]].
5. **Follow "one reason to change"**: Ensure a class changes only for its defined responsibility.
Keep methods focused
## **Open Closed Principle**

> "Software entities (classes, modules, functions, etc.) should be open for extension but closed for modification."

### *Key Techniques to Apply the Principle*

1. **Inheritance**: Extend existing classes to add new functionality.
2. **Interfaces or Abstract Classes**: Define common behaviors for new classes to implement.
3. **Composition**: Combine existing classes to achieve new behavior.

Suppose you have a class `Shape` with a method `calculateArea()` that returns the area of a shape. If you want to add a new type of shape (e.g., a triangle), instead of modifying the existing class, you can extend it.
## **Liskov Substitution Principle**

> "Objects of a superclass should be replaceable with objects of a subclass without altering the correctness of the program."

### *Key Techniques to Apply the Principle*

1. **Use a Common Abstraction**: Ensure that your superclass (or interface) defines **general behaviors** that all subclasses are expected to implement.
2. **Avoid Overriding with Unexpected Behavior**: Subclasses should not change the meaning of a method inherited from the superclass.
3. **Avoid Tight Coupling**: Do not hard-code logic that depends on specific subclasses.
4. **Favor [[Composition]] Over Inheritance**: Sometimes, **[[Composition]]** (combining objects) is a better solution than inheritance.
## **Interface Segregation**

> "A class should not be forced to implement interfaces it does not use."

This principle emphasizes that interfaces should be small and focused on specific behaviors, ensuring that implementing classes only provide methods that are relevant to their roles.
### *Key Techniques to Apply the Principle*

1. **Avoid Fat Interfaces**: Large interfaces with many unrelated methods force classes to implement methods they do not need, leading to unnecessary code and violations of ISP.
2. **Split Interfaces**: Break large, general-purpose interfaces into smaller, more specific ones, each representing a distinct responsibility.
3. **Keep Implementations Relevant**: Classes implementing an interface should only be required to provide functionality they actually use.
## **Dependency Inversion Principle**

> [[High-level module]] should not depend on [[Low-level module]]. Both should depend on abstractions.

This means:

- High-level components (like business logic) should not be tightly coupled to low-level components (like database or network services).
- Instead, both should rely on interfaces or abstract classes, making the system more flexible and easier to maintain.

### *Key Techniques to Apply DIP*

1. **Use Dependency Injection**:
    
    - Pass dependencies (like services or repositories) to classes via constructors or setter methods.
2. **Program to Interfaces**:
    
    - Define abstractions (e.g., interfaces or abstract classes) that both high-level and low-level modules depend on.
3. **Avoid Hard-Coded Dependencies**:
    
    - Avoid directly instantiating low-level classes inside high-level modules. 