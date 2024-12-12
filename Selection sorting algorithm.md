# **Selection sorting algorithm**

Selection Sort is a simple sorting algorithm that repeatedly selects the smallest (or largest) element from the unsorted part of the array and swaps it with the first unsorted element. It divides the array into two parts: sorted and unsorted.

## **How it Works**:
1. Start at the first element of the array and assume it is the smallest.
2. Compare it with all the other elements in the unsorted portion of the array.
3. If a smaller element is found, update the smallest element's index.
4. After checking all elements, swap the smallest element with the first element of the unsorted portion.
5. Repeat the process for the remaining unsorted portion until the entire array is sorted.

## **Example**:
For the array `[64, 25, 12, 22, 11]`:
- **First iteration**: The smallest element `11` is swapped with `64`, resulting in `[11, 25, 12, 22, 64]`.
- **Second iteration**: The smallest element `12` is swapped with `25`, resulting in `[11, 12, 25, 22, 64]`.
- **Third iteration**: The smallest element `22` is swapped with `25`, resulting in `[11, 12, 22, 25, 64]`.
- The array is now sorted.

## **Time Complexity**:
- **Best, Worst, and Average Case**: O(n^2), where n is the number of elements in the array.
- Selection Sort has a quadratic time complexity because it uses two nested loops: the outer loop for each element and the inner loop to find the smallest element in the unsorted portion.

## **Pros and Cons**:
- **Pros**:
  - Simple and easy to implement.
  - Works well for small datasets or when memory is limited (because of its O(1) space complexity).
- **Cons**:
  - Inefficient for large datasets due to its O(n^2) time complexity.
  - Performs unnecessary swaps even when the array is partially sorted.

## **PHP Implementation**:

```php
function selectionSort($array) {
    $n = count($array);
    for ($i = 0; $i < $n - 1; $i++) {
        $minIndex = $i;
        for ($j = $i + 1; $j < $n; $j++) {
            if ($array[$j] < $array[$minIndex]) {
                $minIndex = $j;
            }
        }
        $temp = $array[$i];
        $array[$i] = $array[$minIndex];
        $array[$minIndex] = $temp;
    }
    return $array;
}
