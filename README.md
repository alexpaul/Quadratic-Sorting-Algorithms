# Quadratic Sorting Algorithms

Quadratic sorting algorithms. Bubble sort and Insertion sort. 


## Bubble Sort 

Rumtime: `O(n ^ 2)`   
Space complexity: `O(1)`  

In the illustration below we do the following: 

1. We use two for loops to sort an unsorted array. 
2. In the inner for loop we start from index 1 and traverse the array. 
3. We compare adjacent values of position at `j` and postion at `j - 1`, `j`'s value is less we perform a `swap`. 
4. The steps above continue until we have exhausted traversing the outer loop's elements. 

![bubble sort](https://user-images.githubusercontent.com/1819208/98544593-3b2ee300-2262-11eb-9fc9-b8f66608f4ff.jpg)

## Bubble Sort Implementation 

```swift 
func bubbleSort(_ arr: inout [Int]) {
  for i in 0..<arr.count {
    for j in 1..<arr.count {
      print(i, j) // 12 times
      if arr[j] < arr[j - 1] {
        arr.swapAt(j, j - 1)
      }
    }
  }
}

var unsortedArr = [10, 2, -8, 4]
bubbleSort(&unsortedArr)
print(unsortedArr) // [-8, 2, 4, 10]
```

## Bubble Sort Implementation (optimized) 

```swift 
func optimizedBubbleSort(_ arr: inout [Int]) {
  var swaps = false
  outerloop: for i in 0..<arr.count {
    for j in 1..<arr.count - i {
      print(i, j) // 6 times
      if arr[j] < arr[j - 1] {
        arr.swapAt(j, j - 1)
        swaps = true
      }
    }
    if !swaps {
      print("abort") // if the array is already sorted it will simply break out of the entire loop
      break outerloop
    }
  }
}

var outOfOrderArr = [10, 2, -8, 4]
optimizedBubbleSort(&outOfOrderArr)
print(outOfOrderArr) // [-8, 2, 4, 10]
```

## Insertion Sort

Rumtime: `O(n ^ 2)`   
Space complexity: `O(1)`    

```swift 
func insertionSort(_ arr: inout [Int]) {
  guard arr.count > 1 else { return }
  for current in 1..<arr.count {
    for j in (1...current).reversed() {
      print(current, j) // 5 times
      if arr[j] < arr[j - 1] {
        arr.swapAt(j, j - 1)
      } else {
        break // inner loop
      }
    }
  }
}

var unsortedArr = [10, 2, -8, 4]
insertionSort(&unsortedArr)
print(unsortedArr) // [-8, 2, 4, 10]
```
