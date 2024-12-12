#  **Strategy Pattern**

## **Definition**

The **Strategy Design Pattern** is a behavioral design pattern that allows a class to change its behavior at runtime by selecting one of a family of algorithms. It encapsulates algorithms into separate classes and makes them interchangeable, promoting flexibility and extensibility.

## **Components**

1. **Strategy Interface**: Defines a common interface for all algorithms.
2. **Concrete Strategies**: Implement the algorithm (strategy) defined in the Strategy Interface.
3. **Context**: The class that uses a specific strategy, allowing the strategy to be set dynamically and delegating the actual algorithm to the strategy.

## **Benefits**

- **Open/Closed Principle**: The system is open for extension but closed for modification. You can add new strategies without changing the context.
- **Loose Coupling**: The context and the strategies are loosely coupled, meaning the context doesn’t need to know the specifics of the strategies.
- **Flexibility**: Easily switch between different strategies during runtime.

## **Example**

```php
// Strategy interface
interface SortingStrategy {
    public function sort(array $data): array;
}

// Concrete strategy: BubbleSort
class BubbleSort implements SortingStrategy {
    function sort(array $data): array {
        $length = count($data);
        for ($i = 0; $i < $length; $i++) {
            for ($j = 0; $j < $length - 1; $j++) {
                if ($data[$j] > $data[$j + 1]) {
                    $temp = $data[$j];
                    $data[$j] = $data[$j + 1];
                    $data[$j + 1] = $temp;
                }
            }
        }
        return $data;
    }
}

// Concrete strategy: SelectionSort
class SelectionSort implements SortingStrategy {
    function sort(array $data): array {
        $n = count($data);
        for ($i = 0; $i < $n - 1; $i++) {
            $minIndex = $i;
            for ($j = $i + 1; $j < $n; $j++) {
                if ($data[$j] < $data[$minIndex]) {
                    $minIndex = $j;
                }
            }
            $temp = $data[$i];
            $data[$i] = $data[$minIndex];
            $data[$minIndex] = $temp;
        }
        return $data;
    }
}

// Context class
class SortingContext {
    private SortingStrategy $sortingStrategy;
    
    public function setSortingStrategy(SortingStrategy $sortingStrategy): void {
        $this->sortingStrategy = $sortingStrategy;
    }
    
    public function sortData(array $data): array {
        return $this->sortingStrategy->sort($data);
    }
}

// Using the strategy pattern
$array = [64, 25, 12, 22, 11];
echo "Original array: " . implode(", ", $array) . PHP_EOL;

$sortingContext = new SortingContext();

// Use BubbleSort
$bubbleSort = new BubbleSort();
$sortingContext->setSortingStrategy($bubbleSort);
echo "Sorted array with Bubble Sort: " . implode(", ", $sortingContext->sortData($array)) . PHP_EOL;

// Use SelectionSort
$selectionSort = new SelectionSort();
$sortingContext->setSortingStrategy($selectionSort);
echo "Sorted array with Selection Sort: " . implode(", ", $sortingContext->sortData($array)) . PHP_EOL;
