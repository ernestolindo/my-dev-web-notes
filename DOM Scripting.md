# DOM Scripting

## Selecting HTML elements

Nowadays, the two most popular forms to select HTML elements are by using 
-    `querySelector()`: single selection
-    `querySelectorAll()`: all elements returned in an array-like structure
For most modern JavaScript applications they are recommended because they support complex CSS selectors, are easier to use and reduce the need for multiple selection methods.

## Creating HTML elements

JavaScript allows us to create dynamic HTML elements using the `createElement()` method, which has properties like `element.textContent`, `element.classList` and `element.attribute` to personalize our element. An element can be added to the document as an element's child using the `appendChild()` function.

## Events

The window object includes  `addEventListener()` defines an event to listen to, and fires a function when the event is dispatched.

