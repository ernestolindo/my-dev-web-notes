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

Una clase padre debería poder ser reemplazada por sus clases hijas sin problemas en la ejecución.

Solucion 1: clase abstracta con metodo abstracto
Solucion 2: interfaz

## Interface Segregation

Subdividir interfaz muy general en interfaces mas especificas.