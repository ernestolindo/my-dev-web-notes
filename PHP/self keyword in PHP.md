# **self keyword in PHP**

In PHP, **`self`** is a keyword used within a class to refer to the **current class** where it is defined. It is typically used to access:

- **Static properties**
- **Static methods**
- **Constants**

**Key Points:**

- **`self` does not respect inheritance**, meaning it always refers to the class in which it is written, not a child class.
- Access is also done using the [[scope resolution operator]] `::`.

```
class MyClass {
    const GREETING = "Hello from MyClass";

    public static function sayHello() {
        return self::GREETING; // Refers to the constant in this class
    }
}

echo MyClass::sayHello(); // Outputs: Hello from MyClass
```