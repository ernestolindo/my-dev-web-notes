# **Scope Resolution Operator**

The **scope resolution operator** (`::`) is called so because it is used to **resolve the scope** of class members (such as static properties, constants, or methods). Essentially, it determines the **context (scope)** in which a class member is being accessed or referenced.

The operator `::` explicitly tells PHP which class to look at when accessing a member. This is particularly important when:

- Working with **static members**.
- Referencing **constants**.
- Differentiating between a **parent class** and a **child class** in inheritance.

## **[[Parent keyword]] and [[self keyword]]**

When using `self` or `parent` with the scope resolution operator, it resolves the context to:

- `self::` → The **current class** where the code is being executed.
- `parent::` → The **parent class** of the current class.