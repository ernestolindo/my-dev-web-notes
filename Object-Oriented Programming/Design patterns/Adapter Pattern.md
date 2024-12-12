# **Adapter Pattern**

## **Definition**

The **Adapter Design Pattern** is a structural design pattern used to enable two incompatible interfaces or classes to work together. It acts as a bridge, converting the interface of one class (adaptee) into another (target interface) that the client expects.

## **Key characteristics**

- **Structural Design Pattern**: It focuses on the structure of classes and objects.
- **Interface Conversion**: The adapter changes the interface of a class so that it can be used by another class.
- **Decoupling**: It decouples client code from the adaptee code, providing a layer that translates the method calls.

## **When to use**

- When you need to integrate classes or systems that have incompatible interfaces.
- When you want to re-use existing classes or components but need to adapt their interfaces to suit new requirements.
- When you don't want to change existing code but need it to work with other components.

## **How to implement**

- **Target Interface**: Define the interface that the client expects.
- **Adapter Class**: Create an adapter class that implements the target interface and uses the adaptee (the existing class with a different interface).
- **Adaptee**: The existing class whose interface is incompatible with the target.
- **Client**: The client interacts with the target interface, and the adapter ensures that the client gets the correct behavior.

## **Basic PHP Implementation**

```
<?php

// Adaptee: Provides temperature in Celsius
class CelsiusTemperature
{
    public function getTemperature(): float
    {
        return 25.0; // Temperature in Celsius
    }
}

// Target Interface: Defines the method expected by the client
interface TemperatureInFahrenheit
{
    public function getTemperatureInFahrenheit(): float;
}

// Adapter: Converts Celsius to Fahrenheit
class TemperatureAdapter implements TemperatureInFahrenheit
{
    private CelsiusTemperature $celsiusTemperature;

    public function __construct(CelsiusTemperature $celsiusTemperature)
    {
        $this->celsiusTemperature = $celsiusTemperature;
    }

    public function getTemperatureInFahrenheit(): float
    {
        $celsius = $this->celsiusTemperature->getTemperature();
        return ($celsius * 9 / 5) + 32; // Celsius to Fahrenheit
    }
}

// Client: Uses the TemperatureInFahrenheit interface
function displayTemperature(TemperatureInFahrenheit $temperatureSource)
{
    echo "The temperature is " . $temperatureSource->getTemperatureInFahrenheit() . "°F.\n";
}

// Usage
$celsiusTemperature = new CelsiusTemperature();
$adapter = new TemperatureAdapter($celsiusTemperature);
displayTemperature($adapter);
```