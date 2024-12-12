## **Factory Method Pattern**

### *Definition*

The **Factory Method Pattern** is a **creational design pattern** that defines an interface or abstract class for creating an object, but allows subclasses to alter the type of objects that will be created.

The main idea is to delegate the instantiation of objects to subclasses, making the code more flexible and reusable.
### *Key Characteristics*

- **Encapsulation of Object Creation**: The pattern encapsulates the instantiation logic, making the code more flexible and easier to maintain.
- **Polymorphism**: It relies on subclasses to define the exact type of object to create, promoting flexibility and scalability.
- **Abstract Products**: The base class defines an abstract method (factory method) to be implemented by subclasses, which create specific products.
### *When to use*

Direct instantiation is fine for **simple cases** with few object types and little growth. However, as your application grows, the **Factory Method** becomes invaluable for **flexibility**, **maintainability**, and adhering to **good design principles**.

| Feature              | Direct Instantiation                    | Factory Method                      |
| -------------------- | --------------------------------------- | ----------------------------------- |
| **Flexibility**      | Hard to extend (modifies existing code) | Easy to extend (adds new factories) |
| **Code Duplication** | Risk of repeating instantiation logic   | Centralized in factories            |
| **Coupling**         | Tightly coupled to concrete classes     | Decoupled using abstractions        |
| **Scalability**      | Becomes harder with more types          | Easily scales with new types        |
| **Reusability**      | Logic tied to specific context          | Reusable factory logic              |
### *How to Implement*

1. **Creator Class**:
    - Defines the factory method as an abstract method or virtual function.
    - May also include some default behavior for object management.
2. **Concrete Creator**:
    - Implements the factory method to create specific product instances.
3. **Product Interface**:
    - Declares common operations that all product types support.
4. **Concrete Product**:
    - Implements the product interface.
### *Basic PHP Implementation*

```
<?php
// Step 1: Define the Product Interface
interface Product {
    public function getName(): string;
}

// Step 2: Implement Concrete Products
class ConcreteProductA implements Product {
    public function getName(): string {
        return "Product A";
    }
}

class ConcreteProductB implements Product {
    public function getName(): string {
        return "Product B";
    }
}

// Step 3: Define the Abstract Creator
abstract class Creator {
    // Factory method to be overridden by subclasses
    abstract public function factoryMethod(): Product;

    // Operation using the factory method
    public function getProductInfo(): string {
        $product = $this->factoryMethod();
        return "Created: " . $product->getName();
    }
}

// Step 4: Implement Concrete Creators
class CreatorA extends Creator {
    public function factoryMethod(): Product {
        return new ConcreteProductA();
    }
}

class CreatorB extends Creator {
    public function factoryMethod(): Product {
        return new ConcreteProductB();
    }
}

// Step 5: Client Code
function clientCode(Creator $creator) {
    echo $creator->getProductInfo() . PHP_EOL;
}

// Example Usage
clientCode(new CreatorA()); // Output: Created: Product A
clientCode(new CreatorB()); // Output: Created: Product B
```




