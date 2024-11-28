# DOM Scripting

## Selecting HTML elements

Nowadays, the two most popular forms to select HTML elements are by using 
-    `querySelector()`: single selection
-    `querySelectorAll()`: all elements returned in an array-like structure
For most modern JavaScript applications they are recommended because they support complex CSS selectors, are easier to use and reduce the need for multiple selection methods.

## Creating HTML elements

JavaScript allows us to create dynamic HTML elements using the `createElement()` method, which has properties like `element.textContent`, `element.classList` and `element.attribute` to personalize our element. An element can be added to the document as an element's child using the `appendChild()` function.

## Events

The **window** object represents the browser's window. It includes the **document** object.  `addEventListener()` defines an event to listen to, and fires a function when the event is dispatched. The **`load`** event is fired when the whole page has loaded, including all dependent resources such as stylesheets, scripts, iframes, and images, except those that are [loaded lazily](https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading#images_and_iframes). This is in contrast to [`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/API/Document/DOMContentLoaded_event "DOMContentLoaded"), which is fired as soon as the page DOM has been loaded, without waiting for resources to finish loading.

```
addEventListener(type, listener)
```

The `addEventListener()` method is available for any HTML element selected to use. The callback accepts a single parameter: an object describing the event that has occurred.

### *Some common events*

- "**click**": when an element is clicked
- "**change**": is fired for [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), and [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements when the user modifies the element's value after the element loses focus 
- "**input**": is fired for each alteration to an element's `value`.

### *Square bracket syntax to access the properties of an object*

It is possible to use square bracket syntax to access the properties of an object in JavaScript. This is an alternative to the dot (`.`) notation and provides more flexibility, especially in cases where the property name is dynamic.

```
const person = { name: "Zat", age: 20, "favorite color": "blue" };

// Accessing properties dynamically 
const property = "name"; 
console.log(person[property]);
```

### *`submit` event vs `click` event in forms*

When you use both events (click and submit) together, using `preventDefault()` on the click event cancels the normal flow of the submit event because when you click on the submission button the `click` event fires first. To avoid conflicts, it is recommended to use only the submit event in the form, as this covers all forms of submission, including clicks and the Enter key.

### **Form validation**

Form validation is ==a process that checks user input against specific rules before it's submitted to a server==.