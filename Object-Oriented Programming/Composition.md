# Composition
### **What is Composition?**

**Composition** is a design principle in object-oriented programming where an object is built using other objects. Instead of inheriting behavior from a parent class (inheritance), a class uses other classes to achieve its functionality. This is often referred to as a **"has-a" relationship** (e.g., a `Car` **has a** `Engine`).

It promotes **loose coupling**, allowing more flexibility and reusability compared to inheritance.

| **Composition**                           | **Inheritance**                                       |
| ----------------------------------------- | ----------------------------------------------------- |
| Objects are composed of other objects.    | Objects are specialized versions of their superclass. |
| Flexible and allows for dynamic behavior. | Statically defined at compile time.                   |
| Promotes loose coupling.                  | Often leads to tight coupling.                        |
| "Has-a" relationship.                     | "Is-a" relationship.                                  |
### **How to Implement Composition in PHP**

To implement composition in PHP:

1. **Create a Helper Class for Shared Behavior**  
    Extract shared functionality into a reusable class that can be used by multiple other classes.
    
2. **Use the Helper Class as a Dependency**  
    Include the helper class in other classes as a property (composition) instead of extending it (inheritance).