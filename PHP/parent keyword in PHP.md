# **parent keyword in PHP**

- Refers to the **parent class** of the current class (in the context of inheritance).
- Used to:
    - Call a parent class's **methods** or **constructor** that have been overridden in the child class.
    - Access **static properties and methods** from the parent class.

**Key Points:**

1. `parent` is only relevant in a class that extends another class.
2. Access is also done using the [[scope resolution operator]] `::`.

**Example:**

```
class ParentClass {
    public static function greet() {
        return "Hello from ParentClass";
    }
}

class ChildClass extends ParentClass {
    public static function greet() {
        return parent::greet() . " and ChildClass"; // Calls the parent method
    }
}

echo ChildClass::greet(); // Outputs: Hello from ParentClass and ChildClass
```