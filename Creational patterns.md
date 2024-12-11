# **Creational Patterns**

## **Singleton Pattern**

### *Definition*

The **Singleton Pattern** is a **creational design pattern** that ensures a class has only **one instance** and provides a **global point of access** to that instance.

### *Key Characteristics*

- **One Instance**: Only one object of the class will be created throughout the application.
- **Global Access**: The instance can be accessed globally through a static method.
- **Controlled Creation**: The creation of the instance is controlled by the class itself, typically through a static method (e.g., `getInstance()`).

### *When to Use*

- When you need to ensure **one instance** of a class (e.g., for managing shared resources like database connections, logging systems, etc.).
- When the creation of an object is **expensive** or you want to avoid the overhead of creating multiple instances.

### *How to Implement*

1. **Private Constructor**: Prevents external instantiation.
2. **Static `getInstance()` Method**: Returns the **single instance** and creates it only if it doesn’t already exist.
3. **Static Variable**: Stores the unique instance.

### *Basic PHP Implementation*

```
<?php
class Singleton {
    // Holds the single instance of the class
    private static ?Singleton $instance = null;

    // Private constructor to prevent direct instantiation
    private function __construct() {}

    // Static method to get the single instance of the class
    public static function getInstance(): Singleton {
        if (self::$instance === null) {
            self::$instance = new Singleton();
        }
        return self::$instance;
    }

    // Example method
    public function doSomething(): void {
        echo "Singleton instance is working!";
    }
}

// Usage
$singleton = Singleton::getInstance();
$singleton->doSomething();
```

## **Factory Method Pattern**

### *Definition*

The Factory Method Pattern is a creational design pattern that defines an interface or abstract class for creating an object, but allows subclasses to alter the type of objects that will be created.

The main idea is to delegate the instantiation of objects to subclasses, making the code more flexible and reusable.
### *Key Characteristics*

- **Product Interface/Abstract Class**: Defines the interface for the objects created by the factory.
- **Concrete Products**: Implement the product interface.
- **Creator (Factory)**: Declares the factory method that returns objects of the product type.
- **Concrete Creators**: Override the factory method to specify the concrete product to instantiate.
### *When to use*

Direct instantiation is fine for **simple cases** with few object types and little growth. However, as your application grows, the **Factory Method** becomes invaluable for **flexibility**, **maintainability**, and adhering to **good design principles**.

| Feature              | Direct Instantiation                    | Factory Method                      |
| -------------------- | --------------------------------------- | ----------------------------------- |
| **Flexibility**      | Hard to extend (modifies existing code) | Easy to extend (adds new factories) |
| **Code Duplication** | Risk of repeating instantiation logic   | Centralized in factories            |
| **Coupling**         | Tightly coupled to concrete classes     | Decoupled using abstractions        |
| **Scalability**      | Becomes harder with more types          | Easily scales with new types        |
| **Reusability**      | Logic tied to specific context          | Reusable factory logic              |
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




