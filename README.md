# Quadratic Sorting Algorithms

Quadratic sorting algorithms. Bubble sort and Insertion sort. 

## Bubble Sort 

```swift 
func bubbleSort(_ arr: inout [Int]) {
  for _ in 0..<arr.count { // n
    for j in 1..<arr.count { // n
      if arr[j] < arr[j - 1] {
        arr.swapAt(j, j - 1)
      }
    }
  }
}

var inputArr = [10, 2, -8, 4]

bubbleSort(&inputArr)

print(inputArr) // [-8, 2, 4, 10]
```

## Insertion Sort
