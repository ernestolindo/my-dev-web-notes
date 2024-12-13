# **JSON Encoding**

The `json_encode` function in PHP is used to convert a value (such as an array or object) into a JSON-formatted string.

```php
json_encode(mixed $value, int $flags = 0, int $depth = 512): string|false
```


### Example:

If `$message` is `"Hello world"`, this function call will return the JSON string:

json

Copy code

`{"message":"Hello world"}`

### Why is it useful?

- **Standardized format:** JSON (JavaScript Object Notation) is a lightweight data-interchange format widely used in web APIs and data exchange.
- **Compatibility:** It's easy for other systems or programming languages to parse JSON.

In this case, the function is part of the `JsonOutput` strategy and is used to represent the message in JSON format.