# SOLID Principles for OPP - FSJ

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

#### 1. Use a Common Abstraction

- Ensure that your superclass (or interface) defines **general behaviors** that all subclasses are expected to implement.
#### 2. Avoid Overriding with Unexpected Behavior

- Subclasses should not change the meaning of a method inherited from the superclass.

#### 3. Avoid Tight Coupling

- Do not hard-code logic that depends on specific subclasses.
#### 4. Favor Composition Over Inheritance

- Sometimes, **composition** (combining objects) is a better solution than inheritance.
## Interface Segregation

Subdividir interfaz muy general en interfaces mas especificas.