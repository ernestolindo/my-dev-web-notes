# **Decorator Pattern**

## **Definition** 

The **Decorator Pattern** is a structural design pattern that allows behavior to be added to individual objects dynamically without altering their code. It works by wrapping an object in another object (a decorator) that implements the same interface, enabling additional functionalities.

## **Key characteristics** 

- **Open for Extension, Closed for Modification**:
    
    - The base class (component) remains untouched, while decorators extend its behavior dynamically.
- **Flexibility**:
    
    - Different combinations of decorators can be applied to achieve various functionalities.
- **Composition Over Inheritance**:
    
    - Avoids creating a complex inheritance hierarchy by using composition to combine behaviors.
- **Transparency**:
    
    - From the client’s perspective, the decorated object behaves like the original object.
- **Layered Behavior**:
    
    - Decorators can be stacked, with each layer adding or modifying behavior.

## **When to use** 

- **Dynamic Behavior Addition**:
    
    - Use when you need to add behavior to an object dynamically without altering its structure.
- **Avoid Overuse of Subclasses**:
    
    - When subclassing would result in a large number of combinations (e.g., `ClassWithBehaviorA`, `ClassWithBehaviorAB`, etc.).
- **Multiple Independent Features**:
    
    - When behaviors should be added independently without relying on inheritance or affecting other objects.

## **How to implement** 

- **Define a Component Interface**:
    
    - It declares methods that both concrete components and decorators must implement.
- **Create a Concrete Component**:
    
    - The original object to which additional functionality will be added.
- **Define a Decorator Abstract Class**:
    
    - Base class for all decorators, ensuring that they follow the same interface as the objects they are decorating. Contains a reference to the component it wraps (also known as the **wrapped object**)
- **Create Concrete Decorators**:
    
    - Extend the decorator class to add specific behaviors.

## **Basic PHP Implementation**