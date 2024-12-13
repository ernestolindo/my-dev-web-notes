# **JSON Encoding**

The `json_encode` function in PHP is used to convert a value (such as an array or object) into a JSON-formatted string.

## **Basic structure**

```php
json_encode(mixed $value): string|false
```

 **Parameters**:
**`$value`** (required):  
- `array` or `object` are commonly used for creating JSON structures.
- Scalars like `string`, `int`, or `float` are encoded as JSON primitives.
- `null` is encoded as `null`.

## **Why is it useful?**

- **Standardized format:** JSON (JavaScript Object Notation) is a lightweight data-interchange format widely used in web APIs and data exchange.
- **Compatibility:** It's easy for other systems or programming languages to parse JSON.

## **Example**

**PHP**:
```php
$data = ["name" => "John", "age" => 30];
$json = json_encode($data);
echo $json;
```

**JSON**:
```JSON
{"name":"John","age":30}
```
