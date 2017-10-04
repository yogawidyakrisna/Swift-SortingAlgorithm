# Swift Sorting Algorithm
### Insertion Sort
```swift
//insertion sort - rank items by comparing each key in the list.
func insertionSort() {
    var x, y, key : Int
    for (x = 0; x < numberList.count; x++) {
    
        //obtain a key to be evaluated
        key = numberList[x]
        
        //iterate backwards through the sorted portion
        for (y = x; y > -1; y--) {
            if (key < numberList[y]) {
            
            //remove item from original position
            numberList.removeAtIndex(y + 1)
            
            //insert the number at the key position
            numberList.insert(key, atIndex: y)
            }
        } //end for
    } //end for
} //end function
```

### Optimized Insertion Sort
```swift
func insertionSort(_ array: [Int]) -> [Int] {
    var a = array			 // 1
    for x in 1..<a.count {		 // 2
        var y = x
        while y > 0 && a[y] < a[y - 1] { // 3
            a.swapAt(y - 1, y)
            y -= 1
        }
    }
    return a
}
```

### Bubble sort
```swift
func bubbleSort() {
    var x, y, z, passes, key : Int
    //track collection iterations
    for x in 0..<numberList.count {
        passes = (numberList.count - 1) - x;
        //use shorthand "half-open" range operator
        for y in 0..<passes {
            key = numberList[y]
            //compare and rank values
            if (key > numberList[y + 1]) {
                z = numberList[y + 1]
                numberList[y + 1] = key
                numberList[y] = z
            }
        } //end for
    } //end for
} //end function
```
