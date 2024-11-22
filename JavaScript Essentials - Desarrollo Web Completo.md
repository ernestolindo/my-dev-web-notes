Destructuring allows us to extract properties from an object in a straightforward way.
`const { nombre, precio } = producto`

Object methods:
- Seal(): no create, no delete
- Freeze(): no create, no update, no delete

Spread operator vs Rest operator
- The **rest operator (`...`)** collects multiple items into a single array or object.
- The **spread operator (`...`)** expands items from an array, object, or iterable into individual elements.

Modify arrays
- Add elements at the beginning: array.unshift()
- Add elements at the end: array.push()

- Delete the first element: array.shift()
- Delete the last element: array.pop()

Is an element included in the array?
- **`includes()`** is simpler and checks for a specific value. Doesn't work with arrays of objects.
- **`some()`** is more versatile and checks for a condition using a callback function. Works well with arrays of objects.

The `reduce()` method is a flexible tool for **condensing an array into a single value** using custom logic.

The **`filter()`** method is a versatile and non-mutating way to create a new array with only the elements that satisfy a condition. It's great for extracting specific elements from an array based on logic you define in the callback.

How to create functions?

| **Function Type**              | **Syntax**                                      | **Key Points**                     |
| ------------------------------ | ----------------------------------------------- | ---------------------------------- |
| **Function Declaration**       | `function add(a, b) { return a + b; }`          | Hoisted, named function.           |
| **Function Expression**        | `const add = function(a, b) { return a + b; };` | Not hoisted, anonymous function.   |
| **Arrow Function**             | `const add = (a, b) => a + b;`                  | Concise syntax, inherits `this`.   |
| **IIFE (Immediately Invoked)** | `(function() { /* code */ })();`                | Runs immediately after definition. |
| **Constructor Function**       | `function Person(name) { this.name = name; }`   | Used with `new` to create objects. |
**Use `map()`** when you want to **create a new array** based on the transformation of elements from the original array. **Use `forEach()`** when you want to **perform an action** for each element without modifying the array or needing a result.