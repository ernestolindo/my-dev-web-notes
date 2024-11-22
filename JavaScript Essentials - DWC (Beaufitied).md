## **Destructuring**

Destructuring allows us to extract properties from an object in a straightforward way.  
Example:

`const { nombre, precio } = producto;`

---

## **Object Methods**

### *seal()*

-    Prevents adding or deleting properties but allows updates to existing properties.

### *freeze()*

-    Prevents adding, deleting, or updating properties.

---

## **Spread Operator vs Rest Operator**

### *Rest Operator (`...`)*

-    Collects multiple items into a single array or object.  
	Example:

`function sum(...numbers) {   return numbers.reduce((acc, num) => acc + num, 0); }`

### *Spread Operator (`...`)*

-    Expands items from an array, object, or iterable into individual elements.  
    Example:

`const arr1 = [1, 2]; const arr2 = [...arr1, 3, 4];`

---

## **Modifying Arrays**

### *Adding Elements*

-    At the beginning: `array.unshift()`
-    At the end: `array.push()`

### *Deleting Elements*

-    First element: `array.shift()`
-    Last element: `array.pop()`

---

## **Checking for Elements in Arrays**

### *includes()*

-    Checks for a specific value.
-    Does not work with arrays of objects.

### *some()*

-    Checks if **at least one element** satisfies a condition (callback function).
-    Works with arrays of objects.

---

## **Useful Array Methods**

### *reduce()*

-    Condenses an array into a single value using custom logic.  
    Example:

`const total = [1, 2, 3].reduce((acc, val) => acc + val, 0); // Result: 6`

### *filter()*

-    Creates a new array with elements that satisfy a condition.
-    Non-mutating.  
    Example:

`const evenNumbers = [1, 2, 3, 4].filter(num => num % 2 === 0); // Result: [2, 4]`

### *map() vs forEach()*

|**Use Case**|**Description**|
|---|---|
|**`map()`**|Creates a **new array** by transforming each element from the original array.|
|**`forEach()`**|Performs an action on each element without returning a new array or result.|

---

## **Creating Functions**

|**Function Type**|**Syntax**|**Key Points**|
|---|---|---|
|**Function Declaration**|`function add(a, b) { return a + b; }`|Hoisted, named function.|
|**Function Expression**|`const add = function(a, b) { return a + b; };`|Not hoisted, anonymous function.|
|**Arrow Function**|`const add = (a, b) => a + b;`|Concise syntax, inherits `this`.|
|**IIFE (Immediately Invoked)**|`(function() { /* code */ })();`|Runs immediately after definition.|
|**Constructor Function**|`function Person(name) { this.name = name; }`|Used with `new` to create objects.|

---

## **Global objects**

The **global object** is the top-level object in a JavaScript runtime, providing access to built-in functions, variables, and APIs. In browsers, the global object is the **`window`**, representing the browser window where the web page runs. It includes properties like `document` (to manipulate the HTML), `location` (for the URL), and functions like `alert()`. While both serve as global objects, `window` focuses on browser interactions, whereas `global` powers server-side JavaScript in Node.js.

---

## **`This` value in arrow functions**

The arrow function **inherits `this` from the enclosing scope at the time of its definition**. When used as a **callback**, it maintains the `this` of the outer function or object. When used as a **method** in an object, it doesn’t bind to the object and instead keeps the `this` from the context where the method was defined.

---

## **Prototypes**

In modern JavaScript, methods and properties shared across instances should be defined on the prototype to ensure efficient memory usage. The prototype chain allows all instances to reference a single copy of shared methods, while instance-specific properties remain unique to each object. This practice is even more streamlined with ES6+ `class` syntax, which abstracts the prototype logic while still using it under the hood.

| Feature          | `[[Prototype]]`                    | `__proto__`              | `prototype`                         |
| ---------------- | ---------------------------------- | ------------------------ | ----------------------------------- |
| **Type**         | Internal property (hidden)         | Legacy accessor property | Property of functions               |
| **Found On**     | Every object                       | Most objects             | Functions (constructor)             |
| **Purpose**      | Links object to its prototype      | Access/modify prototype  | Defines blueprint for new instances |
| **Modern Usage** | Access via `Object.getPrototypeOf` | Discouraged (legacy)     | Used for inheritance                |

---

## **Notification API**

The **Notification API** allows web applications to display notifications to the user, even if the application is not actively in focus. It’s a powerful way to engage users by providing timely updates or alerts directly in their operating system’s notification system.

### *Key Points:*

1.   **Permission Request**:  
    Users must grant permission before notifications can be displayed. This ensures user privacy and prevents spam.

2.   **Creating Notifications**:  
    Notifications are created using the `Notification` constructor, which takes a title and an options object as parameters.

---

## **Promises in JavaScript**

A **Promise** is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

```
new Promise((resolve, reject) => {
  // Perform some asynchronous task
  if (taskCompletedSuccessfully) {
    resolve(result);  // Resolves the Promise
  } else {
    reject(error);    // Rejects the Promise
  }
});
```

Promises are used to handle asynchronous operations, like making API requests or performing time-consuming tasks, without blocking the main thread.

```
function fetchData() {
  return new Promise((resolve, reject) => {
    fetch('https://jsonplaceholder.typicode.com/posts/1')
      .then(response => response.json())
      .then(data => resolve(data))
      .catch(error => reject(error));
  });
}

fetchData().then(data => console.log(data)).catch(error => console.error(error));
```

In this example:

- **`fetch()`** returns a Promise that resolves with the response.
- The `.then()` method handles the resolved value, and `.catch()` handles any errors.

### *Async/Await*

**`async`** and **`await`** are modern JavaScript keywords used to handle asynchronous operations in a more readable and synchronous-like style. An `async` function always returns a **Promise**, and within it, you can use `await` to pause execution until the Promise is resolved.

```
async function fetchData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}

fetchData();
```

- **`await`** pauses the execution of the `async` function until the **Promise** resolves or rejects.
- **`try/catch`** is used for error handling, making it easier to manage asynchronous errors.

### *Promise.all()*

A method used to start multiple Promises simultaneously, i. e., not sequentially. If any Promise rejects, the entire operation fails. It takes an array as the parameter and resolves to an array containing the resolved values of each input Promise.